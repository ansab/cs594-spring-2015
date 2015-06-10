# Water Consumption & Precipitation

****Data Science Question:****	How rainfall affects water consumption in Southern California metropolitan cities.
****Conclusion:****	There is no corelation between water consumption and precipitation.

**Problem:** Scrap a website that uses form processing

**Solution:** Use selenium.  See example below (Selenium-Python documentation: https://selenium-python.readthedocs.org/)
--
Access a web page using selenium browser driver
--

from selenium import webdriver

browserDriver = webdriver.Firefox()
browserDriver.get("https://www.web-url.com")

"""
Wait for a "select" tag to load and then access it using its ID. Select a specific value of that tag
"""
from selenium import webdriver
from selenium.webdriver.support.ui import Select
from selenium.webdriver.support import expected_conditions as EC

browserDriver = webdriver.Firefox()
browserDriver.get("https://www.web-url.com")
waitTime = 10
wait = WebDriverWait(browserDriver, waitTime)
selectTagAsWebElement = wait.until(EC.presence_of_element_located((By.ID,"TagID")))
/* selectTag is of type: "web element". Need to parsed as html "select" tag */
selectTag = Select(selectTagAsWebElement)
selectTag.select_by_value("Value to be selected")

"""
Wait for a link to appear then click it
"""
from selenium import webdriver
from selenium.webdriver.common.keys import Keys

browserDriver = webdriver.Firefox()
browserDriver.get("https://www.web-url.com")
waitTime = 10
wait = WebDriverWait(browserDriver, waitTime)
link = wait.until(EC.element_to_be_clickable((By.ID,"linkID")))
link.send_keys(Keys.RETURN)

"""
Wait for a text field to appear then populate it
"""
from selenium import webdriver
from selenium.webdriver.common.keys import Keys

browserDriver = webdriver.Firefox()
browserDriver.get("https://www.web-url.com")
waitTime = 10
wait = WebDriverWait(browserDriver, waitTime)
textField = wait.until(EC.element_to_be_clickable((By.ID,"linkID")))
textField.send_keys("text to be filled")

"""
Access all open windows including pop-ups
"""
browserDriver.window_handles

"""
Switch between windows and frames
"""
browserDriver.switch_to.window(windowToBeSelected)
browserDriver.switch_to.frame(frameToBeSelected)

"""
Close the browser
"""
browserDriver.close()

----------------------------------------------------------------------------------------------------

**Problem:** Clustering Data

**Solution:** Use Sci-kit(K-means) and SciPy(NumPy and Matplotlib).  See example below
(Example Source: http://pythonprogramming.net/flat-clustering-machine-learning-python-scikit-learn/)

import numpy as np
import matplotlib.pyplot as plt
from sklearn.cluster import KMeans

x = [1, 5, 1.5, 8, 1, 9]
y = [2, 8, 1.8, 8, 0.6, 11]

plt.scatter(x,y)
plt.show()

X = np.array([[1, 2],
              [5, 8],
              [1.5, 1.8],
              [8, 8],
              [1, 0.6],
              [9, 11]])
        
kmeans = KMeans(n_clusters=2)
kmeans.fit(X)

centroids = kmeans.cluster_centers_
labels = kmeans.labels_

print(centroids)
print(labels)

colors = ["g.","r.","c.","y."]
for i in range(len(X)):
    print("coordinate:",X[i], "label:", labels[i])
    plt.plot(X[i][0], X[i][1], colors[labels[i]], markersize = 10)

plt.scatter(centroids[:, 0],centroids[:, 1], marker = "x", s=150, linewidths = 5, zorder = 10)
plt.show()

----------------------------------------------------------------------------------------------------

**Problem:** Compute corelation

**Solution:** Use NumPy.  See example below

import numpy as np

dataX = [1, 2, 3]
dataY = [4, 5, 6]
np.corrcoef(dataX, dataY)
