# Sentimental_Analysis_Using_Opinion_Target_and_Opinion_words.
This project aim to target sentiment analysis based on opinion words (like good, bad, beautiful, wrong, best, awesome, etc) of selected opinion target ( like product name for amazon product reviews). The code provides steps of pre-processing like stopword removal, removal of duplicates in the review, spelling correction, etc.
  From the review biwords and triwords are generated for each reviewed text and use it to generate 8 patterns from rule-based method (by POS tagging). Opinion target and their opinion words are extracted using these 8 patterns. 
    The extracted opinion words gets polarity directly from TextBlob library using polarity function of sentiment class. This polarity is generated for every opinion word in every reviewed text, and the highest magnitude polarity word is selected from every reviewed text.
    These highest magnitude polarity word along with its polarity is selected in a list named tuple_word_score.  These list is used for searching focused opinion words and eliminate noise within the data. Afterward the average of all the polarity of opinion word obtained from the search is taken and decide a threshold to categories positive and negative semantics.
    For 300 reviews our threshold value came out to be 0.125. In the dataset "overall" represents reviewer rating ranging from 1 to 5. I considered "overall" rating of 1, 2 and 3 as negative semantic rating and "overall" rating of 4 and 5 as the positive semantic rating for testing of proposed method. The average score value of polarity of all the reviewed text is partitioned in to five parts in their ascending order of the polarity. The first 3 parts are assigned negative semantic name and the last 2 parts are assigned positive name. This way the model is trained to generate a positive and negative polarity. It is tested with the positive and negative semantic "overall" rating explained previously. The accuracy obtained was 71% for only first 300 reviews. It can be increase further for more reviews. Dataset is provided with 33620 review text this for analysis.
    Whole project used semi-supervised approach wherein predefined list of opinion target was provided in a variable named stuff. The synonyms of these opinion targets are used to figure out many similar words within the pattern. In addition, synonyms of opinion words are also included in the opinion word set to the generated similar opinion words of the pattern.
    Also I validated the obtained result with Logistic Regression, Decision Tree, Gaussian Naive Bayes, Bernoulli Naive Bayes, Multinomial Naive Bayes, Random Forest, K-Nearest Neighbour, SVM(Linear and Non-linear kernel) using bag of word model with the accuracy of 58.31%, 82.26%, 73.75%, 76.42%, 81.80%, 82.15%, 78.67%, 79.15% respectively.
