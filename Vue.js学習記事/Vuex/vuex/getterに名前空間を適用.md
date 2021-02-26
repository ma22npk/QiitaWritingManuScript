## 要約

## 説明

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

ゲッターに名前空間を適応してみましょう！

## html

```html

```

## JS

```jsx
<script src="https://cdn.jsdelivr.net/npm/vue"></script>
<script src="https://unpkg.com/vuex@3.1.2/dist/vuex.js"></script>

<script>
  const moduleA = {
    // namespacedを定義してください
    namespaced: true,
    getters: {
      doneTodos: state => {
        console.log('moduleAのゲッターが呼ばれました')
      }
    }
  }
  
  const moduleB = {
    namespaced: true,
    getters: {
      doneTodos: state => {
        console.log('moduleBのゲッターが呼ばれました')
      }
    }
  }
  
  const store = new Vuex.Store({
    modules: {
      a: moduleA,
      b: moduleB
    }
  })
  
  // gettersを呼び出す
  store.getters['doneTodos']
  store.getters['a/doneTodos']
  store.getters['b/doneTodos']
</script>
```

### 出力結果

> moduleAのゲッターが呼ばれました
moduleBのゲッターが呼ばれました
