# 排序


## 外排序
指在排序期间全部对象太多，不能同时存放在内存中，必须根据排序过程的要求，不断在内，外存间移动的排序。


## 内排序
指在排序期间数据对象全部存放在内存的排序。


#### 常见的稳定排序算法有：

- 冒泡排序（Bubble Sort） — O(n²)
- 插入排序（Insertion Sort）— O(n²)
- 桶排序（Bucket Sort）— O(n); 需要 O(k) 额外空间
- 计数排序 (Counting Sort) — O(n+k); 需要 O(n+k) 额外空间
- 合并排序（Merge Sort）— O(nlogn); 需要 O(n) 额外空间
- 二叉排序树排序 （Binary tree sort） — O(n log n) 期望时间; O(n²)最坏时间; 需要 O(n) 额外空间
- 基数排序（Radix sort）— O(n·k); 需要 O(n) 额外空间


#### 常见的不稳定排序算法有：

- 选择排序（Selection Sort）— O(n²)
- 希尔排序（Shell Sort）— O(nlogn)
- 堆排序（Heapsort）— O(nlogn)
- 快速排序（Quicksort）— O(nlogn) 期望时间, O(n²) 最坏情况; 对于大的、乱数串行一般相信是最快的已知排序


快速排序
```javascript
var quickSort2 = function(arr) {
  console.time('2.快速排序耗时');
  if (arr.length <= 1) { return arr; }
  var pivotIndex = Math.floor(arr.length / 2);
  var pivot = arr.splice(pivotIndex, 1)[0];
  var left = [];
  var right = [];
  for (var i = 0; i < arr.length; i++){
  if (arr[i] < pivot) {
  left.push(arr[i]);
  } else {
  right.push(arr[i]);
  }
  }
  console.timeEnd('2.快速排序耗时');
  return quickSort2(left).concat([pivot], quickSort2(right));
};
```