# Storeオブジェクトをモジュールに分割

## 要約

ストアをモジュールにすることで、アプリが大規模になって、ストアが大きくなっても分割することが出来ます。

## 説明

以下の手順で行います

1. モジュール１を作成
2. モジュール２を作成
3. モジュール１と２よりストアを定義する

## 書式

### HTML

```html

```

### JS

```jsx

```

### 出力結果

> 

## サンプルコード

storeオブジェクトをモジュールに分割してみましょう！

## JS

```jsx
<script src="https://cdn.jsdelivr.net/npm/vue"></script>
<script src="https://unpkg.com/vuex@3.1.2/dist/vuex.js"></script>

<script>
  // moduleAを定義してください
  const moduleA = {
    state: { message: 'Hello moduleA'},
    mutations: {},
    actions: {},
    getters: {}
  }
  
  const moduleB = {
    state: { message: 'Hello moduleB' },
    mutations: {},
    actions: {},
    getters: {}
  }
  
  // moduleA,Bよりstoreを定義してください
  const store = new Vuex.Store({
    modules: {
      a: moduleA,
      b: moduleB
    }
  })
  
  // state全体を出力
  console.log(store.state)
  // モジュールAのストアを出力
  console.log(store.state.a.message)
  // モジュールBのストアを出力
  console.log(store.state.b.message)
</script>
```

### 出力結果

> {
"a": {
"message": "Hello moduleA"
},
"b": {
"message": "Hello moduleB"
}
}
Hello moduleA
Hello moduleB
