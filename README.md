### DM Mini-Project 2

**Project Title:**  
Charting Unconventional Cinematic Pathways: Advanced Network Analysis of Actor Personas and Genre Evolution in the CMU Movie Corpus

**Abstract:**  
This project explores the CMU Movie Summary Corpus through advanced network analysis, machine learning, and natural language processing to uncover unconventional patterns in actor personas and genre evolution. It aims to unravel the intricate networks that shape actor careers, identify genre archetypes and evolution trends, and create machine learning models to predict box office revenue based on a combination of metadata and plot summaries. By leveraging graph theory, clustering, and time series analysis, this study will reveal the hidden cinematic pathways that underpin the evolution of the film industry.

**Data Analysis Questions:**  
1. **Actors' Career Networks:**  
   - Which actors navigate their roles within collaborative networks across different genres?  
   - How does an actor's network position impact their exposure to diverse genres, career longevity, and recognition?  

2. **Genre Evolution and Cultural Trends:**  
   - How have genre popularity trends shifted over time, and how do these trends relate to historical and cultural milestones?  
   - Can we use clustering and natural language processing to uncover genre archetypes and their sub-genres?  
   - What role do regional and linguistic differences play in shaping genre preferences?

3. **Predictive Box Office Models:**  
   - What metadata features are the strongest predictors of box office revenue?  
   - How accurately can machine learning models estimate box office revenue by combining metadata with plot summaries?  

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
**Note**: Refer the code in Jupyter Notebook

#### Actors' Career Network Analysis
**Objective**: Analyze the structure and implications of actor collaboration networks within the film industry.

##### Graph Network & Stastical Analysis
- **Network Construction**: Building a network graph where nodes represent actors and edges represent collaborations between them.
- **Centrality Measures**: Calculating metrics such as degree centrality and betweenness centrality to identify influential actors within the network.
- **Correlation Analysis**: Assessing relationships between an actor’s network centrality and their career longevity, genre diversity, and recognition.
  
##### Questions Analysis
- **Question 1**: Which actors navigate their roles within collaborative networks across different genres?
- **Analysis**: The degree centrality metric shows actors with the most frequent collaborations in their networks. By observing the genres associated with their collaborations, we can identify how these actors navigate their roles within different genres.
- **Output**:
     Top 10 actors by degree centrality:
  [('Samuel L. Jackson', 0.09638168427793788), ('Robert De Niro', 0.07845020813320525), ('John Goodman', 0.06724303554274735), ('Christopher Walken', 0.06468139609349983), ('Stanley Tucci', 0.06372078130003202), ('Liam Neeson', 0.0627601665065642), ('Morgan Freeman', 0.06243996157540826), ('Ben Stiller', 0.062119756644252316), ('Matt Damon', 0.06147934678194043), ('Tom Wilkinson', 0.05891770733269292)]
- **Result**:From this analysis, we can infer that actors with high degree centrality are likely navigating their roles within a wide array of genres. Their ability to connect with diverse actors suggests versatility and adaptability in their careers. For instance, Samuel L. Jackson appearing in genres ranging from action to drama indicates his broad appeal and ability to fit into various narrative contexts. This versatility not only enhances an actor’s visibility but may also contribute to career longevity and success.

- **Question 2**: How does an actor's network position impact their exposure to diverse genres, career longevity, and recognition?
- **Analysis**: This metric can be correlated with an actor's longevity and recognition in the industry. Actors with high exposure to multiple genres often demonstrate versatility and flexibility.
- **Output**:
     Top 10 actors with highest genre diversity:
  [('Samuel L. Jackson', 76), ('Robert De Niro', 63), ('John Goodman', 63), ('Christopher Walken', 58), ('Amitabh Bachchan', 55), ('Morgan Freeman', 52), ('Randy Quaid', 50), ('Danny DeVito', 49), ('Brian Cox', 48), ('Danny Trejo', 48)]
- **Result**: Actors with high centrality and genre diversity, such as Samuel L. Jackson and Robert De Niro, demonstrate that a strong network position can lead to broader opportunities in diverse film genres. This diversity can contribute to an actor’s recognition in the industry, making them more appealing to casting directors looking for versatile talent. Additionally, this versatility and recognition are likely contributors to their career longevity, allowing them to maintain relevance in the film industry over long periods.

##### Conclusion:
Both degree centrality and genre diversity are important indicators of an actor's ability to navigate and succeed in the film industry. The high correlation between an actor’s network position and their genre diversity not only highlights their adaptability and skill but also suggests potential strategies for aspiring actors aiming for long-term success and recognition in the industry.

### 3. Genre Evolution and Archetype Analysis

**Objective**: Explore how film genres have evolved over time and identify distinct genre archetypes.

#### Time Series Analysis
- **Trend Analysis**: Using time series data to identify trends in genre popularity over decades, correlating these trends with historical and cultural developments.

#### Natural Language Processing (NLP)
- **Clustering**: Applying clustering techniques to plot summaries to discover underlying genre archetypes and thematic elements common within genres.
- **Sub-genre Identification**: Using advanced NLP techniques to parse complex narrative structures and identify emerging sub-genres within traditional genres.

### 4. Predictive Box Office Model

**Objective**: Develop models that predict box office revenue based on movie metadata and narrative features.

#### Feature Engineering
- **Integration of Features**: Combining various metadata elements (e.g., actor influence, director popularity, budget) with extracted features from plot summaries to form a comprehensive feature set for modelling.

#### Model Training and Improvement
- **Machine Learning Models**: Training regression models and random forests to predict box office success based on the developed features.
- **Model Optimization**: Enhancing model accuracy by incorporating additional data such as production costs and marketing spend, and tuning model parameters based on performance metrics.

### Results and Discussion

The project will involve interpreting the results from each of these analyses to draw conclusions about actor networking effects, genre evolution, and the predictability of box office performance. Each analysis will help answer the posed research questions by providing insights into the dynamics of film production and reception, the strategic positioning of actors within the industry, and the financial success of films.

By implementing this methodology, the project aims to provide a holistic understanding of the complex interplay between actor networks, genre development, and market success in the film industry.
