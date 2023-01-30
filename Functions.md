this is  funcion to clean cells and takes specific caracteristics from it 

import re

def clean_column(df, column_name, match_string):
    # Create a regular expression pattern that matches the specified string
    pattern = r'(' + match_string + ')'

    # Convert the specified column to lowercase
    df[column_name] = df[column_name].str.lower()

    # Extract the matched substrings from the specified column and store them in a new column with " cleaned" suffix
    df[column_name + ' cleaned'] = df[column_name].str.extract(pattern, expand=True)

    #Delete the original column
    df.drop(columns=column_name, inplace=True)
    return df

For example, you can use the function to clean the "Species" column with the match string "white shark|Tiger shark|Bull shark" like this:
def clean_species_column(df):
    # Create a regular expression pattern that matches white shark, Tiger shark or Bull shark
    pattern = r'(white shark|Tiger shark|Bull shark)'

    # Convert the "Species" column to lowercase
    df['Species'] = df['Species'].str.lower()

    # Extract the matched substrings from the "Species" column and store them in a new column "Species cleaned"
    df['Species cleaned'] = df['Species'].str.extract(pattern, expand=True)

    #Delete the original column
    df.drop(columns='Species', inplace=True)
    return df




attacks = pd.read_csv("/Users/victorramos/documents/ironhack/Proyectos Ironhack/attacks.csv", encoding='latin1')
attacks = clean_column(attacks, 'Species', 'white shark|Tiger shark|Bull shark')
attacks = clean_column(attacks, 'Country', 'US|Australia')

