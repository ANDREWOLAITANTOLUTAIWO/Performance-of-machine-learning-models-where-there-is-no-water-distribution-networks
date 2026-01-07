Introduction

Clean water consumption by the poor directly affects their wellbeing, productivity and ability to escape the trap of poverty. Nygren et al., (2016) discovered that return-trip travel time greater than 30 minutes in order to fetch clean water was significantly associated with moderate-to-severe diarrhoea in Kenya. While launching the 2023 UN Water Report, UNICEF in Nigeria declares that 78 million children suffer from poor water access, and are at risk of water-related crises (UNICEF, 2023). 

This is a reason the seventeen United Nations sustainable development goals (UN SDGs) shown in Figure 1.1 has water running through them. From poverty eradication in goal 1 to partnership for the goals in goal 17, water and the various opportunities it provides runs through the goals like lubricating oil, ensuring all the parts work together for smooth progress towards their achievements. UNESCO World Water Assessment Programme (WWAP, 2015) links poverty to lack of access to clean water, and access to clean water as part of the solution. 

One way of improving access to clean water is expanding water distribution network (WDN) to connect every household to water services. It is the most effective way of improving sanitation and reducing transmission of water borne diseases (Hutton, 2004). The problem of access to clean water among the urban poor in low-income countries persists partly because there is no WDN in poor urban areas, and therefore no empirical data about the volume of water consumed by poor people. This leads them to seek water from different sources, such as water vendors, borehole water kiosks and well (UNDP,2015). They pay heavily for drinking water, which is provided by private businesses through vending (Chukwu, 2015). Since there is no automatic way of gathering data about volume of water consumed, it is difficult to model and predict volume of water consumed in poor urban areas. Yet it is important to model volume of water consumed in a poor urban area before a decision to extend water distribution network (WDN) to the area. 

The aim of this study is to examine performance of machine learning models for predicting volume of water consumed by poor urban households where there is no WDN. Though there is WDN in rich areas nearby, yet the urban poor live in slums where there is no WDN, and so they pay heavily for drinking water, which is provided by private businesses through vending. Safe water consumption directly affects people’s wellbeing, productivity and ability to escape the trap of poverty. United Nations-Sustainable Development Goals (UN-SDG) recommends equal right to quality water for both the rich and the poor (WGF, 2012).  This study is necessary to provide solution to the problem of access to clean water within poor urban areas in low-income countries. Accurately predicting volume of water consumed is the first step towards extending WDN to poor urban areas, and solving the problem of lack of access to clean water. 

Methods

Datasets

Nyanya-Mararaba Dataset
This study made use of Nyanya-Mararaba dataset described in Taiwo et. al (2023). The dataset includes both primary and secondary sources of data. Primary sources of data include questionnaires administered to households in the study area, location of households and water points, collected with hand-held GPS. Secondary sources of data include: rainfall data downloaded from www.chrsdata.eng.uci.edu; digital elevation model downloaded from https://earthexplorer.usgs.gov/; Temperature data downloaded from www.weatherspark.com; and land use land cover (LULC) maps downloaded from https://maps.arcgis.com. Nyanya-Mararaba dataset; which consists of socioeconomic data, weather data, property data, historic data and geospatial data collected with questionnaires in Nyanya-Mararaba Town.

Data Pre-processing

Data pre-processing includes feature engineering processes, which include data cleaning, data scaling, categorical encoding and feature creation in Geographic Information System (GIS). 

Four new features were created: volume of water consumed in litre per day, shortest distance, height difference, and LULC type. It is necessary to create these features for the following reasons: One, volume of water consumed is better measured in litre per capita per day, which is deduced from volume of water consumed per day that is retrieved from the questionnaires. Two, shortest distance, height difference and LULC type add geospatial variables to the dataset.

Feature Selection

Taiwo et al. (2023) carried out experiments with Nyanya-Mararaba datasets to select few best features that produced optimal model performance. They experimented with five feature selection techniques: Pearson Correlation (PC), Information Gain (IG), Recursive Feature Elimination (RFE), Least Absolute Shrinkage and Selection Operator (LASSO) and Principal Component Analysis (PCA). The experiments selected nine features out of the twenty-nine; that is, household income, household size, rainfall, average temperature, travel time, amount spent, willingness to pay, shortest distance and height difference. These formed the data input in the machine learning models. 

Implementing the Models

Four machine learning techniques, Multilinear Regression (MLR), Random Forest (RF), Support Vector Regression (SVR), and Artificial Neural Network (ANN), were employed for the modelling. The models were implemented with codes in Jupyter Notebook® environment where the experiments were carried out. 

