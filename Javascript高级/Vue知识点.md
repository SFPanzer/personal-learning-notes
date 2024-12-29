# 第一章
## Vue是什么
- Vue 是一个轻量级的前端框架，专注于构建用户界面（UI）
- 与 Angular 和 React 相比，Vue 更加灵活，易于集成和使用。

## Vue特性
- 数据驱动视图：

    Vue 使用响应式的数据绑定来自动更新视图。

- 双向数据绑定：

    Vue 可以通过 `v-model` 实现数据与视图的双向绑定，简化了表单操作。

- 插件化开发：

    Vue 支持插件化开发，通过插件可以扩展 Vue 的功能。

- 轻量级：

    Vue 的体积较小，适合渐进式应用开发，可以逐步引入功能。

## Vue语法
- 指令：

    Vue 中的指令以 v- 开头，例如 v-bind、v-if、v-for。

- 自定义指令：

    Vue 支持用户自定义指令，但自定义指令的名称不能以 on- 开头（错误的说法）。

- 支持 Pinia 插件：

    Pinia 是 Vue 3 的官方状态管理库，取代 Vuex。

## MVVM
- Model：负责应用的业务数据。
- View：负责界面的渲染。
- ViewModel：负责连接 Model 和 View，监听数据变化并更新视图。

Model 和 View 不直接通信，数据通过 ViewModel 进行传递和更新。

## Node.js
- Node.js 是一个基于 Google V8 引擎的 JavaScript 运行环境，使得 JavaScript 能在服务器端运行。

## npm
- npm 是 Node.js 的包管理工具，管理 JavaScript 包的安装、卸载、更新等。
- 缓存：npm 会缓存已安装的包，避免重复下载。
- 安装顺序：npm 按顺序安装依赖，安装一个包时，必须等待当前包安装完成。
- `npm install <package-name>`：安装指定包。
- `npm uninstall <package-name>` 卸载指定包。
- `npm update` 更新包的版本。
- `npm install -g` 用来全局安装包，不是安装到项目中。

## yam
- `yarn add <package-name>`：安装指定包

# 第二章
## 单文件组件
- 脚本 `<script>`
- 模板 `<template>`

    在 Vue3 中可以包含多个根节点

- 样式 `<style>`


## 模板语法
- `v-model` 建立双向绑定

    `v-model` 用于在表单元素（如输入框、单选框、复选框等）和 Vue 数据之间建立双向绑定。它可以简化数据与视图之间的同步更新。

    ``` html
    <script>
    const str = ref('')
    </script>

    <template>
        <input v-model="str" type="text"/>
        <p>你输入的内容是：{{ str }}</p>
    </template>
    ```

    当用户输入内容时，str 会自动更新，

- `v-bind` 绑定属性

    `v-bind` 用来动态绑定一个 HTML 属性或组件的 prop。它可以让你绑定任意属性的值。

    ``` html
    <script>
        const imgSrc = ref('https://example.com/image.jpg')
    </script>

    <template>
        <img v-bind:src="imgSrc" alt="Image"/>
    </template>
    ```

    `v-bind:src` 会将 `imgSrc` 的值绑定到 `src` 属性上。如果 `imgSrc` 改变，`src` 属性也会自动更新。

- `v-on` 监听事件

    `v-on` 用于监听 DOM 事件，并在事件触发时执行方法。你可以绑定事件处理器，例如 `click`、`input`、`change` 等。

    ``` html
    <script>
        const count = ref(0)

        function increment() {
            count.value++
        }
    </script>

    <template>
        <!-- 监听 click 事件 -->
        <button v-on:click="increment">增加</button>
        <p>点击次数：{{ count }}</p>
    </template>
    ```

    `v-on:click` 监听按钮的点击事件，当点击按钮时，`increment` 方法会被调用，`count` 会增加。

    也可以使用简写 `@click`

- `v-for` 循环渲染列表

    `v-for` 用于在模板中渲染一个列表，可以根据数组或对象的内容动态生成多个 DOM 元素。

    ``` html
    <script>
        const fruits = ref(['苹果', '香蕉', '橙子'])
    </script>

    <template>
        <!-- 循环渲染水果列表 -->
        <ul>
            <li v-for="fruit in fruits" :key="fruit">{{ fruit }}</li>
        </ul>
    </template>
    ```

    `v-for="fruit in fruits"` 循环遍历 `fruits` 数组中的每一项，并渲染 `<li>` 元素。

    `:key="fruit"` 是每个dom的标识符，最好唯一，否则会产生bug

## 响应式数据

响应式数据就是Vue可以更新的动态数据，需要由特定的构造函数构建，这些函数均需要`import` 才能使用

``` js
import { xxx } from 'vue'
```

- `ref()`

    创建基本的数据类型

    ``` js
    var number = ref(0)

    // js修改变量要使用xx.value
    count.value++
    ```

- `reactive()`

    创建一个响应式对象

    ``` js
    const state = reactive({
        count: 0,
        name: 'Vue 3'
    })

    // 对象名.元素名 即可操作，无需加value
    state.count++ 
    ```

- `toRefs()` 与 `toRef()`

    用于把响应式对象解组，同时保留响应性

    ```js
    const state = reactive({
    count: 0,
    name: 'Vue 3'
    })

    // 解构每个元素
    const { count, name } = toRefs(state)

    // 解构特定元素
    const countRef = toRef(state, 'count')
    ```

