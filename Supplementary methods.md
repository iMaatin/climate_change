# Supplementary Methods

## Estimation of $CO_2$ Emission
The amount of carbon dioxide emission was calculated by the method of carbon footprint. This method measures the total amount of $CO_2$ emitted directly and indirectly over the food production and its life storages stage (19). For calculating $CO_2$ emission, we used the ‘BCFN DOUBLE PYRAMID DATABASE’ which is a global database for carbon dioxide emissions and provides gram $CO_2$ emission per kg for each food item. The $CO_2$ emission for each country in different years was calculated by multiplying the average amount of emitted $CO_2$ per gram of food groups by the average intake of the corresponding food group. The sum of emitted $CO_2$ for all food groups was regarded as the food carbon emission for the country (20).

To derive a precise $CO_2$ emission value for each food item, with a particular focus on data relevant to EMR countries, a classification method was implemented. The food items were classified based on the quantity of available reporting studies within the database:

* **Type 1 (Data-Limited Items):** This category comprised the largest group of 89 food items, each supported by fewer than 10 reporting studies. Given the limited data for these items, the $CO_2$ emission value was determined by calculating the arithmetic mean of all available reported emissions, serving as a standard measure of central tendency.
* **Type 2 (Data-Rich Items):** This category consisted of 23 food items with 10 or more available studies. The greater data volume for this group permitted a more granular, geographically-focused analysis to enhance the relevance of the estimates for the Mediterranean region. This category was further divided into:
    * **Type 2A (Mediterranean-Specific Analysis):** This sub-category included 5 items (Milk, Yogurt, Olive oil, Pasta, and Tomatoes) for which a substantial number of studies ($\ge10$) originated specifically from the Mediterranean area. For these items, a region-specific clustering analysis was performed, and the final emission value was calculated as the mean of this geographically-constrained clusters. Further details on the clustering methodology are available in the supplementary materials.
    * **Type 2B (General Analysis with Robust Statistics):** This sub-category comprised the remaining 18 items. Although data-rich, these items lacked a significant concentration of studies from the Mediterranean region, resulting in a more heterogeneous dataset. The presence of potential outliers and data heterogeneity necessitated a robust measure of central tendency. While Huber's M-estimation was initially considered, it failed to achieve convergence for several items. Therefore, Tukey’s biweight method was employed to calculate the final, robust $CO_2$ emission estimate for each item in this group. (Items: Apples, Beans, Beef meat, Bread, Butter, Carrots, Cheese, Codfish, Cucumbers, Eggs, Lamb meat, Lettuce, Potatoes, Poultry meat, Rice, Salmon, Strawberries, Trout). Further details are available in the supplementary materials.

## Data Source and Preprocessing
The carbon footprint data for all food items were extracted from the ‘BCFN DOUBLE PYRAMID DATABASE’ (`CO2.xlsx`). Initial data preprocessing involved standardizing the ‘Region’ field to consolidate synonymous entries (e.g., ‘Mediterranean Area’ was mapped to ‘Mediterranean area’).

## Stratification of Food Items
To apply the most appropriate statistical analysis based on data availability, all food items were stratified into two primary types:

* **Type 1 (Data-Limited Items):** This category included 89 food items with fewer than 10 available $CO_2$ emission measurements in the database. 
    > **Items:** Almonds, Bananas, Beet Sugar, Beetroot, Biscuits, Blueberries, Broccoli, Cabbage, Cakes, Cane Sugar, Cashew Nut, Cauliflower, Cherries, Chinese Orange, Chocolate, Citrus, Cornetti All'albicocca, Cornetti Alla Crema, Cow Meat, Cracker Gran Pavesi, Cream, Diamond Fish, Dried Fruit, Dry Legumes, Eggplant, Fava Beans, Fish, Fish Fillet, Grapes, Green Beans, Hamburger, Herring, Honey, Hotdog Baguette, Kiwis, Legumes, Lemon Juice, Manderin Oranges, Margarine, Melons, Mincead Meat, Mooncake, Mozzarella, Mushrooms, Nectarine, Onions, Orange Juice, Oranges, Pan Goccioli, Paradise Cake, Peach, Peanut, Pear Juice, Pears, Peas, Peppers, Pistachio, Plumcake Integrale, Plumcake Allo Yogurt, Plumcake Con Gocce Di Cioccolato, Pomegranate, Raisins, Raspberries, Rolls, Saccottini Al Cioccolato, Saccottini All'albicocca, Saccottini Alla Crema, Sardine, Sausage, Sfoglia Di Grano Non Salati, Sfoglia Di Grano Salati, Shrimps, Skimmed Milk, Sole, Soybean, Soybean Oil, Spinach, Sugar, Sunflower Oil, Tangerines, Tuna, Turbot, Vanilla Danish Pastry, Veal Meat, Vegetables, Walnuts, Whiting, Whole Wheat Pasta, Zucchini.
