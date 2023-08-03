# Customer-Churn-Analysis
In this repository, I have taken a dataset of a telecom company and performed the end to end Exploratory Data Analysis, and identified the characteristics of the customers that are more likely to churn, and I have used them wisely to create a model by applying different models, and lately, have deployed the model.

[For EDA, please refer to: Churn Analysis - EDA.ipynb](https://github.com/ydvsheetal/Customer-Churn-Analysis/blob/main/Churn%20Analysis%20-%20EDA.ipynb)
Derived insights from EDA:
HIGH Churn seen in case of Month to month contracts, No online security, No Tech support, First year of subscription and Fibre Optics Internet
LOW Churn is seens in case of Long term contracts, Subscriptions without internet service and The customers engaged for 5+ years
Factors like Gender, Availability of PhoneService and # of multiple lines have alomost NO impact on Churn
Electronic check medium are the highest churners
Contract Type - Monthly customers are more likely to churn because of no contract terms, as they are free to go customers.
No Online security, No Tech Support category are high churners
Non senior Citizens are high churners

[For Model Building, please refer to: Churn Analysis - Model Building.ipynb](https://github.com/ydvsheetal/Customer-Churn-Analysis/blob/main/Churn%20Analysis%20-%20Model%20Building.ipynb)

Conclusion from modeling:
Firstly, I applied logistic regression but the accuracy it gives is 77-78% which is very low as the data is imbalanced(73:27 ratio).
Secondly, I tried the random forest classifier model but the accuracy in this case is nearly 80% which is again very low.
The main reason for getting this low accuracy is data imbalances.
In order, to overcome this problem I have used SMOTE(Smote+EEN) library to upsampling the data.
Then I again tried Logistic regression and the results far soo good that we get before. This time the accuracy is 93%.
Then I applied Random Forest Classifier and the accuracy in this case is highest(96%). Then I finalize this model as my final model and saves this model using pickle.
[For Model Deployment, please refer to app.py](https://github.com/ydvsheetal/Customer-Churn-Analysis/blob/main/app.py)
Imported the saved model.
Takes input from the user and makes my dataset the same as the dataset which I passed during training.
Created the flask API.

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
![Customer Retention](https://github.com/ydvsheetal/Customer-Churn-Analysis/blob/main/model.png)


Practical Usage:
Any company based on various parameters of customers which I used in my model can find out which are their loyal customers and which are churners. Different parameters have different impact on the churning of customers, so a company can find which parameters they can improve so that they don't give a chance to their customers to churn and stands in the market.
