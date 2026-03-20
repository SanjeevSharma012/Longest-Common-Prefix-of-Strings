Longest Common Prefix (Java)
📌 Problem Statement

Given an array of strings arr[], find the longest common prefix among all strings.
If there is no common prefix, return an empty string "".

🧠 Approach

Take the first string as reference.

Compare each character of the first string with the same index in all other strings.

If:

Characters don’t match OR

Index exceeds length of any string
→ Return substring till that index.

If all characters match, return the full first string.

💻 Code Implementation
class Solution {
    public String longestCommonPrefix(String arr[]) {
        if(arr == null || arr.length == 0){
            return "";
        }
        
        for(int i = 0 ; i < arr[0].length() ; i++){
            char ch = arr[0].charAt(i);
            
            for(int j = 1 ; j < arr.length ; j++){
                if(i >= arr[j].length() || arr[j].charAt(i) != ch){
                    return arr[0].substring(0 , i);
                }
            }
        }
        return arr[0];
    }
}
🧪 Example
Input:
arr = ["geeksforgeeks", "geeks", "geek", "geezer"]
Output:
"gee"
⏱️ Complexity Analysis

Time Complexity: O(N * M)

N = number of strings

M = length of shortest string

Space Complexity: O(1)

⚠️ Edge Cases

Empty array → return ""

No common prefix → return ""

Single string → return the string itself

👨‍💻 Author

Sanjeev Sharma
