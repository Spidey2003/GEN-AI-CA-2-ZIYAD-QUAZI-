# GEN-AI-CA-2-ZIYAD-QUAZI-
Name: Ziyad Quazi. 7TH SEM B 

Prn: 22070521505 

GEN AI CA: 2 

 

Q:6 Generate a model to represent a mathematical equation, write a program to parse the equation, and ask for input for each parameter. 

import re 

import sympy as sp 

  

def parse_equation(equation): 

    # Define a regular expression pattern to extract coefficients 

    pattern = r"([+-]?\d*)x\^2\s*([+-]?\d*)x\s*([+-]?\d*)\s*=\s*0" 

    match = re.match(pattern, equation.replace(" ", "")) 

     

    if match: 

        a = match.group(1) 

        b = match.group(2) 

        c = match.group(3) 

         

        # Handle cases where coefficients are missing or just "+" or "-" 

        a = int(a) if a not in ["", "+", "-"] else (1 if a == "+" or a == "" else -1) 

        b = int(b) if b not in ["", "+", "-"] else (1 if b == "+" or b == "" else -1) 

        c = int(c) if c not in ["", "+", "-"] else (1 if c == "+" or c == "" else -1) 

         

        return a, b, c 

    else: 

        raise ValueError("The equation format is incorrect.") 

  

def solve_quadratic(a, b, c): 

    #Define the quadratic equation 

    x = sp.symbols('x') 

    equation = a*x**2 + b*x + c 

    Solve the quadratic equation 

    solutions = sp.solve(equation, x) 

    return solutions 

  

def main(): 

    # Example input

    equation = input("Enter a quadratic equation in the form 'ax^2 + bx + c = 0': ") 

     

    try: 

        # Parse the equation to extract coefficients 

        a, b, c = parse_equation(equation) 

         

        # Display extracted coefficients 

        print(f"Parsed coefficients: a={a}, b={b}, c={c}") 

         

        # Solve the quadratic equation 

        solutions = solve_quadratic(a, b, c) 

         

        # Display the solutions 

        print("Solutions to the equation are:", solutions) 

     

    except ValueError as e: 

        print(e) 

  

if __name__ == "__main__": 

    main() 

Q:5 Generate a model for Covid 19 with symptoms of parameters like fever, cold, shivering,weight loss, generate 100 model data with random values for each parameter and order by parameter lowest to highest in display based on the input parameter. 

import pandas as pd 

import numpy as np 

  

def generate_random_data(num_records): 

    # Generate random data for each symptom 

    data = { 

        'fever': np.random.uniform(0, 100, num_records), 

        'cold': np.random.uniform(0, 100, num_records), 

        'shivering': np.random.uniform(0, 100, num_records), 

        'weight_loss': np.random.uniform(0, 100, num_records) 

    } 

    return pd.DataFrame(data) 

  

def sort_and_display(df, sort_by): 

    if sort_by not in df.columns: 

        print(f"Error: {sort_by} is not a valid parameter. Choose from: {', '.join(df.columns)}") 

        return 

     

    sorted_df = df.sort_values(by=sort_by) 

    print(f"Data sorted by {sort_by}:") 

    print(sorted_df) 

  

def main(): 

    num_records = 100 

    df = generate_random_data(num_records) 

     

    print("Generated data:") 

    print(df.head())  # Display the first few rows 

     

    # Prompt the user for the parameter to sort by 

    sort_by = input("Enter the parameter to sort by (fever, cold, shivering, weight_loss): ").strip().lower() 

     

    sort_and_display(df, sort_by) 

  

if __name__ == "__main__": 

    main() 

 

Output: 

1. Quadratic Equation Solver 

Program Execution: 

bash 

python quadratic_solver.py 
 

Example Input: 

css 

Enter a quadratic equation in the form 'ax^2 + bx + c = 0': 2x^2 - 4x - 6 = 0 
 

Example Output: 

less 

Parsed coefficients: a=2, b=-4, c=-6 
Solutions to the equation are: [3.0, -1.0] 

 

 

 

2. COVID-19 Symptoms Data Generator 

Program Execution: 

bash 

python covid_symptoms_model.py 
 

Example Input: 

vbnet 

Enter the parameter to sort by (fever, cold, shivering, weight_loss): fever 
 

Example Output: 

Generated data: 
      fever       cold shivering  weight_loss 
0   65.1234  77.2345     12.3456      33.4567 
1   12.3456  23.4567     34.5678      54.6789 
2   45.6789  89.0123     56.7890      78.9012 
... 
 
Data sorted by fever: 
       fever       cold shivering  weight_loss 
85  0.1234  67.2345     23.4567      89.6789 
47  1.2345  54.6789     67.8901      12.3456 
19  2.3456  78.9012     34.5678      56.7890 
... 

 

 

 

 
