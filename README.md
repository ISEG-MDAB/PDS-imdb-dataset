# Programming For Data Science 

## Project - IMDb Data Set Analysis - README

### Group 1:

    - André Viana - l54543 - andreviana@aln.iseg.ulisboa.pt
    - Gonçalo Duarte - l48505 - goncaloduarte@aln.iseg.ulisboa.pt
    - José Cabral - l54997 - l54997@aln.iseg.ulisboa.pt
<br>

Masters Data Analytics for Business - ISEG - University of Lisbon

May 2021

### Summary

Movies are a big part of the entertainment world. Through this project, we aim at analyzing movie data, understanding its evolution over the years regarding different features, develop a model to predict ratings and develop our skills in computer vision.

### Data Description

To develop this project, we worked with <b>5 IMDb data sets </b>, regarding movies from 2010 to 2021:

   - <b><i>title_basics</i></b>
       
     Data set containing a row per movie/series, movie/series code as index and columns:
        - <i>titleType</i> : type of title (ex: for movies, 'titleType': short; for episodes of tv shows, 'titleType': tvEpisode)
        - <i>primaryTitle</i> : movie title;
        - <i>originalTitle</i> : original movie title;
        - <i>isAdult</i> : 0 if movie is not Adult; 1 if it is;
        - <i>startYear</i> : release year;
        - <i>endYear</i> : year in which the series stopped being streamed. '\N' for all movies; 
        - <i>runtimeMinutes</i> : movie duration, in minutes;
        - <i>genres</i> : which genres are associated with the movie (does not have to have only one genre, can store multiple separated by commas (ex: Action,Drama)

    Note that this data set also includes data regarding series, not only movies, but only movies' data were considered for this project.
    
 link for data set download: https://datasets.imdbws.com/title.basics.tsv.gz


   - <b><i>title_ratings</i></b>

     Data set regarding movies' ratings. For each movie, stores by column:
        - <i>averageRating</i> : stores the average rating attributed to the movie (on a scale from 1 to 10);
        - <i>numVotes</i> : number of votes on the corresponding movie;   

 link for data set download: https://datasets.imdbws.com/title.ratings.tsv.gz
 
 <br>
        
   - <b><i>title_crew</i></b>
   
     Data set with crew information (directors and writers) per movie. Each individual is given a code, so there are no names on this data set. Columns:
        - <i>directors</i> : codes of the directors of the movie;
        - <i>numVotes</i> : codes of the writers of the movie;  
     
     On both columns, each cell can store more than one code, doing so separating codes by commas. <i>(ex: code1,code2)</i>
     
 link for data set download: https://datasets.imdbws.com/title.crew.tsv.gz
 
 <br>
 
   - <b><i>title_principals</i></b>
   
     Data set storing information regarding all professionals who took part on the movie
    
     Columns:
        - <i>tconst</i> : movie code;
        - <i>ordering</i> : works as an individual index for each movie. Integers starting at 1, incrementing 1 by each row while the movie code does not change.When the entire movie crew is characterized, 'tconst' column receives a new code and 'ordering' starts from 1 again;
        - <i>nconst</i> : crew member code;
        - <i>category</i> : stores the in which category the person works on this particular movie;
        - <i>job</i> : stores the actual rolle of the person on the movie; (ex: 'category': cinematographer, 'job': director of photography);
        - <i>characters</i> : For actors/actresses, stores the character(s) played on the movie. For all other crew members, '\N'. 

 link for data set download: https://datasets.imdbws.com/title.principals.tsv.gz
 
 <br>
     
   - <b><i>name_basics</i></b>
   
     Data set storing information for each professional related to movies. Has as columns:
        - <i>primaryName</i> : person's name;
        - <i>birthYear</i> : Year in which he/she was born;
        - <i>deathYear</i> : Year in which he/she died. If the corresponding professional is alive, stores '\N'
        - <i>primaryProfession</i> : profession(s) related to movies;
        - <i>knownForTitles</i> : Movie codes in which he/she worked on. Can store multiple codes, separated by commas (<i>ex: code1,code2,code3</i>).
        
 link for data set download: https://datasets.imdbws.com/name.basics.tsv.gz
     
## Project Description


On the folder, you will find <b>7 documents: </b> 

  - <b><i>ProjectStatement.pdf</i></b> : Professor's statement on the requisites of the project;
  

  - <b><i>README.md</i></b> : this document describing all data sets used and what was developed in the project;
  
  
  - <b><i>data_filtering.ipynb</i></b> : a jupyter notebook to prepare and filter the data for further analysis. You can find all the code and process description on the notebook.


  - <b><i>movie_ratings_visualization.ipynb</i></b> : a jupyter notebook to visualize and describe the data.
  
      Five different charts are presented:
      <br>
      - Total number of movies produced by year:
              A scatter plot with the evolution of the total number of movies produced on each year.
              <br>
      - Number of movies produced by year (Genre comparison):
              An interactive scatter plot that allows the user to choose two genres and analyze the evolution of     the number of movies produced by year, for the two corresponding genres.
              <br>
      - Average rating per movie genre, per year:
              An interactive bar chart in which the user selects the year, and visualizes the average rating of the movies per genre, for that particular year.
              <br>
      - Movie rating evolution per actor/actress - Average Rating:
              A combination of a bar chart and a scatter plot to analyze the average rating of the movies in which a particular actor/actress worked on. By choosing an actor/actress, the user will se a bar chart with the overall average rating of the movies for him/her and a scatter plot with the evolution of the movie ratings through the years.
              <br>
      - Versatility indicator:
              The last visualization is an interactive indicator to analyze the versatility of an actor/actress. To do so, an indicator of versatility was developed (further details on the corresponding notebook).
              <br>
  - <b><i>Rating_prediction.ipynb</i></b> : a jupyter notebook to develop prediction of the ratings based on movie features.
  
  To predict the rating of a movie, the following models were tested:
          - Linear Regression model;
          - Ridge model (alpha = 0.5);
          - Lasso Model (alpha = 0.5);
          - Bayesian Ridge;
          - Neural Network;
          - Keras model.
  
  All the information and details regarding the development of the models is available on the correspondent notebook.
  
  For further research on the models' properties, all documentation is available at: 
  
 - https://scikit-learn.org/stable/modules/generated/sklearn.linear_model.LinearRegression.html <i>(Linear Regression models)</i>
      
 - https://www.tensorflow.org/api_docs/python/tf/keras/Sequential <i>(Keras model)</i>
  
  <i>Disclaimer : </i> Due to the big volume of data on these data sets, the rating prediction models were developed using movie data for movies produced in 2020 and 2021.
  
  <br>
  
  - <b><i>Computer_Vision.ipynb</i></b> : on the final notebook of this project, you will find a short approach to computer vision applied to the IMDb data base. 
  
  On this stage of the project, we aimed at developing a process in two phases:
      <br>
      - 1st: reading the front cover of a movie and identifying the title through the image;
      <br>
      - 2nd: automaticlly searching on the IMDb data based by the movie name obtained at stage 1.
      
<br>

 - <b><i>Report.pdf</i></b> : You will also find a report of the project, where results are discussed and analysis made of the overall work.

<br>
<b><i>We hope you find this project as interesting as we did while developing it.</i></b>
