# Python-Exercises-1

weight=input('What is your weight in lbs? ')

weight_kilos=float(weight)/2.205

print('Your weight is ' + str(weight_kilos) + ' in kilos.')

-> converting a user's weight to kilos from lbs

----------------------

price=int(1000000)

is_good_credit=True

if is_good_credit:

    print('Your down payment is $' + str(price*_0.1))
    
else:

    print ('Your down payment is $' + str(price*0.2))
    
->finding what the down payment for a house is with good credit or not

-----------------------------

price=1000000

has_good_credit=True

if has_good_credit:

    down_payment=price*0.1

else:

    down_payment=price*0.2
    
print(f'Down payment: ${down_payment}')

->same as above but using a formatted string

-----------------

name=input('What is your name? ')



if len(name) < 3:
    print('Name must be at least 3 characters')
elif len(name) > 50:
    print('Name can only be a maximum of 50 characters')
else:
    print('Name looks good!')

-> checks if a person's username is of an appropriate length

----------

weight=input('Weight: ')
pounds_or_kilos=input('Enter L for lbs or enter K for kg: ')



if pounds_or_kilos.upper()== "L":
    converted = int(weight)/2.205
    print(f'You are {converted} kgs')
elif pounds_or_kilos.upper()== "K":
    converted = int(weight)*2.205
    print(f'You are {converted} pounds')
else:
    print('Invalid Input')

-> converts weight to pounds or kilos

------

is_car_started = False
while True:
    command = input('>').lower()
    if command == 'help':
        print("""start- to start the car
stop- to stop the car
quit- to exit""")
    elif command == 'start':
        if not is_car_started:
            print('Car started... Ready to go!')
            is_car_started=True
        else:
            print('Car is already started!')
    elif command == 'stop':
        if is_car_started:
            print('Car stopped.')
            is_car_started = False
        else:
            print('Car is already stopped!')
    elif command == 'quit':
        break
    else:
        print("Sorry... I don't understand that")

-> a little car game that lets you control the start and stop of a car and tells you how to do it

---------

list= [1, 5, 3, 6, 7, 8, 4]
max = list[0]
for item in list:
    if item > max:
        max=item
print(max)

-> finds the highest number in a list of numbers

-----

numbers = [2, 2, 6, 3, 1, 4, 6, 7, 8, 8, 8, 9]
uniques = []

for number in numbers:
    if number not in uniques:
        uniques.append(number)
uniques.sort()
print(uniques)


-> creates a list that took out duplicates, then sorted list

--------

class Person:
    def __init__(self, name):
        self.name = name

    def talk(self):
        print(f"Hi I am {self.name}")

john = Person("John Smith")
john.talk()

bob = Person('Bob Smith')
bob.talk()

----------------

import openpyxl as xl
from openpyxl.chart import BarChart, Reference

def process_workbook(filename):
    wb = xl.load_workbook(filename)
    sheet = wb['Sheet1']

    for row in range(2, sheet.max_row + 1):
        cell = sheet.cell(row, 3)
        corrected_price = cell.value * 0.9
        corrected_price_cell = sheet.cell(row, 4)
        corrected_price_cell.value = corrected_price

    values = Reference(sheet,
                       min_row=2,
                       max_row=sheet.max_row,
                       min_col=4,
                       max_col=4)

    chart = BarChart()
    chart.add_data(values)
    sheet.add_chart(chart, 'e2')

    wb.save(filename)

-> creating an automatic process that will update the prices in a column in an excel spreadsheet to corrected prices

---------

