# 막힌 부분

1. 높이가 지정되어 있어야 수직 중앙정렬 가능
  height: 75px;
  top: 0;
  bottom: 0;
  margin: auto;

2. css reset cdn 안하면 li 태그에 점 생김

3. 가장 직접적인 요소에 패딩, 컬러 지정할 것

4. ::before 사용시 content: ""; 필수
   글자 사이
   top: 0;
   bottom: 0;
   margin: auto;
   중앙정렬

5. const searchEl = document.querySelector('search')
   클래스가 search인 요소를 css 선택자로 찾아서 searchEl이라는 변수에 할당

6. :hover = 마우스 올리면 변환
   :focus = 클릭하면 변환

7. searchEl.addEventListener('click', function () {
  searchInputEl.focus();
});
  해당 요소에 이벤트 추가(아이콘 포함 인풋창 어디를 눌러도 포커스 가능)

8. searchEl.classList.add('focused');
  searchEl 요소의 클래스에 focused 라는 클래스 내용을 추가하겠다.
   searchEl.classList.remove('focused')
  focused 라는 클래스 내용을 제거하겠다.

9. searchInputEl.setAttribute('placeholder', '통합검색');
  해당 요소에 html 요소를 지정하는 메소드, 검색창에 통합검색 나타남

10. 