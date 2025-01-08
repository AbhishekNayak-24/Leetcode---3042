# Leetcode---3042
COUNT PREFIX  AND SUFFIX PAIRS I
// CODE IN JAVA
public class Solution {
    public int countPrefixSuffixPairs(String[] words) {
        int count = 0;
        for (int i = 0; i < words.length; i++) {
            for (int j = i + 1; j < words.length; j++) {
                if (isPrefixAndSuffix(words[i], words[j])) {
                    count++;
                }
            }
        }
        return count;
    }

    private boolean isPrefixAndSuffix(String str1, String str2) {
        int m = str1.length();
        int n = str2.length();
        if (m > n) {
            return false;
        }
        // Check if str1 is a prefix of str2
        for (int i = 0; i < m; i++) {
            if (str1.charAt(i) != str2.charAt(i)) {
                return false;
            }
        }
        // Check if str1 is a suffix of str2
        for (int i = 0; i < m; i++) {
            if (str1.charAt(i) != str2.charAt(n - m + i)) {
                return false;
            }
        }
        return true;
    }
}
