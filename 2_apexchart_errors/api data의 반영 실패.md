# apexchart에서 api에 의해 불러온 data가 보이지 않을 경우
- API 함수안에서 할당하기
- apexchart 변수들에 직접 할당하기
<br>
두 가지 다 콘솔로 찍어봤는데 잘 나왔다.
<br>
그러나 apexchart 그래프에는 반영이 안되는 문제가 있었다.
<br>

문제는 내가 ref와 reactive를 사용했다는 것
<br>
&nbsp; → &nbsp;
비동기적으로 데이터가 나중에 나타나면서 그래프에는 반영이 되지않았다.
<br>
<br/>

:heavy_check_mark: 해결 방법 <br>
computed 사용 및 return 문으로 변경 후, <br>
데이터가 반영되면서 잘 나타났다.

```javascript
const 변수명 = computed(() => {
  return [
    {
      name: "이름",
      data,
    },
  ];
});
```

