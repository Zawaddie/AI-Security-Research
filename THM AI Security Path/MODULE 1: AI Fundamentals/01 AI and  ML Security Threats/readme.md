# AI/ML Security Threats

---

## Introduction

---

## The Building Blocks of AI

---

## LLMs

Okay, so we've taken a walk through history in this room. From our goal to have computers behave like humans, the AI field was born, a field that would come closer to achieving that goal with the introduction of ML. In more recent years, the further development of these fields has allowed us to unlock even more potential with neural networks and DL, both of which play a crucial role in enabling our next industry-changing technology: LLMs. 

Chatbox Exploding onto the Scene

Now, I'm no ML algorithm, but if I had to assign a prediction score to the chance of this room's user base having heard of ChatGPT, it would be very high. ChatGPT emerged smack back in the middle of "The AI Boom"; its ability to generate human-like text in response to a user query blew the minds of near everyone with the technology triggering discussions in the news, politics, education, industry, the list goes on. Something had changed. We were entering a new era and everyone knew it, which brings us up to date. Now, let's look at how the technologies we've covered so far enabled LLMs like ChatGPT, LLama and Deepseek to exist, kicking off a technological revolution.  

What are LLMs, and how do they work?
Large Language Models (or LLMs) are deep learning-based AI models that can process and generate text by predicting the next word in a sequence. For example, consider this quote:

Sentance with blank last word

This quote is missing the final word. This quote would be fed into the LLM, and it would be tasked with predicting what the final word is likely to be. When you query a chatbot, this is what is happening in the background. Predictions are being run quickly on what word would likely be next in the response of an AI chat to this query, but how? 

LLMs are first trained in a "pre-training" phase, where they process vast amounts of text, GPT-3 alone was trained on data that would take a human 2,600 years to read nonstop. More advanced models, like GPT-4, require even greater datasets, made possible by DL. Instead of relying on labelled data, LLMs use billions of parameters that function like puzzle pieces, enabling them to understand and generate human-like language when assessed together. These parameters are fine-tuned automatically as the model processes text, adjusting based on prediction accuracy to improve response quality. They begin by generating a word at random to finish the text:

Sentence with random word being guessed for last word 

The guess is then compared with what the correct final word actually was, and the parameters are fine-tuned to make it more likely to predict what, in fact, was the right word until the model can accurately predict the correct word to end the sentence (and less likely to choose the incorrect words) using an algorithm called backpropagation:

LLM being fed sentance and making predications on what last word will be

Now imagine this process happening trillions of times, repeating this process over and over again until it can not only predict the end of the training data but also raw unseen data. The sheer scope of what is being discussed here is only possible due to advancements in hardware, like GPUs (Graphics Processing Units), enabling masses of parallel operations and processing of large datasets as well as advancements in neural networks, specifically a type of neural network called transformer neural networks.

GPU enabling multi-threaded processes

Introduced in Google's 2017 paper Attention is All You Need, transformer neural networks revolutionized LLMs by enabling parallel text processing instead of sequential word-by-word analysis. This breakthrough allowed models to assign "attention" to key words, improving contextual understanding. By encoding words into numerical values and calculating attention scores, transformers enhance accuracy, helping models correctly interpret ambiguous references, like distinguishing whether "it" in this sentence refers to "the bank" or "the loan.":

"The bank approved the loan because it was financially stable." 



After the pre-training, humans come back into play, performing a step called RLHF (Reinforcement Learning from Human Feedback). This is when predictions are reviewed, and any that would be considered unhelpful by a user or have issues are flagged and the parameters are adjusted accordingly. Once trained and reinforced, the LLM can be used, whether as a translator, chatbot, etc. A query is fed to it, and using its trained model, it predicts what the next word would be as a response, and so on and so on until the user has a complete response.

Reviewing of Predictions

LLMs power generative AI products like ChatGPT and LLaMA, which create original text-based content in response to user prompts. Generative AI as a whole extends beyond text, enabling the creation of images, music, and more. The recent AI boom is the result of years of research and innovation, not an overnight development. We’ve now explored key concepts that trace AI’s evolution—let’s quickly recap how they all connect.

AI/ML term breakdown

Artificial Intelligence (AI) is the overarching field, encompassing all systems that mimic human intelligence. Machine learning (ML) is a subfield of AI that enables systems to learn patterns from data without explicit programming. Deep learning (DL) is then a specialised branch of ML, which uses neural networks to process vast amounts of data in complex ways without the need for human interaction, making it effectively scalable ML. Large Language Models (LLMs) , like GPT, are advanced DL models built on neural networks, specifically transformers, designed to understand and generate human-like text. As was said, knowledge is power, and with these last few tasks, you have started your journey in the pursuit of that knowledge and now have a better understanding of the technologies that give AI its powers. Now let's take a look at how all of the discussed is affecting our industry, shall we?

This task has covered the basics of LLMs; however, if you want to take a deeper look into them, check out our Demystifying LLMs room.
