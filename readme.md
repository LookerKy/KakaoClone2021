## CSS 요소 정리
---
### :nth-child(n)

- **`:nth-child(n)`** 는 n번째 자식 선택자로써 단일로 쓴다면 body 내부의 구획에 존재하는 모든 n번째 요소를 가르킨다.  

  EX )
```html
<body>
    <div> <!-- div:nth-child(1) -->
        <div class="section-around"> <!-- div:nth-child(1) -->
            <div class="circle"></div> <!-- div:nth-child(1) -->
            <div class="circle"></div> <!--div: nth-child(1) div: nth-child(2) -->
            <div class="circle"></div>
        </div>
        <div class="section-wave">
            <div class="square"></div> <!-- div:nth-child(1) -->
            <div class="square"></div>
            <div class="square"></div>
            <div class="square"></div>
            <div class="square"></div>
        </div>
    </div>
</body>
```


```css
div: nth-child(1) {
  background-color: black;
}
div: nth-child(1) div: nth-child(2) {
  background-color: blue;
}
```

---
### **`:nth-child(an+b)`** 는 a,b는 사용자 지정 변수이며 n은 0부터 1씩 증가하는 변수이다.  



---
### :nth-last-child(n)

- **`:nth-last-child(n)`** 은 마지막 요소로 부터 n번째 선택자이다. 다만 body아래의 최상단의 요소가 두개 이상 있더라도 최상단의 요소의 마지막 요소는 선택되지 않는다.
  ex)
```html
<body>
    <div> 
        <div class="section-around"> 
            <div class="circle"></div> 
            <div class="circle"></div> 
            <div class="circle"></div> <!-- div:nth-last-child(1) -->
        </div>
        <div class="section-wave">
            <div class="square"></div> 
            <div class="square"></div>
            <div class="square"></div>
            <div class="square"></div>
            <div class="square">
                <div class="semi-black"></div>
                <div class="semi-black"></div> <!-- div:nth-last-child(1) -->
            </div> <!-- div:nth-last-child(1) -->
        </div>
    </div>
</body>
```
```css
div: nth-last-child(1) {
  background-color: black;
}
```

---
### :first-child

- **`:fist-child`** 는 자식 요소 중 가장 첫번째를 선택하는 요소입니다. 다만 명시한 선택요소가 반드시 물리적으로 첫번째에 위치해 있어야 합니다.

```html
<div> 
    <div>text1</div> 
    <p>text2</p> <!-- 여긴 적용되지 않음-->
    <p>text3</p> 
</div>
<div> 
    <p>text1</p> <!-- div p:first-child -->
    <div>text2</div> 
    <p>text3</p> 
</div>

```

```css
div p:first-child {
    background-color : green;
}
```

---
### :first-of-type

- **`:first-of-type`** 은 자식 요소 중 가장 첫번째를 선택하는 요소입니다. 이는 `first-child`와는 달리 선택 요소 중 논리적으로 첫번째에 있는 선택요소에 적용 됩니다.

```html
<div> 
    <div>text1</div> 
    <p>text2</p> <!-- div p:first-of-type -->
    <p>text3</p> 
</div>
<div> 
    <p>text1</p> <!-- div p:first-of-type -->
    <div>text2</div> 
    <p>text3</p> 
</div>

```

```css
div p:first-of-type {
    background-color : green;
}
```
