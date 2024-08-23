swyx's to-read list (incl a lot of history)
- https://aman.ai/primers/ai/transformers/
- https://magazine.sebastianraschka.com/p/understanding-large-language-models


ELI5: https://news.ycombinator.com/item?id=35977891
2017 paper
- https://ai.googleblog.com/2017/08/transformer-novel-neural-network.html?m=1
- nice podcast with Ashish and Jakob https://soundcloud.com/nlp-highlights/36-attention-is-all-you-need-with-ashish-vaswani-and-jakob-uszkoreit
- 30min Yannick Kilcher video review https://www.youtube.com/watch?v=iDulhoQ2pro, 10min [shorter version](https://www.youtube.com/watch?v=SZorAJ4I-sA)
- 2018 - Noam Shazeer on why you should train >1B models https://youtu.be/9P_VAMyb-7k and https://youtu.be/P8FJVfg3Z44
- FT coverage of the paper authors and when and how they left https://archive.is/2023.07.23-044102/https://www.ft.com/content/37bb01af-ee46-4483-982f-ef3921436a50
- backstory on the title https://news.ycombinator.com/item?id=38758413
- aidan gomez [says](https://x.com/aidangomez/status/1773863558482202986?s=46&t=90xQ8sGy63D2OtiaoGJuww) the image was made with adobe illustrator
The Illustrated Transformer - [https://jalammar.github.io/illustrated-transformer/](https://jalammar.github.io/illustrated-transformer/)
- GPT in 60LOC https://jaykmody.com/blog/gpt-from-scratch/
	- pre read https://jaykmody.com/blog/attention-intuition/
	- starts simple, ramps up. Fills in all the gaps between Attention is All You Need right up to coding every single line of a working GPT2 implementation yourself. Even ends with explanations of finetuning for classification, summarization, instruction tuning, and PEFT. 
- explore miniGPT and nanoGPT via Karpathy
	- [makemore and neural networks zero to hero](https://www.youtube.com/watch?v=VMj-3S1tku0&list=PLAqhIrjkxbuWI23v9cThsA9GvCAUhRvKZ)
	- [tweetstorm](https://twitter.com/karpathy/status/1468370605229547522?s=20) on convergence, tweetstorm on [expressive, optimizable, efficient/parallelizable](https://twitter.com/karpathy/status/1593417989830848512?s=20) - elaborated in [1hr stanford lecture](j) and [8min lex fridman summary](https://www.youtube.com/watch?v=9uw3F6rndnA)
	- [Transformers form Scratch](https://blog.matdmiller.com/posts/2023-06-10_transformers/notebook.html) - Karpathy's nanoGPT worked thru a notebook
- poke around LLM visualization https://bbycroft.net/llm
- explore https://osanseviero.github.io/hackerllama/blog/posts/random_transformer/
- then read https://kipp.ly/transformer-inference-arithmetic/
- then read https://finbarr.ca/how-is-llama-cpp-possible/ ([andrej commentary](https://twitter.com/karpathy/status/1691571869051445433))
- then read 5 years of gpt progress:
	- https://finbarr.ca/five-years-of-gpt-progress/


![https://vinija.ai/models/assets/transformers/2.png](https://vinija.ai/models/assets/transformers/2.png)

-  LSTM is dead. Long Live Transformers! ([talk](https://www.youtube.com/watch?v=S27pHKBEp30))
	-  the evolution of natural language processing (NLP) techniques, starting with the limitations of bag-of-words models and vanilla recurrent neural networks (RNNs), which suffer from vanishing and exploding gradients. 
	- The introduction of long short-term memory (LSTM) resolved these issues but was still challenging to train and lacked transfer learning abilities, leading to the development of the transformer model. 
	- The transformer model uses **self-attention** and **a feedforward neural network** to read input sequences and create output sequences, incorporating **multi-headed attention** to generate multiple attention outputs with different sets of parameters. 
	- Key innovations of the transformer model include **positional encoding** and the use of **ReLU activation** functions. 
	- The speaker highlights the advantages of using transformers and models like Roberta for training models on large-scale unsupervised text data, enabling transfer learning and reduced training time and resources.
	- Despite being replaced in most areas by transformers, LSTM still has applications in real-time control. 
	- The speaker also compares word CNN to transformers and observes that transformers can offer contextual answers more efficiently across the entire document.
	- https://youtu.be/-uyXE7dY5H0?si=Lbgi7nPw4ROpu53L from rnns to lstms
- Little Book of Deep Learning ([pdf](https://fleuret.org/public/lbdl.pdf))
	- The notion of layer
	- Linear layer
	- Activation functions
	- Pooling
	- Dropout
	- Normalizing layers
	- Skip connections
	- Attention layers
	- Token embedding
	- Positional encoding
	- Architectures
	- Multi-Layer Perceptrons
	- Convolutional networks
	- Attention models
- Reminder that my deep learning course [@unige_en](https://twitter.com/unige_en)is entirely available on-line. 1000+ slides, ~20h of screen-casts. [https://fleuret.org/dlc/](https://t.co/6OVyjPdwrC)
- https://e2eml.school/transformers.html Transformers from Scratch

https://www.jvoderho.com/blog.html?blogid=Transformer%20as%20a%20general%20purpose%20computer

https://news.ycombinator.com/item?id=35712334
The Illustrated Transformer is fantastic, but I would suggest that those going into it really should read the previous articles in the series to get a foundation to understand it more, plus later articles that go into GPT and BERT, here's the list:

A Visual and Interactive Guide to the Basics of Neural Networks - [https://jalammar.github.io/visual-interactive-guide-basics-n...](https://jalammar.github.io/visual-interactive-guide-basics-neural-networks/)

A Visual And Interactive Look at Basic Neural Network Math - [https://jalammar.github.io/feedforward-neural-networks-visua...](https://jalammar.github.io/feedforward-neural-networks-visual-interactive/)

Visualizing A Neural Machine Translation Model (Mechanics of Seq2seq Models With Attention) - [https://jalammar.github.io/visualizing-neural-machine-transl...](https://jalammar.github.io/visualizing-neural-machine-translation-mechanics-of-seq2seq-models-with-attention/)
[I made a transformer by hand (no training)](https://vgel.me/posts/handmade-transformer/) 
"Thinking Like Transformers" [1]. They introduce a primitive programming language, RASP, which is composed of operations capable of being modeled with transformer components, and demonstrate how different programs can be written with it, e.g. histograms, sorting. Sasha Rush and Gail Weiss have an excellent blog post on it as well [2]. Follow on work actually demonstrated how RASP-like programs could actually be compiled into model weights without training [3].

[1] [https://arxiv.org/abs/2106.06981](https://arxiv.org/abs/2106.06981)

[2] [https://srush.github.io/raspy/](https://srush.github.io/raspy/)

[3] [https://arxiv.org/abs/2301.05062](https://arxiv.org/abs/2301.05062)


[3blue 1 brown visualizing attention](https://www.3blue1brown.com/lessons/attention) https://news.ycombinator.com/item?id=40035514
- https://www.youtube.com/watch?v=wjZofJX0v4M


The Illustrated BERT, ELMo, and co. (How NLP Cracked Transfer Learning) - [https://jalammar.github.io/illustrated-bert/](https://jalammar.github.io/illustrated-bert/)

The Illustrated GPT-2 (Visualizing Transformer Language Models) - [https://jalammar.github.io/illustrated-gpt2/](https://jalammar.github.io/illustrated-gpt2/)

How GPT3 Works - Visualizations and Animations - [https://jalammar.github.io/how-gpt3-works-visualizations-ani...](https://jalammar.github.io/how-gpt3-works-visualizations-animations/)

The Illustrated Retrieval Transformer - [https://jalammar.github.io/illustrated-retrieval-transformer...](https://jalammar.github.io/illustrated-retrieval-transformer/)

The Illustrated Stable Diffusion - [https://jalammar.github.io/illustrated-stable-diffusion/](https://jalammar.github.io/illustrated-stable-diffusion/)

The math behind Attention Mechanisms - math behind the Keys, Queries, and Values matrices, in a friendly pictorial way using diagrams and linear transformations
https://www.youtube.com/watch?v=UPtG_38Oq8o


If you want to learn how to code them, this book is great: [https://d2l.ai/chapter_attention-mechanisms-and-transformers...](https://d2l.ai/chapter_attention-mechanisms-and-transformers/index.html)

Transformer Taxonomy (the last lit review)
https://kipp.ly/blog/transformer-taxonomy/
- It covers 22 models, 11 architectural changes, 7 post-pre-training techniques and 3 training techniques (and 5 things that are none of the above).

attention visualization https://catherinesyeh.github.io/attn-docs/

### Explainers

-   [**The illustrated transformer**](https://jalammar.github.io/illustrated-transformer/): A more technical overview of the transformer architecture by Jay Alammar.
-   **[The annotated transformer](http://nlp.seas.harvard.edu/annotated-transformer/)**: In-depth post if you want to understand transformers at a source code level. Requires some knowledge of PyTorch.
-   [**Let’s build GPT: from scratch, in code, spelled out**](https://www.youtube.com/watch?v=kCc8FmEb1nY): For the engineers out there, Karpathy does a video walkthrough of how to build a GPT model.
-   **[The illustrated Stable Diffusion](https://jalammar.github.io/illustrated-stable-diffusion/)****:** Introduction to latent diffusion models, the most common type of generative AI model for images.
-   **[RLHF: Reinforcement Learning from Human Feedback](https://huyenchip.com/2023/05/02/rlhf.html)**: Chip Huyen explains RLHF, which can make LLMs behave in more predictable and human-friendly ways. This is one of the most important but least well-understood aspects of systems like ChatGPT.
-   [**Reinforcement learning from human feedback**](https://www.youtube.com/watch?v=hhiLw5Q_UFg): Computer scientist and OpenAI cofounder John Shulman goes deeper in this great talk on the current state, progress and limitations of LLMs with RLHF.
- _Linearized Transformers are Secretly Fast Weight Programmers_, [How Transformers Work](https://ig.ft.com/generative-ai/), https://news.ycombinator.com/item?id=37774676

### Courses

-   [**Stanford CS25**](https://www.youtube.com/watch?v=P127jhj-8-Y): Transformers United, an online seminar on Transformers.
-   **[Stanford CS324](https://stanford-cs324.github.io/winter2022/)**: Large Language Models with Percy Liang, Tatsu Hashimoto, and Chris Re, covering a wide range of technical and non-technical aspects of LLMs.

### Reference and commentary

-   **[Predictive learning, NIPS 2016](https://www.youtube.com/watch?v=Ount2Y4qxQo&t=1072s)**: In this early talk, Yann LeCun makes a strong case for unsupervised learning as a critical element of AI model architectures at scale. Skip to [19:20](https://youtu.be/Ount2Y4qxQo?t=1160) for the famous cake analogy, which is still one of the best mental models for modern AI.
-   [**AI for full-self driving at Tesla**](https://www.youtube.com/watch?v=hx7BXih7zx8): Another classic Karpathy talk, this time covering the Tesla data collection engine. Starting at [8:35](https://youtu.be/hx7BXih7zx8?t=515) is one of the great all-time AI rants, explaining why long-tailed problems (in this case stop sign detection) are so hard.
-   **[The scaling hypothesis](https://gwern.net/scaling-hypothesis)**: One of the most surprising aspects of LLMs is that scaling — adding more data and compute — just keeps increasing accuracy. GPT-3 was the first model to demonstrate this clearly, and Gwern’s post does a great job explaining the intuition behind it.
-   [**Chinchilla’s wild implications**](https://www.lesswrong.com/posts/6Fpvch8RR29qLEWNH/chinchilla-s-wild-implications): Nominally an explainer of the important Chinchilla paper (see below), this post gets to the heart of the big question in LLM scaling: are we running out of data? This builds on the post above and gives a refreshed view on scaling laws.
-   **[A survey of large language models](https://arxiv.org/pdf/2303.18223v4.pdf)**: Comprehensive breakdown of current LLMs, including development timeline, size, training strategies, training data, hardware, and more.
-   [**Sparks of artificial general intelligence: Early experiments with GPT-4**](https://arxiv.org/abs/2303.12712): Early analysis from Microsoft Research on the capabilities of GPT-4, the current most advanced LLM, relative to human intelligence.
-   [**The AI revolution: How Auto-GPT unleashes a new era of automation and creativity**](https://pub.towardsai.net/the-ai-revolution-how-auto-gpt-unleashes-a-new-era-of-automation-and-creativity-2008aa2ca6ae): An introduction to Auto-GPT and AI agents in general. This technology is very early but important to understand — it uses internet access and self-generated sub-tasks in order to solve specific, complex problems or goals.
-   **[The Waluigi Effect](https://www.lesswrong.com/posts/D7PumeYTDPfBTp3i7/the-waluigi-effect-mega-post)**: Nominally an explanation of the “Waluigi effect” (i.e., why “alter egos” emerge in LLM behavior), but interesting mostly for its deep dive on the theory of LLM prompting.
- QKV https://x.com/karpathy/status/1794021159895507173



## flash attention

https://twitter.com/amanrsanger/status/1657835933503479808?s=46&t=90xQ8sGy63D2OtiaoGJuww

## hyena

- https://hazyresearch.stanford.edu/blog/2023-03-07-hyena


## transformer interpretability

openai had a  gpt labeling gpt paper

https://twitter.com/generatorman_ai/status/1664410300110766082?s=20
- Induction heads, modular addition, indirect object circuit, OthelloGPT.
- see also: ChessGPT: https://adamkarvonen.github.io/machine_learning/2024/01/03/chess-world-models.html
https://github.com/JShollaj/awesome-llm-interpretability


## transformer family tree

Applications of Transformers New survey paper highlighting major applications of Transformers for deep learning tasks. Includes a comprehensive list of Transformer models. [https://arxiv.org/abs/2306.07303](https://t.co/z0y6R4CUh6)

Efficient Methods for Natural Language Processing: A Survey It lists effective techniques that use fewer resources while producing comparable outcomes to resource-intensive NLP systems.
![https://pbs.twimg.com/media/FhnMjm7WYAA8e18?format=jpg&name=medium]
abs: [https://arxiv.org/abs/2209.00099](https://t.co/99Gp0rPZHi)


## linear transformers

- see https://manifestai.com/blogposts/faster-after-all/