# Regression
to find relationship sunday vs daily circulation 
import pandas
from pandas import DataFrame
import matplotlib.pyplot as plt

from sklearn.linear_model import LinearRegression
data = pandas.read_csv('C:/Users/minimini/OneDrive/MSc.DS/RA/cia.csv')
data.describe()
X = DataFrame(data, columns=['daily'])
y = DataFrame(data, columns=['Sunday'])
plt.figure(figsize=(10,6))
plt.scatter(X, y, alpha=0.3)
plt.title('sunday circulation vs daily circulation')
plt.xlabel('Sunday')
plt.ylabel('daily')
plt.show()
regression = LinearRegression()
regression.fit(X, y)
regression.coef_    # theta_1
regression.intercept_
plt.figure(figsize=(10,6))
plt.scatter(X, y, alpha=0.3)
# Adding the regression line here:
plt.plot(X, regression.predict(X), color='red', linewidth=3)
plt.title('sunday circulation vs daily circulation')
plt.xlabel('sunday')
plt.ylabel('daily')
plt.show()
