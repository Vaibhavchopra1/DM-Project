### DM Mini-Project 2

**Project Title:**  
Charting Unconventional Cinematic Pathways: Advanced Analysis of Actor Personas and Genre Evolution in CMU Movie & Oscars dataset

**Abstract:**  
This project aims to uncover hidden patterns within the film industry by exploring actor personas and genre evolution. Leveraging advanced techniques such as network analysis, machine learning, and natural language processing, the study analyzes intricate networks shaping actor careers, identifies genre archetypes and evolution trends, and pinpoints features impacting box office revenue. The motivation is to gain a deeper understanding of how actors navigate roles across collaborative networks, the impact of network positions on career longevity, and shifts in genre popularity over time. Additionally, the project seeks to determine the influence of winning or being nominated for an Oscar on a movie's financial performance and the role of regional and linguistic differences in shaping genre preferences. This comprehensive analysis will illuminate the cinematic pathways that shape the evolution of the film industry.

**Data Analysis Questions:** 
- Which actors navigate their roles within collaborative networks across different genres?
- How does an actor's network position impact their exposure to diverse genres, career longevity, and recognition?
- How have the top 10 genre popularity trends shifted over time, and how do these trends relate to historical and cultural milestones? Which genre has the best trend?
- How does the best trend genre(Drama) popularity trends shift over time?
- Can we use clustering and natural language processing to uncover genre archetypes and their sub-genres? (Only the top 10 genres considered)
- What movie metadata features are the strongest predictors of box office revenue?  
- To what extent does winning or being nominated for an Oscar affect the subsequent box office revenue of a movie?
  
**Additional Dataset used**: Oscar Dataset(used for Q7 only)

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

### 2. Data Analysis Questions
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
- **Approach**: Using time series data to identify trends in genre popularity over decades.The approach involves extracting the year from movie release dates, filtering the dataset to the top 10 genres, and then grouping by year and genre to analyze trends. This data is visualized in a line graph to highlight changes in genre popularity over time.
- **Output**:
 ![image](https://github.com/Vaibhavchopra1/DM-Project/assets/70208602/c5aee902-edce-4e77-b733-dadf42c37fe6)
- **Result**:From the visual analysis, it is evident that the drama genre exhibits the most robust and consistent growth trend among the top genres over the observed period. This upward trajectory is particularly pronounced from the mid-1990s onwards, peaking around the early 2000s. The popularity of the drama genre can be attributed to its versatility and ability to resonate with universal human experiences, making it adaptable to various cultural contexts and historical moments. The significant rise in the number of films across most genres in the late 1990s correlates with technological advancements in digital filmmaking and distribution, which democratized film production and expanded global reach. This era also coincides with significant cultural shifts that influenced film content, reflecting a broader diversity of stories and themes in cinema. Overall, the drama genre stands out for its enduring appeal and dynamic adaptation to changing societal trends, securing its place as the genre with the best trend in this analysis.

**Question 4**: How does the best trend genre(Drama) popularity trends shift over time?
- **Approach**: Using time series data to identify the best trends(Drama) in genre popularity over decades after that performing seasonal decomposition to analyze its trend, seasonality, and residuals.The approach involves extracting the yearly trend of drama genre popularity using time series decomposition. This technique decomposes the time series data into three components: trend, seasonality, and residuals, providing a detailed analysis of the underlying patterns.
- **Output**:
  
![image](https://github.com/Vaibhavchopra1/DM-Project/assets/70208602/11e937a3-2d36-4143-9edc-5ef7031a6814)
- **Result**:The time series decomposition of the drama genre popularity from 1930 to 2010 shows a clear and consistent trend of increasing popularity, particularly from the 1980s onwards, with a notable spike in the late 1990s and 2000s. The trend component reflects a sustained growth in the genre's appeal, culminating in significant peaks, which likely correlates with periods of increased production and global audience interest. The seasonal component is minimal, indicating that the popularity of the drama genre does not fluctuate widely across different times of the year. Lastly, the residuals are quite stable and low, suggesting that the model fits well and most variations in drama genre popularity are well explained by the trend component, without much unexplained noise.

**Question 5**: Can we use clustering and natural language processing to uncover genre archetypes and their sub-genres? (Only the top 10 genres considered)
- **Approach**:Applying clustering techniques to plot summaries to discover underlying genre archetypes and thematic elements common within genres. Using advanced NLP techniques to parse complex narrative structures and identify emerging sub-genres within traditional genres.
- **Output**:
![image](https://github.com/Vaibhavchopra1/DM-Project/assets/70208602/1ff23a91-397f-43c0-81a6-67756652e80a)
- **Result**:The heatmap visualization from clustering and TF-IDF vectorization of movie summaries shows clear distinctions and patterns in how different genres are grouped into clusters. Notably, genres such as "Romantic comedy, Romance Film, Comedy" and "Drama" form distinct clusters, indicating specific narrative structures or themes that are prevalent within these genres. For instance, the "Romantic comedy, Romance Film, Comedy" genre shows a high concentration in Cluster 5, suggesting a unique archetype associated with romantic and comedic elements.

The results confirm that clustering and NLP can effectively uncover genre archetypes and their sub-genres. Each cluster represents a grouping of movies that share similar narrative elements, highlighting the utility of this method in exploring and understanding the underlying structures within film genres. This technique allows us to visualize and quantify the relationships between genres and their narrative compositions, providing a valuable tool for industry analysis and academic study in film genre classification.

  **Question 6**: What movie metadata features are the strongest predictors of box office revenue?
- **Approach**: The approach involves encoding movie metadata features (movie runtime, genres, and countries) using one-hot encoding, followed by training an XGBoost regressor(Random Forest Regressor) to predict box office revenue. The importance of each feature is then aggregated and visualized to assess their predictive power.
- **Output**:
  
 ![image](https://github.com/Vaibhavchopra1/DM-Project/assets/70208602/3bd49faa-e4a2-4bfa-8c79-5b66063eee33)

- **Result**:The bar chart clearly demonstrates that "Movie genres" is the most influential predictor of box office revenue, significantly outweighing the other features like "Movie runtime" and "Movie countries." This suggests that the genre of a movie plays a crucial role in its financial success, likely because genre significantly influences audience appeal and marketing strategies. "Movie runtime" and "Movie countries" have much lower aggregate importance, indicating they have less impact on revenue prediction. This insight could be valuable for producers and marketers in prioritizing elements that might attract larger audiences and generate higher earnings.

**Question 7**: To what extent does winning or being nominated for an Oscar affect the subsequent box office revenue of a movie?
- **Approach**: The approach involves first loading the Oscar and CMU movie datasets, filtering the Oscar data to identify relevant winners. A ColumnTransformer is used to preprocess both numerical and categorical features. After training the model on the training set to predict box office revenue, the predictions on the test set are evaluated with Mean Squared Error (MSE) and R-squared metrics to measure the model's accuracy.
- **Output**:
Mean Squared Error: 5662417742259266.00
R-squared: 0.77
- **Result**:Winning or being nominated for an Oscar has a significant impact on a movie's subsequent box office revenue. This conclusion is based on a regression model that explains 77% of the variability in box office revenue, as reflected by the R-squared value. By incorporating features like genre, runtime, and whether a movie won an Oscar, the model demonstrates that winning or even just being nominated contributes positively to a film's financial success. Although the predictions have room for improvement due to a relatively high mean squared error, the model's strong performance indicates that winning an Oscar generally leads to a substantial boost in revenue, highlighting the considerable value of such recognition in the film industry.

