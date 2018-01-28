# AI-Law-Minicourse-HW

<h1>Supreme Court Topic Modeling Analysis</h1> 

1. Step 1 - Data Collection & Preparation.ipynb
The code uses Beautiful Soup to pull data from the caselaw.findlaw URL for specific years, 1760-2018. The year_getter line of code then converts the data into a pandas data frame table. The next lines of code are there to validate the case URLs, simplify the data structure and then give the number of cases in the table. 

2. Step 2 - Data Collection & Preparation.ipynb
The code splits the data frame into three separate data frames to prevent your IP from being blocked due to the high volume of requests from the caselaw URL. The next line grabs a description of each case to put in the data table. They next take the three data frames and pickle them, and then combine them into one data table. The final step is to save it so you don't have to run the file again. 

3. Step 3 - Data Processing.ipynb
Variables are assigned to common words to create a stop list, which would take out extra terms which may slow down processing. The final stop list is defined so the machine knows what words to leave out. The final steps clean out the text to make it easier for grouping. 

4. Step 4 - Topic Modeling Method Testing.ipynb
This step is testing the machine by telling it to print the words that come out after the data was processed and compressed, and then it fits the model by telling the machine specifically how it should be formatted. The code uses LDA to get the most important topic terms, and specifies that stop words should not be included. The number of topics are defined, and each topic groups different sets of terms. Because it's hard to see how the documents relate, they try an LSA model next. The LSA model is still not modeled well, so then they use NMF which gives a better grouping of words that show how the documents relate to each other. 

5. Step 5 - Topic Model Application to Data.ipynb
The code tells the machine to use the pickled, cleaned file and to pull information out of the entire set of documents. To do this, the code stacks the documents by putting it in a vector, fits the model, and then commands a return of the top words found in all the documents. They then test the model against the data frame to make sure it's a good model to use by returning it as a series. The code then asks to run the model again, but then to create topic words to look up in the data frame by again vectorizing the data and then asking for a topic dictionary in return. They then look up topic words for each item in teh data frame to make sure the model worked and then the data is arranged for a final table. All of the data is merged and then sorted by year, and then converted into a graph. 

<h2>Tensorflow word2vec Tutorial Analysis</h2>

1. Step 1 - Data Collection & Preparation 
After installing all the modules, the code tells the machine to download data from the specified URL. It then tells the machine to read the data into a list of strings by extracting the data in the file as a list. The output is the data size found for the set. 

2. Step 2 - Data Processing
The next step is to build the dictionary by setting the vocabulary size and then processing the inputs from the previous step and turning it into a dataset. The code tells the machine to use the data strings and transform them into a useable dataset. The code then tells the machine to print out the most common words and assign values to those words.

3. Step 3 - Creating Training Data
This step creates training data for the model. It tells he machine which words to use for which variables, and it results in a dictionary of words with assigned variables. The code specifically tells the machine to go back through a little before the end of the batch to avoid skipping words at the end of a batch. This ensures a more complete analysis. 

4. Step 4 - Building and Training the Model 
This step creates and trains the model. Dimensions are set, and the code tells the machine to choose random sets of words to compare their similarity, and to only use specific samples that show up more frequently to increase accuracy. The machine then computes the average NCE loss for the batch to remove biases. 

5. Step 5 - Training the Model 
This step actually trains the model by optimizing how the machine compares the data and then applying that optimization to the dataset. The code tells the machine to find similarities in the original set and compare it to neighboring words, and then to create a list of similar words to that original word. 

6. Step 6 - Visualization
This step tells the machine to create a plot. Labels are created on the x and y axes. The plot helps the user to clearly see how the words are associated with each other based on similarities.  