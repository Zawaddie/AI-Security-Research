# AI Models & Data

---

## Introduction

Every AI model is, at its core, a product of its training data. Before a single prediction is made or a single prompt is answered, decisions about what data to collect, where to collect it from, and how to process it have already shaped everything the model will ever do. 

Those decisions carry security implications that most organisations deploying AI today have never examined. From PII scraped from the open web to credentials baked into model weights to safety mechanisms quietly eroded during fine-tuning, the risks don't begin when a model is deployed. They begin long before, in a data supply chain that is often invisible, poorly documented, and almost entirely unaudited.


---

## Training Data

Training a large language model requires a staggering amount of text. GPT-3 was trained on roughly 570GB of filtered text, and that's considered relatively modest by "modern" standards. To hit numbers like that, developers can't carefully hand-pick sources.

The pipeline typically draws from four buckets:

<img width="1265" height="414" alt="image" src="https://github.com/user-attachments/assets/f3360c74-2e22-4b35-88b2-e22fdde1af64" />


The most widely used training dataset is Common [Crawl](https://commoncrawl.org/), a free, publicly available archive of web crawl data that has underpinned essentially every major model family. 

DeepSeek-V2 was pretrained on it; DeepSeek-V3 trained on 14.8 trillion tokens with Common Crawl as a core source; and LLaMA 4 was scaled to 40 trillion tokens across 200 languages using a similar pipeline. 

GPT-3 is one of the few models whose breakdown is publicly documented: 60% of its tokens came from a filtered version of Common Crawl, and more recent models lean even more heavily on it. The keyword is "filtered", and how that filtering was done, by whom, and what slipped through is where the security story begins.

### The Problem of Provenance

**Data provenance** is the ability to answer three questions about any piece of training data:

1. Where did it come from?
2. When was it collected?
3. Has it been modified since?

In most AI supply chains today, the honest answer to all three is we don't fully know. Most major models are essentially trained on datasets of datasets, huge composites assembled from hundreds of upstream sources, where the original attribution has been lost, simplified, or never recorded in the first place. 

The [Data Provenance Initiative](https://www.dataprovenance.org/) audited over 1,800 datasets and found that more than 70% of licenses on popular hosting platforms were listed as "Unspecified", and of those that were labelled, 66% were miscategorised, usually listed as more permissive than they actually were. Organisations fine-tuning on these datasets often don't know what they legally have, let alone what's actually inside it.

The software security world has been here before. SolarWinds taught the industry that you can't trust a compiled binary if you don't know what went into it, which is exactly why software bills of materials (SBOMs) became standard practice. The AI equivalent is the **ML-BOM:** a documented inventory of dataset sources, licenses, PII categories, and filtering decisions. Adoption is still early, and most organisations deploying third-party models today have nothing close to one.

### PII in the Pipeline

One of the most direct consequences of undocumented, large-scale web scraping is that personally identifiable information ends up baked into model weights. Once it's there, it's very difficult to remove. 

Medical records, personal email threads, forum posts about health conditions or political views: all of it gets swept up if it was publicly accessible at crawl time. 

The EU's GDPR explicitly requires data minimisation (collect only what's necessary). This sits in direct tension with the "more data is always better" logic driving pre-training.


The security implication is measurable and concrete. [Truffle Security](https://trufflesecurity.com/blog/research-finds-12-000-live-api-keys-and-passwords-in-deepseek-s-training-data) scanned the December 2024 Common Crawl archive (400TB of data from 2.67 billion web pages) and found nearly 12,000 live, verified API keys and passwords. With the right prompt, a model trained on that data can sometimes be coaxed into surfacing training content near-verbatim, including credentials. This isn't a bug introduced by an attacker. It's a consequence of what went in during training, and no patch fixes it once the model is deployed.

### A Model Engineer

A model's behaviour is a direct product of what it was trained on. If that data was scraped without audit, contaminated with PII, or manipulated upstream, those characteristics become part of the model, and there's no reliable way for the organisation deploying it to know. The data supply chain is as real and as exploitable as a software supply chain. For organisations right now, it's almost entirely invisible.

---












## Conclusion

- Understood where AI training data comes from and the security risks introduced by poor data provenance
- Recognised how PII and sensitive credentials can become permanently embedded in model weights through large-scale web scraping
- Understood how key model-building decisions (overfitting, quantisation, and federated learning) each introduce distinct security risks
- Understood the inheritance problem and what organisations unknowingly take on when fine-tuning pre-trained models
- Recognised why trained models are opaque black boxes, and what model cards do (and fail to do) to address this.
