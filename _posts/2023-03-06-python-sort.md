---
layout: post
title: 선택 정렬, 삽입 정렬, 퀵 정렬
subtitle: 코딩 테스트에 많이 출제가 되는 3가지 정렬을 python과 java로 알아보자.
author: Jeffrey
categories: jekyll
banner:
  loop: true
  volume: 0.8
  start_at: 8.5
  image: https://bit.ly/3xTmdUP
  opacity: 0.618
  background: "#000"
  height: "100vh"
  min_height: "38vh"
  heading_style: "font-size: 4.25em; font-weight: bold; text-decoration: underline"
  subheading_style: "color: gold"
tags: python java sort
sidebar: []
---
* * *
## 선택 정렬
선택 정렬은 주어진 배열에서 가장 작은 값을 찾아 맨 앞으로 이동시키는 과정을 반복하여 정렬하는 알고리즘입니다.
### python
```python
def selection_sort(arr):
    n = len(arr)
    for i in range(n):
        min_index = i
        for j in range(i+1, n):
            if arr[j] < arr[min_index]:
                min_index = j
        arr[i], arr[min_index] = arr[min_index], arr[i]
    return arr
```
### java
```java
public static void selectionSort(int[] arr) {
    int n = arr.length;
    for (int i = 0; i < n; i++) {
        int minIndex = i;
        for (int j = i + 1; j < n; j++) {
            if (arr[j] < arr[minIndex]) {
                minIndex = j;
            }
        }
        int temp = arr[i];
        arr[i] = arr[minIndex];
        arr[minIndex] = temp;
    }
}
```
* * *
## 삽입 정렬
삽입 정렬은 배열을 순회하면서 각 원소를 이미 정렬된 배열에서 적절한 위치에 삽입하는 방법으로 정렬하는 알고리즘입니다.
### python
```python
def insertion_sort(arr):
    n = len(arr)
    for i in range(1, n):
        key = arr[i]
        j = i - 1
        while j >= 0 and arr[j] > key:
            arr[j+1] = arr[j]
            j -= 1
        arr[j+1] = key
    return arr
```
### java
```java
public static void insertionSort(int[] arr) {
    int n = arr.length;
    for (int i = 1; i < n; i++) {
        int key = arr[i];
        int j = i - 1;
        while (j >= 0 && arr[j] > key) {
            arr[j + 1] = arr[j];
            j--;
        }
        arr[j + 1] = key;
    }
}
```
* * *
## 퀵 정렬
퀵 정렬은 분할 정복 방식을 사용하여 배열을 빠르게 정렬하는 알고리즘입니다.   
배열에서 피벗(pivot)이라는 값을 선택한 후, 피벗보다 작은 값은 왼쪽으로, 큰 값은 오른쪽으로 분할한 후 각각을 재귀적으로 정렬하는 과정을 반복합니다.
### python
```python
def quick_sort(arr):
    if len(arr) <= 1:
        return arr
    pivot = arr[len(arr)//2]
    left, right, equal = [], [], []
    for i in arr:
        if i < pivot:
            left.append(i)
        elif i > pivot:
            right.append(i)
        else:
            equal.append(i)
    return quick_sort(left) + equal + quick_sort(right)
```
### java
```java
public static void quickSort(int[] arr, int left, int right) {
    if (left >= right) {
        return;
    }
    int pivot = arr[(left + right) / 2];
    int index = partition(arr, left, right, pivot);
    quickSort(arr, left, index - 1);
    quickSort(arr, index, right);
}

private static int partition(int[] arr, int left, int right, int pivot) {
    while (left <= right) {
        while (arr[left] < pivot) {
            left++;
        }
        while (arr[right] > pivot) {
            right--;
        }
        if (left <= right) {
            swap(arr, left, right);
            left++;
            right--;
        }
    }
    return left;
}

private static void swap(int[] arr, int i, int j) {
    int temp = arr[i];
    arr[i] = arr[j];
    arr[j] = temp;
}
```
* * *