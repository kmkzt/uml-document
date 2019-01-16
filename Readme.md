# SetUp
VSCodeのextensionを追加する。
https://github.com/shd101wyy/vscode-markdown-preview-enhanced

下記をインストール
```
brew install Graphviz
```

## UML 図の書き方
下記参考
https://qiita.com/ykawakami/items/f6688b845945669f0ce5

```PlantUML
@startuml

Foo -> Bar : メッセージ
Foo <-- Bar

@enduml
```

- class
  
```PlantUML
@startuml

class A {
  +id: number
  -name: string
  #func1()
  ~func2()
}
note left
  コメント複数行
end note

class B
note right: コメント一行

package サンプル {
  class C
}

note as N
  複数のクラスに紐付ける
end note

N .. B
N .. C


A - B : A-Bラベル
A -- C : A-Cラベル >
A --- D

A <|-- E
A <|.. F
A -() Interface
A "1" *-- "0..*" G

A .> B
note right on link
  A-Eに対するコメント
end note

@enduml
```


- diagram
```PlantUML
@startuml
digraph FSM {
  rankdir = LR;
  size = "8,5"
  bgcolor = transparent;

  node [color = grey60, fontcolor = grey80];

  node [shape = doublecircle];
  LR_0 LR_3 LR_4 LR_8;

  node [shape = circle];
  edge [color=grey60, fontcolor = grey80];
  LR_0 -> LR_2 [ label = "SS(B)" ];
  LR_0 -> LR_1 [ label = "SS(S)" ];
  LR_1 -> LR_3 [ label = "S($end)" ];
  LR_2 -> LR_6 [ label = "SS(b)" ];
  LR_2 -> LR_5 [ label = "SS(a)" ];
  LR_2 -> LR_4 [ label = "S(A)" ];
  LR_5 -> LR_7 [ label = "S(b)" ];
  LR_5 -> LR_5 [ label = "S(a)" ];
  LR_6 -> LR_6 [ label = "S(b)" ];
  LR_6 -> LR_5 [ label = "S(a)" ];
  LR_7 -> LR_8 [ label = "S(b)" ];
  LR_7 -> LR_5 [ label = "S(a)" ];
  LR_8 -> LR_6 [ label = "S(b)" ];
  LR_8 -> LR_5 [ label = "S(a)" ];
}
@enduml
```