---
title: "Value vs Reference"
emoji: "📑"
type: "tech" # tech: 技術記事 / idea: アイデア
topics: ['Javascript']
published: true
---


例えば、

```js
const a = 1
const b = 1

console.log(a === b) // true
```
これは単純に`true`になる。


しかし、

```js
const a = [1]
const b = [1]

console.log(a === b) // falseになる。
```
これだと`false`になる。

`Array`,`Object`,`function`,`date`などの`Object`はメモリ上の場所（アドレス）を保持するので
中身が同じ`Array`であろうが別々の`Object`のアドレスを保持しているので
ここで`false`になる。






