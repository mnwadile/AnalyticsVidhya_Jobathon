# AnalyticsVidhya_Jobathon
AnalyticsVidhya_Jobathon - Feb 22. Regression Problem
<br><br>
<b>Introduction</b>
<br><br>
On February 11th, 2022, Analytics Vidhya conducted a 3-day hackathon in data science. The top candidates had the chance to be selected by various participating companies across a multitude of roles, in the field of data science, analytics and business intelligence.
<br><br>
The objective of the hackathon was to develop a machine learning approach to predict the engagement between a user and a video. The training data already had an engagement score feature, which was a floating-point number between 0 and 5. This considerably simplified matters, as in recommender systems, calculating the engagement score is often more challenging than predicting them. The challenge, therefore, was to predict this score based on certain user related and video related features.
<br><br>
The list of features in the dataset is given below:
<br><br>
<table>
<thead>
<tr>
<th><strong>Variable</strong></th>
<th><strong>Description</strong></th>
</tr>
</thead>
<tbody>
<tr>
<td>row_id</td>
<td>Unique identifier of the row</td>
</tr>
<tr>
<td>user_id</td>
<td>Unique identifier of the user</td>
</tr>
<tr>
<td>category_id</td>
<td>Category of the video</td>
</tr>
<tr>
<td>video_id</td>
<td>Unique identifier of the video</td>
</tr>
<tr>
<td>age</td>
<td>Age of the user</td>
</tr>
<tr>
<td>gender</td>
<td>Gender of the user (Male and Female)</td>
</tr>
<tr>
<td>profession</td>
<td>Profession of the user (Student, Working Professional, Other)</td>
</tr>
<tr>
<td>followers</td>
<td>No. of users following a particular category</td>
</tr>
<tr>
<td>views</td>
<td>Total views of the videos present in the particular category</td>
</tr>
<tr>
<td>engagement_score</td>
<td>Engagement score of the video for a user</td>
</tr>
</tbody>
</table>
<br>
<br>
<b>Regression Models</b> : Since the engagement score was a continuous variable, one could use a regression model.
<br>
<b>Approach 1</b> - The features "user_id", "category_id" and "video_id" were discrete features. One hot encoding is not possible here. So I have dropped them and trained the model using remaining features.
I have created regression algorithms pipleine to train model. Catboost and LGBM algorithm are top 2 algorithm which gave highest r2 score among other algorithm. But this r2 score is not enough. 
<br><br>
<b>Approach 2</b> - I have created more features by combining Age bucket - Gender,  Gender - Profession, Age bucket - Profession variable. My model r2 score is slightly improved
<br><br>
<b>Approach 3</b> - I have created mean of engagement score by customer id, video id, and user id to create new feature. This feature increased my model accuracy.
<br><br>
<b>Final Model</b> - As mention in Approach 3 this feature gives me highest r2 score among my all submissions. So I have decided to go with this features and catboost model.
