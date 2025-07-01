 Weather-Analysis
 Weather Data Analysis Project 🌤️

This project provides a basic exploratory data analysis (EDA) of historical weather data using Python and pandas. It aims to uncover key insights such as unique weather conditions, average wind speeds, visibility trends, and conditions during specific weather events like snow or fog.

 📂 Dataset
The dataset used in this project is a CSV file:
`Weather Project dataset.csv`
It includes features such as:

 Temperature (°C)
 Dew Point Temp (°C)
 Rel Hum (%)
 Wind Speed (km/h)
 Visibility (km)
 Press (kPa)
 Weather Condition

> Note: File path attached to this Repository

 🛠️ Tools & Libraries
 Python 3.x
 pandas


 🔍 Key Explorations
The analysis covers:
•	Viewing dataset structure: `.head()`, `.shape`, `.columns`, `.dtypes`
•	Understanding data distributions with `.value_counts()` and `.unique()`
•	Detecting missing values using `.isnull()` and `.notnull()`
•	Statistical summaries: `.mean()`, `.median()`, `.mode()`, `.std()`, `.var()`
•	Conditional filtering: querying weather conditions (e.g., 'Clear', 'Snow', 'Fog')
•	Group-based analysis: `.groupby()` with `.min()`, `.max()`, `.sum()`
•	Multi-condition filtering using logical operators

 📈 Sample Insights
•	Days with `Clear` weather or specific wind speeds (e.g., 4 km/h)
•	Days with visibility exactly at 25 km
•	Records where wind speed > 24 km/h and visibility == 25 km
•	Group statistics by weather condition
•	Weather conditions involving 'Snow' using string matching
•	Days with visibility > 40 km or humidity > 50% during clear weather

CODE :
#!/usr/bin/env python
# coding: utf-8

# In[20]:


import pandas as pd


# In[21]:


data = pd.read_csv(r"C:\Users\oodan\Downloads\My Projects\Weather Project dataset.csv")


# # data

# In[22]:


data.head()


# In[23]:


data.shape


# In[24]:


data.index


# In[25]:


data.columns


# In[26]:


data.dtypes


# In[27]:


data['Weather'].unique()


# In[28]:


data.nunique()


# In[29]:


data.count()


# In[30]:


data['Weather'].value_counts()


# In[31]:


data.info


# In[32]:


data.info()


# In[33]:


data.head(2)


# In[34]:


data.nunique()


# In[35]:


data['Weather'].nunique()


# In[36]:


data['Weather'].unique()


# In[37]:


data['Weather'].unique


# In[38]:


data['Wind Speed_km/h'].nunique()


# In[39]:


data['Wind Speed_km/h'].unique()


# In[40]:


data.head(2)


# In[41]:


#data.head(2)
data[data.Weather == 'Clear']


# In[42]:


data.Weather.value_counts


# In[43]:


#data.head(2)
data.groupby('Weather').get_group('Clear')


# In[44]:


data.head(10)


# In[45]:


data[data['Wind Speed_km/h'] == 4]


# In[46]:


data.isnull()


# In[47]:


data.isnull().sum()


# In[48]:


data.notnull()


# In[49]:


data.notnull().sum()


# In[50]:


data.rename(columns = {'Weather' : 'Weather Condition'}, inplace = True)


# In[51]:


data.head()


# In[52]:


data.head()


# In[53]:


data.Visibility_km.mean()


# In[54]:


data.head()
data.Visibility_km.median()


# In[55]:


data.head()
data.Visibility_km.mode()


# In[56]:


data.head()


# In[57]:


data.Press_kPa.std()


# In[58]:


data['Rel Hum_%'].var()


# In[59]:


data['Weather Condition'].value_counts()


# In[60]:


data.groupby('Weather Condition').get_group('Snow')


# In[61]:


data[data['Weather Condition'] == 'Snow'].head(100)


# In[62]:


data[data['Weather Condition'].str.contains ('Snow')].tail(50)


# In[63]:


data[data['Weather Condition'].str.contains ('Snow')].head(50)


# In[64]:


data.head()


# In[65]:


data[data['Wind Speed_km/h'] >24]


# In[66]:


data[data['Visibility_km'] ==25]


# In[67]:


data[(data['Wind Speed_km/h'] >24) & (data['Visibility_km'] ==25)]


# In[68]:


data['Visibility_km'].mean()


# In[69]:


data.head(5)


# In[70]:


data.groupby('Weather Condition').min()


# In[71]:


data.groupby('Weather Condition').max()


# In[72]:


data[data['Weather Condition']== 'Fog']


# In[73]:


data.groupby('Weather Condition').sum()


# In[74]:


data[data['Weather Condition'] == 'Clear'] 


# In[75]:


data[data['Visibility_km']>40]


# In[ ]:


data.groupby('Weather Condition').min()


# In[77]:


data[(data['Weather Condition'] == 'Clear') & (data['Rel Hum_%'] > 50)|(data['Visibility_km'] > 40)]


# In[ ]:






