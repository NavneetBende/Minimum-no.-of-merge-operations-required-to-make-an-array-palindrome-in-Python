Minimum no. of merge operations required to make an array palindrome
Here on this page, we will learn how to Minimum no. of merge operations required to make an array palindrome in Python Programming Language.

Example :

Input : array = [2, 10, 12, 26, 3, 22, 2]
Output : 2
Explanation : We need to merge 10 and 22 so, the array will become [2, 22, 26, 3, 22, 2]. Again we will merge 26 and 3 so the array becomes [2, 22, 29, 22, 2]. Now, the array becomes palindromic, hence we need to do 2 merging operations to make the given array palindromic.
Minimum no. of merge operations required to make an array palindrome in Python

Algorithm
Declare a variable say, count=0, that will count the required merging operation.
Take two variables, i=0, and j=n-1.
Now, run a loop till i<j, inside loop check if (arr[i]==arr[j]), then increase the value of i by 1 and decrease the value of j by 1.
Else if (arr[i]>arr[j]), then set arr[j-1] = arr[j-1]+arr[j] and decrease the value of j and increase the value of count by 1.
Else set, arr[i+1] = arr[i]+arr[i+1] and increase the value of i and count by 1.
After the traversal print the value of count.
Minimum no. of merge operations required to make an array palindrome
Python Code
Run
def find(arr):
    ans = 0

    i, j = len(arr) - 1, 0
    while j <= i:
        if arr[j] == arr[i]:
            j += 1
            i -= 1

        elif arr[j] > arr[i]:
            i -= 1
            arr[i] += arr[i + 1]
            ans += 1

        else:
            j += 1
            arr[j] += arr[j - 1]
            ans += 1

    return ans


array = [2, 10, 12, 26, 3, 22, 2]
print("Total number of merging operation required is", find(array))
Output
Total number of merging operations required is 2
