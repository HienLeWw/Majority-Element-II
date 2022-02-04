# Problem Solution: 
  Majority Element II
  
# Difficulty: 
  Medium
  
# Description:
  Given an integer array of size n, find all elements that appear more than ⌊ n/3 ⌋ times.
  Example :

  Input: nums = [3,2,3]
  Output: [3]

  For more details: https://leetcode.com/problems/majority-element-ii/

# Idea:
  - We need to find the count of each element in the given array.
  - So, the simplest way is using STL:'map' for counting. 
  - Now, we iterate over the map to get the result.

# Code:
  Here is my completed function:
  
  vector<int> majorityElement(vector<int>& nums) {
        map <int,int> countApearance;
        vector <int> result;
        for(int i=0;i<nums.size();++i)
            countApearance[nums[i]]++;
        map <int,int>::iterator it;
        for(it = countApearance.begin();it != countApearance.end();++it)
            if(it->second > nums.size()/3)
                result.push_back(it->first);
        return result;
    }
