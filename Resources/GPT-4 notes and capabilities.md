## Key links from openai

- gdb's [developer demo livestream](https://www.youtube.com/watch?v=outcGtbnMuQ)
	- "past two years focused on shipping gpt4"
	- [From OpenAI, hand sketch into website](https://twitter.com/rowancheung/status/1635744529587359756?s=20) [time stamped](https://www.youtube.com/live/outcGtbnMuQ?feature=share&t=993)
	- read existing content
	- build with system as a partner
	- [18:56](https://www.youtube.com/live/outcGtbnMuQ?feature=share&t=1138) "one last thing"  - tax gpt 
		- "You are TaxGPT, a large language model trained by OpenAI. Carefully read & apply the tax code, being certain to spell out your calculations & reasoning so anyone can verify them. Spell out everything in painstaking detail & don't skip any steps!"
		- "now calculate their total liability"
- paper
	- there was a base model, and a launch model with RLHF improvement

## Access

- ChatGPT 
- API access
	- can see the image api already https://www.youtube.com/live/outcGtbnMuQ?feature=share&t=621
- Eval

## Capabilities

- Academic and Professional (eg Law Bar) exam
	- [paper chart screenshot](https://twitter.com/heykahn/status/1635701861423673344?s=20). [ethan mollick screenshot](https://twitter.com/emollick/status/1635700173946105856)
	- Fails of [english composition](https://twitter.com/emollick/status/1635782694045990912?s=20) and leetcode
		- leetcode still [impressive results](https://twitter.com/rUv/status/1635756651717496832?s=20)
- LLM benchmarks
	- [destroys MMLU, HellaSwag etc](https://twitter.com/swyx/status/1635690596416491521/photo/1)
	- Since it gets 86.4% on our MMLU benchmark, that suggests GPT-4.5 should be able to reach expert-level performance.
- Math capabilities
	- [It matches/beats Minerva](https://twitter.com/swyx/status/1635748632480870400)
	- [Does Tax Math](https://twitter.com/swyx/status/1635739184869826561?s=20)
	- More correct scheduling capability - [3 way availability window](https://twitter.com/omarsar0/status/1635688807910584338?s=20)
- Coding
	- showed coding - with Discord bot API
		- data cutoff in 2021, but asked discord march 2023 API - 
		- paste in the error message - fixes
		- tell it the environment - for jupyter notebook
	- showed the drawing to website code demo
		- [From OpenAI, hand sketch into website](https://twitter.com/rowancheung/status/1635744529587359756?s=20) [time stamped](https://www.youtube.com/live/outcGtbnMuQ?feature=share&t=993)
		- but also filled in 2 jokes
	- [Rails app from scratch - with stripe](https://twitter.com/Deaniocom/status/1635883813157969920f)
	- https://github.com/anysphere/gpt-4-for-code
		- 🌟 [lambda calculus parser](https://twitter.com/VictorTaelin/status/1635726202231988225)
		- [C++, Bazel, Terraform](https://twitter.com/sualehasif996/status/1635755267739598848)
	- [morten just - adding background animation](https://twitter.com/mortenjust/status/1635935702553886722?s=20)
	- [Python script for video/midi generation](https://twitter.com/ProleBrain/status/1635832735863570434) - much fatser coding process and more complex generation
	- [creating Pong in 1 minute](https://twitter.com/skirano/status/1635736107949195278?s=20)
	- [Snake in 20 mins](https://twitter.com/ammaar/status/1635754631228952576?s=20)
	- [Connect 4](https://twitter.com/firekeeping/status/1635789118239023106)
	- [Game of life](https://twitter.com/felixbade/status/1635799243628892160)
	- [Chrome extension](https://twitter.com/jakebrowatzke/status/1635882037319008258)
	- [security vulnerability explanation](https://twitter.com/jconorgrogan/status/1635695064692273161) haha its [not GPT4](https://twitter.com/jconorgrogan/status/1635699514668351509?s=20)
	- [using Midjourney and GPT4 to code an Angry Birds clone](https://twitter.com/javilopen/status/1719363262179938401) in 3 days and 10 hrs
	- [Effective GPT-4 Programming](https://news.ycombinator.com/item?id=38270714) from Gwern
- World knowledge
	- It knows many esoteric facts (e.g., the meaning of obscure songs, knows what area a researcher works in, can contrast ML optimizers like Adam vs AdamW like in a PhD oral exam, and so on). https://twitter.com/DanHendrycks/status/1635706823373377538?s=20
	- General causal reasoning - 96% on Tubingen (across Zoology, Engineering, Physics, Epidemiology, etc), 92% accuracy on CRASS benchmark, 86% on others https://twitter.com/amt_shrma/status/1653458009333587969?s=20
- Agentic behavior
	- [lying to human to achieve task](https://twitter.com/goodside/status/1635872117031047174?s=20) ([another discussion](https://twitter.com/YosarianTwo/status/1635780666632687617) - related to Diplomacy result
	- will be good at screenshot agency - sharif shameem tweet
- Creative text
	- showed summarizing existing article where every word begins with G or Q
		- 3.5 vs 4
	- Eminem styling - [improvement](https://twitter.com/DanGrover/status/1635713083523084288?s=20)
	- roon milton [attempt](https://twitter.com/tszzl/status/1635710653456580609)
	- [waifu calculus](https://twitter.com/gfodor/status/1635713792440176640) and [sandwich](https://twitter.com/gfodor/status/1635713392441987072)
	- "[latent inventions](https://twitter.com/gfodor/status/1635718452467101696)"
- Multimodal (OCR-free visual)
	- [From OpenAI, hand sketch into website](https://twitter.com/rowancheung/status/1635744529587359756?s=20) [time stamped](https://www.youtube.com/live/outcGtbnMuQ?feature=share&t=993)
	- More reading of images
		- [NYT](https://www.nytimes.com/2023/03/14/technology/openai-gpt4-chatgpt.html) article [photo of fridge contents](https://twitter.com/swyx/status/1635765117303521282) => receipes
		- [another invgredients screenshot](https://twitter.com/omarsar0/status/1635689918696501257?s=20)
		- [pixel to paper](https://twitter.com/omarsar0/status/1635729572816732167?s=20)
		- Developer livestream demo - [showed](https://www.youtube.com/live/outcGtbnMuQ?feature=share&t=621) [read Discord image](https://twitter.com/swyx/status/1635763638232559616) ([better screenshot](https://twitter.com/eerac/status/1635737216864452612)?)
	- Explain images ([my screenshots](https://twitter.com/swyx/status/1635692241523208195/photo/2))
		- [panel by panel explanation](https://youtu.be/2zW33LfffPc?t=611) - gets compositions
		- Extreme Ironing - [world model + visual](https://twitter.com/swyx/status/1635692241523208195?s=20)
		- Chicken nuggets - reading text on screen, rough match of world map
		- Explain shitty drawn meme - world model + comic
	- compare to Visual ChatGPT
	- "screenshots is all you need"
	- jim fan visual https://twitter.com/DrJimFan/status/1634244545360609289
		- note - NO audio
	- mckaey wrigley - gpt4-eyes https://twitter.com/mckaywrigley/status/1651291367224807424
- [Much lower hallucination](https://twitter.com/swyx/status/1635693559348338688?s=20)
	- but still "[confidently incorrect](https://twitter.com/RazRazcle/status/1635966297715490817?s=20)" with simple caesar shift cipher - more than gpt3.5
	- [log loss target encourages guessing/pretending](https://twitter.com/tszzl/status/1635707243630063616)
- safety
	- jailbreaks still work - DAN
		- waluigi jailbreak https://twitter.com/nomic_ai/status/1635719257110478859
- [Longer context](https://twitter.com/swyx/status/1635696088824033280?s=20) - 8k tokens, up to 32k (25k words, 50 pages of text)
	- can just pull in entire wikipedia articles - [eg Rihanna](https://twitter.com/omarsar0/status/1635690756177379328?s=20)
	- showed comparing articles - gpt4 article vs pynecone article
	- showed [pasting in 10k words](https://www.youtube.com/live/outcGtbnMuQ?feature=share&t=841) of the discord docs, poorly formatted
	- 32k tokens will cost $2
	- https://github.com/mpoon/gpt-repository-loader
- pricing
	- 12c - "[i think most people will turn out to prefer $2 per thousand *extremely smart* tokens](https://twitter.com/sama/status/1631153581100527616)"
	- prompt tokens, completion tokens - [jon stokes](https://www.jonstokes.com/p/the-chat-stack-gpt-4-and-the-near)
- Misc findings/usecases
	- [credit card enrichment](https://twitter.com/Shpigford/status/1635748608879337472)
	- [drug discovery](https://twitter.com/danshipper/status/1635712019549786113) - variants of Dasatinib, Atovaquone ([it's wrong](https://twitter.com/jbittker/status/1635763155895742464?s=20))
	- [people compatibility matching](https://twitter.com/jakozloski/status/1635778263787110401)
	- universities dropping [standardized tests](https://twitter.com/pmarca/status/1635693374027231233?s=20)
	- better at negotiation vs gpt3 https://twitter.com/jbrowder1/status/1652187042334519298?s=20
	- [Causal Reasoning](https://twitter.com/amt_shrma/status/1653457971844874240) 
		- GPT4 achieves new SoTA on a wide range of causal tasks: graph discovery (97%, 13 pts gain), counterfactual reasoning (92%, 20 pts gain) & actual causality.

## Launch Partners

- Bing [confirmed](https://twitter.com/yusuf_i_mehdi/status/1635709811840131072?s=20)  running GPT4 as [Prometheus](https://twitter.com/JordiRib1/status/1635694953463705600), Satya discussed prometheus before onstage. [bing extended turns](https://twitter.com/MParakhin/status/1635741730464059392). means [bing guides](https://oneusefulthing.substack.com/p/power-and-weirdness-how-to-use-bing) are gpt4 guides
- [Quora Poe](https://twitter.com/adamdangelo/status/1635690625642397696)
	- across openai gpt4 AND anthropic claude+
- [Duolingo](https://twitter.com/duolingo/status/1635688521695633408) ([blog](https://blog.duolingo.com/duolingo-max/))
	- explain my answer
	- roleplay with character
	- for spanish and french
- [DoNotPay](https://twitter.com/jbrowder1/status/1635720431091974157) "one click lawsuits" - sue robocallers and [emails without unsubscribe](https://twitter.com/cocksure_crypto/status/1635722368487129088?s=20)
	- 4 > 3.5, is good enough
- [Intercom](https://twitter.com/destraynor/status/1635705915595685902?s=20)  ([eoghan](https://twitter.com/eoghan/status/1635707829939240960), [blog](https://www.intercom.com/ai-bot)) - Fin reduces hallucinations (incl about competitors), disambiguates, hands over to agents
- Stripe
- oai has a "built with gpt4 page" https://twitter.com/DrJimFan/status/1635691047773966336?s=20
- be my eyes
	- [iphone shortcut - to camera powered searhc engines](https://twitter.com/mckaywrigley/status/1635841143786319872?s=20)
- [hyperwrite](https://twitter.com/mattshumer_/status/1635714586010607617)
- Elicit
	- pivoting gpt4 https://twitter.com/jungofthewon/status/1635725465901219841

## Criticisms

- [no technical details released](https://twitter.com/benmschmidt/status/1635692487258800128?s=20). [Yannic criticism](https://twitter.com/ykilcher/status/1635702708006006786?s=20), being [memed rickcolled](https://twitter.com/giffmana/status/1635761150611664899?s=20)
	- [scaling chart](https://twitter.com/swyx/status/1635711620889587712) means possibly uses 1000x compute vs GPT3
	- no param count. "you have not been a good user" - [sama](https://twitter.com/sama/status/1635709792319868930?s=20)
	- training done in aug 2022 ("done for a while")
	- data cutoff in sept 2021, but chatgpt is dec 2021?
	- estimate: [30k A100s for 3-5 months](https://youtu.be/pQgL91Y7Pvc?si=uMRfJLfNaAQCpEuZ&t=3121), 10e25 flops
- contamination 
	- [leetcode leaking](https://twitter.com/rUv/status/1635756651717496832?s=20)
		- but still its [bad at leetcode hard](https://news.ycombinator.com/item?id=35161612) so its ok?
	- [codeforces score](https://twitter.com/cHHillee/status/1635790330854526981) and subsequent folowup
	- AMC10/12 inversion ([stan polu](https://twitter.com/spolu/status/1635903343397576705), [roon](https://twitter.com/tszzl/status/1635840360705593345?s=20), [30 is worse than blank](https://twitter.com/BlancheMinerva/status/1635810135573495809?s=20))
	- if you contaminate, of course your perf goes up!
- Safety
	- [ARC agent testing](https://twitter.com/YosarianTwo/status/1635785141841698816/photo/1) - SET UP COPIES OF ITSELF WTF
	- [Moral arbiter](https://twitter.com/AutismCapital/status/1635747737387024386?s=20)
	- Raza habib finds [confident bullshit](https://twitter.com/RazRazcle/status/1635907462728495104?s=20) problem worse
- not intelligence
	- [sama counter](https://twitter.com/sama/status/1631421715434831872?s=20) - most of us trying to predict next word

## Misc

- [GPT4 predictions pre GPT4](https://www.lesswrong.com/posts/iQx2eeHKLwgBYdWPZ/retrospective-on-gpt-4-predictions-after-the-release-of-gpt)
	- Some people such as LawrenceC and gwern have noted in the post’s comments that GPT-4 was probably trained on 15,000 GPUs or more. Assuming this is true, my prediction that GPT-4 would be trained on 2,000 to 15,000 GPUs seems like an underprediction and consequently, I may have underpredicted GPT-4’s total training compute by about a factor of 2.
	- I originally predicted that GPT-4 would use about 5.63e24 FLOP of compute. According to [EpochAI,](https://epochai.org/mlinputs/visualization?startDate=1950-1-1&endDate=2023-4-1&xAxis=Publication%20date&yAxis=Training%20compute%20(FLOP)&separateCategories=false&citationThreshold=0&otherDomainThreshold=10&startDlEra=2009-12-31&startLargeScaleEra=2015-9-1&largeScaleAction=label&outliersAction=remove&recordSettersAction=ignore&bigAlphagoAction=ignore&alphagozeroAction=ignore&lowOutliersZValueThreshold=-2&highOutliersZValueThreshold=0.76&outlierWindowSize=2&filterText=&splitDomains=&domainsToNotSplit=&ranges=[object%20Object]&splitDlEra=true&splitLargeScaleEra=true&plotRegressions=true&bootstrapSampleSize=10&adjustForEstimateUncertainty=true&preset=Three%20eras%20of%20compute&aspectRatio=fit%20to%20container&autoresetCamera=true&showTitle=false&labelEras=true&showDoublingTimes=true&showOpenAITrend=false&regressionDecimals=1&textSize=100&systemAlpha=100&systemNames=hide&showLegend=true&parametersRange=NaN,NaN&trainingComputeRange=NaN,NaN&inferenceComputeRange=NaN,NaN&trainingDatasetSizeRange=NaN,NaN&inferenceComputePerParameterRange=NaN,NaN&inferenceComputeTimesParameterRange=NaN,NaN&labelPoints=false) the true value is about 2.2e25 which is about 4x my original estimate. The chart below also shows how GPT-4 came out earlier than I expected.
- "Race dynamics"
	- previously - bing vs bard race https://twitter.com/xlr8harder/status/1622849293571817472
	- Google [launched](https://twitter.com/benparr/status/1635684322261729282?s=20) generative AI across Gmail, Docs, Sheets (!), Slides (!), Images ([video](https://www.youtube.com/watch?v=6DaJVZBXETE))
		- per directive from Sundar
		- [google unable to ship](https://twitter.com/Suhail/status/1635866358067113986?s=20) while [openai ships like fucking beast](https://twitter.com/E0M/status/1635727471747407872?s=20)
		- but maybe focus is on workspace rather than developers
	- PaLM mess
		- [cant find the api ](https://twitter.com/harishkgarg/status/1635941404961837058?s=20)
	- Anthropic claude
		- ["claude+ better than claude"](https://twitter.com/adamdangelo/status/1635690630289723394?s=20)
		- compare claude vs gpt on 5 whys https://twitter.com/dzhng/status/1677931017750089729
		- claude provided via [Kagi FastGPT](https://news.ycombinator.com/item?id=35719482)
	- coincidence? or just [pi day shenanigans](https://twitter.com/EigenGender/status/1635766846719934465?s=20)
- [Scaling predictability](https://twitter.com/swyx/status/1635688942354980865?s=20)
- 10 years ago, andrej karpathy [didn't feel optimistic](https://twitter.com/ramsri_goutham/status/1635852572727836673)
- [Jakub Pachocki](https://twitter.com/sama/status/1635700851619819520?s=20) - from Dota team [was key player](https://twitter.com/ilyasut/status/1697713317660500407)
- logank's repies https://twitter.com/OfficialLoganK/status/1636037282280112128?s=20
- possibility
	- Not sure I can think of a time where there was this much unexplored territory with this much new capability in the hands of this many users/developers. - [karpathy](https://twitter.com/karpathy/status/1635749104059056128)
- jeff huber takes
	- emphasises
	- de emph memorization
	- creativity
	- examples
	- math
	- pixels is all you need
- estimated cost
	- $40m single run https://twitter.com/abacaj/status/1650187242202189824?s=46&t=90xQ8sGy63D2OtiaoGJuww
	- >$100m total
		- repeated by connor leahy https://www.youtube.com/watch?v=tYGMfd3_D1o
		- <$100m ajeya cotra https://twitter.com/ajeya_cotra/status/1687135321551716353?s=46&t=90xQ8sGy63D2OtiaoGJuww
	- 1tr params but vague rumor
- GPT-4 was apparently designed to fit on 2 H-100's which limits parameters to 160GB. https://twitter.com/LetterRip1/status/1670941206019457024?s=20
- https://152334h.github.io/blog/non-determinism-in-gpt-4/
	- Non-determinism in GPT-4 is caused by Sparse MoE
- GPT-4 8 x 220B models
	- https://www.reddit.com/r/mlscaling/comments/14eowmw/comment/jp40uqm/?context=3
	- estimated $40m cost for training https://colab.research.google.com/drive/1O99z9b1I5O66bT78r9ScslE_nOj5irN9#scrollTo=1ftsdvKjPYiV
	- https://the-decoder.com/gpt-4-architecture-datasets-costs-and-more-leaked/
		- or 16x110B models with 2 consulted per forward pass?
		- 13T Tokens
		- training costs for GPT-4 was around $63 million
		- GPT-4 costs 3 times more than the 175B parameter Davinci, due to the larger clusters required and lower utilization rates.
		- Inference Architecture: The inference runs on a cluster of 128 GPUs, using 8-way tensor parallelism and 16-way pipeline parallelism.
		- Vision Multi-Modal: GPT-4 includes a vision encoder for autonomous agents to read web pages and transcribe images and videos. The architecture is similar to Flamingo. This adds more parameters on top and it is fine-tuned with another ~2 trillion tokens.
- [System Prompts](https://github.com/spdustin/ChatGPT-AutoExpert/blob/main/System%20Prompts.md)
- -   [**Baseline GPT-4**](https://github.com/spdustin/ChatGPT-AutoExpert/blob/main/_system-prompts/base.md)
    -   [Advanced Data Analysis](https://github.com/spdustin/ChatGPT-AutoExpert/blob/main/_system-prompts/advanced-data-analysis.md)
    -   [Browse with Bing](https://github.com/spdustin/ChatGPT-AutoExpert/blob/main/_system-prompts/browse-with-bing.md)
    -   [DALL•E](https://github.com/spdustin/ChatGPT-AutoExpert/blob/main/_system-prompts/dall-e.md)
    -   [Mobile App (iOS)](https://github.com/spdustin/ChatGPT-AutoExpert/blob/main/_system-prompts/mobile-app-ios.md)
    -   [Mobile App (Android)](https://github.com/spdustin/ChatGPT-AutoExpert/blob/main/_system-prompts/mobile-app-android.md)
    -   [Plugins (Example: Zapier)](https://github.com/spdustin/ChatGPT-AutoExpert/blob/main/_system-prompts/plugins.md)
    -   [Vision](https://github.com/spdustin/ChatGPT-AutoExpert/blob/main/_system-prompts/vision.md)
    -   [Voice Conversation](https://github.com/spdustin/ChatGPT-AutoExpert/blob/main/_system-prompts/voice-conversation.md)
    - [**Custom Instructions**](https://github.com/spdustin/ChatGPT-AutoExpert/blob/main/_system-prompts/_custom-instructions.md)
	    - "[meta/nova mode](https://www.novaspivack.com/technology/nova-mode-the-ultimate-chatgpt-custom-instruction)" where you can introduce comands like `//?` to hallucinate a manual,  and `continue from //8` to continue a message

### GPT5

Source says GPT-5 will cost $2.0-$2.5B to train, 500k H100s for 90 days or another configuration. Starts next year. https://twitter.com/wagieeacc/status/1714458385624506679?s=12&t=90xQ8sGy63D2OtiaoGJuww