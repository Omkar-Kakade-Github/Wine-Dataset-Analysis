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

MULTIVARIATE PLOTS:( I could have used better colours:))

![image](https://github.com/Omkar-Kakade-Github/Wine-Dataset-Analysis/assets/142827433/6ec6d71d-09f1-48fd-9e79-d1c0c6e86a4b)

As we expected, the higher the sugar content of the sample, the higher the density value. The higher the score of the sample(the 8, 9 points), the sample density tended to be lower. If the sample has the same sugar content, the lower the density of the sample score relatively high.

![image](https://github.com/Omkar-Kakade-Github/Wine-Dataset-Analysis/assets/142827433/0db4ea87-c88c-4a16-86a3-625c009cf6b9)

As expected, the density of alcohol is negatively correlated with the density of wine. During the fermentation process, because the sugar is slowly converted to alcohol, the sugar decreases, the alcohol increases, and the overall density decreases. Also, the sample with high alcohol content indicates that the fermentation process is good, the chances of getting a high score increase. There are more blue or blue-green data points in the high-alcohol scatter area.

![image](https://github.com/Omkar-Kakade-Github/Wine-Dataset-Analysis/assets/142827433/2132cc04-6fcb-41e0-85a9-c916f105fc26)

Samples with high alcohol content, such as samples above 10.5%, have a slightly lower residual sugar content of less than 9g / ml. There are more samples with high scores in this range.

![image](https://github.com/Omkar-Kakade-Github/Wine-Dataset-Analysis/assets/142827433/20dee71b-b19a-487b-899f-44c10f245a6b)

Overall，the total SO2 content is low, and the sample with higher alcohol intent to have a higher score.

![image](https://github.com/Omkar-Kakade-Github/Wine-Dataset-Analysis/assets/142827433/2f3f78b6-ea4d-405b-baf6-03e3a96f910c)

The figure above shows that when the chloride content is low and the alcohol content is high, the sample score will be higher.

![image](https://github.com/Omkar-Kakade-Github/Wine-Dataset-Analysis/assets/142827433/445190ce-d219-4e42-b752-edcf654e7d6d)

There is no obvious difference in the fixed acidity in the samples with different alcoholity, and there is no obvious trend in the score of the samples with different acidity.

MULTIVARIATE ANALYSIS:

- The acetic acid, malic acid, citric acid, consumed sugar, alcohol, and sterilization and freshness of SO2 produced in the winemaking process can be comprehensively reflected in the physical parameter density. Approximately, alcoholicity 10.5-11 as a reference, we can observe Low-alcohol samples have higher densities, and the scores are mainly represented by the color crimson indicating the wine quality of 3-4. In samples with an alcohol content of 11 or higher, the sample density shows a decreasing trend, with blue and blue scores representing 7, 8, 9. The green sample data points are mainly, the high-scoring samples are concentrated in the areas with low density and high alcohol content. Alcohol and wine density are negatively correlated. During the fermentation process, because sugar is slowly converted to alcohol, the sugar content is reduced, and the alcohol content is increased, it further decreased the density. At the same time, samples with high alcohol content indicate that the fermentation process is good, and the probability of the sample getting a high score is increased.

- The relationship between the added SO2 and alcohol content during the brewing process affects the score. In the data description chart, we can see that as the alcohol content increases, the samples with high scores increase, and the total SO2 decreases. To maintain the freshness and stop the oxidation, the level of SO2 added needs to be monitored. When the fermentation process is smooth, a certain amount of SO2 is consumed and kept in balance with free SO2. When the fermentation is not smooth, SO2 needs to be added to maintain the normal pH value and prevent brewing failure. The sample with a lower total SO2 content tends to have a higher overall score. This phenomenon shows that the total SO2 content is generally low in samples with an alcohol content higher than 11%.

- In the previous data exploration, it was found that the residual sugar data showed a right skewed curve. In linear regression analysis, if the data was converted by log10 function processing, then it would have been easier to find the correlation with alcohol content. In all the samples that were scored, the higher the score of the sample, the lower the residual sugar amount. We can observe that with the increase of alcohol content, the number of samples with a high residual sugar amount is decreasing.

- Fixed acidity, malic acid, citric acid, and residual sugar have no positive effect on the score. High alcohol samples have a tendency to get high scores.

- Under the influence of alcohol, the taste of the wine has more full body feel, and the amount of residual sugar has not played a role in increased score. With too much sugar, other tastes tends to be over powered by the sweetness.

FINAL REFLECTION:

- The entire process is to understand the data type and distribution by exploring a single data set, and to explore the correlation between the two sample parameters. In the second step, we are showing which factors are affected by the score. It is a gradual process. In each step of the drawing process, by adjusting the drawing parameters and adjusting the data image, the image is clearer and easier to discuss.
  
- The process of exploring this data requires a general understanding of the process of making wine, such as why the SO2 in the sample need to be in balance, and how it affects the density, pH, alcohol content and fermentation process of the wine. When the graph drawn is not consistent with prognosis, there are clues to find the cause of the inconsistency.
  
- From the process of data exploration, the influence of alcohol content on scoring is becoming more and more obvious. It is the ultimate product in the fermentation process. Fermentation goes smoothly, the amount of sugar in grapes gradually decreases, the density decreases, the alcohol content increases, and the organic substances in the alcohol affecting the taste and body of the wine, also by avoiding excessive SO2 in the wine to prevent the biochemical inbalance, thus the total SO2 content remain low.
  
- Lesson learned: When drawing multivariate graphics, I found that according to the original quality classification, the color difference of the graphs is not obvious since there are few samples with 8, 9 scores, and it would be much better to classify the scores into smaller categories for the sake of better visibility and understanding.

- Difficulties encountered: For majority of the the bivariate and multivariate plots, the regression line was negatively affected due to the presence of a large number of outliers and the precision of the plots was to be questioned. In the final section of the code, the detection and removal of the outliers is carried out using Tukey’s Method.
