# Homework 3 - 快速排序演算法實作

### code
```
def Quick_Sort(array, start, end):
    if start >= end:
        return
    pivot = array[start]
    left = start
    right = end
    while left < right:
        while left < right and array[right] >= pivot:
            right -= 1
        while left < right and array[left] <= pivot:
            left += 1
        if left < right:
            array[left], array[right] = array[right], array[left]
    array[start], array[right] = array[right], array[start]
    print("以", pivot, "為基準點排列陣列排列結果:", array)
    Quick_Sort(array, start, right - 1)
    Quick_Sort(array, right + 1, end)


arr = [33, 67, 8, 13, 54, 119, 3, 84, 25, 41]
print("原先陣列:", arr, "\n")
Quick_Sort(arr, 0, len(arr) - 1)
print("\n最終陣列:", arr)

```

### 執行結果  
原先陣列: [33, 67, 8, 13, 54, 119, 3, 84, 25, 41] 

  以 33 為基準點排列陣列排列結果: [3, 25, 8, 13, 33, 119, 54, 84, 67, 41]  
  以 3 為基準點排列陣列排列結果: [3, 25, 8, 13, 33, 119, 54, 84, 67, 41]  
  以 25 為基準點排列陣列排列結果: [3, 13, 8, 25, 33, 119, 54, 84, 67, 41]  
  以 13 為基準點排列陣列排列結果: [3, 8, 13, 25, 33, 119, 54, 84, 67, 41]  
  以 119 為基準點排列陣列排列結果: [3, 8, 13, 25, 33, 41, 54, 84, 67, 119]  
  以 41 為基準點排列陣列排列結果: [3, 8, 13, 25, 33, 41, 54, 84, 67, 119]  
  以 54 為基準點排列陣列排列結果: [3, 8, 13, 25, 33, 41, 54, 84, 67, 119]  
  以 84 為基準點排列陣列排列結果: [3, 8, 13, 25, 33, 41, 54, 67, 84, 119]  

最終陣列: [3, 8, 13, 25, 33, 41, 54, 67, 84, 119]
![GitHub Logo](pic_1.png)
