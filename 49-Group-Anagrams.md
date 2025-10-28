# 🧩 Problem: Group Anagrams

Given an array of strings `strs`, group the **anagrams** together. You may return the answer in any order.

---

## 🧠 Example

**Input**

```python
["eat", "tea", "tan", "ate", "nat", "bat"]
```

**Output**

```python
[["bat"], ["nat", "tan"], ["ate", "eat", "tea"]]
```

class Solution:
def groupAnagrams(self, strs: List[str]) -> List[List[str]]:
if len(strs) == 1:
return [strs]

        seen_value = {}
        index = 0
        for word in strs:
            comparing_word = "".join(sorted(word))

            if comparing_word not in seen_value.keys():
                seen_value[comparing_word] = [word]
            else:
                seen_value[comparing_word].append(word)

        return list(seen_value.values())

---

✅ **Copy Tip:**  
Copy everything from the first line

This was actually quite good time complexity compared to my peers and I was quite happy with this implementation.
