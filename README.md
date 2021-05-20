# Data_logging
# To simplify the data entry at reception .

import pandas as pd

name_list = []
phone_list = []
place_list = []
temp_list = []
while True:
    try:
        name = input("Name: ")                      #  Enter name
        if name == 'Done' or name == 'done':
            break
        phone = int(input("Phone Number: "))        # Enter phone number
        place = input("Place: ")                    # Residential address
        temp = float(input("Body temperature: "))     # body temperature
    except:
        print('Try again')                          #error msg

    name_list.append(name)                          # append all values to the created list
    phone_list.append(phone)
    place_list.append(place)
    temp_list.append(temp)

# The data entered to be made into dataset
data = {
    'Name': name_list,
    'Phone_number': phone_list,
    'Place': phone_list,
    'Temperature': temp_list
}

# Creating dataframe from the data
df = pd.DataFrame(data)

# Convert dataframe to .csv file
df.to_csv('Data.csv') 
