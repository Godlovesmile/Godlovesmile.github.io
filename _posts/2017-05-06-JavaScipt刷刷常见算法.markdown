---
layout: post
title: JavaScipt刷刷常见算法
date: 2017-05-06 11:11:11.000000000 +09:00
categories: 数据结构算法
tags: 算法;Github
---

# 一.冒泡算法
## 1.官方解释
&emsp;&emsp;冒泡排序（英语：Bubble Sort，台湾另外一种译名为：泡沫排序）是一种简单的排序算法。它重复地走访过要排序的数列，一次比较两个元素，如果他们的顺序错误就把他们交换过来。走访数列的工作是重复地进行直到没有再需要交换，也就是说该数列已经排序完成。这个算法的名字由来是因为越小的元素会经由交换慢慢“浮”到数列的顶端。
## 2.Code
```
 //冒泡算法
   var i, j, temp;
   Array.prototype.bubble_sort = function () {
    for (i = 0; i < this.length - 1; i++) {
      for (j = 0; j < this.length - 1 - i; j++) {
        if (this[j] > this[j+1]) {
          temp = this[j];
          this[j] = this[j+1];
          this[j+1] = temp;
        }
      }
    }
    return this;
   }
   var arr = [-52, 3, 22, 11, 23, 45];
   console.log(arr.bubble_sort());
```
## 3.运作
&emsp;&emsp;其实不要看着代码这那儿想入非非,这种东西,我们跟着它走一遍,就可以明明白白入坑了.
&emsp;&emsp;举个简单的栗子,现在有数组arr=[3,2,1]一枚,开始使用冒泡排序:
第一次:(数组arr=[3,2,1];判断条件:i<2;j<2)
i=0;
j=0;
&emsp;&emsp;if(arr[0]>arr[1]){//成立,执行交换};交换后的结果是:arr=[2,3,1];
j=1;
&emsp;&emsp;if(arr[1]>arr[2]){//成立,执行交换};交换后的结果是:arr=[2,1,3];
j=2;第一次结束

第二次:(数组arr=[2,1,3],判断条件:i<2;j<1)
i=1;
j=0;
&emsp;&emsp;if(arr[0]>arr[1]){//成立,执行交换};交换后的结果是:arr=[1,2,3];
j=1;第二次结束

第三次:(数组arr=[1,2,3],判断条件:i<2;j<0)
i=2;所有循环结束


# 二.选择排序（Selection Sort）


# 三.插入排序（Insertion Sort）


# 四.希尔排序（Shell Sort）


# 五.归并排序（Merge Sort）


# 六.快速排序（Quick Sort）
```
function quickSort(arr, left, right) {
    var len = arr.length,
        partitionIndex,
        left = typeof left != 'number' ? 0 : left,
        right = typeof right != 'number' ? len - 1 : right;

    if (left < right) {
        partitionIndex = partition(arr, left, right);
        quickSort(arr, left, partitionIndex-1);
        quickSort(arr, partitionIndex+1, right);
    }
    return arr;
}

function partition(arr, left ,right) {     //分区操作
    var pivot = left,                      //设定基准值（pivot）
        index = pivot + 1;
    for (var i = index; i <= right; i++) {
        if (arr[i] < arr[pivot]) {
            swap(arr, i, index);
            index++;
        }        
    }
    swap(arr, pivot, index - 1);
    return index-1;
}

function swap(arr, i, j) {
    var temp = arr[i];
    arr[i] = arr[j];
    arr[j] = temp;
}
```

