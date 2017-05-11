## 一、开发背景

为了全面的熟悉Vue+Vue-router+Vuex+axios技术栈，结合V2EX的开放API开发了这个简洁版的V2EX。

## 二、项目优势

* 界面非常简洁
* 可以满足一般的浏览需求
* 项目使用Vue全家桶开发，具有参考意义
* ...

## 三、项目安装

项目兼容IE9+，使用项目前，请确保安装好了NodeJS。

```

git clone https://github.com/bergwhite/v2ex-vue.git  // 克隆项目
cd v2ex-vue  // 进入项目目录
npm install  // 安装依赖
npm run dev  // 运行项目

```

## 四、解决方案

### 4.1 跨域方案

通过配置代理表实现跨域

```

config/index.js
-------------------
proxyTable: {
  '/api': {
    target: 'https://www.v2ex.com',
    changeOrigin: true,
    pathRewrite: {
      '^/api': '/api'
    }
  }
}

```

### 4.2 Vuex支持IE

直接引入Vuex无法在IE中显示

```

npm install babel-polyfill --save-dev  // 安装babel-polyfill

src/main.js
---------------
import 'babel-polyfill'  // 在vue主文件中导入

```