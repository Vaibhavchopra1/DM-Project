### DM Mini-Project 2

**Project Title:**  
Charting Unconventional Cinematic Pathways: Advanced Analysis of Actor Personas and Genre Evolution in CMU Movie & Oscars dataset

**Abstract:**  
This project explores the CMU Movie Summary Corpus through advanced network analysis, machine learning, and natural language processing to uncover unconventional patterns in actor personas and genre evolution. It aims to unravel the intricate networks that shape actor careers, identify genre archetypes and evolution trends, and find the features which impact the box office revenue most. By leveraging graph theory, clustering, and time series analysis, this study will reveal the hidden cinematic pathways that underpin the evolution of the film industry. Using the Oscars dataset to see how actors affect the movie's financial performance and more.

**Data Analysis Questions:** 
- Which actors navigate their roles within collaborative networks across different genres?
- How does an actor's network position impact their exposure to diverse genres, career longevity, and recognition?
- How have the top 10 genre popularity trends shifted over time, and how do these trends relate to historical and cultural milestones? Which genre has the best trend?
- How does the best trend genre(Drama) popularity trends shift over time?
- Can we use clustering and natural language processing to uncover genre archetypes and their sub-genres? (Only the top 10 genres considered)
- What role do regional and linguistic differences play in shaping genre preferences?(Top 5 countries and Top 10 genres are considered)
- What movie metadata features are the strongest predictors of box office revenue?  
- How does the presence of Oscar-nominated actors and crew members influence a movie's financial performance?
  
**Additional Dataset used**: Oscar Dataset(used for Q8 only)

**Method & Result:**  
### 1. Data Handling and Exploratory Analysis

**Objective**: Prepare the dataset for analysis, ensuring data quality and usability for subsequent analyses.

#### Labelling and Data Identification
- **Data Collection**: Data is sourced from the CMU Movie Summary Corpus, which includes metadata and plot summaries for a variety of films.
- **Dataset Selection**:I have used character metadata, movie metadata and plot summaries datasets for this analysis.
- **Labelling**: Columns of datasets are properly labelled as can be seen in the notebook.

