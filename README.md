# bank-resreq-lendingmodel

# Simple program to model cumulative loan volumes stemming from an initial deposit
# Calculates how much of an initial sum x a bank can lend out

# uses a large number of iterations to find the maximum

# uses the typical Fed reserve requirement before March 2020 
# this reserve ratio can be changed as desired to see the impacts

# takes input for an initial deposit

reserveReq = 0.1
print('Enter a deposit amount:')
initialDeposit = int(input())

def lendTotal(initialDeposit):
    loanAddition = 0
    loanVolume = 0
    for x in range(10001):
        loanAddition = (initialDeposit * (1-reserveReq))
        loanVolume += loanAddition
        initialDeposit = loanAddition
    return round(loanVolume, 2)
print('Over time a bank would lend out $' + str(lendTotal(initialDeposit)) + ' using your deposit.')
