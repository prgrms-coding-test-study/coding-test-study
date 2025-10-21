## 👤 작성자

김지우

---

## 🧩 문제 정보
<!-- [문제 제목](문제 링크) 형식으로 작성하세요 -->
예) [K번째수](https://school.programmers.co.kr/learn/courses/30/lessons/42748)

---

## 💭 아이디어
<!-- - 문제에서 요구하는 조건 정리 -->
<!-- - 해결을 위한 접근 방식 -->
<!-- - 사용한 알고리즘 및 자료구조 -->

- i,j,k가 주어질 때, i번째부터 j번째까지 잘라서, 오름차순 정렬하고 k번째 숫자를 얻는 것을 반복해 리스트를 리턴.
- 입력의 길이가 1\~100이고, command는 1\~50번 이므로 길이가 100인 입력에 대해서, i,j가 항상 1,100이라면 O(n*nlogn)이 걸림.
(길이 n * n길이 정렬nlogn)
만약 n이 100 이상의 값이라면 다른 해답을 고민해봐야 하지만, 100이기 때문에, 문제에서 시키는 대로 하면 해결 가능.
- `sort()`는 `TimSort` 알고리즘을 사용해서, 항상 `O(nlogn)`을 보장함.(quickSort가 최악의 경우 O(n^2)인 것에 반해)

---

## 🧑‍💻 코드
<!-- 작성한 코드를 백틱으로 감싸 넣어주세요 --> 
```python
def solution(array, commands):
    answer = []
    for command in commands:
        start, end, k = command
        splitted = array[start-1:end]
        splitted.sort()
        
        # print(splitted)
        # print(array)
        answer.append(splitted[k-1])
    
    
    return answer
```

---

## ⏰ 복잡도
- 시간 복잡도: O(n^2logn)
- 공간 복잡도: O(len(commands))

---

## 📝 회고
<!-- - 구현하며 어려웠던 점 -->
<!-- - 실수한 부분 -->
<!-- - 새롭게 공부한 내용 -->
`sort()` 메소드가 quicksort로 구현된 줄 알았는데, 그게 아니었다는 것을 알았습니다.
그리고, 리스트 슬라이싱이 `(start, end]`라는 것도 확인했습니다. 보통 `[start, end)`인데 말이죠.
