# Profile: Christian Alexander Marrero

- **NetID:** cmarr8
- **Major:** Computer Science (with concentration in Software Engineering)
- **Favorite CS Topic:** C
- **Topic I Find Challenging / Want to Learn:** Assembly

## Random Image

![GitHub's mascot, Mona, atop a puddle.](https://cameronmcefee.com/img/work/the-octocat/original.jpg)

## Summary Table

| Request           | Response |
| ----------------  | -------- |
| NetID             | cmarr8   |
| Major             | CS-SWE   |
| Favorite Topic    | C lang.  |
| Challenging Topic | Assembly |

## Code for [Longest Palindromic Substring](https://www.geeksforgeeks.org/problems/longest-palindrome-in-a-string1956/1)

```C++
class Solution {
  public:
    bool isPalindrome(const string& s, size_t i, size_t j) {
        while (i <= j && j + 1 > j && i < s.size()) {
            if (s[i] != s[j]) return false;
            i++; j--;
        }
        return true;
    }
    string getLongestPal(string &s) {
        // code here
        vector<pair<size_t, size_t>> ipairs;
        for (size_t i = 0; i < s.size(); i++) {
            for (size_t j = i; j < s.size(); j++) {
                ipairs.push_back({i, j});
            }
        }
        
        size_t largest_width = 0;
        string largest_substr = "";
        
        size_t width;
        for (const pair<size_t, size_t>& p : ipairs) {
            if (isPalindrome(s, p.first, p.second)) {
                width = p.second - p.first + 1;
                if (width > largest_width) {
                    largest_width = width;
                    largest_substr = largest_substr = s.substr(0, width);
                }
            }
        }
        
        return largest_substr;
    }
};
```