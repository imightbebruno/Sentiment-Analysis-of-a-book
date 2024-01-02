# Sentiment-Analysis-of-a-book
Sentiment Analysis of a Chapter of a Book using SpaCy TextBlob, Vader and Afinn libraries 

The present work constitute a sentiment analysis using three distinct libraries for NLP: Afinn, SpaCy, and Vader. The objective is to compare the results and methodologies of these tools for sentiment analysis. The selected text is Chapter IV of Leo Tolstoy's novel "War and Peace", extracted from an eBook available from the Gutenberg Project. (For more information, visit www.gutenberg.org). This text was chosen due to the intensity and complexity of its dialogues, where characters frequently employ irony or exaggeration in communication. This aspect is later discussed in this analysis.

In common, all three analyses aim to provide:
• The count of positive, negative, and neutral sentiments in the overall text.
• The top 5 most positive words.
• The top 5 most positive sentences in the chapter.

For the Afinn library analysis, I created variables to store the sentiment score of each line, computing the percentage of the total for each sentiment. Determining the 5 most positive words involved utilizing functions to store sentiments in an empty dictionary, checking for words with a positive score (more than 0), and using list slicing to identify the highest-scoring words. The same approach was used to compute sentence scores by splitting the text into a list of sentences using ('\n').
The analysis using the Afinn library demonstrates coherent selections of positive words ("rapturous," "handsome," "pleased", "charming," and "glad"). Regarding the most positive sentences, the tool generally reflects the accurate text, though it tends to emphasize common polite words excessively.

The analysis using Vader Sentiment Analysis employs a similar approach. It returns a compound score close to 1, indicating an overall strongly positive tone in the text. To tokenize the sentences, various methods were tested, with the Punkt tokenizer tool providing the best results. However, some sentences are still too lengthy, occasionally returning more than a single line of dialogue. The identified most positive words align closely with other analyses ("handsome," "pretty," "kissed," "hand," and "like"). However, in sentence analysis, this tool sometimes selects ambiguous sentences, especially when characters use words to mask their true feelings, leading to misinterpretations.

The last tool analyzed was SpaCy TextBlob. A similar approach was employed to write the code, storing words in a dictionary and then utilizing list slicing to identify the top five highest-scoring words. This tool highlights words that weren't picked by the other two tools ("best," "beautiful," "great," "pleasant," "charming"). The selected sentences are relatively shorter compared to the previous analyses. Similar to other tools, this library tends to overweight positive words used by characters for politeness (such as "lovely" or "dear").

In summary, all three tools effectively identify the strongest emotions words present in the text. However, the complexity of meanings and the hidden intentions of the characters in this text challenge these tools. Words might carry the intensity of a context rather than a genuinely positive meaning. Literary works often employ sarcasm, irony, and figurative language, confounding the tools used in this analysis. 

It's acknowledged that the lexicons used were not designed for the specific context of literary works. For instance, the Vader Library targets texts from social media and online reviews, misunderstanding irony and insensitivity to shifts in sentiment through poetic choices by the writer. Similarly, the Afinn library, constrained by a limited vocabulary, might miss words due to the historical period of the text. SpaCy, although used for sentiment analysis, was primarily built for different tasks and has limited ability to understand the emotional connotations of the text itself.

Recognizing the limitations of the selected libraries, this analysis aims to highlight the challenges when using these tools to interpret complex texts. My future projects could explore strategies involving different libraries and pre-trained data to improve performance. For data scientists, this serves as a reminder of how these libraries might perform, even in an online context where complex language, word choices, slang, and cultural references significantly impact algorithmic performance. Not only is it useful to keep in mind when analyzing texts of this nature, but also the target texts for analysis on the internet sometimes contain similar features to the text of the present analysis, such as sarcasm, complexity, and cultural references.
