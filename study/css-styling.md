# CSS

## 전통적인 css 작성방법

- 선택자에 의해 의도치 않은 수정사항이 발생할 수 있음
- 특히 우선 순위 때문에 의도치 않은 side effect 발생할 확률이 높아짐, `!important` 남용 가능성
- 프로젝트 규모가 커질수록 관리가 어려워짐
- global namespace 하나만 존재하기 때문에 name 충돌이 자주 일어남

## CSS를 발전시킨 방법

### Sass

- css preprocessor
- 함수, 변수, mixin 등 추가적인 기능들을 지원함으로써 css를 더 효율적으로 작성할 수 있게 함

### BEM

- Block, Element, Modifier의 약자
- `form__submit--disabled` 같은 방식으로 사용함
- 클래스명을 짓는 방법론으로, css를 더 효율적으로 작성할 수 있게함

### CSS Module

- css의 고질적인 문제인 global namespace를 해결한 방법
- `index.module.css` 같은 방식으로 css를 모듈단위로 나눠서 관리

## CSS in JS(emotion)

- 위 방법들의 단점들을 해결하기 위해서 등장한 방법
- 아예 js 안에 CSS를 입력하면서, 모듈 단위의 관리가 가능하게 함
- 유명한 라이브러리로는 emotion, styled-components 가 있음
- 모듈 크기는 더 가벼우면서, 확장성이 뛰어난 emotion을 채택하기로 결정
- 작성 예시

  ```
  import React from 'react';
  import styled from '@emotion/styled';

  const Container = styled.div`
      display: flex;
      justify-content: space-between;
  `;

  function Test(){
      return (<Container>Hello</Container>);
  }

  export default Test;
  ```

## Reference

[emotion을 활용한 크몽 프론트엔드 스타일링 시스템 (brunch.co.kr)](https://brunch.co.kr/@kmongdev/17#comment)
