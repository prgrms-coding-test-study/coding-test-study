## 👤 작성자
김지수

---

## 🧩 문제 정보
<!-- [문제 제목](문제 링크) 형식으로 작성하세요 -->
[K번째 수](https://school.programmers.co.kr/tryouts/198387/challenges)

---

## 💭 아이디어
- 슬라이싱으로 부분 배열 선택
- 선택한 부분 배열 정렬
- k번째 원소 선택

---

## 🧑‍💻 코드
<!-- 작성한 코드를 백틱으로 감싸 넣어주세요 --> 
```python
def solution(array, commands):
    answer = []
    
    for i, j, k in commands:
        sub = array[i-1:j]
        sub.sort()
        answer.append(sub[k-1])
    
    return answer
```

---

## ⏰ 복잡도
- 시간 복잡도: O(M * KlogK) -> M: 명령의 개수, K: 부분 배열 길이
- 공간 복잡도: O(K)

---

## 📝 회고
- 슬라이싱을 활용한 부분 배열 추출 -> array[i:j]에서 i는 포함, j는 미포함
- 인덱스 1-based → 0-based 변환 주의