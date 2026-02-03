#include <iostream>
#include <string>
#include <vector>
#include <numeric>   // for std::accumulate
#include <algorithm> // for std::sort, std::max_element, std::remove_if
#include <iomanip>   // for std::setprecision

/**
 * 1. Sum of two integers
 * Returns the arithmetic sum of x and y.
 */
int sum(int x, int y) {
    return x + y;
}

/**
 * 2. Count vowels in a string
 * Counts 'a', 'e', 'i', 'o', 'u' (case-insensitive).
 */
int countVowels(const std::string& str) {
    int count = 0;
    std::string vowels = "aeiouAEIOU";
    for (char c : str) {
        if (vowels.find(c) != std::string::npos) {
            count++;
        }
    }
    return count;
}

/**
 * 3. Average of a list of integers
 * Returns the average as a double. Returns 0.0 if list is empty.
 */
double getAverage(const std::vector<int>& nums) {
    if (nums.empty()) return 0.0;
    double sum = std::accumulate(nums.begin(), nums.end(), 0.0);
    return sum / nums.size();
}

/**
 * 4. Remove vowels from a sentence
 * Returns a new string with all vowels removed.
 */
std::string removeVowels(const std::string& sentence) {
    std::string result = "";
    std::string vowels = "aeiouAEIOU";
    for (char c : sentence) {
        if (vowels.find(c) == std::string::npos) {
            result += c;
        }
    }
    return result;
}

/**
 * 5. Longest string in a list
 * Returns the first longest string found in the vector.
 */
std::string getLongestString(const std::vector<std::string>& strings) {
    if (strings.empty()) return "";
    std::string longest = strings[0];
    for (const std::string& s : strings) {
        if (s.length() > longest.length()) {
            longest = s;
        }
    }
    return longest;
}

/**
 * 6. Median of a list of integers
 * Sorts the list and finds the middle value.
 */
double getMedian(std::vector<int> nums) {
    if (nums.empty()) return 0.0;
    std::sort(nums.begin(), nums.end());
    size_t size = nums.size();
    if (size % 2 == 0) {
        return (nums[size / 2 - 1] + nums[size / 2]) / 2.0;
    } else {
        return nums[size / 2];
    }
}

/**
 * 7. Remove even numbers
 * Returns a new vector containing only the odd numbers.
 */
std::vector<int> removeEvens(const std::vector<int>& nums) {
    std::vector<int> odds;
    for (int n : nums) {
        if (n % 2 != 0) {
            odds.push_back(n);
        }
    }
    return odds;
}

/**
 * 8. Sort strings alphabetically
 * Returns a new sorted vector of strings.
 */
std::vector<std::string> sortStrings(std::vector<std::string> strings) {
    std::sort(strings.begin(), strings.end());
    return strings;
}

/**
 * 9. Sum of integers in a list
 */
int sumList(const std::vector<int>& nums) {
    return std::accumulate(nums.begin(), nums.end(), 0);
}

/**
 * 10. Reverse strings in a list
 * Returns a new list where each individual string is reversed.
 */
std::vector<std::string> reverseStringsInList(std::vector<std::string> strings) {
    for (std::string& s : strings) {
        std::reverse(s.begin(), s.end());
    }
    return strings;
}

// Utility to print vectors
template <typename T>
void printVec(const std::vector<T>& vec) {
    std::cout << "[ ";
    for (const auto& i : vec) std::cout << i << " ";
    std::cout << "]" << std::endl;
}

int main() {
    // 1. Sum
    std::cout << "1. Sum (5, 10): " << sum(5, 10) << std::endl;