Experimental Design

The MLR, RF, SVR and ANN models, which were named model in the codes. They were each created as an instance of their respective classes in Scikit Learn® library: SGDRegressor, RandomForestRegressor, LinearSVR and MLPRegressor, which were each infused with a scaler to scale the dataset (Pedregosa et al., 2012).  Thus, we had an empty model. The model was then trained or fitted with the training dataset. Training enables the model to learn the relationship between the explanatory variables and the target variable. After training, the model was ready for predictions. The results were evaluated. If the resulting errors were not within tolerance (0.70 ≤ R2 ≥ 0.99), then the model needed refining through parameter tuning and it was built again. If the errors were within tolerance, then the model should be built with the parameters obtained. Afterward, the model was validated and tested.

Training, Validation and Testing

Training a model is a process of fitting it with a dataset so that the learning algorithm can learn the data and the relationships among the features. Training prepares the model for and gives it ability to generalize what it has learnt to new dataset it has not “seen” before. This allows the model to make prediction based on what it has learnt.  A major problem with training is called overfitting, a situation in which the model learns well the training dataset but unable to generalize and make good predictions with new dataset. To avoid overfitting, the dataset was split into three: training data, validation data and test data. After training, validation dataset was used to assess the model performance. If satisfied, then the model was tested with the test dataset, which acts as a new data that the model had never “seen” before. The performance of the model when fed with the test dataset shows how it will perform when it encounters new data in the world. Standard split ratio found in literature are 60-20-20 percent, 70-15-15 percent, and 80-10-10 percent (Pragati, 2023). 80-10-10 was adopted for this study.

Model Evaluation

Three error metrics were used to measure the performance of the model: Mean Absolute Error (MAE), Root Mean Squared Error (RMSE) and R square (R2).

Results 

Dataset Validation
Nyanya-Mararaba dataset collected where there is no WDN is validated with Karu dataset where there is WDN. The models were trained, validated and tested with both datasets. The results in Table 2, Table 3 and Table 4 show the results of each model performance with both datasets. During training, the average R2 score of the models using dataset where there is WDN is 98% while R2 score using dataset where there is no WDN is 63%. As shown in Table 5, significance test carried out at 95% confidence level on the results declares that there is no significance difference between the results of both datasets. Thus, the Nyanya-Mararaba dataset collected with questionnaires where there is no WDN is validated with Karu dataset where there is WDN collected from FCT Water Board. 

odel Performance Where There Is WDN and Where There Is No WDN

Table 4, Table5 and Table 6 also show the results of each model performance. It is obvious that Random Forest performed better than other models. During training, Random Forest gave RMSE of 48 liters and R2 is 98% where there is WDN, and RMSE of 83 liters and R2 score of 65% where there is no WDN. The performance of each model where there is WDN and where there is no WDN is depicted by the graph shown in Figure 2. From the graph, it is obvious that the difference between the actual volume and predicted volume of water consumed is negligible where there is WDN. This shows that the models were well trained; that is, the data was well learnt by the models, and the data was well fitted to the models. The two sets of graphs show that the difference between actual volume and predicted volume of water consumed is larger where there is no WDN than where there is WDN. The difference is due to the sources of the two datasets. Karu dataset was sourced from water meter readings while Nyanya-Mararaba dataset came from field work where number of water containers used per day was counted. The results of the significance test carried out for the datasets can be extended to the model performances since it was the results of their performances that were tested. Thus, the significance test shows that there is no significant difference between model performance where there is WDN and where there is no WDN.

Conclusion

This study examines performance of machine learning models for predicting volume of water consumed by poor urban households in Nyanya-Mararaba Town where there is no WDN. The dataset of volume of water collected with questionnaires where there is no WDN was validated with dataset of volume of water consumed where there is WDN. Four ML models were coded in Jupyter Notebook; they are multilinear regression (MLR), random forest (RF), support vector regression (SVR) and artificial neural network (ANN).  The performances of the models were examined. All four models, MLR, RF, SVR and ANN, performed considerably well in predicting volume of water consumed by the urban poor, as they produced RMSE of 110 litres, 83 litres, 98 litres and 97 litres respectively, and R2 score of 53%, 73%, 62% and 63% respectively, confirming that Random Forest performs better than other models. Significance test performed with t-test at 95% confidence level shows that there is no significant difference between model performances where there is WDN and where there is no WDN.


