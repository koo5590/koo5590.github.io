---
layout: post
title: Recursive Algorithms
tags: [algorithms, recursion]
---

## 재귀적 알고리즘

### 1) 부분집합 생성하기
n개의 원소를 가진 집합 s가 있다. s의 부분집합을 구하라
~~~cpp
vector<int> subset;

void search(int k){ //원소 k
  if (k==n+1){
  //부분집합 완성: 적절한 처리를 한다
  }
  else{
  //k를 부분집합에 포함
  subset.push_back(k);
  search(k+1); //k를 포함하는 부분집합 완성하기
  //k를 부분집합에 불포함
  subset.pop_back();
  search(k+1); //k를 포함하지 않는 부분집합 완성하기
  }
}
~~~
위와 같은 재귀함수에 첫 인자로 1을 주고 호출하면 된다.
이러한 기본 뼈대에 내가 원하는대로 적절히 변형하면 된다. 예를 들어, set이 아닌 list에 원소들이 저장되어 있다면, 
subset이라는 vector 자료구조를 사용하는 대신 길이가 n인 bool형 배열 A를 생성하여 i번째 원소가 부분집합에 포함되는 경우에는 A[i]=true가 되고
반대의 경우에는 A[i]=false가 되도록 할 수 있다. 이러한 방법은 원소가 배열에 저장되어 있고, 부분집합에 포함되는 원소 뿐만이 아니라 포함되지 않은
원소들에 대해서도 처리를 해야할 때 유용하다고 생각한다.

참고: Guide to Competitive Programming
