### Jester Jokes Recommender System
-----------------------------------------------------------
----------------------------------------------------------


#### Abstract
----------------------------------------------------------

    In this exploratory project, we have studied, designed and implemented a joke recommendation system.
    We have used 73,421 users rated jokes dataset provided by Jester Research project under flagship of UC
    Berkeley Laboratory for Automation Science and Engineering to find correlations between users and jokes
    by learning from the previous viewing history of users and to provide recommendations for jokes which 
    users would prefer to see most.
    
    The structure of this project are as follows:
    -- data
        Contains raw and processed data in csv, html and sql format
    -- model
        Contains LDA model for grouping jokes
    -- 1. sql_insertion.ipynb
        Notebook is used to save all the raw data(jokes and ratings) into tables at sql database
    -- 2. Data pre-preprocessing.ipynb
        Notebook is used to normalize users rating data and save it back into sql db for later use
    -- 3. UUCF.ipynb
        Notebook talks about user-user collaborative filtering and one possible way of implementation 
    -- 4. Content Based.ipynb
        Notebook talks about topic modelling of 100 jokes to categorize it followed by content based
        recommendation system
    -- README.md
        .md file used to describe the purpose of this project
    -- requirement.txt
        This file describe the necessary packages we have used for this project. 
    
    

#### Introduction
------------------------------------------------------------------------------------------------

    The rapid development of mobile devices and the internet has led to a boom in content creation and made 
    possible for us to access different media resources freely. The number of jokes and other recreational
    data available exceeds the viewing capacity of a single individual. It is thus quite easy to feel
    overwhelmed while choosing from millions of jokes. Moreover, media service providers need an 
    efficient way to manage their content and help their customers to discover the content they like
    by giving quality recommendations. Thus, there is a strong need for a good recommendation system.
    
    Currently, there are many media streaming services, like Netflix, Amazon, etc. which are working
    on building high-precision commercial recommendation systems. Without personalised recommendations
    , these companies won’t be able to engross a user to an optimum level. Thus, there is a strong
    thriving market for good joke recommendation systems. A joke recommender system is a system which
    learns from considering several users' past viewing history and recommends them jokes which they
    would probably like to see in future. We have implemented two algorithms to try to build an effective
    recommender system.
    
    We firstly implemented a neighbourhood-based user user Collaborative Filtering method which was intuitive
    and based on like people rate alike. Secondly, we used Content Filtering method where we used topic
    modelling approach to create the topics of the 100 jokes!! 

#### Dataset
--------------------------------------------------------------------------------------------

    We have used 73,421 users rated jokes dataset provided by Jester Research project under the flagship of
    UC Berkeley Laboratory for Automation Science and Engineering. The data contains 2 files as jokes in html
    format and ratings in csv format.

#### Algorithm
------------------------------------------------------------------------------------------------------

a. [User-user Collaborative filtering](https://github.com/abbi163/Jester-Joke-Recommender-System/blob/0f0f31846d233ea41100f511c9dfd6727784a076/3.%20UUCF.ipynb)

    Collaborative Filtering techniques make recommendations for a user based on ratings and preferences data
    of many users. The main underlying idea is that if two users have both rated 2 items similarly, then the
    items that one user has liked that the other user has not yet tried can be recommended to him. We are
    recommended items based on the ratings and purchase data that online platforms collect from their total
    user base not only us.
    
    User-user collaborative filtering approach relies on the idea that users who have similar rating behaviours
    so far, share the same tastes and will likely exhibit similar rating behaviours going forward.The algorithm
    first computes the similarity between users by considering ratings both users have in common. 
    
    The similarity is computed by using the Pearson Correlation. The details about the implementation is given
    in UUCF.ipynb notebook


b. [Content based filtering](https://github.com/abbi163/Jester-Joke-Recommender-System/blob/master/4.%20Content%20Based%20.ipynb)
    
    Content based filtering system doesn't involve other user's likes or dislikes but one's own likes or
    dislikes.The algorithm will simply pick items with similar contents to recommed user based on the user's
    rating to other products. 
    
    In our notebook, Content Based.ipynb, we first cluster 100 jokes into 10 clusters using topic modelling 
    technique with LDA since joke metadata wasn't available so we have to create one. Once the joke group is
    determined, we will select an active user and recommend joke for him based on his highest rating. 
    
    
#### Conclusion
-----------------------------------------------------------------------------------------------------------

    In this project, we explored two techniques to make recommendations to the user which ranged from 
    collaborative filtering models that were both time and space consuming to content based filtering
    models which were efficient in time and space however however lacked variety and diversity of 
    recommendation when compared to content based filtering.
    
    
#### Scope of Future Work
-----------------------------------------------------------------------------------------------

    There are plenty of ways to expand on the work done in this project. Firstly, the user-based method
    can be expanded by trying out different method at each step. For example, while calculating similarity
    , we can try cosine similarity or z-score similarity. We can also adopt other technique for neighbours 
    selection. 
    
    Content based filtering can be made more robust if we have more jokes, or the metadata for jokes is 
    created that can give more accurate clustring of jokes. 
    
    In addition, we could try to develop hybrid methods that try to combine the advantages of both
    content-based methods and collaborative filtering into one recommendation system. 
    
    Other scopes are scaling these models to deploy on cloud and use big data techniques like Hadoop
    and Pyspark to handle the large joke rating data.


    
    

    
    
 