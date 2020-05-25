---
layout: post
title: Dynamic Array
tags: [data_structure, vector]
---

### 동적 배열:<br>
프로그램이 실행되는 동안 크기가 변할 수 있는 배열 <br><br>

### Vector<br>
1. <b>벡터 생성</b>
  * vector<int> v;
  * vector<int> v = {1,2,3,4,5};
  * vector<int> v(8);  //size:8, value:0
  * vector<int< v(8,3) //size:8, value:3(each)
2. <b>원소 추가/삭제</b>
  * v.push_back(3);
  * v.insert(3);       //copies or moves the elements into the container by calling copy constructor or move constructor
  * v.emplace(it, 3);  //elements are constructed in-place, i.e. no copy or move operations are performed
  * v.emplace_back(3);
  * v.pop_back();
  * v.erase(v.begin()); //removes a single element at v[0]
  * v.erase(v.begin(), v.begin()+5); //removes elements from 0~4
3. <b>원소 접근</b>
  * int n = v[1];      //배열처럼 접근
  * int n = v.back();  //벡터의 마지막 원소 접근 
  * for(int i=0; i<v.size(); i++){<br>
     &nbsp;&nbsp;cout << v[i];<br>
    }<br>
  * for (auto x: v){<br>
     &nbsp;&nbsp;cout << x;<br>
    }
  * for (const auto& x: v){  //참조 복사  <br>
     &nbsp;&nbsp;cout << x<br>
    }
  * for(auto it=v.begin(); it!=v.end(); ++it){<br>
     &nbsp;&nbsp;cout << (*it);<br>
    }
 4. <b>lower bound & upper bound</b>  //주어진 범위가 정렬되어 있을 때만 올바르게 작동
   * auto it = lower_bound(v.begin(), v.end(),5);  //5보다 작지 않은 가장 첫 번째 원소를 가리키는 iterator
   * auto it = upper_bound(v.begin(), v.end(),5);  //5보다 큰 가장 첫 번째 원소를 가리키는 iterator
