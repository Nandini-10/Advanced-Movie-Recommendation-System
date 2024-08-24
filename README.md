# Advanced-Movie-Recommendation-System

This repository contains all the project files and necessary details about applications required to run the project on your local machine as well as host it as a Django Application on your Server/Domain.

| Title                                    | Description                                                                                                                                                                                                                             |
| ---------------------------------------- | -------------------------------------------------------------------------------------------------------------------|
| Demo                      | Access a live demo of the MRS hosted on a free cloud platform PaaS                                                                                           |
| Requirements           | A list of prerequisites and essential resources to get the project up and running on your local machine                                           |
| Model Training | Details on how the MRS was trained for both a demo and a larger movie dataset from Kaggle                                  | 
| Project Versatility    | Documentation on how to integrate any general recommendation model into this project and deploy it | 
| Troubleshooting Issues          | Guidance on resolving common problems encountered while running or deploying the project                                                             | 



____


## 2. Requirements :

To build this project without any errors/issues, the following requirements needs to be satisfied

1. Create a Virtual Environment using python>=3.8 (Tested on 3.9.16)

2. Install the dependencies from the requirements text file from the repository.

<hr>

## 3. Model Training :

### 3.1 Training & Inference

For complete guide to training your model and inference using the trained model, refer to "[Movie Recommendation System Python Notebook](https://github.com/inboxpraveen/movie-recommendation-system/blob/master/Movie_Recommendation_System_Complete_Guide.ipynb)".

#### 3.2 Django Web Application Integration

[Here is a detailed blog](https://medium.com/analytics-vidhya/movie-recommendation-system-python-flask-web-application-heroku-deployment-7e39492b640c) explaining about complete approach and directory structure essential to understand Django integration.

<hr>

## 4. Project Guide
#### 4.1 Running in Local
```shell
/path/to/env/bin/activate
```

Once done, go to project root directory and run the following command

```she
python manage.py runserver
```

It will take a moment and then show the following output on the terminal.

<img title="" src="./readme_images/runserver_demo.png" alt="">

You can now open your browser and hit the server IP `http://localhost:8000` provided to run the demo on your local system. 

By default, this project will run on Demo model. If you wish to change model, you can train and download the model of your choice using the python notebook to get better or faster recommendations. Once trained, you can integrate by modifying these 2 lines of code inside `recommender/views.py`

```python
Line 5 : movies_data = pd.read_parquet("static/<dataset_name>.parquet")
Line 73: model = pa.parquet.read_table('static/<model_name>.parquet').to_pandas()
```

Note that you have to place dataset and model into the `static` directory.


This code implements a movie recommendation system based on user input. The system provides a simple web interface built on HTML, CSS, and JavaScript libraries. 

Inputs: The user can search for movies by providing a partial or complete movie name. 

Outputs: The system provides movie recommendations based on user input. 

Dependencies: 

* `static/recommender/` -- contains the following CSS files: `cursor.css`, `page.css`, and `navbar.css`
* `static/logo.png` -- the logo of the application
* `static/production ID_4779866.mp4` -- a background video for the web page
* `@tabler/icons@latest/iconfont/tabler-icons.min.css`
* `normalize/5.0.0/normalize.min.css`
* `jquery-ui.css`
* `font-awesome.min.css`
* `bootstrap.min.css`
* `jquery.min.js`
* `jquery-ui.js`

Usage:

1. Open the HTML file in a web browser.
2. Type the name of a movie in the search bar, and the system will provide the movie recommendation. 

Note: Only the top 2.5K movies based on IMDB are present in this system's database.
