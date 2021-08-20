## RailsのためのRuby入門

Railsを習得するにあたってRubyの文法を学びます。
Rubyではオブジェク概念を理解する。

### 文字列

`irb`を使ってターミナル上でスクリプトを実行しながら動作確認を行う

```rb
irb(main):001:0> 'endu'
=> "endu"
irb(main):002:0> "takahashi"
=> "takahashi"
```

### 数値

数値もオブジェクトになる。

```rb
irb(main):003:0> 1
=> 1
irb(main):004:0> 1+3
=> 4
```

### オブジェクトに自分が何者か確認する

`***.class`で確認できる。

```rb
irb(main):005:0> 'endu'.class
=> String
irb(main):006:0> 1.class
=> Integer
```

それぞれのオブジェクトがRubyの世界で固有の存在として生成される。  
ただ、文字列オブジェクトはRubyが実行されるたびに、別のオブジェクトが作られる。  
数値オブジェクトは、同じ数値オブジェクトが提供される。  


```rb
irb(main):006:0> 1.class
=> Integer
irb(main):007:0> 'endu'.object_id
=> 70325841052520
irb(main):008:0> 1.object_id
=> 3
```

### クラスとインスタンスについて

鯛焼きで例えると

```
クラス: 鯛焼きを生成する機器
インスタンス: 鯛焼き
```

インスタンスオブジェクトは単に「インスタンス」、「オブジェクト」と呼んだりする。

### オブジェクトの機能はクラスで決める

Stringオブジェクトだと、`length`メソッドが使えるので文字数をカウントができる。

```rb
irb(main):008:0> 'endu'.length
=> 4
```

一方でIntagerオブジェクトでは`length`メソッドは提供していない。
使うと以下のように怒られる。

```rb
irb(main):009:0> 1.length
Traceback (most recent call last):
        4: from /Users/futoshi.endo/.rbenv/versions/2.6.6/bin/irb:23:in `<main>'
        3: from /Users/futoshi.endo/.rbenv/versions/2.6.6/bin/irb:23:in `load'
        2: from /Users/futoshi.endo/.rbenv/versions/2.6.6/lib/ruby/gems/2.6.0/gems/irb-1.0.0/exe/irb:11:in `<top (required)>'
        1: from (irb):9
NoMethodError (undefined method `length' for 1:Integer)
```

このようにオブジェクトによって提供されるメソッドが異なってくる為、Rubyでプログラムを作る場合はどんなクラスのオブジェクトにどんな機能があるかを知り、目的にあったクラスのオブジェクトを使う事が大切になってきます。
これらを調べたかったら「組み込みライブラリ」を元に確認すると良い。

[Ruby 組み込みライブラリ](https://docs.ruby-lang.org/ja/latest/library/_builtin.html)

>組み込みライブラリは Ruby 本体に組み込まれているライブラリです。このライブラリに含まれるクラスやモジュールは、 require を書かなくても使うことができます。

### 参考文献

- [オブジェクト指向スクリプト言語 Ruby リファレンスマニュアル (Ruby 3.0.0 リファレンスマニュアル)](https://docs.ruby-lang.org/ja/latest/doc/index.html)


