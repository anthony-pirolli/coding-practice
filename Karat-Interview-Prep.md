Problem:
You are given a list of transactions, where each transaction is represented as a string:
"<userId>,<amount>"

Write a function that returns the user ID with the highest total transaction amount.

Code
#input values
input = ["u1,50", "u2,100", "u1,25", "u3,75"]

#initialize map
userMap = {}
for userId in input:
split = userId.split(",")

    if split[0] not in userMap.keys():
        userMap[split[0]] = int(split[1])
    else:
        userMap[split[0]] = userMap.get(split[0]) + int(split[1])

sortedUser = sorted(userMap.items(), key=lambda item: item[1], reverse=True)

#Highest User
print(sortedUser[0][0])
Code

This works however, I do need to check to validate input as a transaction could be missing a number or userId etc.
