<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
<details>
<summary>Table of Contents</summary>

- [Language Models](#language-models)
- [Applications](#applications)
- [Top GPT3 Prompt Engineering Reads](#top-gpt3-prompt-engineering-reads)
- [How GPT works](#how-gpt-works)
- [Don't call it generative](#dont-call-it-generative)
- [Specialized language models](#specialized-language-models)
- [GPT Products](#gpt-products)
- [GPT tooling](#gpt-tooling)
- [Ethical issues](#ethical-issues)
- [Flan-T5](#flan-t5)
- [Misc Text AI](#misc-text-ai)

</details>
<!-- END doctoc generated TOC please keep comment here to allow auto update -->

My best timeline of GPT efforts is listed here: https://lspace.swyx.io/p/open-source-ai

Big list of Text Models

## Datasets

see [[DATASETS]]

## Language Models

<img src="https://pbs.twimg.com/media/FkwdJnEXgAAoteg?format=png&name=small" height=300 />

- huggingface top list of GGUF local llama models https://huggingface.co/models?sort=downloads&search=gguf
- model benchmarks
	- https://www.mosaicml.com/llm-evaluation
	- [https://gpt4all.io/index.html](https://gpt4all.io/index.html "https://gpt4all.io/index.html")
	- stanford CRFM
	- [https://github.com/eugeneyan/open-llms/pulls?q=is%3Apr+is%3Aclosed](https://github.com/eugeneyan/open-llms/pulls?q=is%3Apr+is%3Aclosed "https://github.com/eugeneyan/open-llms/pulls?q=is%3Apr+is%3Aclosed")
- history from Knowledge Graphs -> ELMO (LSTMs) -> Transformers -> BERT -> T5
	- told via [MLST YouTube/Tim Scarfe](https://www.youtube.com/watch?v=N-7rdJK4xlE)
	- R/CNNs couldnt model long range, very lossy
- jonstokes.com/p/the-chat-stack-gpt-4-and-the-near BERT was the world’s first _Large Language Model_ (LLM). It featured around 345 million parameters, which is a measure of the size and complexity of a neural network. (Think of an equation that has 345 million terms. That’s a big equation!) 
	- OpenAI followed Google’s lead and produced BERT-like LLMs of their own in 2018 and 2019: 
	- first GPT-1 with 117 million parameters, and then
	- GPT-2 with 1.5 billion parameters. 
	- In 2020, OpenAI rocked the NLP world by releasing GPT-3 featuring a whopping _175 billion_ parameters, earning it the title of the largest LLM, indeed the largest neural network, ever built. 
	- March 2023 saw the release of GPT-4, which builds on GPT-3. At the time of this writing, OpenAI hasn’t revealed GPT-4’s parameter count, but it is rumored to be in the neighborhood of 1 trillion.
- GPT2 as a step towards AGI https://slatestarcodex.com/2019/02/19/gpt-2-as-step-toward-general-intelligence/
- GPT3 advanced a lot through 2020-2022 https://twitter.com/tszzl/status/1572350675014516738

Model Evolution/Family trees
- ![https://pbs.twimg.com/media/Fu9JeSxXwAA_72R?format=jpg&name=medium](https://pbs.twimg.com/media/Fu9JeSxXwAA_72R?format=jpg&name=medium) https://twitter.com/OpenMedFuture/status/1652620470355652611/photo/1
- https://github.com/stanford-crfm/ecosystem-graphs/ CFRM Ecosystem Graphs
- https://ai.v-gar.de/ml/transformer/timeline/ This is a collection of important papers in the area of Large Language Models and Transformer Models. It focuses on recent development, especially from mid-2022 onwards, and in no way claims to be exhaustive. It is actively updated.

### Direct GPT alternatives

- Eleuther's [GPT-J-6B](https://arankomatsuzaki.wordpress.com/2021/06/04/gpt-j/), GPT-NeoX
	- gptj trained for 200k
	- gpt neox trained for 350k
	- https://overcast.fm/+HaNNYx-_o/1:18:00
- Google 
	- PaLM 570B
	  - https://blog.google/technology/ai/introducing-pathways-next-generation-ai-architecture/
	  - FLAN-T5
		  - - Flan-T5 checkpoints are publicly available (without requesting access) 
		  - Flan-T5 11B outperforms OPT-IML on MMLU and Big-Bench Hard, despite being 10x more compute efficient
		  - https://huggingface.co/docs/transformers/model_doc/flan-t5
	  - LaMDA
		  - https://twitter.com/debarghya_das/status/1638356068870033408
		  - LaMDA [Feb 2022] is a 137B param model trained on 2.81T tokens on 1024 v3 TPUs for 57.7 days. At $3.22/hr (v4 price), that costs ~$4.5M.
		  - RLAIF - trains its own model to predict scores for candidates based on labeled data on attributes: —Sensibleness —Specificity —Interestingness —Safety
		  - Accuracy Uses both retrieval-augmented generation and Toolformer techniques. It maintains a toolset (Search, Calculator...) and performs a "Research" task of predicting a toolset and a query for a response. It loops over this response and research phase up to 4 times.
		  - We know: —Smaller than GPT-3 137B vs 175B params and older: early 2022 —Trained on way more tokes than most (2.8T vs 1.4T) —Does not rely on the model to memorize facts, uses tools like Search —Costs ~$1-4M to train
- Yandex YaLM 100B https://medium.com/yandex/yandex-publishes-yalm-100b-its-the-largest-gpt-like-neural-network-in-open-source-d1df53d0e9a6
  - It took us 65 days to train the model on a pool of 800 A100 graphics cards and 1.7 TB of online texts, books, and countless other sources.
- BLOOM 176B
	-  the [BLOOM large language model](https://huggingface.co/bigscience/bloom-7b1) was trained in France with the support of the French government. The cost was estimated as $2-5M, it took almost four months to train and boasts about its low carbon footprint because most of the power came from a nuclear reactor!
	- Fun fact: as of a few days ago you can now [run the openly licensed BLOOM on your own laptop](https://github.com/NouamaneTazi/bloomz.cpp), using Nouamane Tazi’s adaptive copy of the `llama.cpp` code that made that possible for LLaMA
	- Bloom 7B - 1 https://twitter.com/Nouamanetazi/status/1636077137089400832?s=20
	- On M1 Pro, you can achieve 16 tokens/sec for BLOOMZ-7B1
- Tsinghua GLM-130B
  - outperforms OpenAI's GPT-3 175B and Google's PALM 540B on critical benchmarks. AND it's open sourced, which means — you can run this model on your own machine, for free.
  - only trained on 400B tokens (compared to 1.2T tokens for Chinchilla's 70B parameters)
  - https://twitter.com/AndyChenML/status/1611529311390949376?s=20
- Meta
  - OPT-175B https://opt.alpa.ai/ (bad reviews)
  - OPT-IML (Instruction Meta-Learning): **instruction tuned** https://github.com/facebookresearch/metaseq/tree/main/projects/OPT-IML
    - a new language model from Meta AI with 175B parameters, fine-tuned on 2,000 language tasks — openly available soon under a noncommercial license for research use cases.
    - instruction-finetuned, leverages Chinchilla scaling laws, and has bells and whistles like 4-bit quantization and bidirectional attention. With 4-bit quantization, the model can run on 1 x 80 GB A100 or a consumer GPU rig.
    - https://twitter.com/MetaAI/status/1605991218953191424
    - underperforms Flan-T5 https://twitter.com/_jasonwei/status/1621333297891790848?s=20
- Databricks Dolly
	- 1.0 https://www.databricks.com/blog/2023/03/24/hello-dolly-democratizing-magic-chatgpt-open-models.html
		- A critical step in the creation of Dolly 1.0, or any instruction following LLMs, is to train the model on a dataset of instruction and response pairs. Dolly 1.0 was trained for $30 using a dataset that the Stanford Alpaca team had created using the OpenAI API. That dataset contained output from ChatGPT, and as the Stanford team pointed out, the terms of service seek to prevent anyone from creating a model that competes with OpenAI. So, unfortunately, the answer to this common question was, “probably not!” As far as we know, all the existing well-known instruction-following models ([Alpaca](https://crfm.stanford.edu/2023/03/13/alpaca.html), [Koala](https://bair.berkeley.edu/blog/2023/04/03/koala/), [GPT4All](https://github.com/nomic-ai/gpt4all), [Vicuna](https://vicuna.lmsys.org/)) suffer from this limitation, prohibiting commercial use.
	- 2.0 https://www.databricks.com/blog/2023/04/12/dolly-first-open-commercially-viable-instruction-tuned-llm
		- We knew from the OpenAI research [paper](https://arxiv.org/pdf/2203.02155.pdf) that the original InstructGPT model was trained on a dataset consisting of 13,000 demonstrations of instruction following behavior
		- Databricks has over 5,000 employees who are very interested in LLMs. So we thought we could crowdsource among them to create an even higher quality dataset than the 40 labelers had created for OpenAI.
		- We set up a contest, where the top 20 labelers would get a big award. We also outlined 7 very specific tasks:
			-   Open Q&A: For instance, “Why do people like comedy movies?” or “What is the capital of France?” In some cases, there’s not a correct answer, and in others, it requires drawing on knowledge of the world at large.
			-   Closed Q&A: These are questions that can be answered using only the information contained in a passage of reference text. For instance, given a paragraph from Wikipedia on the atom, one might ask, “What is the ratio between protons and neutrons in the nucleus?”
			-   Extract information from Wikipedia: Here an annotator would copy a paragraph from Wikipedia and extract entities or other factual information such as weights or measurements from the passage.
			-   Summarize information from Wikipedia: For this, annotators provided a passage from Wikipedia and were asked to distill it to a short summary.
			-   Brainstorming: This task asked for open-ended ideation and an associated list of possible options. For instance, “What are some fun activities I can do with my friends this weekend?”.
			-   Classification: For this task, annotators were asked to make judgments about class membership (e.g. are the items in a list animals, minerals or vegetables) or to judge the properties of a short passage of text, such as the sentiment of a movie review.
			-   Creative writing: This task would include things like writing a poem or a love letter.

### LLaMa and variants

Brief history: https://agi-sphere.com/llama-models/ https://news.ycombinator.com/item?id=35736872

- leaderboard https://huggingface.co/spaces/HuggingFaceH4/open_llm_leaderboard
- llama2: [Latent Space writeup](https://www.latent.space/p/llama2#details)
	- [ylecun announcement](https://twitter.com/ylecun/status/1681336284453781505)
	- [finetuning recipes](https://github.com/facebookresearch/llama-recipes)
	- ways to run
		- https://github.com/jmorganca/ollama
		- https://gpt4all.io/index.html
		- https://faraday.dev/
		- https://replicate.com/blog/run-llama-locally
	- list of openai compatibility layers https://llm-tracker.info/books/llms/page/openai-api-compatibility
	- 32k llama2 https://twitter.com/togethercompute/status/1685048832168714240
	- llama2 uncensored: https://huggingface.co/georgesung/llama2_7b_chat_uncensored
		- wizard-vicuna dataset
		- nous hermes -   Llama 2 13B model fine-tuned on over 300,000 instructions. This model stands out for its long responses, lower hallucination rate, and absence of OpenAI censorship mechanisms
		- Eric Hartford’s [Wizard Vicuna 13B uncensored](https://huggingface.co/ehartford/Wizard-Vicuna-13B-Uncensored)
		- [GPT4-x-alpaca uncensored model](https://huggingface.co/chavinlo/gpt4-x-alpaca) - 
	- llama2 finetune for code
		- https://www.numbersstation.ai/post/nsql-llama-2-7b
- https://github.com/facebookresearch/llama
	- [Paper](https://scontent-sjc3-1.xx.fbcdn.net/v/t39.8562-6/333078981_693988129081760_4712707815225756708_n.pdf?_nc_cat=108&ccb=1-7&_nc_sid=ad8a9d&_nc_ohc=vopDLpNfG6gAX84qs6h&_nc_ht=scontent-sjc3-1.xx&oh=00_AfDipCb80g49Ksfxrjxiy7mOOl8ZoBO5QScseom5FDM14Q&oe=641984E2)
	- https://github.com/ggerganov/llama.cpp/
	- run on cpus https://github.com/facebookresearch/llama/compare/main...markasoftware:llama-cpu:main (its slow)
	- run on macs https://github.com/remixer-dec/llama-mps
		- [https://chatonmac.com](https://chatonmac.com/) BYOK, lets you edit system prompt
	- `npx dalai llama` https://cocktailpeanut.github.io/dalai/#/
	- run on iphone [https://mlc.ai/mlc-llm/](https://t.co/sSmUeGJu6T)
		- MLC Chat: [https://llm.mlc.ai](https://llm.mlc.ai/)
		- LLM Farm: [https://llmfarm.site](https://llmfarm.site/)
		- Enchanted (not local, just a frontend): [https://github.com/AugustDev/enchanted](https://github.com/AugustDev/enchanted)
			- Enchanted is open source, [Ollama](https://github.com/jmorganca/ollama) compatible, elegant iOS/iPad mobile app for chatting with privately hosted models such as Llama 2, Mistral, Vicuna, Starling and more. It's essentially ChatGPT app UI that connects to your private Ollama models. You can download Enchanted from the App Store or build yourself from scratch.
		- they use iPhone GPU (Metal), not Apple Neural Engine https://news.ycombinator.com/item?id=38907919
	- fork with int8 quantization https://twitter.com/innokean/status/1632898043811975170?s=46&t=90xQ8sGy63D2OtiaoGJuww
	- run on raspberry pi and pixel 6 https://simonwillison.net/2023/Mar/11/llama/
	- outputs are not very good https://news.ycombinator.com/item?id=35258553
	- LLaMA distros you can run
		- https://huggingface.co/TheBloke/LLaMa-13B-GGML/blob/main/llama-13b.ggmlv3.q4_0.bin via https://github.com/smol-ai/menubar
		- https://faraday.dev/
		- https://gpt4all.io/
		- the dalai llama project
		- 
	- Llama.cpp: LLama.cpp, created by @ggerganov , is a port of Facebook's LLaMA model in C/C++. This is probably the goat of all local LLM frameworks and to my knowledge was the first project that allowed to run LLMs easily on a MacBook.🐐 It’s also worth mentioning that thanks to this project there is a new model format - GGUF - that is used in all previously mentioned frameworks, too. So this project enables the other frameworks. download : https://huggingface.co/TheBloke/Llama-2-7B-GGUF
	- PrivateGPT - Similar to GPT4All, PrivateGPT also comes with a nice UI to chat with LLMs. Its focus does not lie on trying out many different models, but rather on interacting with your own documents 100% privately. It provides a nice @Gradio frontend where you can easily upload your files and then query the documents.
	- Ollama allows you to run LLMs locally through your command line and is probably the easiest framework to get started with. Just use the installer or the command line to install it. Then you can type `ollama run modelname` and it starts an interactive session where you can send prompts. It supports all important models like llama2, mistral, vicunia, falcon, and many more. And trying out new models is as easy as running `ollama pull modelname`.

- https://www.reddit.com/r/LocalLLaMA/comments/11o6o3f/how_to_install_llama_8bit_and_4bit/
- llama alternatives https://thesequence.substack.com/p/the-llama-effect-how-an-accidental
	- Redpajama
		- https://www.together.xyz/blog/redpajama
		- https://venturebeat.com/ai/redpajama-replicates-llama-to-build-open-source-state-of-the-art-llms/
		- openllama the release of preview of the 7B OpenLLaMA model that has been trained with 200 billion tokens on the RedPajama dataset.
			- https://github.com/openlm-research/open_llama
			- finetune openllama https://twitter.com/akshat_b/status/1658123298654355457
			- https://huggingface.co/openlm-research/open_llama_13bh
				- cant be used for code https://news.ycombinator.com/item?id=36383332
	- [Researchers from  UC Berkeley, CMU, Stanford, and UC San Diego open sourced Vicuna](https://vicuna.lmsys.org/), a fine-tuned version of LLama that matches GPT-4 performance.
	-   [Berkeley AI Research Institute(BAIR) released Koala](https://bair.berkeley.edu/blog/2023/04/03/koala/), a version of LLama fine-tuned using internet dialogs.
	-   [Nebuly open sourced ChatLLama](https://github.com/nebuly-ai/nebullvm/tree/main/apps/accelerate/chatllama), a framework for creating conversational assistants using your own data.
	-   [FreedomGPT is an open source conversational agent](https://freedomgpt.com/) based on Alpaca which is based on LLama.
	-   [The Colossal-AI project from UC Berkeley released ColossalChat](https://medium.com/@yangyou_berkeley/colossalchat-an-open-source-solution-for-cloning-chatgpt-with-a-complete-rlhf-pipeline-5edf08fb538b), a ChatGPT type model with a complete RLHF pipeline based on LLama.
	- GPT4all 
		- a 7B param language model finetuned from a curated set of 400k GPT-Turbo-3.5 assistant-style generation. We release! 800k data samples! or anyone to build upon and a model you can run on your laptop! Real-time Sampling on M1 Mac [announcement tweet](https://twitter.com/andriy_mulyar/status/1640836003194630144) Inspired by learnings from Alpaca, we carefully curated ~800k prompt-response samples to produce 430k high-quality assistant-style prompt/generation training pairs including code, dialogue, and stories.
		- Llama.cpp trained on 800k outputs from ChatGPT-3.5-Turbo Over 10x increase in ChatGPT samples from Alpaca.cpp. Outputs seem much better. + runs on your macbook! [tweet](https://twitter.com/mathemagic1an/status/1640864659631755264)
- 65B outputs https://twitter.com/theshawwn/status/1632569215348531201?s=46&t=90xQ8sGy63D2OtiaoGJuww
- simple Llama finetuner https://github.com/lxe/simple-llm-finetuner https://news.ycombinator.com/item?id=35256769 Simple LLaMA Finetuner is a beginner-friendly interface designed to facilitate fine-tuning the LLaMA-7B language model using LoRA method via the PEFT library on commodity NVIDIA GPUs. With small dataset and sample lengths of 256, you can even run this on a regular Colab Tesla T4 instance. With this intuitive UI, you can easily manage your dataset, customize parameters, train, and evaluate the model's inference capabilities.
	- with LoRA https://replicate.com/blog/fine-tune-alpaca-with-lora
	- with LLaMA adapter https://twitter.com/rasbt/status/1641457696074334209?s=20 it's not finetuning the whole model end-to-end. Instead, the Adapter-approach adds a small number of 1.2M parameters on top of a pretrained, frozen 7B LLaMA model. Using the same 52K Instruction-following data, responses are comparable to Alpaca, but in contrast to Alpaca, which took 3 hours on 8 A100 to finetune, LLaMA adapters can be finetuned in 1h.
	- But in short, the difference is that this inserts adapter layers on top of the model. In contrast, LoRA decomposes the model weight matrices using low-rank decomposition. So, LoRA increases finetuning performance by reducing parameter numbers whereas Adapters increases efficiency by keeping the pretrained model frozen (and only tunes a small number of parameters added to the model).
- Alapaca
	- [alpaca.cpp](https://github.com/antimatter15/alpaca.cpp) Locally run an Instruction-Tuned Chat-Style LLM
	- https://simonwillison.net/2023/Mar/13/alpaca/
	- Alpaca 7B was trained for less than $600. It used OpenAI's model to expand a set of 175 human written instruction/output pairs and generate more than 52,000 instruction-following examples to train their model with. Alpaca is fine-tuned on LLaMA (from Meta), so the from-scratch cost isn't exactly $600, but the effective cost is magnitudes smaller when building on open-source models.
	-  [**Alpaca**](https://crfm.stanford.edu/2023/03/13/alpaca.html): A strong instruction following LLM using LLAMA 
	-  [**Alpaca-LoRa**](https://github.com/tloen/alpaca-lora): Code for reproducing Alpaca using low-rank adaptation.
- [**Open-Assistant**](https://github.com/LAION-AI/Open-Assistant): OA also has done instruction fine-tuning + RLHF on LLAMA and Pythia models.
- [**Colossal AI**](https://medium.com/@yangyou_berkeley/colossalchat-an-open-source-solution-for-cloning-chatgpt-with-a-complete-rlhf-pipeline-5edf08fb538b)**:** a ChatGPT-type model with a complete RLHF pipeline based on LLama.
- Vicuna https://vicuna.lmsys.org/
	- Get the weights: [https://github.com/lm-sys/FastChat/#vicuna-weights…](https://t.co/1OMBfXH0jz) Web UI demo: [https://chat.lmsys.org](https://t.co/Vzs3OFe5O1)
	- https://twitter.com/lmsysorg/status/1642968294998306816
	- Alpaca competitor also from stanford 
- _UC Berkeley trained [Koala](https://bair.berkeley.edu/blog/2023/04/03/koala/) using data from ShareGPT_

### Other  text models

- Cerebras GPT https://www.cerebras.net/blog/cerebras-gpt-a-family-of-open-compute-efficient-large-language-models/
	- runs on 4GB https://twitter.com/simonw/status/1641576453740597248?s=20
	- not as good https://www.lunasec.io/docs/blog/cerebras-gpt-vs-llama-ai-model-comparison/
		- Cerebras isn't as advanced as either LLaMA or ChatGPT (gpt-3.5-turbo). It's a much smaller model at 13B parameters and it's been intentionally "undertrained" relative to the other models. Cerebras is ~6% of the size of GPT-3 and ~25% of the size of LLaMA's full-size, 60B parameter model, and they intentionally limited how long the model was trained in order to reach a "training compute optimal" state.
- Dolly 6B LLM https://www.databricks.com/blog/2023/03/24/hello-dolly-democratizing-magic-chatgpt-open-models.html
	- https://github.com/databrickslabs/dolly
	- academic license only
	- dolly-v1-6b is a 6 billion parameter causal language model created by Databricks that is derived from EleutherAI’s GPT-J (released June 2021) and fine-tuned on a ~52K record instruction corpus (Stanford Alpaca) consisting of question/answer pairs generated using the techniques outlined in the Self-Instruct paper. Dolly was trained using deepspeed ZeRO 3 on the Databricks Machine Learning Platform in just 30 minutes using a single NDasrA100_v4 machine with 8x A100 40GB GPUs.
- Nomic AI GPT4All
	- https://twitter.com/AlphaSignalAI/status/1640873710717468674
- FlashAttention - 3-5x faster training ([tweet](https://twitter.com/tri_dao/status/1597580603658231815), [huggingface](https://github.com/HazyResearch/flash-attention/tree/main/training))
	- Flash attention results in insanely fast speeds for ingesting prompts on long sequences. - [salesforce codegen](https://twitter.com/amanrsanger/status/1677090522589188097)
- GPT-JT for classification
  - https://news.ycombinator.com/item?id=33796158
  - https://twitter.com/togethercompute/status/1597611474771668997
  - https://huggingface.co/spaces/togethercomputer/GPT-JT
- Falcon
	- https://huggingface.co/blog/falcon https://huggingface.co/spaces/HuggingFaceH4/falcon-chat
	- https://twitter.com/Francis_YAO_/status/1666833311279517696
- GPT 3.5 (https://beta.openai.com/docs/model-index-for-researchers)
  - code-davinci-002 is a base model, so good for pure code-completion tasks
  - text-davinci-002 is an InstructGPT model based on code-davinci-002
  - text-davinci-003 is an improvement on text-davinci-002
    - https://scale.com/blog/gpt-3-davinci-003-comparison
      - 003 is 30% better at classifying, can rhyme, output iambic pentameter, is more verbose (42 words per sentence vs 23).
    - https://twitter.com/amix3k/status/1597504050852859904
    - https://twitter.com/_brivael_/status/1597625080418533377
  - InstructGPT https://openai.com/blog/instruction-following/
  - ChatGPT: https://openai.com/blog/chatgpt/
    - We’ve trained a model called ChatGPT which interacts in a conversational way. The dialogue format makes it possible for ChatGPT to answer followup questions, admit its mistakes, challenge incorrect premises, and reject inappropriate requests.

![https://pbs.twimg.com/media/Fknc4rkX0AMY5RF?format=jpg&name=large](https://pbs.twimg.com/media/Fknc4rkX0AMY5RF?format=jpg&name=large)

- Uncensored models
	- Wizard-Vicuna-30b-Uncensored and WizardLM-Uncensored-Falcon-7b
	- origin story of all these models https://twitter.com/cto_junior/status/1677563373704060929?s=20
- research only models
	- Baize dataset https://github.com/project-baize/baize-chatbot - chatgpt self chat
- unreleased but notable
	- Bloomberg GPT https://www.niemanlab.org/2023/04/what-if-chatgpt-was-trained-on-decades-of-financial-news-and-data-bloomberggpt-aims-to-be-a-domain-specific-ai-for-business-news/





## GPT4

- gpt4 speculations and improvement directions https://mobile.twitter.com/mayfer/status/1607816595065409536
- https://twitter.com/RamaswmySridhar/status/1605603050403483652?s=20&t=0zl_ZGLHLxjgJ-FLk-m-Fg
  - Biggest model size for GPT-4 will be 1T parameters. Up 6x. Not 100T - The reason is simple: instruction fine tuning achieves same quality with 100x smaller models.
  - GPT-4 will use 10T tokens. Up 33x, and putting them on the Chinchilla scaling curve.
  - We expect 16384 tokens
  - Biggest pre-training modeling change? A loss function that looks like UL2
  - Put together, at least 800x more compute for the pre-trained model.
- https://www.lesswrong.com/posts/jtoPawEhLNXNxvgTT/bing-chat-is-blatantly-aggressively-misaligned?commentId=AAC8jKeDp6xqsZK2K
	- This is not ChatGPT. MS has explicitly stated it is more powerful than ChatGPT, but refused to say anything more straightforward like "it's a more trained GPT-3" etc. If it's not a ChatGPT, then what is it? It is more likely than not some sort of GPT-4 model. There are many concrete observations which point towards this: the timing is right as rumors about GPT-4 release have intensified as OA is running up to release and gossip switches to GPT-5 training beginning (eg [Morgan Stanley](https://twitter.com/davidtayar5/status/1625145377547595776) reports GPT-4 is done and GPT-5 has started), MS has said it's a better model named 'Prometheus' & [Nadella pointedly declined to confirm or deny whether it's GPT-4](https://www.theverge.com/23589994/microsoft-ceo-satya-nadella-bing-chatgpt-google-search-ai), scuttlebutt elsewhere is that it's a GPT-4 model of some sort, it does some things much better than ChatGPT,

### gpt4 api

- huggingface access https://twitter.com/yvrjsharma/status/1637402444522045440

### gpt4 capabilities

- "sparks of agi" microsoft paper
	- https://youtu.be/Mqg3aTGNxZ0
	- https://arxiv.org/pdf/2303.12712.pdf
	- coding 3d game https://twitter.com/ammaar/status/1637592014446551040
	- alleged metadata hidden https://twitter.com/DV2559106965076/status/1638769434763608064
	- summary https://twitter.com/leopoldasch/status/1638848860528472065?s=20
	- fails
		- gpt4 cannot plan ahead
		- writing jokes - cant plan punchline
		- "how many words are in the full response in this prompt"
- econ professor sees gpt3.5 to gpt4 rise from D to an A in econ https://betonit.substack.com/p/gpt-retakes-my-midterm-and-gets-an
- system prompt for gpt4 needs world building. - example https://twitter.com/kevinafischer/status/1637234946434809858/photo/1
- world model
	- https://twitter.com/d_feldman/status/1636955260680847361

## Applications

GPT3 applications:

- text to graphviz https://twitter.com/goodside/status/1561549768987496449?s=21&t=rliacnWOIjJMiS37s8qCCw
- suspending to python for math
  - https://twitter.com/sharifshameem/status/1414029295043764226?lang=en
  - https://twitter.com/amasad/status/1568824744367259648
  - and API's https://twitter.com/sergeykarayev/status/1569377881440276481
- Amelia paragraph sumarizer https://twitter.com/Wattenberger/status/1412480516268437512
- Karina Nguyen Synevyr https://twitter.com/karinanguyen_/status/1566884536054677506
- Lex.page
- https://github.com/louis030195/obsidian-ava obsidian integration
- https://humanloop.com/ Playground that brings variable interpolation to prompts and lets you turn them into API endpoints. Once you're deployed, it also lets you collect past generations along with user behavioral feedback for fine-tunes.
- https://www.everyprompt.com/ extends Playground in a similar way: Putting variables in prompts and giving you a single button to go from prompt to API. Has nice developer-oriented touches in the UI too — e.g. displaying invisible chars as ghosts.
- explaining code diffs https://app.whatthediff.ai/dashboard
- LangChain https://twitter.com/hwchase17/status/1588183981312180225
  - implements and lets you easily compose many published LLM prompting techniques. Implements self-asking, web search, REPL math, and several of my own prompts.
  - All relevant chains now have a "verbose" option to highlight text according to the model or component (SQL DB, search engine, python REPL, etc) that it's from.
- https://dust.tt/ gives a collapsible tree UI for representing k-shot example datasets, prompt templates, and prompt chaining with intermediate JS code. Replaces a lot of code around prompt APIs.
- playing chess??? https://twitter.com/Raza_Habib496/status/1591514638520311809
- chrome extension
  - https://github.com/giosilvi/GPT-Prompter https://www.reddit.com/r/GPT3/comments/wa2db1/new_chrome_extension_for_gpt3_for_fast_and_custom/
  - summarizer https://summate.it/?v2
  - [https://quillbot.com/summarize](https://quillbot.com/summarize)
- simulating people
  - https://jack-clark.net/2022/10/11/import-ai-305-gpt3-can-simulate-real-people-ai-discovers-better-matrix-multiplication-microsoft-worries-about-next-gen-deepfakes/
- Making stories with characters https://medium.com/@turc.raluca/introducing-rick-and-mortify-a14e56a8cb67
- making app from scratch to app store https://twitter.com/mortenjust/status/1639276571574894594

wiring up LLMs to python https://twitter.com/karpathy/status/1593081701454204930?s=20&t=2ra2Yfz0NFSbfJ_IGixNjA

### GPT4 applications

- https://twitter.com/mayfer/status/1638356816836059136?s=20 Turkish Carpet Salesman
- summary thread https://twitter.com/samuelwoods_/status/1642889718336479233?s=20


## Top GPT Prompt Engineering Reads

- **Overview**
  - https://www.gwern.net/GPT-3#prompts-as-programming
  - https://andymatuschak.org/prompts/
  - https://every.to/superorganizers/linus-lee-is-living-with-ai
  - https://platform.openai.com/docs/guides/gpt-best-practices
  - [Prompt Engineering guide from OpenAI at NeurIPS](https://twitter.com/SarahChieng/status/1741926266087870784) via Sarah Chieng
- **Beginner**
  - go through all the GPT3 examples https://beta.openai.com/examples
  - GPT Best practices https://platform.openai.com/docs/guides/gpt-best-practices
- **Intermediate**
  - and deploy GPT2 https://huggingface.co/gpt2
  - play with the smaller GPT3 models https://beta.openai.com/docs/models/gpt-3
  - technique: self-asking, two step prompts https://twitter.com/OfirPress/status/1577302998136819713
    - chain of thought prompting https://twitter.com/OfirPress/status/1577303423602790401
    - https://ai.googleblog.com/2022/05/language-models-perform-reasoning-via.html (emerges at around 100B params)
  - Prompt structure with extensive examples
    - review feedback extraction https://www.youtube.com/watch?v=3EjtHs_lXnk&t=1009s
  - Ask Me Anything prompting
    - https://twitter.com/_akhaliq/status/1577838951905247235
  - using gpt3 for text2image prompts https://twitter.com/fabianstelzer/status/1554229347506176001
- Advanced
  - write a blogpost with GPT3 https://www.youtube.com/watch?v=NC7990PmDfM
  - solving advent of code https://github.com/max-sixty/aoc-gpt/blob/main/openai.py
  - integrating Google Search with GPT3: https://twitter.com/OfirPress/status/1577302733383925762
  - teach AI how to fish - You are X, you can do Y: https://github.com/nat/natbot/blob/main/natbot.py
  - https://gist.github.com/Hellisotherpeople/45c619ee22aac6865ca4bb328eb58faf Prompt Alternating, Editing, Weighting, Blending, Fusion
  - play with gpt-neoX and gpt-j https://neox.labml.ai/playground
  - defense against prompt injection https://twitter.com/goodside/status/1578278974526222336
  - whatever the f this is https://twitter.com/goodside/status/1578614244290924545
  - https://github.com/dair-ai/Prompt-Engineering-Guide
    - Surveys / Overviews:
      - [Pre-train, Prompt, and Predict: A Systematic Survey of Prompting Methods in Natural Language Processing](https://arxiv.org/abs/2107.13586)
      - [A Taxonomy of Prompt Modifiers for Text-To-Image Generation](https://arxiv.org/abs/2204.13988)
      - [Emergent Abilities of Large Language Models](https://arxiv.org/abs/2206.07682)
  - Applications:
    - [Legal Prompt Engineering for Multilingual Legal Judgement Prediction](https://arxiv.org/abs/2212.02199)
    - [Investigating Prompt Engineering in Diffusion Models](https://arxiv.org/abs/2211.15462)
    - [Conversing with Copilot: Exploring Prompt Engineering for Solving CS1 Problems Using Natural Language](https://arxiv.org/abs/2210.15157)
    - [Piloting Copilot and Codex: Hot Temperature, Cold Prompts, or Black Magic?](https://arxiv.org/abs/2210.14699)
  - Approaches/Techniques:
    - [Ask Me Anything: A simple strategy for prompting language models](https://paperswithcode.com/paper/ask-me-anything-a-simple-strategy-for)
    - [Fantastically Ordered Prompts and Where to Find Them: Overcoming Few-Shot Prompt Order Sensitivity](https://arxiv.org/abs/2104.08786)
    - [AutoPrompt: Eliciting Knowledge from Language Models with Automatically Generated Prompts](https://arxiv.org/abs/2010.15980)
    - [Large Language Models Are Human-Level Prompt Engineers](https://sites.google.com/view/automatic-prompt-engineer?pli=1)
    - [Structured Prompting: Scaling In-Context Learning to 1,000 Examples](https://arxiv.org/abs/2212.06713)
    - [Reframing Instructional Prompts to GPTk's Language](https://arxiv.org/abs/2109.07830)
    - [Promptagator: Few-shot Dense Retrieval From 8 Examples](https://arxiv.org/abs/2209.11755)
    - [Prompt Programming for Large Language Models: Beyond the Few-Shot Paradigm](https://www.arxiv-vanity.com/papers/2102.07350/)
    - [PromptChainer: Chaining Large Language Model Prompts through Visual Programming](https://arxiv.org/abs/2203.06566)
    - [Contrastive Search Is What You Need For Neural Text Generation](https://huggingface.co/blog/introducing-csearch): (1) [Paper](https://arxiv.org/abs/2210.14140) and (2) [Official Implementation](https://github.com/yxuansu/Contrastive_Search_Is_What_You_Need).
- Academics
  - P3: Public pool of prompts https://huggingface.co/datasets/bigscience/P3
    - and Promptsource https://github.com/bigscience-workshop/promptsource
  - Real-world Annotated Few-shot Tasks (RAFT) dataset https://huggingface.co/datasets/ought/raft
  - Study chain of thought reasoning https://ai.googleblog.com/2022/05/language-models-perform-reasoning-via.html
    - and self-consistency (Sample a diverse set of reasoning paths on the _same_ model) to improve it https://arxiv.org/abs/2203.11171
    - and UL2 20B https://ai.googleblog.com/2022/10/ul2-20b-open-source-unified-language.html
	    - released as UL2 20B https://twitter.com/YiTayML/status/1631359468675166208
	    - see templates https://twitter.com/abacaj/status/1633494842352214016?s=46&t=90xQ8sGy63D2OtiaoGJuww
  - building GPT-JT: https://www.together.xyz/blog/releasing-v1-of-gpt-jt-powered-by-open-source-ai

## How GPT works

- original paper Improving Language Understanding by Generative Pre-Training Radford et al 2018 https://s3-us-west-2.amazonaws.com/openai-assets/research-covers/language-unsupervised/language_understanding_paper.pdf
- https://github.com/karpathy/minGPT
  - announcement https://twitter.com/karpathy/status/1295410274095095810
  - used in https://www.mosaicml.com/blog/gpt-3-quality-for-500k
  - check out nanoGPT too
- https://yaofu.notion.site/How-does-GPT-Obtain-its-Ability-Tracing-Emergent-Abilities-of-Language-Models-to-their-Sources-b9a57ac0fcf74f30a1ab9e3e36fa1dc1
  - There are three important abilities that the initial GPT-3 exhibit: Language generation, In-context learning, World knowledge
  - to pretrain the 175B parameters model on 300B tokens (60% [2016 - 2019 C4](https://stanford-cs324.github.io/winter2022/lectures/data/) https://www.tensorflow.org/datasets/catalog/c4 + 22% WebText2 + 16% Books + 3% Wikipedia).
  - **Language generation** comes from **training objective**
  - **World knowldge** comes from **300b token corpus** and **stored in 175b model**
  - The ability of complex reasoning with chain-of-thought is likely to be a magical side product of training on code
  - We have concluded:
    - The language generation ability + basic world knowledge + in-context learning are from pretraining (`davinci`)
    - The ability to store a large amount of knowledge is from the 175B scale.
    - The ability to follow instructions and generalizing to new tasks are from scaling instruction tuning (`davinci-instruct-beta`)
    - The ability to perform complex reasoning is likely to be from training on code (`code-davinci-002`)
    - The ability to generate neutral, objective, safe, and informative answers are from alignment with human. Specifically:
      - If supervised tuning, the resulting model is `text-davinci-002`
      - If RLHF, the resulting model is `text-davinci-003`
      - Either supervised or RLHF, the models cannot outperform code-davinci-002 on many tasks, which is called the alignment tax.
    - The dialog ability is also from RLHF (`ChatGPT`), specifically it tradeoffs in-context learning for:
      - Modeling dialog history
      - Increased informativeness
      - Rejecting questions outside the model’s knowledge scope
  - https://jaykmody.com/blog/gpt-from-scratch/
	  - https://github.com/jaymody/picoGPT
  - OpenAI trained their original GPTs to pay special attention to <|endoftext|> for separating documents. But <|endoftext|> was in fact a special token: [50256]. Encoders need to encode that text string specially, since otherwise there's itno way to generate [50256]. https://news.ycombinator.com/user?id=sillysaurusx

## Don't call it generative

- Reasoning: https://twitter.com/alexandr_wang/status/1588933553290870785
	- https://every.to/chain-of-thought/gpt-4-is-a-reasoning-engine
- Understanding: https://twitter.com/EMostaque/status/1585903983180537856
- stochastic parrot/autoregressive model counterpoints https://twitter.com/ESYudkowsky/status/1639661303785721859?s=20
- 

## Specialized language models

- Scientific language models like Meta's Galactica exist. Commentary https://news.ycombinator.com/item?id=33614608

## GPT Products

- directory
	- https://gpt3demo.com/
- Jasper
- CopyAI
- Great Question customer research https://www.ycombinator.com/companies/great-question/jobs/AokShrj-full-stack-rails-engineer
- Features of existing products
  - NotionAI
  - https://hashnode.com/neptune
- Email
  - Ellie email https://twitter.com/JamesIvings/status/1602855048148500480
  - Everyprompt mail
  - https://merlin.foyer.work/
- content generation
	- https://byword.ai/
- Summarizers
	- explainpaper
	- kagi universal summarizer https://labs.kagi.com/ai/sum?url=airbyte.io
	- https://github.com/josStorer/chatGPTBox Integrating ChatGPT into your browser deeply, everything you need is here
- SQL
	  - https://yale-lily.github.io/spider
	  - https://huggingface.co/NumbersStation/nsql-6B
		  - https://www.numbersstation.ai/post/nsql-llama-2-7b
	  - perplexity.ai/sql
	    - https://twitter.com/perplexity_ai/status/1605250295780773889
	- seekai
	- censusgpt 
		- https://twitter.com/0interestrates/status/1633992774394544128
	- https://vanna.ai/  helps you generate and run accurate SQL for your database using LLMs via Retrieval-Augmented Generation
		- https://twitter.com/llama_index/status/1750196064660127848?


- Newer
  - https://www.protocol.com/generative-ai-startup-landscape-map
  - https://metaphor.systems/
  - dust.tt
  - tools that make tools (toolbot.ai)
  - https://lex.page ([announcement](https://twitter.com/nbashaw/status/1581673516360876032))
  - CLI https://twitter.com/KevinAFischer/status/1601883697061380096?s=20
	  - https://github.com/npiv/chatblade
	  - https://github.com/simonw/llm
  - Zapier OpenAI integrations https://zapier.com/apps/openai/integrations
  - SlackGPT https://zapier.com/shared/query-gpt-3-via-a-slack-channel/a7551c53beda75b3bf65c315f027de04a4b323ef
  - got3discord moderator https://github.com/Kav-K/GPT3Discord
  - extract gpt chrome extension https://twitter.com/kasrak/status/1624515411973922816?s=20
  - https://techcrunch.com/2023/02/28/typeface-emerges-from-stealth-with-65m-to-bring-generative-ai-to-the-enterprise We provide a generative AI application that empowers businesses to develop personalized content,” Parasnis said. “CEOs, CMOs, heads of digital and VPs and directors of creative are all expressing a growing demand for combining generative AI platforms with hyper-affinitized AI content to enhance the future of content workflows.”
  - Embra macos desktop chatgptlike
	  - https://twitter.com/zachtratar/status/1623015294569713665?s=20&t=hw_somO_R_JxGp4zQpFz0Q
	  - competes with Dust XP1
- Writing
  - NovelAI https://novelai.net/
  - https://tavernai.net/
  - Verb (fiction) https://twitter.com/verbforwriters/status/1603051444134895616
	  - (now dead)
  - Orchard https://www.orchard.ink/doc/201a7f63-731e-4487-926a-fdf348f1b00c
    - https://twitter.com/alexjkwang/status/1603408050005557249?s=20
  - Deepmind Dramatron https://deepmind.github.io/dramatron/details.html for **co-writing** theatre scripts and screenplays. Starting from a log line, Dramatron interactively generates character descriptions, plot points, location descriptions and dialogue. These generations provide human authors with material for compilation, editing, and rewriting.
  - BearlyAI https://twitter.com/TrungTPhan/status/1597623720239329280f
- google sheets https://twitter.com/mehran__jalali/status/1608159307513618433

## GPT tooling

mostly from https://twitter.com/goodside/status/1588247865503010816

- [Humanloop.com](https://humanloop.com) Playground - variable interpolations + api endpoints, collect generations with feedback
- [Everyprompt.com](https://everyprompt.com) Playground - similar to above with ux improvements
- Introducing [http://Promptable.ai](https://t.co/xbYN1gYHs7) The Ultimate Workspace for Prompt Engineering
  - 1.  A Delightful Prompt Editor - Organize Prompts in Folders. - Stream completions. - Add variables. - Change Model Parameters (even custom models!)
  - 2.  Batch Testing! We built a table that you can run completions on to evaluate your prompts How? - Add multiple inputs that your prompt needs to handle - Click run and process them in batch. - Add annotation columns (MultiSelect, Markdown) to keep track of the status of Inputs
  - 3.  Version and Deploy. You're happy with your completions, You added some test cases. It's time to ship! Deploy your prompt and fetch the latest version from our API. Simple storage. No added latency between you and your LLM.
- [Langchain](https://github.com/hwchase17/langchain) python package - implements many techniques
- Lamdaprompt https://github.com/approximatelabs/lambdaprompt
  - used in pandas extension https://github.com/approximatelabs/sketch
- https://gpt-index.readthedocs.io/en/latest/ GPT Index is a project consisting of a set of data structures designed to make it easier to use large external knowledge bases with LLMs.
- [Dust.tt](http://dust.tt) - tree UI for k-shot datasets, prompt templates, prompt chaining
- [Spellbook](https://scale.com/spellbook) from ScaleAI - automatically write k-shots, eval metrics for prompt varaints, prompts to spreadsheet functions
- Linus/thesephist tools
  - tree of branches https://twitter.com/thesephist/status/1590545448066252800
  - scrubbing a text for length https://twitter.com/thesephist/status/1587929014848540673
  - Most knowledge work isn't a text-generation task, and your product shouldn't ship an implementation detail of LLMs as the end-user interface https://twitter.com/thesephist/status/1592924891208372224
- mozilla's readability-cli https://www.npmjs.com/package/readability-cli ([tip](https://twitter.com/scottleibrand/status/1599988038721212416?s=20&t=cmSnNOsSSvutmlWTZpzYCQ))

### dealing with GPT context size

- there is actually a paper by OpenAI themselves on summarizing long document. essentially, break a longer text into smaller chunks, and run a multi-stage sequential summarization. each chunk uses a trailing window of previous chunk as context, and run this recursively. [https://arxiv.org/abs/2109.10862](https://arxiv.org/abs/2109.10862). more: https://news.ycombinator.com/item?id=34423822
- https://github.com/jerryjliu/gpt_index
  - Current state: LLM’s have made phenomenal progress in encoding knowledge as well as reasoning. BUT a big limitation of LLM’s is context size (4096 in Davinci), and if you want to feed an LLM custom knowledge it will either need to fit in the prompt or be finetuned (expensive)!
  - https://twitter.com/mathemagic1an/status/1609225733934616577?s=46&t=DgrykKeTlGWgdxRkv2_tKw
- godly ai https://godly.ai
- HyDE: Hypothetical Document Embeddings
  - https://twitter.com/mathemagic1an/status/1615378778863157248
  - Take your query => create _hypothetical_ answer => embed hypothetical answer => use this to search through doc embeddings
- [Structured Prompting: Scaling In-Context Learning to 1,000 Examples](https://arxiv.org/abs/2212.06713)

## Ethical issues

- tokens are more 16x expensive for other languages https://denyslinkov.medium.com/why-is-gpt-3-15-77x-more-expensive-for-certain-languages-2b19a4adc4bc
- Galactica fallout
  - https://twitter.com/Michael_J_Black/status/1593133722316189696
  - https://news.ycombinator.com/item?id=33611265
  - https://www.youtube.com/watch?v=ZTs_mXwMCs8&t=19s

## Flan-T5

- https://twitter.com/quocleix/status/1583523186376785921
- Flan-T5 is instruction-finetuned on 1,800+ language tasks, leading to dramatically improved prompting and multi-step reasoning abilities.
  - 7 min summary video https://www.youtube.com/watch?v=oqi0QrbdgdI

## Misc Text AI

- OpenAI NarrativeQA Summarizing books https://openai.com/blog/summarizing-books/
- GPT2 chess story with shawn presser and gwern https://slatestarcodex.com/2020/01/06/a-very-unlikely-chess-game/

## Karpathy analogies

- https://twitter.com/karpathy/status/1644183721405464576
- The analogy between GPTs of today to the CPUs of early days of computing are interesting. GPT is a funny kind of programmable text computer. Have to think through it more !
- Memory 
	- GPT-4 RAM is ~log2(50K vocab size)*(32K context length)/(8 bits/byte) ~= 64kB, roughly a Commodore64. Just as then, optimizing this precious resource is critical. GPT registers are the residual stream. There are d_model of them, e.g. GPT-3 has ~12K registers. VLIW architecture vibes. 
- CPU 
	- The LOAD instruction is the Attention mechanism, except it can address by both location and/or content. 
	- The STORE instruction is forced every n_layer number of clock cycles. 
	- The ALU are the MLPs + LayerNorms.
	- Awkwardly, as their params are not shared across layers, the ALU changes at each clock cycle. 
	- Optionally the MLPs may also be interpreted as supporting a kind of fixed knowledge database lookup. The programs always takes the form [[LOAD, ALU]*N, STORE]*M, where N is n_layer and M is num_tokens. 
- Architecture GPT feels closer to a fixed-function than stored-program computer because the number of parameters is so large. In contrast, the description length of a CPU is very low and all the action is in the memory configuration. Another way to look at it is that GPT is a much more bloated/complex computer. Which is fine because it is not engineered but optimized and the upshot is that the programs can be shorter.
- related: div garg version of software 3.0 https://divgarg.substack.com/p/software-3