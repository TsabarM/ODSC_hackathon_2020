# ODSC_hackathon_2020

In this repository I present my solution for the ODSC 2020 hackathon https://odsc.com/hackathon/ 

The final solution notebook can be found [here](https://github.com/TsabarM/ODSC_hackathon_2020/blob/final_submission/ODSC_Hackathon_notebook%20.ipynb).   
The pairplot is available [here](https://github.com/TsabarM/ODSC_hackathon_2020/blob/master/pairplot.png).
The correlation heatmap is available [here](https://github.com/TsabarM/ODSC_hackathon_2020/blob/master/correlation%20heatmap.png).

In this challenge the competitors need propose a model that predicts the temperature of 4 components of an electric car motor. 
There is a high correlation between the temperatures of the 4 components. 
Therefore, at first I trained a fully connected network on only one temperature target variable. 
I took the predictions from my first model and used it as a feature to the other 3 components models.

In other words:   
first stage:   
y1=f(X)+error (best model = stator_yoke)   
y2=h(x)+error   
y3=g(x)+error   
y4=j(x)+error   

second stage:   
y2=h(x + f(x))+error   
y3=g(x + f(x))+error   
y4=j(x + f(x))+error   


The final RMSE results on the test set are:   
 
 RMSE_pm = 1.011369259   
 RMSE_stator_yoke = 0.192175924   
 RMSE_stator_tooth = 0.36982214   
 RMSE_stator_winding = 0.470236891
   
 adding up to 2.043604214 total RMSE

A video explaining my solution can be found here:   
youtube link
