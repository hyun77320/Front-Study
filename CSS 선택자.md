## 1. CSS 선택자(Selector)란?

**1.0 개념**

말 그대로 선택을 해주는 요소이다.

이를 통해 특정 요소들을 선택하여 타일을 적용할 수 있게 된다.



**1.1 Rule Set**

Rule Set은 HTML안의 특정 요소들을 어떻게 할 것인지 알려주는 CSS문장이다.

```css
h1 {
    color: black;
}
```



## 2. 선택자(Selector)의 종류

**2.1 전체 선택자(Universal Selector)**

전체 선택자는 HTML페이지 내부의 모든 태그에 같은 CSS속성을 적용한다.

!! 문서안의 모든 요소를 읽어내려야 하기 때문에 느리다 !!

```css
* { margin: 0; text-decoration: none; }
```



**2.2 태그 선택자(Type Selector)**

태그에 대한 스타일만 지정이 된다.

```css
p { background: yellowgreen; color: darkgreen; }

<!-- HTML -->  
<p>태그 선택자(Type Selector)</p>  
<div>태그 선택자(Type Selector)</div> 
```



**2.3 클래스 선택자(Class Selector)**

클래스 선택자는 주어진 값은 class속성값으로 가진 HTML요소를 찾아 선택한다.

선택하려는 속성값 앞에 마침표를 추가하여 작성한다.

```CSS
.class1 { background: yellowgreen; color: darkgreen; }
div.class2 { background: darkgreen; color: yellowgreen; }
```



**2.4 ID 선택자(ID Selector)**

ID 선택자는 마침표 대신 #을 사용한다.

클래스 선택자와 매우 유사하다.

```CSS
div#id2 { background: darkgreen; color: yellowgreen; }
```



#### *클래스 선택자와 ID선택자*

* 한 페이지 내에서 여러 번 반복될 필요가 있는 스타일을 클래스, 유일하게 적용될 스타일은 ID 선택자를 사용하는 것이 좋다.
  * class속성은 어떤 분류 안에 포함된 요소의 특성을 정의하는 데 사용된다.
  * id속성은 어떤 요소에 대해 유일한 특성을 정의한다.
* ID 선택자의 클래스 선택자의 우선순위보다 높다.



**2.5 복합 선택자(Combinator)**

복합 선택자는 두 개 이상의 선택자 요소가 모인 선택자이다.

태그들이 포함 관게를 가질 때 포함하는 요소를 부모요소, 포함되는 요소를 자식요소라고 한다.

하위 선택자는 부모 요소에 포함된 모든 하위 요소에 스타일을 적용하지만, 자식 선택자는 부모의 바로 아래 자식에만 적용한다.

```css
/* 하위 선택자 */
section ul { border: 1px dotted black; }

/* 자식 선택자 */
section>ul { border: 1px dotted black; }
```

**2.5.1 인접 형제 선택자와 일반 형제 선택자**

같은 부모 요소를 가지는 요소들을 형제 관계라고 부른다.

먼저 나오는 요소는 형, 나중에 나오는 요소는 동생 요소이다.

인접 형제 선택자는 형제 중 첫번째 동생 요소가 조건을 충족시킬 때에만 스타일을 적용하지만 일반 형제 선택자는 조건을 충족하는 모든 동생 요소에 스타일을 적용한다.

```css
/* 인접 형제 선택자 */
h1+ul { background: yellowgreen; color: darkgreen; }

/* 일반 형제 선택자 */
h1~ul { background: darkgreen; color: yellowgreen; }
```