#### Descriptive Statistics
- **Summary Statistics**: Generating basic statistics (mean, median, mode, etc.) for numerical data to get a sense of data distribution. Along with 
- **Textual Analysis**: Applying natural language processing tools to plot summaries to extract features that describe the narrative elements of the movies. Also, help us find the Top 20 commonly used words as seen in the figure below.
  ![image](https://github.com/Vaibhavchopra1/DM-Project/assets/70208602/0bfa4c4e-2a1a-4dd6-aa3a-dd046efc5721)
  
#### Cleaning and Preprocessing
- **Normalization**: Standardizing data formats, such as dates and categorical data, to ensure consistency across the dataset.
- **Missing Values**: Handling missing data through imputation or exclusion, depending on the nature and impact of the missing data on the analysis. The first calculating the number of missing values. Now treating the missing values by replacing them with some columns with mean/median/ mode and have dropped some column values where they were missing.
- **Textual Data Transformation**: Converting plot summaries and other textual data into a format suitable for machine learning and network analysis, using techniques such as tokenization and vectorization.
-**Converting into Readable data**: Converted the Movie countries, Movie languages and Movie genres columns' data values into a readable format to make it easy for visualization. Example: Converted {"/m/03rk0": "India"} into "India".

### 2. Approach for Data Analysis Questions
**Note**: Refer to the code in Jupyter Notebook

**Question 1**: Which actors navigate their roles within collaborative networks across different genres?
- **Approach**: Building a network graph where nodes represent actors and edges represent collaborations between them.Calculating metrics such as degree centrality and betweenness centrality to identify influential actors within the network.
- **Output**:
     Top 10 actors by degree centrality:
  [('Samuel L. Jackson', 0.09638168427793788), ('Robert De Niro', 0.07845020813320525), ('John Goodman', 0.06724303554274735), ('Christopher Walken', 0.06468139609349983), ('Stanley Tucci', 0.06372078130003202), ('Liam Neeson', 0.0627601665065642), ('Morgan Freeman', 0.06243996157540826), ('Ben Stiller', 0.062119756644252316), ('Matt Damon', 0.06147934678194043), ('Tom Wilkinson', 0.05891770733269292)]
- **Result**:From this analysis, we can infer that actors with high degree centrality are likely navigating their roles within a wide array of genres. Their ability to connect with diverse actors suggests versatility and adaptability in their careers. For instance, Samuel L. Jackson appearing in genres ranging from action to drama indicates his broad appeal and ability to fit into various narrative contexts. This versatility not only enhances an actor’s visibility but may also contribute to career longevity and success.

**Question 2**: How does an actor's network position impact their exposure to diverse genres, career longevity, and recognition?
- **Approach**: Using Question 1, the graph and the degree centrality and betweenness centrality matrix calculated to then do correlational analysis where in assessing relationships between an actor’s network centrality and their career longevity, genre diversity, and recognition.
- **Output**:
     Top 10 actors with the highest diversity:
  [('Samuel L. Jackson', 76), ('Robert De Niro', 63), ('John Goodman', 63), ('Christopher Walken', 58), ('Amitabh Bachchan', 55), ('Morgan Freeman', 52), ('Randy Quaid', 50), ('Danny DeVito', 49), ('Brian Cox', 48), ('Danny Trejo', 48)]
- **Result**: Actors with high centrality and genre diversity, such as Samuel L. Jackson and Robert De Niro, demonstrate that a strong network position can lead to broader opportunities in diverse film genres. We are all well aware of the names of these actors listed above which also implies how diverse and well-known these actors are. We have seen their career last for a long period as well as get recognized by many. This diversity can contribute to an actor’s recognition in the industry, making them more appealing to casting directors looking for versatile talent. Additionally, this versatility and recognition are likely contributors to their career longevity, allowing them to maintain relevance in the film industry over long periods.


**Question 3**: How have the top 10 genre popularity trends shifted over time, and how do these trends relate to historical and cultural milestones? Which genre has the best trend?
- **Approach**: Using time series data to identify trends in genre popularity over decades.
- **Output**:
 ![image](https://github.com/Vaibhavchopra1/DM-Project/assets/70208602/c5aee902-edce-4e77-b733-dadf42c37fe6)
- **Result**:

**Question 4**: How does the best trend genre(Drama) popularity trends shift over time?
- **Approach**: Using time series data to identify the best trends(Drama) in genre popularity over decades after that performing seasonal decomposition to analyze its trend, seasonality, and residuals.
- **Output**:
  
![image](https://github.com/Vaibhavchopra1/DM-Project/assets/70208602/11e937a3-2d36-4143-9edc-5ef7031a6814)
- **Result**:

**Question 5**: Can we use clustering and natural language processing to uncover genre archetypes and their sub-genres? (Only the top 10 genres considered)
- **Approach**:Applying clustering techniques to plot summaries to discover underlying genre archetypes and thematic elements common within genres. Using advanced NLP techniques to parse complex narrative structures and identify emerging sub-genres within traditional genres.
- **Output**:
![image](https://github.com/Vaibhavchopra1/DM-Project/assets/70208602/1ff23a91-397f-43c0-81a6-67756652e80a)
- **Result**:


**Question 6**: What role do regional and linguistic differences play in shaping genre preferences?(Top 5 countries and Top 10 genres are considered)
- **Approach**: 
- **Output**:
![image](https://github.com/Vaibhavchopra1/DM-Project/assets/70208602/a1ccd638-fa27-4620-b3a0-3c5ed8789c00)
- **Result**:

  **Question 7**: What movie metadata features are the strongest predictors of box office revenue?
- **Approach**: 
- **Output**:
  
  <img width="220" alt="Screenshot 2024-05-10 131348" src="https://github.com/Vaibhavchopra1/DM-Project/assets/70208602/fea7dcb2-3a70-4206-b8fe-9cc6464aa32c">

- **Result**:

**Question 8**: How does the presence of Oscar-nominated actors and crew members influence a movie's financial performance?
- **Approach**: The approach involves first loading the Oscar and CMU movie datasets, filtering the Oscar data to identify relevant winners. A ColumnTransformer is used to preprocess both numerical and categorical features. After training the model on the training set to predict box office revenue, the predictions on the test set are evaluated with Mean Squared Error (MSE) and R-squared metrics to measure the model's accuracy.
- **Output**:
Mean Squared Error: 5662417742259266.00
R-squared: 0.77
- **Result**:Winning or being nominated for an Oscar has a significant impact on a movie's subsequent box office revenue. This conclusion is based on a regression model that explains 77% of the variability in box office revenue, as reflected by the R-squared value. By incorporating features like genre, runtime, and whether a movie won an Oscar, the model demonstrates that winning or even just being nominated contributes positively to a film's financial success. Although the predictions have room for improvement due to a relatively high mean squared error, the model's strong performance indicates that winning an Oscar generally leads to a substantial boost in revenue, highlighting the considerable value of such recognition in the film industry.

