# Teaset

React Native UI 组件库, 超过 20 个纯 JS(ES6) 组件, 专注于内容展示和操作控制。

Teaset 设计精巧, 不依赖任何第三方库, 全部源代码不压缩时也只有 300+k, 即使加上图标文件也不足 600k, 如果只需要使用其中的少量组件, 也可以使用按需加载方式只加载需要使用的组件。

Teaset 组件采用 React Native 原生组件同样的风格来编写, 可以与 React Native 无缝融合开发, 你不需要太多的学习成本即可掌握。由于使用纯 JS 开发, 因此在 iOS 和 Android 下的表现形式几乎一样。

利用 Teaset, 你可以快速搭建 App 页面框架, 丰富的 UI 组件大大改善页面开发效率, 强大的 Overlay 浮层类把你从繁琐的交互控制中解放出来, 使得你可以专注于业务与逻辑。


![](https://github.com/rilyu/teaset/blob/master/screenshots/00-Teaset1.png?raw=true) ![](https://github.com/rilyu/teaset/blob/master/screenshots/00-Teaset2.png?raw=true)

# 快速上手

## 安装
在你的 React Native App 工程根目录下执行以下命令进行安装:
```
npm install --save teaset
```

## Hello world
从 teaset 包中 import 组件即可使用
```
import React, {Component} from 'react';
import {View, AppRegistry} from 'react-native';

import {Label} from 'teaset';

class HelloWorldApp extends Component {
  render() {
    return (
      <View style={{flex: 1, alignItems: 'center', justifyContent: 'center'}}>
        <Label size='xl' text='Hello world!' />
      </View>
    );
  }
}

AppRegistry.registerComponent('HelloWorldApp', () => HelloWorldApp);
```
## 按需加载
使用单独 import 组件实现按需加载
```
import Label from 'teaset/components/Label/Label';
```

## 运行示例程序
从 github clone teaset 工程(或者下载 zip 文件):
```
git clone https://github.com/Sigeu/teaset-example.git
cd teaset-example
npm install
```
在 iOS 下运行:
```
cd ios && pod install && cd ..
react-native run-ios
```
在 Android 下运行:
```
react-native run-android
```

## 动画流畅度
在使用 debug 模式运行, 特别是在 Android 设备上运行时, 部分动画效果不太流畅, 有时会有卡顿现象, 这是由于 debug 模式下有日志输出、远程调试等操作比较耗时导致, 在 release 模式下运行完全没有问题。

## iPhoneX
从 0.6.0 开始全面支持 iPhoneX 、 iPhoneXS ，且默认**打开**自动适配开关。

如使用了 SafeAreaView 请使用 ```Theme.set({fitIPhoneX: false})``` 手动关闭。

## Redux
如果你使用了 Redux ，需要使用 ```<TopView>``` 包裹 container ，用于给 Overlay 类型的组件提供容器(感谢 [@Alexorz](https://github.com/Alexorz) 的贡献)。

```
import { TopView } from 'teaset';

container => () => <Provider store={store}><TopView>{container}</TopView></Provider>
```

# 文档
请进入原作者Github阅读文档 [teaset](https://github.com/rilyu/teaset/blob/master/docs/cn/README.md)

# License
MIT