- `computed` 计算属性

    ``` js
    const count = ref(2)
    const price = ref(50)

    // 使用 computed 来计算折扣后的价格
    const discountedPrice = computed(() => {
    return price.value * (1 - count.value / 100)
    })
    ```

- `watch` 监听器

    ```js
    const state = reactive({
        user: {
            name: 'Vue',
            age: 3
        }
    })

    // 深度监听 state.user 对象
    watch(() => state.user, (newValue, oldValue) => {
        console.log('用户信息变化了:', newValue)
    }, { deep: true })
    ```

# 第三章
## 生命周期
- onBeforeMount()：组件挂载之前调用。
- onMounted()：组件挂载完成后调用。
- onUpdated()：组件更新后调用。
- onUnmounted()：组件实例销毁后调用。

## 选项式api
通过定义一个包含多个选项的对象（例如 data、methods、computed、watch 等）来定义组件的各个部分。每个选项都有特定的功能，且有清晰的结构。

``` js
Vue.component('my-component', {
  // 1. 数据
  data() {
    return {
      message: 'Hello, Vue!'
    };
  },

  // 2. 计算属性
  computed: {
    reversedMessage() {
      return this.message.split('').reverse().join('');
    }
  },

  // 3. 方法
  methods: {
    greet() {
      console.log(this.message);
    }
  },

  // 4. 侦听器
  watch: {
    message(newVal, oldVal) {
      console.log(`Message changed from ${oldVal} to ${newVal}`);
    }
  }
});
```

## 组合式api
它通过 setup() 函数让我们能够在组件中组合和组织代码。

``` js
import { ref, computed, watch } from 'vue';

export default {
  setup() {
    // 1. 定义响应式数据
    const message = ref('Hello, Vue!');
    
    // 2. 计算属性
    const reversedMessage = computed(() => {
      return message.value.split('').reverse().join('');
    });

    // 3. 方法
    const greet = () => {
      console.log(message.value);
    };

    // 4. 侦听器
    watch(message, (newVal, oldVal) => {
      console.log(`Message changed from ${oldVal} to ${newVal}`);
    });

    // 返回需要暴露给模板的变量和方法
    return {
      message,
      reversedMessage,
      greet
    };
  }
};
```

# 第四章
## 动态组件

``` html
<template>
  <component :is="getComponent"></component>
</template>

<script>
import ComponentA from './ComponentA.vue';
import ComponentB from './ComponentB.vue';

export default {
  data() {
    return {
      isConditionMet: false,  // 条件
    };
  },
  computed: {
    getComponent() {
      return this.isConditionMet ? ComponentA : ComponentB;  // 根据条件返回不同组件
    }
  }
};
</script>
```

## 组件缓存

Vue 提供了一个名为 `<KeepAlive>` 的内置组件，用于缓存其包裹的子组件。所有被 `<KeepAlive>` 包裹的组件实例在切换时会被缓存，而不会被销毁。

## 插槽

插槽（Slot） 是 Vue 中的一种功能，允许父组件向子组件传递内容（通常是 HTML 或 Vue 组件），从而实现组件的 内容分发。

``` html
<template>
  <div>
    <header><slot name="header">默认头部内容</slot></header>
    <main><slot name="main">默认主体内容</slot></main>
    <footer><slot name="footer">默认底部内容</slot></footer>
  </div>
</template>
```

``` html
<template>
  <Child>
    <template v-slot:header>
      <h1>自定义头部</h1>
    </template>
    
    <template v-slot:main>
      <p>自定义主体内容</p>
    </template>
  </Child>
</template>

<script>
import Child from './Child.vue';

export default {
  components: {
    Child,
  },
};
</script>
```

## 私有自定义指令
## 自定义指令的生命周期

# 第五章
## Vue Router 基本概念
- 路由模式
    - hash模式
        ``` js
        const router = new VueRouter({
            mode: 'hash',  // 默认为 hash 模式，可以不写
            routes: [
                { path: '/', component: Home },
                { path: '/about', component: About }
            ]
        });
        ```
    - history模式
        ``` js
        const router = new VueRouter({
            mode: 'history',
            routes: [
                { path: '/', component: Home },
                { path: '/about', component: About }
            ]
        });
        ```    

- 动态路由

    不同的网址显示不同的内容

    ```js
    const routes = [
        {
            path: '/user/:id',  // :id 表示动态路由参数
            component: UserDetail
        }
    ];

    export default {
        created() {
            console.log(this.$route.params.id); // 输出动态参数 id 的值
        }
    };
    ```

- 子路由

    父路由的 children 数组中添加其他的路由

    ``` js
    const routes = [
        {
            path: '/user/:id',  // 父路由
            component: UserLayout,
            children: [
            {
                path: '',  // 空路径，表示默认子路由
                component: UserProfile
            },
            {
                path: 'settings',  // 子路由：/user/:id/settings
                component: UserSettings
            },
            {
                path: 'posts',  // 子路由：/user/:id/posts
                component: UserPosts
            }
            ]
        }
    ];
    ```

- 命名路由

    给路由添加name属性

    后续导航可以直接拿name去引用

## Vue Router 导航守卫
- 全局前置守卫

    一个钩子函数，在导航跳转前被触发

    

- 路由重定向
- 控制路由访问权限

## 路由视图和链接
- 路由视图
- 路由链接


