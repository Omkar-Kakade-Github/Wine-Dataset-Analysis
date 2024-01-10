# Wine Dataset Analysis

This small project is my entry into the world of analytics and data. I will be analyzing and obtaining insights from the dataset obtained from The University of California Irvine’s Machine Learning Repository. The dataset contains 12 different variables,

- Fixed acidity: Titratable acidity, sometimes referred to as fixed acidity, is a measurement of the total concentration of titratable acids and free hydrogen ions present in your wine.

- Volatile acidity: Volatile acidity is mostly caused by bacteria in the wine creating acetic acid — the acid that gives vinegar its characteristic flavor and aroma — and its byproduct, ethyl acetate. Volatile acidity could be an indicator of spoilage, or errors in the manufacturing processes — caused by things like damaged grapes, wine exposed to air, and so on.

- Citric acid: Citric acid is generally found in very small quantities in wine grapes. It acts as a preservative and is added to wines to increase acidity, complement a specific flavor or prevent ferric hazes.

- Residual sugar: Residual Sugar, or RS for short, refers to any natural grape sugars that are leftover after fermentation ceases. Composed of fructose and glucose, the natural ingredients in grapes. Most of the bacteria becomes alcohol after fermentation, and the remaining sugar that is not converted is the residual.

- Chlorides: The amount of chlorides present in a wine is usually an indicator of its “saltiness.” This is usually influenced by the territory where the wine grapes grew, cultivation methods, and also the grape type.

- Free sulfur dioxide and Total sulfur dioxide: Sulfur dioxide exists in wine in free and bound forms, and the combinations are referred to as total SO2. It’s the most common preservative used, usually added by wine makers to protect the wine from negative effects of exposure to air and oxygen. Wines with added sulphur dioxide contents usually have “Contains Sulphites” on their labels.

- Density: Also known as specific gravity, it can be used to measure the alcohol concentration in wines. During fermentation, the sugar in the juice is converted into ethanol with carbon dioxide as a waste gas. Monitoring the density during the process allows for optimal control of this conversion step for highest quality wines. Sweeter wines generally have higher densities.

- Sulfates: Sulfates are salts of sulfuric acid. They aren’t involved in wine production, but some beer makers use calcium sulfate — also known as brewers’ gypsum — to correct mineral deficiencies in water during the brewing process. It also adds a bit of a “sharp” taste. Generally, white wine has a higher sulfate content than red wine.

- pH: pH stands for power of hydrogen, which is a measurement of the hydrogen ion concentration in the solution. Generally, solutions with a pH value less than 7 are considered acidic, with some of the strongest acids being close to 0. Solutions above 7 are considered alkaline or basic. The pH value of water is 7, as it is neither an acid nor a base.

- Alcohol: The alcohol content of the wine

- Quality: Comprehensive score of the wine

This dataset contains 4898 observations of 12 characteristics (fixed acidity, volatile acid, citric acid, residual sugar, chloride, free sulfur dioxide, total sulfur dioxide, density, pH, sulfate, alcohol, and quality). Here, 11 Characteristics are numerical data types that reflect the physical and chemical characteristics of wine, and the last one(quality) is the wine score. Although it is a numerical value, we use the wine’s score as an index to measure quality as a categorical variable.

![image](https://github.com/Omkar-Kakade-Github/Wine-Dataset-Analysis/assets/142827433/20daf39d-7ca0-4d29-92c4-7f902906a401)

As you can see, most wines fall under the average quality. There are fewer wines that are of very high quality and great tasting, and very few wines that aren’t so good.

![image](https://github.com/Omkar-Kakade-Github/Wine-Dataset-Analysis/assets/142827433/d064a839-4a78-431c-ac85-53259ee1b00a)

As you can see, the squares with positive values show direct co-relationships between features. The higher the values, the stronger these relationships are. That means, if one feature increases, the other one also tends to increase, and vice-versa.
The squares that have negative values show an inverse co-relationship. The more negative these values get, the more inversely proportional they are. This means that if the value of one feature is higher, the value of the other one gets lower.
Finally, squares close to zero indicate almost no co-dependency between those sets of features.

From the above correlation coefficients, the coefficients worth our effort to explore further more.
- Between SO2 and density, residual sugar
- Correlation coefficients between alcohol content and chlorides, residual sugar content, total SO2, fixed acidity
- Quality is related to the following factors: volatile acidity, total SO2, density, alcohol, chloride.

The correlation between the density and the amount of residual sugar, and the amount of alcohol is relatively easy to understand.The sugar content is high,then the density will increase. The density of alcohol is smaller than water and the pH is low. The key point for us to explore is the relationship between density, alcohol and chloride and quality score.

BIVARIATE PLOTS:

![image](https://github.com/Omkar-Kakade-Github/Wine-Dataset-Analysis/assets/142827433/223607ac-eba1-4640-ae03-f82a9e36d40c)

As you can see, the higher the alcohol content, the higher its quality rating is. However, even the lower rated wine contains alcohol whose levels are closer to the average rated wines. This means that there are other parameters which affect the aroma and taste of the wine, and which further determines the final quality of the wine.

![image](https://github.com/Omkar-Kakade-Github/Wine-Dataset-Analysis/assets/142827433/c7a9e662-dd9b-4954-b782-675334dd9f7b)

This scatter-plot shows how the values of pH change with changing fixed acidity levels. We can see that, as fixed acidity levels increase, the pH levels drop. A lower pH level is, after all, an indicator of high acidity.

![image](https://github.com/Omkar-Kakade-Github/Wine-Dataset-Analysis/assets/142827433/ce081857-c44d-47de-aafb-9af71ec0dc07)

The figure above shows that the higher the total SO2 content, the greater the density, and a positive correlation between the two.

![image](https://github.com/Omkar-Kakade-Github/Wine-Dataset-Analysis/assets/142827433/37b17a06-fa56-49a9-b25f-f983b8384b93)

Samples with high total SO2 content tend to have higher residual sugar content.

![image](https://github.com/Omkar-Kakade-Github/Wine-Dataset-Analysis/assets/142827433/2b0827eb-b355-4380-805b-6bf9f7003ae3)

In samples with high alcohol content, the total SO2 content is low, and in the samples with smooth fermentation, so2 will not be added again to adjust the fermentation reaction. This verifies the control logic of SO2 during the brewing.

BIVARIATE ANALYSIS:

Based on the general knowledge of biochemistry, you can judge the correlation between some parameters, such as sugar content and alcohol content can affect the density.Are there any more correlations? After listing the correlation coefficient matrix, based on the calculated correlation coefficients, roughly ploting the coefficients above 0.2 to see if the coefficients and the map match. During this exploration, we found the density and the amount of residual sugar have correlation with total SO2.Through the correlation coefficient matrix, we can see the quality has a greater correlation with the following factors: density, alcohol, alchohol, total SO2 content. These are the focus of further exploration.The strongest correlation is between the density and the amount of residual sugar, with a coefficient of 0.84.
