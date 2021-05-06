# 정렬 알고리즘
#### 1. 내부 정렬(Internal Sort)
 : 버블 정렬, 선택 정렬, 삽입 정렬, 합병 정렬, 퀵 정렬, 힙 정렬, 쉘 정렬
#### 2. 외부 정렬(External Sort)
 : 다방향 합병, 다단계 합병
 
### 1. 내부 정렬
#### 1) Bubble Sort
 1. 첫 번째 데이터부터 인접한 데이터끼리 계속 자리를 바꾸면서 맨 뒷자리까지 이동과 반복
 2. 정렬이 끝나면 가장 큰 원소가 마지막 자리로 정렬

![KakaoTalk_20210506_221642960](https://user-images.githubusercontent.com/80522538/117305848-1be3dc00-aeba-11eb-8432-1e765648e31b.jpg)

##### 시간 복잡도
O(n^2)

##### 코드
```
public class bubblesort {
  public void sort(int[] arr){
    int n = arr.length;
    for(int i=0; i<n; i++){
      for(int j=0; j<n-1; j++){
        if(arr[j]>arr[j+1]){
          int temp = arr[j];
          arr[j] = arr[j+1];
          arr[j+1] = temp;
        }
      }
    }
  }
}
```

#### 2) Selection Sort
 1. 입력 배열 전체에서 최소값을 선택해 배열의 0번과 자리를 바꿈.
 2. 0번을 제외한 나머지에서 최소값을 선택하여 배열의 1번과 자리 바꿈
 3. 이 과정을 반복하여 오름차순 정렬

![KakaoTalk_20210506_221643032](https://user-images.githubusercontent.com/80522538/117305882-2605da80-aeba-11eb-9ea0-7257be2dd4fe.jpg)

##### 시간 복잡도
O(n^2)

##### 코드
```
public class selectionsort {
  public void sort(int[] arr){
    int n = arr.length;
    for(int i=0; i<n-1; i++){
      int min = i;
      for(int j=n; j<n; j++){
        if(arr[min]>arr[j])
          min = j;
      }
      int temp = arr[i];
      arr[i] = arr[min];
      arr[min] = temp;
    }
  }
}
```

#### 3) Insertion Sort
 1. 배열을 정렬된 부분과 정렬 안 된 부분으로 나눔
 2. 정렬 안 된 부분의 가장 왼쪽을 정렬된 부분의 적절한 위치에 삽입하여 정렬
 3. 이 과정을 반복

![KakaoTalk_20210506_221643106](https://user-images.githubusercontent.com/80522538/117305934-3027d900-aeba-11eb-8d4e-911da834e844.jpg)

##### 시간 복잡도
O(n^2)

##### 코드
```
public class insertionsort{
  public void sort(int[] arr){
    int n = arr.length;
    for(int i=1; i<n; i++){
      int temp = arr[i];
        for(j=i-1; j>=0 && arr[j]>temp; j--){
          arr[j+1] = a[j];
        }
      }
      arr[j+1] = temp;
    }
  }
}
```

#### 4) Shell Sort
 1. 배열 뒷부분의 작은 숫자를 앞부분으로 빠르게 이동시키고 동시에 앞부분의 큰 숫자는 뒷부분으로 이동
 2. 사장 마지막에는 삽입 정렬을 수행

##### 시간 복잡도
O(n^2)

##### 코드
```
public class shellsort{
  public void sort(int[] arr){
  int n =arr.length;
    for(int gap=n/2; gap>=1; gap/=2){
      for(int i=gap;i<n;i++){
        int temp = arr[i];
        int j=i;
        while(j>=gap && arr[j-gap]>temp){
          arr[j] = arr[j-gap];
          j -= gap;
        }
        arr[j] = temp; 
      }
    }
  }
}
```
