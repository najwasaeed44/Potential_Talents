<br>
<hr style="height:4px;border-width:10;color:blue;background-color:black">

<img src="img/logo.png" alt="Smiley face" width="100" height="100" align="left">

# Potential Talents
<hr style="height:4px;border-width:10;color:blue;background-color:black"><br><br><br>


<img src="https://images.genial.ly/59e059d30b9c21060cb4c2ec/5bbf17763292ef649e9b810f/175cbb1e-df65-405a-9cd0-cf177e1a2f00.gif?genial&1633910400074" alt="Smiley face" width="60" height="60" align="left">

## Background:
<hr style="height:1.5px;border-width:10;color:blue;background-color:black">

As a talent sourcing and management company, we are interested in finding talented individuals for sourcing these candidates to technology companies. Finding talented candidates is not easy, for several reasons. The first reason is one needs to understand what the role is very well to fill in that spot, this requires understanding the client’s needs and what they are looking for in a potential candidate. The second reason is one needs to understand what makes a candidate shine for the role we are in search for. Third, where to find talented individuals is another challenge.

The nature of our job requires a lot of human labor and is full of manual operations. Towards automating this process we want to build a better approach that could save us time and finally help us spot potential candidates that could fit the roles we are in search for. Moreover, going beyond that for a specific role we want to fill in we are interested in developing a machine learning powered pipeline that could spot talented individuals, and rank them based on their fitness.

We are right now semi-automatically sourcing a few candidates, therefore the sourcing part is not a concern at this time but we expect to first determine best matching candidates based on how fit these candidates are for a given role. We generally make these searches based on some keywords such as “full-stack software engineer”, “engineering manager” or “aspiring human resources” based on the role we are trying to fill in. These keywords might change, and you can expect that specific keywords will be provided to you.

Assuming that we were able to list and rank fitting candidates, we then employ a review procedure, as each candidate needs to be reviewed and then determined how good a fit they are through manual inspection. This procedure is done manually and at the end of this manual review, we might choose not the first fitting candidate in the list but maybe the 7th candidate in the list. If that happens, we are interested in being able to re-rank the previous list based on this information. This supervisory signal is going to be supplied by starring the 7th candidate in the list. Starring one candidate actually sets this candidate as an ideal candidate for the given role. Then, we expect the list to be re-ranked each time a candidate is starred.


<img src="https://media.baamboozle.com/uploads/images/67969/1595412283_471863" alt="Smiley face" width="60" height="60" align="left">

## Data Description:
<hr style="height:1.5px;border-width:10;color:blue;background-color:black">

The data comes from our sourcing efforts. We removed any field that could directly reveal personal details and gave a unique identifier for each candidate.

<img src="https://c.tenor.com/1_5w5vXEH5gAAAAj/mandalorian-star-wars.gif" alt="Smiley face" width="60" height="60" align="left">

## Attributes:
<hr style="height:1.5px;border-width:10;color:blue;background-color:black">

| Column        | Description                                           | Type   | 
|---------------|-------------------------------------------------------| ------ | 
| `id `         | Unique identifier for candidate .                     | `numeric` | 
| `job_title  ` | Job title for candidate.                              | `text` | 
| `location  `  | Geographical location for candidate.                  | `text` | 
| `connections ` | Number of connections candidate has. | `text` | 
| `fit`         | How fit the candidate is for the role?                | `numeric, probability between 0-1` | 


<img src="https://media0.giphy.com/media/LmqdA28jZ7bitDeDWr/200.webp" alt="Smiley face" width="60" height="60" align="left">

## Project Overview:
<hr style="height:1.5px;border-width:10;color:blue;background-color:black">

I used 5 different strategies to find the similarities between the targeted sentences and each job title as follows:

1. **`TF-IDF`**.

2. **`GloVe `**.

3. **`Word2Vec`** ==> `Google News` model.

4. **`FastText`**.

5. **`BERT`**.

**BERT** model was one of the best model to find the similarity between our data and the targeted phrase **(aspiring human resources)** as we can see the next images.



<h1 align="center">
  <img src="img/BERT model 1.png" width="500px"/><br/>
</h1>

<h1 align="center">
  <img src="img/BERT model 2.png" width="500px"/><br/>
</h1>


As for the Ranking model, I run the RankNet model on the data and our best loos score is 48%. I believe the data size play a major role to get this result, even TF-IDF gives us a more reliable result in my opinion than the RankNet model as in the next image.

<h1 align="center">
  <img src="img/RankNet model.png" width="500px"/><br/>
</h1>



**S3rXQORkdPBm0ap9**
