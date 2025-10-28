# 💻 Problem: Highest Total Transaction Amount

You are given a list of transactions, where each transaction is represented as a string:

Write a function that returns the user ID with the highest total transaction amount.

---

## 🧠 Example

**Input**

```python
["u1,50", "u2,100", "u1,25", "u3,75"]

# input values
input = ["u1,50", "u2,100", "u1,25", "u3,75"]

# initialize map
userMap = {}
for userId in input:
    split = userId.split(",")

    if split[0] not in userMap.keys():
        userMap[split[0]] = int(split[1])
    else:
        userMap[split[0]] = userMap.get(split[0]) + int(split[1])

sortedUser = sorted(userMap.items(), key=lambda item: item[1], reverse=True)

# Highest User
print(sortedUser[0][0])
```

This will get the right answer but does not take into consideration of any specific input validation, like malformed strings, missing Uids, etc.
