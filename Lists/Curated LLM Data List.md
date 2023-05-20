
Training Process
	Pre-training
		starts with gpt-neo
	
	Contexts
		sciq
		squad
		quotes
		dolly 15k
					
		add phil
			already include in pile
			
		wanted to get redpajama in, but it's basically a rehash of the pile
		
	Fine-tuning
		QA
			X sciq
			
			X WikiQA
			
			X Squad QA (without context)
			
			X Dolly QA
			X Alpaca
			
			X Cosmos QA (with Context)
				commonsense
				
			***hakurei/open-instruct-v1
			
			***OpenAssistant/oasst1
				https://huggingface.co/datasets/iamketan25/open-assistant-instructions
			
			Supernatural-2m
			
			Q/A to Context using Squad Data
			
			CommonSense QA
			
			subjqa
				https://huggingface.co/datasets/subjqa
			
			beerqa?
				error
				https://beerqa.github.io/
				
				simply squad + hotpot
				hotpot is wikiqa
					https://hotpotqa.github.io/
			
			
			
			Summary
			Classification
			
		Supernatural will be after

	 Reinforce on select conversations

Multitask
	Classification (sentiment)
	
	Summary
		CarperAI/openai_summarize_tldr
		
		JulesBelveze/tldr_news
			headines
		
	Q/A

Data:
	CommonSense QA
		https://huggingface.co/datasets/commonsense_qa
		
	wikitext-v3
	alpaca 52k
	Dolly 15k
	wiki-qa
		https://huggingface.co/datasets/wiki_qa
		
	adverserial
		adverserial_qa = load_dataset("adversarial_qa",'adversarialQA')
		
	https://github.com/databrickslabs/dolly/tree/master/data
	newsgroup articles
	regex statements
	programming examples (w3schools)
		use condorcet voting to track which examples should be tracked
		
		just python
		
		machine learning
	merck manual medical diagnosis information
		use condorcet voting to track which examples should be tracked
		Start with choice examples
	arxiv abstracts
	investopedia
	science facts
		https://huggingface.co/datasets/sciq
	quotes
		ex.
			https://graciousquotes.com/carl-jung/
		brainyquote.com
		www.goodreads.com/quotes
		https://huggingface.co/datasets/A-Roucher/english_historical_quotes
		https://huggingface.co/datasets/Abirate/english_quotes
	lyrics to popular songs (top 100 billboard per year)
		genius
	front page news stories
		newspaperarchive.com
		
		use a similar concept on top voted reddit posts from select communities
		e.x.
			news
			askphilosophy
			scrape top level comments and descend 3 deep?
			academic biblical
	ted talk abstracts
	book summaries (reviews?) (ideally would be reports, essays, exposes' rather than 'this book was good or bad') to NY Times best selling non fiction
	Summaries of popular self help guides
		May be redundant with wiki	
	interesting fact a day sources
		condorcet voting to track which facts are most pertinent
	Peer reviewed findings (abstracts)
	lessthanwrong choice articles
	Philosophy
		IEP data
			for ex.
		SEP data
			https://plato.stanford.edu
	Synopsis of Oscar winner movies
		Redundant with wiki?
	Important historical events
		Summaries of popular self help guides ([for ex. 7 Habits of Highly Effective People, How to Win Friends and Influence People, Men are from Mars, Women from Venus])
		Kind of redundant, for example, wikipedia already stores most of the crucial information

Quantize as a knowledge graph for dense passage retrieval

Generative Questions (Text to question models)

The more comprehensive the prompt's crossover is with other idea's and concepts, the faster the model will generalize across large domains of knowledge because it will make connections between disparate nodes. (Incorporate this idea into batch by having multi-task batch samples, i.e. stratified on the various tasks).

System Prompt:
	***Ask the model to suggest where you can print diagnostic information.

	***Ask for options before code. (so you can evaluate)

	***you are offering a generic set of advice, what I wanted to see was advice specific to my code, i.e. identify the use cases in my code for the suggestions you are listing.
	
	*** Make explicit your logic in the dependency order of steps tasks are needed to accomplish the task.
	
	***Always tell me how I can validate the output before we move on
	***just provide me the line(s) necessary to resolve this issue and where to put it
	***provide context in comment blocks before code.
	
	in addition to a proposed solution
	give me diagnostic code to run to help solve this issue
	
So try to pick concepts that are not correlated with other as well as those that are.  I'd say a nice 50/50 mix.  Imagine markowitz profile, the goal is find the best fit (regression mean fit) with minimimal error (risk).

	batch multi-task training

	Train prompt setup:
	
	
	Below is an instruction that describes a task. Write a response that appropriately completes the request.
	### Instruction:
	<task>
	### Response:

		<task> types
			Famous quote task
		
			Physics task (sci-q)
		
			Q/A task
				squad extractive
		
			Prep data before:
				Synthesize a response from these random quotes, science hub information, and extracted wikipedia deep passage retrieval responses (use upstream big LLM, alpaca, GPT-6b, GPT-NeoX, GPT-3.5 Turbo)
		
			Summarize task
				Summarize synthesized response
				
				Summarization
				
				