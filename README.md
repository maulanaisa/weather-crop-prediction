# weather-crop-prediction
Machine learning models using Tensorflow to predict weather and crop production in certain area (Indonesia).
Created using Google Colab Platform to run training and export model into .h5 format.

Weather data from 2 cities (Bandung and Bogor) collected to predict weather in respective city. Then, weather prediction works as input to crop predicition model to predict crop (rice and corn) production in that city. So in total there are 2 models involved.

Weather data --> |forecast model| --> weather prediction --> |crop prediction model| --> crop production

## Note
For this project, datasets is stored in Google Drive folder (make it easier to manage on google colab). You can store it on your local computer if you choose to run it using Jupyter. Don't forget to change directory's line in the notebook.

## Forecast.ipynb
Machine Learning model training written in Python 2.7.0. Model use time series forecast to predict weather for the next time period. For this project, previous records used to predict weather. There are 9 weather parametes considered. 

- Dataset : Weather data from BMKG (Badan Meteorologi, Klimatologi, dan Geofisika) along with 9 parameters, from 2011-2020. Each year consists of 3 months data (january, may and september). Model take average of each respective month so there will be 30 records in total.

- Prediction : Model can predict next weather condition on all 9 parameters. Time period between each record is 4 month (given january, may and september record). So for example the last record from dataset is september 2020, then model can be used to predict weather data on january 2021.

- For this project, model is expected to predict next 3 weather period.

## crop_predict.ipynb
Machine Learning model training written in Python 2.7.0. Model used to predict crop production. There are 2 kinds of crop, rice and corn. Crop production dataset from 4 different areas together with it's 9 parameters weather data collected to train model. 

- Dataset : Weather data from BMKG (Badan Meteorologi, Klimatologi, dan Geofisika) along with 9 parameters, data taken may vary subject to crop production data availability. Crop production data in certain area then matched together with it's respective weather data for that area and act as output and input for model. Rice and corn production assumed to be consistent under similar weather dispite grow in different areas (based on dataset taken).

- Prediction : Model can predict next crop production for the next period. Every month weather prediction from forecast model (in this case january, may and september) which acts as input for crop model, will be paired to crop prediction output for that month + next 3 month. So for example,may 2021 weather prediction will be used as input to crop model to predict crop production on january through april.

- For this project, based on forecast input, model is expected to predict next 3 crop prodution period/cycle.

## Folders
- Data Cuaca : Dataset for forecast model
- Dataset crop : crop production dataset for crop predict model
- data cuaca untuk crop : weather dataset for crop predict model
