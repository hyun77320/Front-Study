## 2. 선택자(Selector)의 종류

**2.6 속성 선택자(Attribute Selectors)**

속성 선택자는 태그 안의 특정 속성들에 따라 스타일을 지정함.

속성 값의 조건에 따라 다양한 스타일을 지정할 수 있기 때문에 활용도가 높음.

```css
/* E[attr]형식 */
a[href] { background: yellowgreen; color: black; }

/* E[attr="val"]형식 */
input[type="text"] { width: 150px; border: 1px solid #000; }

/* E[attr$="val"]형식 */
a[href$=".xls"] { background: darkgreen; }
```

속성 선택자는 모두 앞쪽에 태그명과 대괄호 사이 속성에 관련된 내용을 넣어서 선택함.



**2.6 가상 클래스 선택자(Pseudo-Classes Selector)**

웹 문서의 소스에는 존재하지 않지만 필요에 의해 임의로 가상의 선택자를 지정하여 사용하는 것.

:link와 :visited는 문서 안의 링크와 관련된 선택자.

나머지 세가지 선택자는 링크 요소뿐만 아니라 다른 요소에도 적용 가능함. 

:active선택자는 해당 요소가 활성화된 상태를 선택함. 

:hover선택자는 마우스 포인터가 해당 요소위에 올라가 있는 상태를 선택함.

마지막 :focus선택자는 해당 요소에 초점이 맞춰있는 상태를 선택함.



***구조적 가상 클래스 선택자(Structural pseudo-classes)***

구조적 가상 클래스 선택자는 위치를 기준으로 삼음.

요소가 위치에 따라 스타일을 다르게 지정 가능함.

![image-20200924224416771](C:\Users\user\AppData\Roaming\Typora\typora-user-images\image-20200924224416771.png)



**그 외의 선택자**

* 언어 선택자(language pseudo-classes)
* 부정 선택자(Negation pseudo-class)
* 목적 선택자(The target pseudo-class)
* UI요소 상태 선택자(The UI element states pseudo-classes)
* 가상 엘리먼트 선택자(Pseudo-Elements)



## 3. 선택자(Selector) 우선순위

스마일 시트는 다음과 같은 3개의 CSS원천 소스를 가질 수 있음.

- 제작자(author) 원천 소스 : 웹 사이트 제작자가 지정하는 자신의 페이지 스타일.
- 사용자(user) 원천 소스 : 사용자가 직접 정하는 자신이 사용할 스타일.
- 사용자 도구(user agent) 원천 소스 : 웹 브라우저 자체에 지정된 기본 스타일.

!! 스타일을 적용하는데 동시에 여러가지 방법을 사용하면 스타일이 충돌할 가능성이 있음 !!

-> 우선순위 규칙을 통해 스타일을 정확히 정용할 필요성이 있음.



#### 1) 원천소스 우선 순위

!important 선언을 한 사용자 스타일 > !important 선언을 한 제작자 스타일 > 제작자 스타일 > 사용자 스타일 > 사용자 도구 선언 (브라우저 자체의 선언).



#### 2) CSS명시도(Specificity) 계산법

```csss
!important > id [ 100 ] > class [ 10 ] > tag [ 1 ] > * [ 0 ]
```

!important선언을 사용한 형식이 가장 우선 순위가 높음.

나머지 선택자는 대괄호 안에 있는 숫자를 각각의 점수로 부여하여 우선순위를 계산.

- ID 선택자의 갯수를 세어서 개당 100 으로 계산합니다. (= a)
- 클래스 선택자의 갯수를 세어서 개당 10 으로 계산합니다. (= b)
- 태그 선택자의 갯수를 세어서 개당 1 로 계산합니다. (= c)
- 공용 선택자는 모두 0으로 계산합니다. (= d)
- 가상 엘리먼트는 무시합니다.

a > b > c > d



#### 3) 마지막에 지정된 스타일을 우선 적용

스타일 우선순위가 같거나, 계산 방법이 없는 경우 마지막에 지정된 스타일이 우선으로 적용됨.