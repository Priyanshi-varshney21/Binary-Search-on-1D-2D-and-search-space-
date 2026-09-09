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
        
