# 이 프로젝트는 Vue.js의 공부를 위해서 제작되었습니다.

## Vue.js는 사용자 인터페이스를 만들기 위한 프로그레시브 "프레임워크" 입니다.

### 시작하기

```javaScript
<!-- 개발버전, 도움되는 콘솔 경고를 포함. -->
<script src="https://cdn.jsdelivr.net/npm/vue/dist/vue.js"></script>
```

### 선언적 랜더링

- Vue.js의 핵심에는 간단한 템플릿 구문을 사용하여 DOM에서 데이터를 선언적으로 렌더링 할 수있는 시스템이 있습니다.

```HTML
<div id="app">
  {{ message }}
</div>
```

```javaScript
var app = new Vue({
  el: '#app',
  data: {
    message: '안녕하세요 Vue!'
  }
})
```

### 디렉티브 속성.

- v-bind 속성은 '디렉티브'라고 합니다.
- '디렉티브'는 Vue에서 제공하는 특수 속성임을 나타내는 v- 접두어가 붙어있으며 사용자가 짐작할 수 있듯 렌더링 된 DOM에 특수한 반응형 동작을 합니다.

### 조건문과 반복문

```HTML
<div id="app-3">
  <p v-if="seen">이제 나를 볼 수 있어요</p>
</div>
```

```javaScript
var app3 = new Vue({
  el: '#app-3',
  data: {
    seen: true
  }
})
```

- Vue 엘리먼트가 Vue에 삽입/업데이트/제거될 때 자동으로 트랜지션 효과를 적용할 수 있는 강력한 전환 효과 시스템을 제공합니다.

### v-for의 사용법

```HTML
<div id="app-4">
  <ol>
    <li v-for="todo in todos">
      {{ todo.text }}
    </li>
  </ol>
</div>
```

```javaScript
var app4 = new Vue({
  el: '#app-4',
  data: {
    todos: [
      { text: 'JavaScript 배우기' },
      { text: 'Vue 배우기' },
      { text: '무언가 멋진 것을 만들기' }
    ]
  }
})
```

### 이벤트 리스너 사용하기

- v-on 디렉티브를 사용하여 Vue 인스턴스에서 메소드를 호출하는 이벤트 리스너를 추가 할 수 있습니다.

```HTML
<div id="app-5">
  <p>{{ message }}</p>
  <button v-on:click="reverseMessage">메시지 뒤집기</button>
</div>
```

```javaScript
var app5 = new Vue({
  el: '#app-5',
  data: {
    message: '안녕하세요! Vue.js!'
  },
  methods: {
    reverseMessage: function () {
      this.message = this.message.split('').reverse().join('')
    }
  }
})
```

### 컴포넌트 만들기

- todo-item 이름을 가진 컴포넌트를 정의합니다

```javaScript
Vue.component('todo-item', {
  template: '<li>할일 항목 하나입니다.</li>'
})
var app = new Vue(...)
```

```HTML
<ol>
  <!-- todo-item 컴포넌트의 인스턴스 만들기 -->
  <todo-item></todo-item>
</ol>
```

### props 사용하기

```javaScript
Vue.component('todo-item', {
  // 이제 todo-item 컴포넌트는 "prop" 이라고 하는
  // 사용자 정의 속성 같은 것을 입력받을 수 있습니다.
  // 이 prop은 todo라는 이름으로 정의했습니다.
  props: ['todo'],
  template: '<li>{{ todo.text }}</li>'
})
```

### 디렉티브 종류

- v-model
- v-if ,v-else는 형제 태그이면서 인접해야 작동합니다.

## 궁금한점

- 문자열 템플릿이란?
