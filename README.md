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
