# foldcontent-zhihu

> 用原生 js && jquery 实现知乎收起答案功能

> 具体实现可以看一下这篇[文章](https://segmentfault.com/a/1190000007503399) ٩(ˊᗜˋ*)و

## Introduction

src/ 目录下是原生 js 写法🌰

jquery/ 目录下是 jquery 写法🌰

## Install

* 请安装3.0.5及以上版本, version1.0.0 ~ 3.0.1 经测试存在 bug (>_<) 请已经 install 的盆友们更新一下吧

```
$ npm install foldcontent-zhihu@">=3.0.5" --save
```


## Usage

### 方法一: 引用原生 js 写法

#### 方法一: Work with module bundler

##### HTML
```HTML
<div class="foldcontent-panel">
    <div class="part-content"><!--此处是部分内容--></div>
    <div class="all-content"><!--此处是全部内容--></div>
</div>
<!-- ... -->
```

##### JS

```JS
var foldcontent = require('foldcontent');
var foldcontent_demo = new foldcontent({
        'btnBg': '#eff6fa',
        'btnColor': '#0c5897',
        'fixBtnBg': '#81baeb',
        'fixBtnColor': '#fff',
        'fontSize': '12px',
        'padding': '5px',
        'initialText': '展开',
        'fixText': '收起',
        'bottom': '10px',
        'right': '20px',
        'lineHeight': '1'
});
```

#### 方法二: 直接通过 script 标签引入 dist/目录下的 foldcontent.min.js 文件

##### HTML

```HTML
<div class="foldcontent-panel">
    <div class="part-content"><!--此处是部分内容--></div>
    <div class="all-content"><!--此处是全部内容--></div>
</div>
<!-- ... -->
<script src="foldcontent.min.js"></script>
```

##### JS

```JS
var foldcontent_demo = new foldcontent({
    // ...
});
```

### 方法二: 引用 jquery 写法 


#### HTML

```HTML
<div class="foldcontent-panel">
    <div class="part-content"><!--此处是部分内容--></div>
    <div class="all-content"><!--此处是全部内容--></div>
</div>
<!-- ... -->
<script src="../demo/js/01-jquery-1.11.3.min.js"></script>
<script src="foldcontent.min.js"></script>
```

#### JS
##### 方法一: script 标签引入 jquery/目录下的 foldcontent.jquery.js 文件

```JS
$('.unfold').foldContentPlugin({
                'btnBg': 'lightpink',
                'btnColor': '#fff',
                'paddingTop': '2px'
            });
```

##### 方法二: webpack 加载
```
// webpack 全局加载 jquery 的一种方法
 resolve: {         
    alias: {             
        jquery: path.resolve(js_path, 'lib/01-jquery-1.11.3.min.js')         
} },
 plugins: [          
    new webpack.ProvidePlugin({             
        $: 'jquery' // 将jquery暴露给所有模块，不用显式require('jquery')；只要模块的代码中出现了$，webpack就会自动将jQuery注入。         
    })
]
```
#### Options

```JS
{
    btnBg: '#eff6fa',     // 按钮背景颜色
    btnColor: '#0c5897',  // 按钮字体颜色
    fixBtnBg: '#81baeb',  // 固定定位按钮背景颜色
    fixBtnColor: '#fff',  // 固定定位按钮字体颜色
    fontSize: '12px',     // 按钮字体大小
    padding: '5px',       // 按钮尺寸
    initialText: '展开',   // 按钮初始文本内容
    fixText: '收起',       // 固定定位按钮文本内容
    bottom: '10px',       
    right: '20px',        // 绝对定位
    lineHeight: '1'       // 按钮行高
};
```

## How to Run 

```
$ npm install
$ npm start
```


## LICENSE

MIT

[MIT License](https://github.com/luyilin/foldcontent-zhihu/blob/master/LICENSE)