* **Type 2 (Data-Rich Items):** This category included 23 food items with 10 or more available $CO_2$ emission measurements. These items were further sub-stratified based on the concentration of data from the Mediterranean region.
    * **Type 2A (Mediterranean Focus):** This sub-group consisted of 5 items (`Milk`, `Olive oil`, `Pasta`, `Tomatoes`, and `Yogurt`) for which 10 or more data points originated from the Mediterranean area.
    * **Type 2B (General Focus):** This sub-group comprised the remaining 18 items which had fewer than 10 data points from the Mediterranean region.
        > **Items:** Apples, Beans, Beef meat, Bread, Butter, Carrots, Cheese, Codfish, Cucumbers, Eggs, Lamb meat, Lettuce, Potatoes, Poultry meat, Rice, Salmon, Strawberries, Trout.

## $CO_2$ Emission Estimation Methodology
Figures are availble in the word version 


### Type 1 Items (Data-Limited)
For the 89 items with limited data, the $CO_2$ emission value was calculated as the arithmetic mean of all available reported values after converting the data to a numeric type and removing any non-numeric entries.

### Type 2A Items (Mediterranean-Specific Analysis)
For the 5 items with a high concentration of Mediterranean data, a region-specific clustering analysis was performed to identify the optimal number of distinct emission groups.

* **K-Means Clustering and Elbow Method:** The data for each food item was first standardized using `StandardScaler` from the `scikit-learn` library. K-Means clustering was then applied for a range of one to ten clusters ($k$). The optimal number of clusters for each food item was determined using the "Elbow method," which identifies the point of diminishing returns in the within-cluster sum of squares (WCSS). The number of clusters selected for each item was: Milk ($k=3$), Olive Oil ($k=3$), Pasta ($k=4$), Tomatoes ($k=4$), and Yogurt ($k=2$).
* **Outlier Removal and Final Estimation:** Based on the cluster visualizations, specific outliers were identified and removed for Olive Oil (index 876) and Yogurt (index 191). The final $CO_2$ emission estimate for Type 2A items was calculated as the arithmetic mean of the cleaned, region-specific data.

### Type 2B Items (General Analysis with Robust Statistics)
For the 18 data-rich items with heterogeneous geographical sources, a robust statistical estimator was required to determine the central location while minimizing the influence of potential outliers.

* **Tukey’s Biweight Estimator:** Tukey’s biweight method was selected for this analysis. This method calculates a weighted mean where weights are determined based on the distance of data points from the median, effectively down-weighting or removing extreme outliers. The median absolute deviation (MAD) was used as the robust measure of scale, and a tuning constant of $c=4.685$ was applied. The `tukey_biweight` function was implemented in Python using the NumPy library.
* **Alternative Method Consideration:** Huber’s M-estimator (using `statsmodels.robust.scale.Huber`) was also considered but was found to have convergence issues for several food items (e.g., 'Salmon', 'Trout'), making it unsuitable for this dataset.

## Food Group $CO_2$ Emission Estimation
To provide broader emission estimates, the individual food items were aggregated into food groups based on the Combination2 scheme defined in the `CO2 combination.xlsx` file. For each defined group, an aggregate $CO_2$ emission value was calculated using the previously determined individual food item estimations. The mean and median of the $CO_2$ values for all food items within a specific group were calculated to represent the central tendency of that group's carbon footprint. 

## Diet Score Calculations
We selected diet scores with clear, predefined cutoffs rather than those based on relative distributions such as quintiles or quartiles. This decision was critical for two reasons. First, relying on means or medians to compare EMR scores with global scores would consistently yield a value of half the maximum, offering no meaningful discriminative power. Second, because the global GDD dataset contains only a single value per time point, scores without absolute cutoffs would have been inapplicable. The selected scoring systems and their references are listed below.

* **PHDI:** Bui LP, Pham TT, Wang F, Chai B, Sun Q, Hu FB, et al. Planetary Health Diet Index and risk of total and cause-specific mortality in three prospective cohorts. Am J Clin Nutr. 2024;120(1):80-91.
* **MEDIT:** Bach-Faig A, Berry EM, Lairon D, Reguant J, Trichopoulou A, Dernini S, et al. Mediterranean diet pyramid today. Science and cultural updates. Public Health Nutr. 2011;14(12a):2274-84.
* **DASH (Dixon):** National Heart LaBI. DASH Eating Plan: National Heart, Lung and Blood Institute; 2025 [updated January 202510th June 2025]. Available from: https://www.nhlbi.nih.gov/education/dash-eating-plan. 

## Software
All data processing and statistical analyses were conducted using **Python (version 3.10)**, with the `pandas`, `scikit-learn`, `statsmodels`, and `matplotlib` libraries.