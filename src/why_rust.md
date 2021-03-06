# なぜRustなのか
Gtk+アプリケーション開発の際に、Rustを利用するメリットは以下の通りです。

## ランタイムが軽量な言語環境
Rustは、静的型付けのコンパイラ型言語で、コンパイラはネイティブコードを出力します。
C++のようにスコープによるリソース管理を前提とするため、GCレスで言語ランタイムが軽量です。

インタプリタによる言語解釈や、言語ランタイムによる起動のオーバーヘッドが少ない分、
軽快な動作が可能です。

## とっつきやすいC言語系の文法＋GUIアプリケーションに便利な記法
CやJava, C#のようなC言語系の文法のため、比較的とっつきやすい記法になっています。

また、Rubyのイテレータの記法に似た、イベント処理に便利なクロージャの記法をサポートしており、
Gtk+をCから利用する場合と比較してスムーズなイベントハンドラの記述が可能です。

## 言語レベルでのデータ競合安全性の担保
GUIアプリケーションでは、UIのブロッキングを防ぐため、長時間の処理をスレッドで
行うことがあります。Rustではデータのスレッド境界越えに対して、言語レベルで保護機構を
備えているため、意図しないデータ競合を減らすことが可能です。
（不用意なスレッド境界越えを記述しようとすると、コンパイルエラーになります。）
