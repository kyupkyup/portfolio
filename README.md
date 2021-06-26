# portfolio
프론트엔드 포트폴리오입니다.

## 접속
https://kyupkyup.github.io/portfolio/

## 템플릿
https://codepen.io/dev_loop/pen/MWKbJmO

## 기존 코드 & 변경 코드 비교
### 변경점
1. 카드의 개수 변경(3 -> 5)
카드의 개수가 변경됨에 따라 자바스크립트 코드와 scss 코드에 변경이 생겼다.
   - z-index 수정
   - 자바스크립트 코드 수정
   - 이미지 각도 변경
2. 카드의 태그 변경
div 태그 대신 anchor 태그로 바꿔주었다.

### html
#### 기존코드
```html
<div class="card current--card">
	<div class="card__image">
		<img src="https://source.unsplash.com/Z8dtTatMVMw" alt="" />
	</div>
</div>
```
#### 변경 코드
```html
<a class="card current--card" href="https://drive.google.com/file/d/1NnprBOELbpXO7YdSvkFFAeWAn0ySPFjj/view?usp=sharing" rel="noreferrer noopener" target="_blank">
  <div class="card__image1">
    <img src="./images/KakaoTalk_20210104_190020600.jpg" alt="" />
  </div>
</a>
```
### scss 
#### 기존 코드
```scss
&.next--card {
	--card-translateX-offset: calc(var(--card-width) * 1.1);
	--card-rotation-offset: -25deg;
}
```
#### 변경 코드
```scss
&.nextnext--card {
	--card-translateX-offset: calc(var(--card-width) * 1.6);
	--card-rotation-offset: -25deg;
}
```
#### 기존 코드
```scss
.cardList {
  position: absolute;
  width: calc(3 * var(--card-width));
  height: auto;
```
#### 변경 코드
```scss
.cardList {
  position: absolute;
  width: calc(5 * var(--card-width));
  height: auto;

```

### 자바스크립트
#### 기존 코드
```javascript
	function swapCardsClass() {
		currentCardEl.classList.remove("current--card");
		previousCardEl.classList.remove("previous--card");
		nextCardEl.classList.remove("next--card");

		currentCardEl.style.zIndex = "50";
		currentBgImageEl.style.zIndex = "-2";

		if (direction === "right") {
			previousCardEl.style.zIndex = "20";
			nextCardEl.style.zIndex = "30";

			nextBgImageEl.style.zIndex = "-1";

			currentCardEl.classList.add("previous--card");
			previousCardEl.classList.add("next--card");
			nextCardEl.classList.add("current--card");

```

#### 변경 코드
```javascript
  function swapCardsClass() {
    currentCardEl.classList.remove("current--card");
    previousCardEl.classList.remove("previous--card");
    nextCardEl.classList.remove("next--card");
    previousPreviousCardEl.classList.remove("previousprevious--card");
    nextNextCardEl.classList.remove("nextnext--card");

    currentCardEl.style.zIndex = "50";
    currentBgImageEl.style.zIndex = "-2";

    if (direction === "right") {
      previousCardEl.style.zIndex = "20";
      nextCardEl.style.zIndex = "30";
      previousPreviousCardEl.style.zIndex = "4";
      nextNextCardEl.style.zIndex = "5";
      nextBgImageEl.style.zIndex = "-1";

      currentCardEl.classList.add("previous--card");
      previousCardEl.classList.add("previousprevious--card");
      previousPreviousCardEl.classList.add("nextnext--card");
      nextCardEl.classList.add("current--card");
      nextNextCardEl.classList.add("next--card");

```

## 스크린샷
### 템플릿
![](https://images.velog.io/images/lky9303/post/4e713361-148a-412a-95c7-f0696938ccd2/image.png)
### 포트폴리오
![](https://images.velog.io/images/lky9303/post/af83cde4-4d11-47b3-b009-9c4896ad7574/image.png)
