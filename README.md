# v-editor

[![Build Status](https://travis-ci.com/FEMessage/v-editor.svg?branch=master)](https://travis-ci.com/FEMessage/v-editor)
[![NPM Download](https://img.shields.io/npm/dm/@femessage/v-editor.svg)](https://www.npmjs.com/package/@femessage/v-editor)
[![NPM Version](https://img.shields.io/npm/v/@femessage/v-editor.svg)](https://www.npmjs.com/package/@femessage/v-editor)
[![NPM License](https://img.shields.io/npm/l/@femessage/v-editor.svg)](https://github.com/FEMessage/v-editor/blob/master/LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://github.com/FEMessage/v-editor/pulls)
[![Automated Release Notes by gren](https://img.shields.io/badge/%F0%9F%A4%96-release%20notes-00B2EE.svg)](https://github-tools.github.io/github-release-notes/)

根据 [wangEditor][wangeditor] 以及 [upload-to-ali][] 封装的轻量级富文本编辑器。

![view](./assets/view.png)

## Table of Contents

* **[Introduction](#introduction)**
* **[Feature](#feature)**
* **[Demo](#demo)**
* **[Pre install](#pre-install)**
* **[Install](#install)**
* **[Quick Start](#quick-start)**
* **[Props](#props)**
* **[Methods](#methods)**
* **[Events](#events)**
* **[Slots](#slots)**
* **[Dev](#dev)**
* **[License](#license)**
* **[Contributors](#contributors)**

## Introduction

公司内部对于富文本组件的需求比较简单：简单的图文编排。

因此选型富文本组件主要考虑：

### 组件大小

倾向于最轻量的富文本编辑器。

选型对比了业界比较出名（开源 star 比较高）的组件：quill，wangEditor,tinymce-vue,medium editor。

![view](./assets/diff.png)

[⬆ Back to Top](#table-of-contents)

### OSS 文件上传

搭载 [upload-to-ai][upload-to-ali] 组件，富文本组件能自动将图片上传到 oss，避免图片信息以 base64 编码形式保存在内容中，有效压缩文本信息。

[⬆ Back to Top](#table-of-contents)

## Feature

* **轻量**：最小的富文本编辑器，[组件选型范围](https://mubu.com/doc/sA3r4QKBK0) 参考了（quill,tinymce-vue,medium editor）
* **oss 上传**：整合了上传组件，只需配置 OSS 的基本信息([配置参考][upload-to-ali])，即可将图片上传到 oss，支持截图粘贴上传

[⬆ Back to Top](#table-of-contents)

## Demo

* [doc and online demo](https://femessage.github.io/v-editor/)

[⬆ Back to Top](#table-of-contents)

## Pre install

```
yarn add @femessage/upload-to-ali
```

[⬆ Back to Top](#table-of-contents)

## Install

```
yarn add @femessage/v-editor
```

[⬆ Back to Top](#table-of-contents)

## Quick start

```
//step1 确保oss配置

//step2 在需要使用该渲染器的.vue文件中
<template>
  <v-editor v-model="content"/>
</template>

<script>
import VEditor from '@femessage/v-editor'
export default {
  name: 'my-page',
  components: {
    VEditor
  },
  data(){
    return {
      content:''
    }
  }
}
</script>
```

[⬆ Back to Top](#table-of-contents)

## Props

| 参数          | 说明                                                                    | 类型    | 默认值                                            |
| ------------- | ----------------------------------------------------------------------- | ------- | ------------------------------------------------- |
| uploadOptions | 可自定义[upload-to-ali]上的所有属性                                     | Object  | {}                                                |
| editorOptions | 可自定义[wangEditor] 部分参数，例子如下：{debug:false, menus: ['head']} | Object  | **[defaultEditorOptions](#defaultEditorOptions)** |
| disabled      | 编辑器是否可编辑                                                        | Boolean | false                                             |
| height        | 编辑器高度，单位**px**                                                  | Number  | 400                                               |

### defaultEditorOptions（默认编辑器参数）

| 参数            | 说明                                                    | 类型    | 默认值                                                                                                                                                                  |
| --------------- | ------------------------------------------------------- | ------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| debug           | debug 模式下，有 JS 错误会以 throw Error 方式提示出来。 | Boolean | false                                                                                                                                                                   |
| onchangeTimeout | 自定义 onchange 触发的延迟时间，单位 **ms**             | Number  | 200                                                                                                                                                                     |
| menus           | 默认菜单配置                                            | Array   | ["head","bold","fontSize","fontName","italic","underline","strikeThrough","foreColor","backColor","link","list","justify","quote","image","table","code","undo","redo"] |

[⬆ Back to Top](#table-of-contents)

## Methods

| 方法      | 说明                                                           | 返回值      |
| --------- | -------------------------------------------------------------- | ----------- |
| getEditor | 返回的是 wangEditor 对象，用于调用[wangEditor api][wangeditor] | editor 对象 |

[⬆ Back to Top](#table-of-contents)

## Events

| 事件           | 说明                             | 回调参数   |
| -------------- | -------------------------------- | ---------- |
| upload-loading | 可监听并增加上传 loading 交互    | 是否加载中 |
| upload-error   | 可监听并增加上传错误时的提醒交互 | -          |

[⬆ Back to Top](#table-of-contents)

## Slots

| 插槽    | 说明           |
| ------- | -------------- |
| loading | 自定义上传文本 |

[⬆ Back to Top](#table-of-contents)

## Dev

install dependency

```
yarn

yarn add @femessage/upload-to-ali -P
```

run dev story

```
yarn story
```

publish to npm

```
npm publish --access public
```

[⬆ Back to Top](#table-of-contents)

## License

[MIT](./LICENSE)

[⬆ Back to Top](#table-of-contents)

[upload-to-ali]: https://github.com/FEMessage/upload-to-ali 'upload-to-ali'
[wangeditor]: https://github.com/wangfupeng1988/wangEditor 'wangEditor'

## Contributors

Thanks goes to these wonderful people ([emoji key](https://allcontributors.org/docs/en/emoji-key)):

<!-- ALL-CONTRIBUTORS-LIST:START - Do not remove or modify this section -->

<!-- prettier-ignore -->
<table><tr><td align="center"><a href="https://github.com/kunzhijia"><img src="https://avatars2.githubusercontent.com/u/4848041?v=4" width="100px;" alt="kunzhijia"/><br /><sub><b>kunzhijia</b></sub></a><br /><a href="https://github.com/FEMessage/v-editor/commits?author=kunzhijia" title="Code">💻</a> <a href="https://github.com/FEMessage/v-editor/issues?q=author%3Akunzhijia" title="Bug reports">🐛</a> <a href="https://github.com/FEMessage/v-editor/commits?author=kunzhijia" title="Documentation">📖</a></td><td align="center"><a href="https://github.com/listars"><img src="https://avatars2.githubusercontent.com/u/20613509?v=4" width="100px;" alt="listars"/><br /><sub><b>listars</b></sub></a><br /><a href="https://github.com/FEMessage/v-editor/issues?q=author%3Alistars" title="Bug reports">🐛</a> <a href="https://github.com/FEMessage/v-editor/commits?author=listars" title="Documentation">📖</a></td><td align="center"><a href="https://donaldshen.github.io/portfolio"><img src="https://avatars3.githubusercontent.com/u/19591950?v=4" width="100px;" alt="Donald Shen"/><br /><sub><b>Donald Shen</b></sub></a><br /><a href="https://github.com/FEMessage/v-editor/issues?q=author%3Adonaldshen" title="Bug reports">🐛</a> <a href="https://github.com/FEMessage/v-editor/commits?author=donaldshen" title="Documentation">📖</a></td><td align="center"><a href="http://levy.work"><img src="https://avatars3.githubusercontent.com/u/9384365?v=4" width="100px;" alt="levy"/><br /><sub><b>levy</b></sub></a><br /><a href="#review-levy9527" title="Reviewed Pull Requests">👀</a> <a href="#infra-levy9527" title="Infrastructure (Hosting, Build-Tools, etc)">🚇</a> <a href="#ideas-levy9527" title="Ideas, Planning, & Feedback">🤔</a></td></tr></table>

<!-- ALL-CONTRIBUTORS-LIST:END -->

This project follows the [all-contributors](https://github.com/all-contributors/all-contributors) specification. Contributions of any kind welcome!
