# Turkish_Wikipedia_Search_Engine
A search engine algorithm that operates on Turkish Wikipedia, Vikipedi.
It finds the entry that is most relevant to a given query using tf_idf measure.
Since going through all the categories in Vikipedi will require a lot of timeand GPU, the current code only works in the categories that are determined by the user.
# How to use it?
To be able to run, the code requires two documents: "tmp_cat.txt" and "query_file.txt"
- "tmp_cat.txt" is a txt file that contains the name of the categories in Vikipedi that search engine will work on in different lines. The categories can be picked after running the 6th cell in the code which will print out all the categories in Vikipedi. The categories should not be Vikipedi's internal categories. An example of this file is provided in this repository.
- "query_file.txt" is a txt file that contains the queries that are going to be searched in Vikipedi in different lines. An example of this file is provided in this repository.

After these files are ready, the code can be ran straightforward. It will get the data from the Vikipedi api MediaWiki. Then, it will ask for a user input for the n-gram sizes. The user needs to provide an integer number for the n-gram sizes that are going to be used in the search engine. Then, depending on the user input, the algorithm will get the n-grams from the first paragraph of entries in the given categories in "tmp_cat.txt". Then, using this information tf_idf values of each n-gram for each category will be calculated. Then, using this information feature vectors for each category will be calculated. Also, the feature vectors for the search query will be calculated. Then, comparing their feature vectors, the category that is closest to the search query will be determined. Then feature vector calculation process for the first paragraphs of the entries in the closest category will be conducted. The vectors for each entry will be compared with query entry. The closest entry will be printed out as the result.
# N-gram Evaluation
In the analysis, the algorithm had a precision of 37% when n-gram size was 4, 23% when it was 5, and 7% when it was 6. Therefore, it is advised to use with smaller n-grams.
