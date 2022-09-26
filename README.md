# Information-Extraction-Iterative-Set-Expansion

a. Teammates:
Paras Tehria - pt2557
Sakshi Arora - sa3871


b. Files Submitted :
project2.py, spanbert.py, spacy_help_functions.py


Instructions on running:-
Inside the SpanBert folder cloned using Github, add three python files mentioned above from the submission. We have made changes to original spanbert.py and spacy_help_functions.py, so make sure to replace the old files with the new ones.


c. Commands for running :

1. Go to the SpanBert folder:
	
	cd SpanBert

2. Run the command :

	pip3 install -r requirements.txt

3. Run the command :

	python3 project2.py <google api key> <google engine id> <r> <t> "<query>" <k>


d. The flow of the project is as follows :

1. The program starts with a seed query, extraction confidence threshold, number or tuples and given relation
2. We will then search the web and get the results using the google search api 
3. We then use the BeautifulSoup toolkit to get the text from the paragraphs in html pages we have received as a result from the google search api
4. Now we preprocess the text before sending it to spacy
5. Spacy will then annotate, tokenize and detect entities on the text
6. The sentences and the entities are then sent to the spanbert however, we only send the entities that follow the corresponding subject object format wrt the relation
7. The spanbert then returns the relations on which check if the confidence threshold is reached or not
8. We do this in multiple iterations until k number of relations have been extracted


e. Description of Step 3: We maintained a list of processed_urls to keep track of all the urls already encountered and prevent us from processing it again
1. We entered a timeout of 20sec to retrieve a webpage, if it does not happen under 20 sec, we ignore that url
2. We then extracted all the visible text
3. If the visible text extracted was greater than 20,000, we clipped it
4. URLs already process are kept in processed_queries set so that no query is repeated
5. We then filtered out those generated candidate pairs which did not follow the subject object format for the given relation
6. We then updated the confidence of a relation if spanbert returned that relation with greater confidence


f.
google api key - AIzaSyD4cANvEPxUNlRS1ckb4u06Z8ZK1v08gD0
google engine id - dc64f97150ea60e6b

