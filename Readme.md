# Car Price Prediction Application
The data science project is aimed at building a machine learning model that can predict the price of cars based on various attributes such as make, model, year, and mileage. The model was trained on a large dataset obtained from various sources, after performing data analysis, data cleaning, and preprocessing. The data was then processed using various techniques such as feature engineering to improve the accuracy of the model. After experimenting with multiple models, the most accurate model was chosen as the final model.

The frontend for the project was designed using Streamlit, which allows users to input various parameters and receive the predicted price on the same page. The model was trained and tested on a large dataset, and the final model achieved a high level of accuracy. The project demonstrates the power of machine learning in predicting car prices and can be used by individuals or car dealerships for pricing their cars.

# Setup Project
1. Create Repository on Github and clone it to locally using this command `git clone repo_name`
2. Files Structure
   1. main.py
   2. rf_model.pkl
   3. car.png
   4. requirements.txt
   5. .gitignore
   6. Analysis/
      - Jupyter notebook and datasets on which data analysis has been done and model trained
3. freeze packages `pip freeze -r requirements.txt`
         
# Usage
- This code creates a web application using the Streamlit library
- The application allows a user to input details about a car and predict its price using a pre-trained Random Forest model
- The user can input:
  - Present price of the car
  - Number of kilometers driven
  - Fuel type
  - Transmission type
  - Car's build year
  - Seller type (Dealer or Individual)
- When the user clicks the "Predict Price!!" button, the application uses the input data to make a prediction and displays the result to the user.
- The application also has various links of my profiles like LinkedIn, Kaggle, Github, Tableau.

# Deployment
## Deploying on Heroku
   - Requirements for Heroku: below additional files required for Streamlit app deploying on Heroku 
     - Procfile
       ```
       web: sh setup.sh && streamlit run main.py
       ```
     - setup.sh
      ```
      mkdir -p ~/.streamlit/
      echo "\
      [server]\n\
      port = $PORT\n\
      enableCORS = false\n\
      headless = true\n\
      \n\
      " > ~/.streamlit/config.toml
      ```
     - requirements.txt 
       - add `gunicorn` package in requirements.txt along with packages used in this application 
         ```
         gunicorn
         ```
     
     - Total files required for Heroku deployment
       1. main.py
       2. rf_model.pkl
       3. car.png
       4. requirements.txt
       5. Procfile
       6. setup.sh
       7. .gitignore

### steps to deploy a Python Streamlit app on Heroku from Local file:
 1. Login to [Heroku](https://dashboard.heroku.com/) and create new project 'carprice'
 2. Install the Heroku CLI
 3. Open the cmd or Pycharm/VS Code terminal and run this command `heroku login` and then verify account
 4. Run line by line below commands 
    ```
    heroku git:clone -a carprice
    cd carprice
    git add .
    git commit -am "files added"
    git push heroku master
    ```
 5. Once deployment gets completed, access link will be generated or run `heroku open` to access it in browser

### steps to deploy a Python Streamlit app on Heroku from Github Repo:
1. First push application will all requirements to github
2. Open Heroku, create new project > go to deploy section > select github option and verify connection with github account
3. Give the repo name and choose branch of code then select `Enable automatic Deploys` 
4. Click on Deploy button to deploy
    