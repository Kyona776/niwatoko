# 要件定義書

## 1. 足し算モジュール

### 1.1 概要
2つの数値を足し算する関数、数値のリストの合計を計算する関数、複数の数値を足し算する関数を提供する。

### 1.2 機能
1. `add(a, b)`: 2つの数値 `a` と `b` を足し算する関数
    - 入力: 2つの数値 (`a`, `b`)
    - 出力: `a` と `b` の和 (int または float)
2. `add_list(numbers)`: 数値のリスト `numbers` の合計を計算する関数
    - 入力: 数値のリスト (`numbers`)
    - 出力: `numbers` の合計値 (int または float)
3. `add_multiple(*args)`: 複数の数値を足し算する関数
    - 入力: 可変長引数 (`*args`)
    - 出力: 引数として渡された数値の合計 (int または float)

### 1.3 使用方法
1. `add(a, b)` を使用して2つの数値の和を計算する
2. `add_list(numbers)` を使用して数値のリストの合計を計算する
3. `add_multiple(a, b, c, ...)` を使用して複数の数値の合計を計算する

## 2. 掛け算モジュール

### 2.1 概要
2つの数値を掛け算する関数、数値のリストの積を計算する関数、複数の数値を掛け算する関数を提供する。

### 2.2 機能
1. `multiply(a, b)`: 2つの数値 `a` と `b` を掛け算する関数
    - 入力: 2つの数値 (`a`, `b`)
    - 出力: `a` と `b` の積 (int または float)
2. `multiply_list(numbers)`: 数値のリスト `numbers` の積を計算する関数
    - 入力: 数値のリスト (`numbers`)
    - 出力: `numbers` の積 (int または float)
3. `multiply_multiple(*args)`: 複数の数値を掛け算する関数
    - 入力: 可変長引数 (`*args`)
    - 出力: 引数として渡された数値の積 (int または float)

### 2.3 使用方法
1. `multiply(a, b)` を使用して2つの数値の積を計算する
2. `multiply_list(numbers)` を使用して数値のリストの積を計算する
3. `multiply_multiple(a, b, c, ...)` を使用して複数の数値の積を計算する