import time
import pandas as pd
import numpy as np


city = {'chicago': 'chicago.csv', 'new york city': 'new_york_city'}

cities = input('Enter chicago, new york city, or washington ')

# The user will choose between chicago, new york city, and washtington.

def user_input(city):
    chicago = pd.read_csv('chicago.csv')
    new_york_city = pd.read_csv('new_york_city.csv')
    washington = pd.read_csv('washington.csv')
    chicago['Start Time'] = pd.to_datetime(chicago['Start Time'])
    city = cities
    ch = chicago['Start Time']

    if city.lower() == 'chicago':
        return(chicago)
    elif city.lower() == 'new york city':
        return(new_york_city)
    elif city.lower() == 'washington':
        return(washington)
    else:
        print('you entered the wrong city')

# This line will print the data chosen by the user

print(user_input(city))
print()
