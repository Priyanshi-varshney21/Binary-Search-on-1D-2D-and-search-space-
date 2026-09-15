# Binary-Search-on-1D-2D-and-search-space-

# SEARCH X IN SORTED ARRAY
def search(self, nums, target):
        low=0
        high=len(nums)-1
        while low<high:
            mid=(low+high)//2
            if nums[mid]==target:
                return mid
            elif target<nums[mid]:
                high=mid-1
            else:
                low=mid+1
        return -1

# LOWER BOUND 
def lowerBound(self, nums, x):
        low=0
        high=len(nums)-1
        ans=len(nums)
        while low<=high:
            mid=low+(high-low)//2
            if nums[mid]>=x:
                ans=mid
                high=mid-1
            else:
                low=mid+1
        return ans

# UPEER BOUND
 def upperBound(self, nums, x):
        low=0
        high=len(nums)-1
        while low<=high:
            mid=low+(high-low)//2
            if nums[mid]>x:
                high=mid-1
            else:
                low=mid+1
        return low

# SEARCH INSERT POSITION
def searchInsert(self, arr, target):
        low=0
        high=len(nums)-1
        while low<=high:
            mid=low+(high-low)//2
            if arr[mid]==target:
                return mid
            elif arr[mid]>target:
                high=mid-1
            else:
                low=mid+1
        return low

# FIRST AND LAST OCCURENCE
def searchRange(self, nums, target):
        first=-1
        low=0
        high=len(nums)-1
        while low<=high:
            mid=low+(high-low)//2
            if nums[mid]==target:
                first=mid
                high=mid-1
            elif nums[mid]<target:
                low=mid+1
            else:
                high=mid-1
        
        last=-1
        low=0
        high=len(nums)-1
        high=len(nums)-1
        while low<=high:
            mid=low+(high-low)//2
            if nums[mid]==target:
                last=mid
                low=mid+1
            elif nums[mid]<target:
                low=mid+1
            else:
                high=mid-1
        return ([first,last])                

# COUNT OCCURENCE IN A SORTED ARRAY
def countOccurrences(self, nums, target):
        first=-1
        low=0
        high=len(nums)-1
        while low<=high:
            mid=low+(high-low)//2
            if nums[mid]==target:
                first=mid
                high=mid-1
            elif nums[mid]<target:
                low=mid+1
            else:
                high=mid-1
        last=-1
        low=0
        high=len(nums)-1
        while low<=high:
            mid=low+(high-low)//2
            if nums[mid]==target:
                last=mid
                low=mid+1
            elif nums[mid]<target:
                low=mid+1
            else:
                high=mid-1
        ans=(last-first)+1
        return ans

# SEARCH IN A SORTED ROTATED ARRAY-I
def search(self, nums, k):
        low=0
        high=len(nums)-1
        while low<=high:
            mid=low+(high-low)//2
            if nums[mid]==k:
                return mid
            #left half is sorted
            if nums[low]<=nums[mid]:
                if nums[low]<=k<nums[mid]:
                    high=mid-1
                else:
                    low=mid+1
            #Right half is sorted
            else:
                if nums[mid]<k<=nums[high]:
                    low=mid+1
                else:
                    high=mid-1
        return -1

# SEARCH IN A SORTED ROTATED ARRAY -II
def searchInARotatedSortedArrayII(self, nums, k):
        low=0
        high=len(nums)-1
        while low<=high:
            mid=low+(high-low)//2
            if nums[mid]==k:
                return True
            #left half is sorted
            if nums[low]<=nums[mid]:
                if nums[low]<=k<nums[mid]:
                    high=mid-1
                else:
                    low=mid+1
            #Right half is sorted
            else:
                if nums[mid]<k<=nums[high]:
                    low=mid+1
                else:
                    high=mid-1
        return False

# FIND MINIMUM IN A ROTATED SORTED ARRAY 
def findMin(self, arr):
        low=0
        high=len(nums)-1
        while low<=high:
            mid=low+(high-low)//2
            if nums[mid]>nums[high]:
                low=mid+1
            else:
                high=mid
        return nums[low]

# FIND OUT HOW MANY TIMES THE ARRAY IS SORTED
def findKRotation(self, arr):
        low=0
        high=len(arr)-1
        while low<high:
            mid=low+(high-low)//2
            if arr[mid]>arr[high]:
                low=mid+1
            else:
                high=mid
        return low

# SINGLE ELEMENT IN A SORTED ARRAY
def singleNonDuplicate(self, nums):
        n=len(nums)-1
        s=0
        e=n
        if n==1:
            return nums[0]
        while s<e:
            mid=s+(e-s)//2
            if mid==0 and nums[0]!=nums[1]:
                return nums[0]
            if mid==n-1 and nums[n-1]!=nums[n-2]:
                return nums[n-1]
            if nums[mid-1] != nums[mid] != nums[mid+1]:
                return nums[mid]
            if mid%2==0:   #EVEN 
                if nums[mid]==nums[mid+1]:
                    s=mid+2
                else:
                    e=mid-1
            else: #ODD
                if nums[mid-1]==nums[mid]:
                    s=mid+1
                else:
                    e=mid-1
                    
