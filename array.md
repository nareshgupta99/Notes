
## 1. Remove duplicate elements from sorted Array
Given a sorted array A[] of size N, delete all the duplicated elements from A[]. Modify the array such that if there are X distinct elements in it then the first X positions of the array should be filled with them in increasing order and return the number of distinct elements in the array.

### Note:
[practice here](https://leetcode.com/problems/remove-duplicates-from-sorted-array/#:~:text=Input%3A%20nums%20%3D%20%5B0%2C,%2C%203%2C%20and%204%20respectively.)

1. Don't use set or HashMap to solve the problem.
2. You must return the number of distinct elements(X) in the array, the generated output will print all the elements of the modified array from index 0 to X-1.

### Example 1:

```
Input:
N = 5
Array = {2, 2, 2, 2, 2}
Output: {2}
Explanation: After removing all the duplicates 
only one instance of 2 will remain.

```
### solution
```java
int remove_duplicate(int arr[],int N){
       int previous=arr[0];
       int j=0;
       for(int i=1;i<arr.length;i++){
           if(arr[i]!=previous){
               arr[j]=previous;
               previous=arr[i];
           }
       }
           return j;
    }
```

## 2. Union of Two Sorted Arrays

merge two array without redudency/duplicate element in a sorted order

### ***brute force***

when we talk about unique element , map & set come into mind but i have to maintened sorted order so i will go with Set.

* i declare a Set and putting element one by one 
* ***time complexity***
O(n2logn)  
* ***space complexity***
O(n) 


***Example:-***
[practice here](https://practice.geeksforgeeks.org/problems/union-of-two-sorted-arrays-1587115621/1)
```
Input: 
n = 5, arr1[] = {1, 2, 3, 4, 5}  
m = 3, arr2 [] = {1, 2, 3}
Output: 1 2 3 4 5
Explanation: Distinct elements including 
both the arrays are: 1 2 3 4 5.
```
***solution***
```java
public static ArrayList<Integer> findUnion(int arr1[], int arr2[], int n, int m)
    {
        Set l=new TreeSet<Integer>();
        ArrayList <Integer> l1=new ArrayList<Integer>();
        for(int i=0;i<arr1.length;i++){
            l.add(arr1[i]);
        }
        for(int i=0;i<arr2.length;i++){
                l.add(arr2[i]);
        }
            l1.addAll(l);
        return l1 ;  
    }
```
## ***optimial***

we used two pointer algorithm ,i take a two pointer one is pointed first array & another is pointed second array 

* compare element of both array which one smallest select them and check wheather element is present in answer array if not present put in answer array otherwise do nothing & increse pointer of array

```java
public static ArrayList<Integer> findUnion(int arr1[], int arr2[], int n, int m) {
        ArrayList<Integer> list = new ArrayList<Integer>();
        int i = 0, j = 0;
        while (i < n && j < m) {
            if (arr1[i] <= arr2[j]) {

                if (list.isEmpty() || list.get(list.size() - 1) != arr1[i]) {
                    list.add(arr1[i]);
                }

                i++;
            } else if (arr2[j] <= arr1[i]) {
                if (list.isEmpty() || list.get(list.size() - 1) != arr2[j]) {
                    list.add(arr2[j]);
                }
                j++;
            }
        }
        while (i < n) {

            if (list.isEmpty() || list.get(list.size() - 1) != arr1[i]) {
                list.add(arr1[i]);
            }

            i++;

        }

        while (j < m) {
            if (list.isEmpty() || list.get(list.size() - 1) != arr2[j]) {
                list.add(arr2[j]);
            }
            j++;

        }

        return list;
    }

```
### Intersection Of Two Sorted Arrays

you have 2 sorted array .both these array are sorted in non-decresing order.you have to find intersection(means elements make pair in 2 array) like this

### ***example***
```
input
1 2 2 2 3 4
2 2 3 3
output
223
input
7 9 9
6 7 7 9 9 9 10
output
799

```
### ***brute force***

in this approach we declare a nested loop 1 is iterate 0 ->n & inner loop iterate 0->m

* compare element of both array if elements are = ,put them into ans array & update value as null of second array
* ***time complexity***
O(n2)  
* ***space complexity***
O(n) 

```java
int flag=0;
		int index=-1;
		for(int i=0;i<n;i++){
			flag=0;
			index=-1;
			for(int j=0;j<m;j++){
				if(arr1.get(i)==arr2.get(j)){
					flag=1;
					index=j;
				}
				if(arr2.get(j)>arr1.get(i)){break;}
			}
			if(flag==1){
				ans.add(arr2.get(index));
				arr2.set(index, Integer.MIN_VALUE);
			}

		}
		return ans;
```

### ***Optimal***

we use 2 pointer algorithm to solve this problem

* ***time complexity***
O(n)  
* ***space complexity***
O(n) 
```java
public static ArrayList<Integer> findArrayIntersection(ArrayList<Integer> arr1, int n, ArrayList<Integer> arr2, int m)
	{
		ArrayList<Integer> ans=new ArrayList<Integer>();
		int i=0,j=0;
		while(i<n && j<m){
			
			 if(arr1.get(i)>arr2.get(j)){
				j++;
			}
			else if(arr1.get(i)<arr2.get(j)){
				i++;
			}
			else{
				ans.add(arr2.get(j));
				i++;
				j++;
			}
		}
		return ans;
	}
	
```

##  Longest subarray with sum k

***Brute Force***
```java
    public static int lenOfLongSubarr (int a[], int n, int k) {
        int sum=0,len=0,max=0;
            for(int i=0;i<n;i++){
                for(int j=i;j<n;j++){
                    sum=0;len=0;
                    for(int r=i;r<=j;r++){
                        sum+=a[r];
                        len++;
                    }
                    if(sum==k){
                        max=(len>max?len:max);
                    }
                }
            }
            return max;  
    }

```
***Time Complexity:-*** approx O(n^3)