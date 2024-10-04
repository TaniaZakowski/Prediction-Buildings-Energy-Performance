Prediction-Buildings-Energy-Performance

In the context of housing situation as a worldwide struggle for populations, many softwares dedicated to architectures are  implementing new functionalities to calculate energy efficiency at different levels, both for econonomic and environmental challenges.
The analysis present in this repository is based on a simulated dataset initially created by A. Tsanas and  Angeliki Xifara for their paper Accurate quantitative estimation of energy performance of residential buildings using statistical machine learning tools .

This article aims at predicting the energy consumptions from 12 theoretical buildings to keep temperatures in a range acceptable for people use. 8 features are considered ("Relative Compactness","Surface Area","Wall Area","Roof Area","Overall Height","Orientation","Glazing Area","Glazing Area Distribution","Heating Load","Cooling Load") to predict heating load and cooling load calculated through the software for the area of Athen, Greece, using the Ecotect software.

The analysis  conducted in this project was done considering regressions models for both targets,using all features, transformed with minmax scaler.
Despite most features being continuous variables ( such as height), the actual possible values was shaped as they are measured in buildings. Hence, linear regressions models were not considered.
Instead, a KNN regressor model was chosen since it doesn’t depend on data normality . A Random Forest was calculated for comparison, as this ensemble model handling collinearity in features, and a grid search was used to find the best tree as the method is good for small datasets and few features.
Results show that R2 of 0,91 and 0,89 were already obtained with KNN regressions respectively for heating and cooling loads.
The Random Forests for heating load returned a R2 of 0,997 with a MSE of 0,334 , and is considered overfitted.
Meanwhile the Random Forest for cooling load returned a R2 of 0,96 with a MSE of 3,228.
This suggest that these models are better suited for cooling load predictions, which is particularly interesting as often only heating load is considered in models focusing on buildings energy consumptions.

It is important to keep in mind that the heating and cooling loads are not measurements but results of calculations depending heavily on location as they take into account parameters such as external temperatures and humidity, but also relative compactness of the buildings, which was one of the features of the dataset, meaning that hidden correlations should be expected.
Nonetheless, these types of models could have great applications in decision making, for exemple when renovating old buildings, or building new ones from used containers (cargotecture), helping providing homes to populations economically challenged.

Links:
dataset
initial paper
slides
