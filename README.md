# Customer-Churn-Analysis
In this repository, I have taken a dataset of a telecom company and performed the end to end Exploratory Data Analysis, and identified the characteristics of the customers that are more likely to churn, and I have used them wisely to create a model by applying different models, and lately, have deployed the model.

[For EDA, please refer to: Churn Analysis - EDA.ipynb](https://github.com/ydvsheetal/Customer-Churn-Analysis/blob/main/Churn%20Analysis%20-%20EDA.ipynb)

[For Model Building, please refer to: Churn Analysis - Model Building.ipynb](https://github.com/ydvsheetal/Customer-Churn-Analysis/blob/main/Churn%20Analysis%20-%20Model%20Building.ipynb)

[For Model Deployment, please refer to app.py](https://github.com/ydvsheetal/Customer-Churn-Analysis/blob/main/app.py)

Creating the flask API

```
app = Flask("__name__")
```

The loadPage method calls our home.html.
```
@app.route("/")
def loadPage():
	return render_template('home.html', query="")
```

The predict method is our POST method, which is basically called when we pass all the inputs from our front end and click SUBMIT.
```
@app.route("/", methods=['POST'])
def predict():
```
  
The run() method of Flask class runs the application on the local development server.
```
app.run()
```


Yay, our model is ready, let’s test our bot.
The above given Python script is executed from Python shell.

Go to Anaconda Prompt, and run the below query.
```
python app.py
```


Below message in Python shell is seen, which indicates that our App is now hosted at http://127.0.0.1:5000/ or localhost:5000
```
* Running on http://127.0.0.1:5000/ (Press CTRL+C to quit)
```


HERE'S HOW OUR FRONTEND LOOKS LIKE:

