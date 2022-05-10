# Motoko Chinese Document



<p style="text-align: center; width: 400px">
    <img src="https://smartcontracts.org/img/IC_logo_horizontal.svg" />
</p>


## 什么是 Motoko ?

> The Motoko programming language is a new, modern and type safe language for developers who want to build the next generation of distributed applications to run on the Internet Computer blockchain network. Motoko is specifically designed to support the unique features of the Internet Computer and to provide a familiar yet robust programming environment. As a new language, Motoko is constantly evolving with support for new features and other improvements.

以上为官方所述，中文翻译👇🏻

> Motoko编程语言是一种新型、现代且类型安全的语言，适用于希望构建下一代分布式应用程序以在互联网计算机区块链网络上运行的开发人员。Motoko专门设计用于支持互联网计算机的独特功能，并提供一个熟悉但强大的编程环境。作为一种新语言，Motoko在不断发展，支持新功能和其他改进。

## 可以学到什么 ？

> `Motoko` 目前没有中文开发文档和详细的教程，因此整理出中文开发文档，方便于对 `ic` 开发感兴趣的开发者，或者是刚入门的开发人员或新手进行学习与交流，利于 `Dfinity` 生态建设，为即将到来的 `Web3` 做好准备，你是否也想开发出令人激动的 `Dapp` ？ 那就一起！

## 准备
* 安装 `Dfinity` SDK ( Mac/Linux 用户 )

```
sh -ci "$(curl -fsSL https://sdk.dfinity.org/install.sh)"
```

* 查看版本

```
dfx --version
```

* 安装 `Node.js` 

> 进入官网下载 [Node.js官网](https://nodejs.org/en/), 建议下载稳定版安装

## Motoko 在线编译器

> 点击进入 [Motoko 在线编译器](https://m7sm4-2iaaa-aaaab-qabra-cai.raw.ic0.app/), 建议下载稳定版安装

## 注释

// 单行注释

/* 多行注释 */

## 变量
Motoko 中分为可变变量 `var`  、常量 `let`

> 可重新赋值
```
var count = 1
count := 2  // success
```

> 不可重新赋值
```
let count = 1
count := 2  // error 
```

## 数据类型

**文本**  `Text, Char`

```
var flag : Char = '\u{6a}'
var message : Text = "hello，world";
```

**数字**  `Nat8, Nat16, Nat32, Nat64, Int8, Int16, Int32, Int64`

```
var age : Nat = 24;  // 默认Nat为Nat16
age := -1; // error
```

```
var age : int = 24;  // 默认Int为Int16
age := -1; // success
```

**浮点数** `Float`

```
var balance : Float = 100.999
balance := -100.999
```

**布尔** `Bool`

```
var flag : Bool = true
flag: Bool = false
```

**元祖** `(Bool, Float, Text)`

```
let tuple = (true or false, 0.6 * 2.0, "foo" # "bar");
```

**Options** `?Text`

```
func display (x : ?Text) : () {
  switch x {
    case (null) { ignore "No value" };
    case (?y) { ignore "Value: " # y };
  };
};

display(null)
display(?"Test")

```

**数组** `[Text], [var Nat]`

```
可变数组
let counters = [var 1, 2, 3];
counters[0] := 2; // success

不可变数组
let counters = [1, 2, 3];
counters[0] := 2; // error
```

**Records**  `{first : Text; last : Text; salary : var Nat}`

```
let employee = { first = "John"; last = "Doe"; var salary = 12 };
```

**结构体** 

```
    type Person = {
        name: Text;
        age: Nat
    };
    let xiaoming : Person = {
        name = "小明";
        age = 33;
    };
```