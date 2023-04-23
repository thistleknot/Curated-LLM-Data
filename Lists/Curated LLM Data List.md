Data:

	wikitext-v3
	alpaca 52k
	Dolly 15k
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

The more comprehensive the prompt's crossover is with other idea's and concepts, the faster the model will generalize across large domains of knowledge because it will make connections between disparate nodes.

So try to pick concepts that are not correlated with other as well as those that are.  I'd say a nice 50/50 mix.  Imagine markowitz profile, the goal is find the best fit (regression mean fit) with minimimal error (risk).

Template
	
	Famous quote task
	
	Physics task
	
	Q/A task
	
	Prep data before:
		Synthesize a response from these random quotes, science hub information, and extracted wikipedia deep passage retrieval responses.
	
	Summarize task
		Summarization
batch

***Ask the model to suggest where you can print diagnostic information.

***Ask for options before code. (so you can evaluate)

	***you are offering a generic set of advice, what I wanted to see was advice specific to my code, i.e. identify the use cases in my code for the suggestions you are listing.

Alpaca
	Below is an instruction that describes a task. Write a response that appropriately completes the request.
	### Instruction:
	Write a poem about the transformers Python library. 
	Mention the word "large language models" in that poem.
	### Response:
