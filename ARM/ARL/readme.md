# Online Retail Data Analysis with Apriori Algorithm

This project demonstrates how to use the Apriori algorithm to perform market basket analysis on an online retail dataset. The main goal is to identify product associations and generate product recommendations based on transaction data.

## Project Structure

- `online_retail_II.xlsx`: The dataset containing online retail transactions for the years 2010-2011.
- `data_preparation.py`: Script for data cleaning and preparation.
- `apriori_analysis.py`: Script for performing Apriori analysis and generating association rules.
- `utils.py`: Utility functions for retrieving product names and generating recommendations.
- `main.py`: Main script to run the analysis and print the recommendations.

## Setup and Installation

1. Clone the repository:

    ```bash
    git clone https://github.com/yourusername/online-retail-analysis.git
    cd online-retail-analysis
    ```

2. Install the required packages:

    ```bash
    pip install -r requirements.txt
    ```

## Usage

1. **Data Preparation**:

    Run the `data_preparation.py` script to clean the data and filter transactions from Germany:

    ```bash
    python data_preparation.py
    ```

2. **Apriori Analysis**:

    Run the `apriori_analysis.py` script to perform the Apriori analysis and generate association rules:

    ```bash
    python apriori_analysis.py
    ```

3. **Generate Recommendations**:

    Use the utility functions in `utils.py` to get product recommendations based on the generated rules. You can modify and run `main.py` to see the recommendations:

    ```bash
    python main.py
    ```

## Files and Functions

- `data_preparation.py`:
    - `prepare_retail(dataframe)`: Cleans and preprocesses the raw data.
    - `create_apriori_datastructure(dataframe, id=False)`: Creates the apriori data structure.

- `apriori_analysis.py`:
    - `get_rules(apriori_df, min_support=0.01)`: Generates frequent itemsets and association rules.

- `utils.py`:
    - `get_item_name(dataframe, stock_code)`: Retrieves the product name based on the stock code.
    - `recommend_products(rules_df, product_id, rec_count=5)`: Recommends products based on association rules.
    - `get_golden_shot(target_id, dataframe, rules)`: Prints the target product and its recommended products.

- `main.py`:
    - Example script to demonstrate the workflow of generating recommendations.

## Example

To generate recommendations for specific products, you can use the following example in `main.py`:

```python
TARGET_PRODUCT_ID_1 = 21987
TARGET_PRODUCT_ID_2 = 23235
TARGET_PRODUCT_ID_3 = 22747

get_item_name(germany_df, [TARGET_PRODUCT_ID_1, TARGET_PRODUCT_ID_2, TARGET_PRODUCT_ID_3])

get_golden_shot(TARGET_PRODUCT_ID_1, germany_df, germany_rules)
get_golden_shot(TARGET_PRODUCT_ID_2, germany_df, germany_rules)
get_golden_shot(TARGET_PRODUCT_ID_3, germany_df, germany_rules)
