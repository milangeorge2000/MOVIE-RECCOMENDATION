# Movie Recommendation System using LLMs

The Movie Recommendation System is designed to provide users with similar movie recommendations. By entering a movie title, users can receive a top 10 list of movies that are similar to their input. Additionally, the system offers a summary of each recommended movie generated by an LLM (Phi-3). 

## Overview
- __Movie Recommendations__: Input a movie title to receive a top 10 list of similar movies that are ranked on weighted scores and popularity of the movie. 
- __Movie Summaries__: Generate summaries for each recommended movie by leveraging phi-3, providing a brief overview of the movie's plot.

## Workflow
- __Data__: The data was taken from [Movies Daily Update Dataset](https://www.kaggle.com/datasets/akshaypawar7/millions-of-movies) available on Kaggle. Extra directors name were scrapped from wikipedia and [The Movie DataBase](https://www.themoviedb.org/) website. The data is ingested and recommendation are provided based on the genre, keywords, cast and director name. 
- __Recommendations__: Previously I have used Count Vectorization method to get embeddings, which essentially represents text as a vector of word counts. To improve this I have generated embeddings using a [Sentence Transformer](https://huggingface.co/sentence-transformers/all-MiniLM-L6-v2) which captures the context, leading to better semantic understanding and improved performance.
- __Weaviate__: Used for storage and performing similarity search.
- __LangChain__: This framework was used to integrate weaviate with workflow and also used to create a pipeline to streamline the process of generateing summaries.
- __Fast API__: Used to handle movie recommendations and summary generation.
- __Next.js__: Used to build the user interface for interacting with the recommendation system.

## Technologies Used
### __Frontend__
- __Next.js__: A React framework that enables server-side rendering and static site generation.
- __React__: A JavaScript library for building user interfaces.
- __Axios__: A promise-based HTTP client for making API requests.
- __Tailwind CSS__: A utility-first CSS framework for styling the application.
  
### __Backend__
- __FastAPI__: A modern, fast (high-performance), web framework for building APIs with Python.
- __Weaviate__: A cloud-native, modular, real-time vector search engine built to scale your machine learning models.
- __HuggingFace Transformers__: State-of-the-art Natural Language Processing for text generation and embeddings.
- __LangChain__: An open-source framework that helps software developers create applications using large language models (LLMs) to perform natural language processing (NLP) tasks

## Usage
1. Open the application in your browser at http://localhost:3000.
2. Enter a movie title in the search bar.
3. Select a movie from the auto-complete dropdown list.
4. Click "Get Recommendations" to view a list of similar movies.
5. Click "Summarize" on any recommended movie to generate and view a summary.

## API Endpoints
- ```/api/movies```
  - Method: ```GET```
  - Description: Retrieves a list of all available movies for the auto-complete feature.
- ```/recommendations```
  - Method: ```POST```
  - Description: Retrieves a list of movies similar to the provided title.
- ```/summary```
  - Method: ```POST```
  - Description: Generates a summary for the specified movie.

## Screenshots
- __Movie Recommendations__:
  
![image](https://github.com/VivekaAryan/Movie_recommendation_system/assets/52493029/18164b83-b846-4186-be04-16630431a2dc)

- __Movie Summary__:
  
![image](https://github.com/VivekaAryan/Movie_recommendation_system/assets/52493029/55377ee5-1925-421e-a4bf-c6034f01f5e2)

## Demo

https://github.com/VivekaAryan/Movie_recommendation_system/assets/52493029/e58af96e-c79b-4491-8da1-1d2bc4521156

## License

This project is licensed under the MIT License.