# apexchart에서 api에 의해 불러온 data가 보이지 않을 경우
- API 함수안에서 할당하기
- apexchart 변수들에 직접 할당하기
<br>
두 가지 다 콘솔로 찍어봤는데 잘 나왔다.
그러나 apexchart 그래프에는 반영이 안되는 문제가 있었다.
<br>

문제는 내가 ref와 reactive를 사용했다는 것.

<br>
<mark> [해결] </mark>

computed로 바꾸고 return 문으로 변경하니까
데이터가 반영되면서 잘 나타났다.
