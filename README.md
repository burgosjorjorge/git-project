import time
import pandas as pd
import numpy as np


city = {'chicago': 'chicago.csv', 'new york city': 'new_york_city'}

cities = input('Enter chicago, new york city, or washington ')

# The user will choose between chicago, new york city, and washtington.

# The user will enter one of the three cities

def user_input(city):
    chicago = pd.read_csv('chicago.csv')
    new_york_city = pd.read_csv('new_york_city.csv')
    washington = pd.read_csv('washington.csv')
    import time
    import pandas as pd
    import numpy as np

    CITY_DATA = {'chicago': 'chicago.csv',
                 'new york city': 'new_york_city.csv',
                 'washington': 'washington.csv'}


    def get_filters():
        """
        Asks user to specify a city, month, and day to analyze.

        Returns:
            (str) city - name of the city to analyze
            (str) month - name of the month to filter by, or "all" to apply no month filter
            (str) day - name of the day of week to filter by, or "all" to apply no day filter
        """
        print('Hello! Let\'s explore some US bikeshare data!')

        # get user input for city (chicago, new york city, washington). HINT: Use a while loop to handle invalid inputs
        city = input('Enter a city ')
        month = input('Enter a month ')
        day = input('Enter a day ')
    # get user input for month (all, january, february, ... , june)

    # get user input for day of week (all, monday, tuesday, ... sunday)

        print('-'*40)
        return city, month, day


    def load_data(city, month, day):
        """
        Loads data for the specified city and filters by month and day if applicable.

        Args:
            (str) city - name of the city to analyze
            (str) month - name of the month to filter by, or "all" to apply no month filter
            (str) day - name of the day of week to filter by, or "all" to apply no day filter
        Returns:
            df - Pandas DataFrame containing city data filtered by month and day
        """

        df = pd.read_csv('chicago.csv')
        df = pd.read_csv('new_york_city.csv')
        df = pd.read_csv('washington.csv')
        return df


    def time_stats(df):
        """Displays statistics on the most frequent times of travel."""

        print('\nCalculating The Most Frequent Times of Travel...\n')
        start_time = time.time()
        df['Start Time'] = pd.to_datetime(df['Start Time'])
        # display the most common month
        df['month'] = df['Start Time'].dt.month
        print(df.month.value_counts().head(1))
        # display the most common day of week
        df['day'] = df['Start Time'].dt.day
        print(df.day.value_counts().head(1))
        # display the most common start hour
        df['hour'] = df['Start Time'].dt.hour
        print(df.hour.value_counts().head(1))
        # convert the Start Time column to datetime


    # extract hour from the Start Time column to create an hour column

        print("\nThis took %s seconds." % (time.time() - start_time))
        print('-'*40)


    def station_stats(df):
        """Displays statistics on the most popular stations and trip."""

        print('\nCalculating The Most Popular Stations and Trip...\n')
        start_time = time.time()

        # display most commonly used start station
        print('The most commonly used start station was', df['Start Station'].value_counts().head(1))
        # display most commonly used end station
        print('The most used End Station was', df['End Station'].value_counts().head(1))
        # display most frequent combination of start station and end station trip

        print("\nThis took %s seconds." % (time.time() - start_time))
        print('-'*40)


    def trip_duration_stats(df):
        """Displays statistics on the total and average trip duration."""

        print('\nCalculating Trip Duration...\n')
        start_time = time.time()

        # display total travel time
        print('The total travel time is', df['Trip Duration'].count())
        # display mean travel time
        print('The average travel time was', df['Trip Duration'].mean())
        print("\nThis took %s seconds." % (time.time() - start_time))
        print('-'*40)


    def user_stats(df):
        """Displays statistics on bikeshare users."""

        print('\nCalculating User Stats...\n')
        start_time = time.time()

        # Display counts of user types
        print('Total count of user type is', df['User Type'].count())
        # Display counts of gender

        # Display earliest, most recent, and most common year of birth

        print("\nThis took %s seconds." % (time.time() - start_time))
        print('-'*40)


    def main():
        while True:
            city, month, day = get_filters()
            df = load_data(city, month, day)

            time_stats(df)
            station_stats(df)
            trip_duration_stats(df)
            user_stats(df)

            restart = input('\nWould you like to restart? Enter yes or no.\n')
            if restart.lower() != 'yes':
                break


    if __name__ == "__main__":
        main()
