# kkonnect.io-assignment-1
KKonnect.io assignment 1
All codes are related to Cost Estimation , Webscraping and supplier matching are in the assignment1.ipybm file.
### Cost Estimation Algorithm:-

2.3 Methodology/Algorithm:-
* 1. Material Cost
    * The algorithm uses predefined average costs per pound for different materials. This cost is essential as different materials have varying prices, and the cost of raw materials significantly impacts the overall manufacturing cost.
* 2. Machine Time
    * The machine time required for manufacturing is estimated based on the part size and complexity. The machine time includes the actual production time, which is crucial for calculating the production cost.
* 3. Setup Time
    * The setup time is considered based on the complexity of the part. More complex parts require more time for setup, which impacts the setup cost.
* 4.Material Cost Calculation
    * The material cost is calculated by assuming the amount of material required based on the part size. The material cost is then derived by multiplying the amount of material by the cost per pound.
    * Pseudocode:-
	if Part_Size == 'small':
   		 material_cost = 50 * material_type_pricing[Material_type]
	elif Part_Size == 'medium':
    	material_cost = 100 * material_type_pricing[Material_type]
	elif Part_Size == 'large':
    	material_cost = 150 * material_type_pricing[Material_type]
* 5. Production Cost Calculation
    * The production cost is calculated by multiplying the estimated machine time by a predefined production cost per hour. This cost reflects the expense of running the machines for the required time.
    * Predefine Production Cost is assumed as 100
    * Pseudocode:-
        * production_cost = estimated_time * 100
* 6. Setup Cost Calculation
    * The setup cost is calculated by multiplying the setup time by a base setup cost. This cost reflects the expense of preparing the machines and workspace for production.
    * Base Setup cost is assumed as 50
    * Pseudocode:-
        * setup_cost = setup_time[Complexity] * 50
* 7. Additional Processing Costs
    * Additional costs are considered for various processes such as finishing, heat treatment, packing, and transport. These costs are added to the total cost to ensure a comprehensive estimation.
    * Pseudocode:-
        * total_additional_cost = sum(additional_cost.values())
* 8.Total Cost Calculation
    * The total approximate cost is calculated by summing the material cost, setup cost, production cost, and additional processing costs. This provides a comprehensive cost estimation.
    * Pseudocode:-
        * aprox_cost = material_cost + setup_cost + production_cost + total_additional_cost
* 9. Cost Range Calculation
    * To provide a price range, a 20% variance is applied to the total cost. This range accounts for potential fluctuations in material costs, machine time, and other factors that may impact the final cost.
    * Pseudocode :-
	twenty_percent = aprox_cost * 20 / 100
	lower_range = aprox_cost - twenty_percent
	upper_range = aprox_cost + twenty_percent
* 10. This Algorithm Provides 2 outputs  
    * Approximate Cost 
    * Ranged Cost 
### Supplier Algorithm
Methodology/Algorithm :-
* 1. Data Preprocessing
    * Before applying the supplier matching algorithm, the dataset is preprocessed. This involves encoding categorical variables and scaling numerical variables to ensure they are in a comparable format.
* 2. Similarity Calculation
    * The algorithm calculates the similarity between the input criteria and each manufacturer in the dataset using cosine similarity. Cosine similarity measures the cosine of the angle between two vectors in a multi-dimensional space, providing a measure of how similar the two vectors are.
* 3. Finding Top 3 Similar Manufacturers
    * The algorithm defines a function Find_similar that takes the input criteria and returns the top three manufacturers that closely match the given criteria. It performs the following steps:
        * Creates a DataFrame with the input criteria.
        * Encodes and scales the input criteria using the same transformers used for the dataset.
        * Calculates the cosine similarity between the input criteria and all manufacturers in the dataset.
        * Identifies the indices of the top three most similar manufacturers.
        * Retrieves the names of the top three similar manufacturers.

