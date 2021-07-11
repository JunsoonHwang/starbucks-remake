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

10. 메인 메뉴 구조

11. div클래스 안에 img태그를 사용 한 경우 border-radius를 사용해도
    적용이 안되는데 이는 div클래스에는 적용이 되었는데 그 위를 img가 덮고 있어서 안되는 것 div클래스에 overflow: hidden;을 적용해서
    이미지가 div클래서를 넘지 못하도록 해주면 해결

12. 뱃지 스크롤시 지우고 보이기

const badgeEl = document.querySelector('header .badges')

window.addEventListener('scroll', _.throttle(function () {
  console.log(window.scrollY)
  if(scrollY > 500) {
    badgeEl.style.display = 'none'
  } else {
    badgeEl.style.display = 'block'
  }
},300))

13. 이미지 순서대로 나타내기

const fadeEls = document.querySelectorAll('.visual .fade-in')
fadeEls.forEach(function (fadeEl, index) {
  gsap.to(fadeEl, 1, {
    delay: (index + 1) * .7,
    opacity: 1
  })
})

14. notice 부분 width: 50%로 좌우 나누려면
    좌우값 필요

15. justify-content: flex-end;
    align-items: center;  정렬 안될 시

    display: flex; 해줄 것

16. 브라우저 확대시 요소 위치 변경될 시
    위치 값을 %와 margin 속성을 통해 지정할 것

17. 해당 버튼 클릭시 밑에 창을 숨김 처리, 보임 처리 해주는 코드

  const promotionEl = document.querySelector('.promotion')
  const promotionToggleBtnEl = document.querySelector('.toggle-promotion')
  let isHidePromotion = false

  promotionToggleBtnEl.addEventListener('click', function () {
    isHidePromotion = !isHidePromotion

    if (isHidePromotion) {
      promotionEl.classList.add('hide')
    } else {
      promotionEl.classList.remove('hide')
    }
  })

18. 유튜브 동영상 삽입

var tag = document.createElement('script');

tag.src = "https://www.youtube.com/iframe_api";
var firstScriptTag = document.getElementsByTagName('script')[0];
firstScriptTag.parentNode.insertBefore(tag, firstScriptTag);

function onYouTubeIframeAPIReady() {
  new YT.Player('player', {
    videoId: 'An6LvWQuj_8',
    playerVars: {
      autoplay: true,
      loop: true,
      playlist: 'An6LvWQuj_8'
    },
    events: {
      onReady: function (event) {
        event.target.mute()
      }
    }
  });
}