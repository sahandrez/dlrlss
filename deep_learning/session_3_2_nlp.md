# Natural Language Processing - Alona Fyshe 

NLP is very multidisciplincary. 80% is easy and can be implemented rule based. 20% is progressivily harder.

* Understanding language is hard.
* It has ambiguity.
* language is complex
	* let's start simple single words.
	* working at word level is easier.
* How can we reprsent a meaning?
	* vector space models (SVM): each word has a vector of numbers associated with it based on 5some criteria. the vectors have hundreads of dimensions. 
	* from context, you can infer meaning. computers need to use the same notion. 
	* build a vector for each word and train on words we observe together.
* SkipGram 
	* one-hot vecotr, 1 only gor the central word, 0 elsewhere
	* output: probablit distribiution over all words
	* train so that the values are high for words coming together 

