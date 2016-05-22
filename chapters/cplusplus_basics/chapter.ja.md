# C++ Language Basics

*by [Josh Nimoy](http://jtnimoy.net)*

> The magician of the future will use mathematical formulas.
>
> **--Aleister Crowley, 1911**

> 未来の魔術師は数式を用いるだろう
>
> **--Aleister Crowley, 1911**

## Look Alive!

## さあ始めよう

This chapter introduces you to writing small computer programs using the C++ language. Although I assume very little about your previous knowledge, the literacy you gain from this chapter will directly influence your comprehension in subsequent chapters of the book, as most other topics stand on the shoulders of this one. Furthermore, the lessons herein are cumulative, meaning you can't skip one of the topics or you will get lost. If you get stuck on one of the concepts, please seek help in understanding specifically the part that did not make sense before moving on to the next topic. Following the lessons with this sort of rigor ensures that not only will you get the most out of openFrameworks, but computers in general.

この章ではC++を使って小さなコンピュータプログラムを書いてみます。事前知識については特に想定していませんが、本章で学ぶ知識は、この本の後の章の理解に大きく影響するでしょう。他のトピックはこの章を前提にしています。加えてここで学ぶ内容はひとつひとつ積み重ねていくようになっているので、途中を飛ばすと分からなくなってしまうでしょう。もしどれかひとつの概念につまづいたら、次に進む前に特に意味が分からなかった箇所を理解できるよう助けを求めましょう。このようなある種厳格な課題をこなすことでopenFrameworksだけでなく、コンピュータ一般についても有効な知識を得ることができます。


## Iteration

## 繰り返し

I did most of my drawing and painting in the mid-nineties, a high school AP art student sporting a long black ponytail of hair shaved with a step, round eyeglasses, and never an article of clothing without spill, fling, smattering, or splotch of Liquitex Basics acrylic paint. Bored out of my mind in economics class, playing with my TI-82 graphing calculator, I discovered something that flipped a light bulb on in my heart. Unlike smaller calculators around my house growing up, the TI-82 had a thick instruction manual. Amidst sections in this manual about trigonometry functions and other dry out-of-reach science, something caught my thirsty, young eye: a sexy black-on-white pyramid with smaller upside-down pyramids infinitely nested inside, shown in Figure 1.

90年代の半ば、サイドを刈り上げたのポニーテールに丸メガネ、リキテックス・ベーシックスの飛沫や染みのついた服を常に着た
アドバンスト・プレースメント（優秀な高校生に対して大学のカリキュラムを与えること）の学生だった私は、人生の大半の素描や絵画を描きました。経済学の授業にすっかり飽きてTI-82グラフ計算機で遊んでいた私は、何かが心の中の電球のスイッチを入れたのを感じました。私が育った家にあったもっと小さな電卓と違って、TI-82には分厚い説明書が付いていました。この説明書の中の三角関数や素っ気なく理解の及ばない科学についてのページに、何かを求める若者の目を捉えたものがありました。図1に示した、白黒のピラミッドの中により小さな逆さまのピラミッドが無限に繰り返されている絵です。



![図1: TI-82によるシェルピンスキーの三角形の出力, Courtesy of Texas Instruments](images/sierpinski-fractal-ti82.png "Figure 1: TI-82 rendering of the Sierpinski triangle, Courtesy of Texas Instruments")

This fractal, the famous [Sierpinski triangle](https://www.wolframalpha.com/input/?i=sierpinski+triangle), accompanied about twenty-five computer instructions making up the full SIERPINS program. I looked closer at the code, seeing a few numeric operations – nothing too advanced, and most of it was commanding words, like "do this", or "if something then do another thing". I was able to key in the code from the book into the graphing calculator and run the program. At first, just a blank LCD panel. Slowly a few random pixels switched to black here and there, not really showing any pattern. After a few more seconds, the scene filled in and I could already see faint outlines of triangles. After a good long time, my calculator finally matched the picture in the book.

このフラクタル、よく知られた[シェルピンスキーの三角形](https://www.wolframalpha.com/input/?i=sierpinski+triangle)の図には、シェルピンスキのプログラムを構成する25個のコンピュータの指示が付いていました。コードをよく見ると、いくつかはそんなに難しくない数値の計算、残りのほとんどは「これを行え」、「もしこうならこれを行え」といった命令文でした。私は説明書をもとにコードを計算機に入力して実行することができました。液晶パネルは初め真っ白でした。次第にいくつかの点があちらこちらでまばらに黒く反転しましたが、特に規則性は見られません。数秒が経つと画面が埋まっていき、ぼんやりと三角形を見て取ることができるようになりました。さらに長い時間が経過し、計算機はついに説明書と同じ絵を完成させました。

My mind was officially blown. Certain things did not make sense. What sort of miracle of nature caused such a complex form to come from so little instruction? The screen had over six thousand pixels in it, so why is it that a mere twenty-five instructions was all it took to create this amazing, organism-like artwork? Whose artwork was it? Might I derive a new work from it? Rarely had I ever seen such a magical reward coming from so little work. I had found my new basics. I felt the need to understand the program because (I decided) it was important. I went back into the code and changed some of the numbers, then ran the program again. The screen went blank, then drew a different picture, only this time, skewed to the left, falling out of the viewport. Feeling more courageous, I attempted to change one of the English instructions, and the machine showed an error, failing to run.

本当に驚きました。何か理解できないことが起きています。どんな奇跡が起きてこんな複雑な形が、ほんの短い指示によって生み出されたのでしょう。画面には6000以上のピクセルがあります。なぜ、たった25行の指示だけでこの素晴らしい有機物のような作品を作ることができるのか。ここから違う作品を作ることもできるのか。本当に少しの仕事でこんな魔法のような成果が得られるなんてほとんど見たことがありません。私は自分の新しい基礎になるものを見つけました。このプログラムは重要で、理解する必要があることだと思いました。私はコードに立ち戻っていくつかの数値を変えてもう一度実行してみました。画面は真っ白になり、それから違う形を描き出しました。今回のものは左に傾いて画面からはみ出しています。勇気を得た私は英語で書かれた指示の1つを書き換えてみました。実行に失敗した計算機はエラーを表示しました。

![図2: プログラマー試行の輪](images/programmer-cycle.png "Figure 2: The human loop of a programmer.")

The cycle illustrated in Figure 2 is an infinitely repeating loop that I have had a great pleasure of executing for a couple decades and I still love what I do. Each new cycle never fails to surprise me. As I pursue what it means to create a program, and what it means to create software art. The process of iteratively evolving a list of computer instructions always presents as much logical challenge as it does artistic reward. Very few of those challenges have been impossible to solve, especially with other people available to collaborate and assist, or by splitting my puzzle into smaller puzzles. If you have already written code in another environment like Processing, Javascript, or even HTML with CSS, then this first important lesson might seem too obvious.

図2に描かれたサイクルは、私が20年の間行ない続け、大いに楽しみ、今なお愛している無限に続く繰り返しです。新しいサイクルは常に私を驚かせてくれます。私はプログラムを書くことの意味、ソフトウェアによるアートを作ることの意味を追い求めています。コンピュータへの指示のリストを繰り返し発展させていくことはいつも芸術的な成果と、同じだけの論理的な挑戦をもたらしてくれます。解くことが不可能な挑戦はほとんどありませんでした。特にパズルをより小さなパズルに分割し、助け合うことのできる人たちがいれば尚更です。もしあなたが既にProcessing、Javascript、HTMLとCSSといった他の環境でプログラムを書いたことがあれば、この重要な教訓はひどく当たり前のものに思えるかもしれません。

![図3: 勘違いしないように](images/profit-not.png "Figure 3: Don't get the wrong idea.")


For those just now familiarizing themselves with what it means to write small programs, it is important to understand the iterative nature of the code writing process. The anecdote in Figure 3 shows what this process is *not*. Rarely would you ever enter some code into the editor just once, and expect to hit compile and see your finished outcome. It is natural, and commonly accepted for programs to start small, have plenty of mistakes (bugs), and evolve slowly toward a goal of desired outcome or behavior. In fact it is so commonplace that to make the former assumption is a downright programmer's mistake. Even in older days when programs were hand-written on paper, the author still needed to eyeball the code obsessively in order to work out the mistakes; therefore the process was iterative. In learning the C++ language, I will provide tiny code examples that you will be compiling on your machine. The abnormal part is typing the code from the book into the editor, and (provided your fingers do not slip) the program magically runs. I am deliberately removing the troubleshooting experience in order to isolate the subject matter of the C++ language itself. Later on, we will tackle the commonplace task of *debugging* (fixing errors) as a topic all its own.

小さなプログラムを書くということに初めて触れる人達にとっては、コードを書くことは本質的に繰り返しを伴うということを理解するのが重要です。図3は、コードを書くことが何で「ない」かを示しています。コードをエディターに一度だけ入力してコンパイルのボタンを押し、完全な結果を見れるということはまずありません。小さな部分から始めて、間違い（バグ）をたくさん犯し、欲しい結果や動作といった目標にゆっくりと発展させていくやり方は、自然でプログラマの間では共通して認められたことです。実際これは本当に当たり前のことなので、先に挙げたような思い込みは全くの間違いです。プログラムが紙に手書きされていた昔ですら、プログラマはコードを執拗に見直し間違いを取り除く必要がありました。作業にはやはり繰り返しが必要だったのです。C++を学ぶにあたって、私はあなたがマシンに入力してコンパイルすることになる短なコードのサンプルを用意しました。本からコードをエディターに入力して、（あなたの指が打ち間違えをしないとして）それが魔法のように実行されるというのは、実際のプログラミングとは違う普通ではないことです。
私は意図的にトラブルの解決方法についてをC++言語自体についての解説から切り離しました。一般的なデバッギング（エラーを修正すること）の作業については独立したトピックとして後ほど取り上げます。


## Compiling My First App
## 最初のアプリケーションをコンパイルする

Let us start by making the smallest, most immediate C++ program possible, then use the convenient environment to test small snippets of C++ code throughout this chapter. In order to do that, we must have a *compiler*, which is a program that translates some code into an actual runnable app, sometimes referred to as the executable file. C++ compilers are mostly free of charge to download, and in a lot of cases, open source. The apps we generate will not automatically show up in places like Apple's App store, Google Play, Steam, Ubuntu Apps Directory, or Pi Store. Instead, they are your personal, private program files and you will be responsible for manually sharing them later on. In the following chapter *oF Setup and Project Structure*, the compiler will sit on your local computer, able to run offline. For now, we will be impatient and compile some casual C++ on the web using a convenient tool by Sphere Research Labs. Please open your web browser and go to [ideone](http://ideone.com) (http://ideone.com).

できる限り最も小さな、すぐに実行できるC++のプログラムから始めて、それからこの章を通じてC++のスニペット（小さなコードの断片）を試すことになる便利な開発環境を使ってみましょう。そのためには「コンパイラ」が必要です。コンパイラはコードを、実行ファイルとも呼ばれる、実際に走らせることのできるアプリケーションに翻訳してくれるプログラムです。C++のコンパイラの多くは無料でダウンロードでき、多くの場合オープンソースです。これから私たちが作り出すアプリケーションは、AppleのApp StoreやGoogle Play、Steam、Ubuntu Apps Directory、PI Storeなどに勝手に表示されることはありません。あなたの個人的なプログラムで、あなた自身の責任で手動で共有することになります。
後の「oF Setup and Project Structure」の章ではコンパイラはあなたのローカルのコンピュータの中に置かれ、オフラインで実行できるようになります。しかしまず今は手間をかけず、Sphere Research Labsによる便利なツールを使って、手軽なC++のコードをWeb上でコンパイルすることにします。ブラウザを開いて[ideone](http://ideone.com) (http://ideone.com)へ移動してください。


You will notice right away that there is an editor already containing some code, but it may be set to another language. Let's switch the language to C++14 if it is not already in that mode. Down at the bottom left of the editor, press the button just to the left of "stdin", as shown in Figure 4. The label for this button could be any number of things.

エディターの中には既にコードが書かれていることに気づくでしょう。もしかしたら他の言語に設定されているかもしれません。その場合は言語をC++14に切り替えましょう。図4に示すように、エディターの左下、「stdin」の左隣にあるボタンを押してください。このボタンのラベルは図とは違うかもしれません。

![図4](images/where-is-says-java.png "Figure 4")

A menu drops down with a list of programming languages. Please choose C++14, shown in Figure 5.

プログラム言語の名前のリストが開きます。図5のようにC++14を選んでください。

![図5](images/choose-c14.png "Figure 5")

Notice that the code in the editor changed, and looks something like figure 6.

エディターの中のコードが変わって、図6のようになっているのを確認してください。

![図6](images/empty-template.png "Figure 6")

This is just an empty code template that does nothing, and creates no errors. The numbers in the left hand gutter indicate the line number of the code. Press the green button labeled *Run*. You will see a copy of the code,  "Success" in the comments, and the section labeled *stdin* (standard input) will be empty. *stdout* (standard output) will also be empty.

これはまだ何もしない、何のエラーも起こさない空のコードのテンプレートです。左脇の数字はコードの行番号を示しています。「Run」と書かれた緑色のボタンを押してください。コードのコピーと「Success」というコメントが見えるでしょう。「stdin（standard input）」と書かれた箇所は空欄（Standard input is empty）のはずです。「stdout（standard output）」も同じく空です。


### Interlude on Typography
### タイポグラフィーについての間奏

Most fonts on the web are variable width, meaning the letters are different widths; the eye finds that comfortable to read. Fonts can also be fixed-width, meaning all the letters (even the W and the lowercase i) are the same width. Although this may look funny and quaint like a typewriter, it serves an important purpose. A fixed width font makes a block of text into a kind of game board, like chess squares or graphing paper. Computer programming code is generally presented in fixed-width typesetting, because it is a form of ASCII-art. The indentation, white space characters, and repetitive patterns are all important to preserve and easily eyeball for comparison. Every coder I know except artist Jeremy Rotsztain uses some manner of monospaced font for their code. Some typeface suggestions are Courier, Andale Mono, Monaco, Profont, Monofur, Proggy, Droid Sans Mono, Deja Vu Sans Mono, Consolas, and Inconsolata. From now on, you will see the font style switch to `this inline style` . . .

Web上のほとんどの（欧文）フォントは文字ごとに幅が異なります。その方が読みやすいからです。固定幅、つまりすべての文字（大文字のWと小文字のiでさえも）の幅が同じになっているフォントもあります。ちょっと変でタイプライターみたいに古臭く見えるかもしれませんが、これには大事な意味があります。コンピュータプログラムのコードはある種アスキーアートなので、一般には等幅の文字組で表示されます。楽に見比べられるよう、インデント、空白文字、繰り返しのパターンが保たれることが重要です。アーティストのJeremy Rotsztain以外、私の知る限りのコーダーは何らかの等幅フォントを使っています。いくつかタイプフェイスの例を挙げると、
Courier、Andale Mono、Monaco、Profont、Monofur、Proggy、Droid Sans Mono、Deja Vu Sans Mono、Consolas、Inconsolataなどがあります。ここからはこのスタイル `this inline style` や、下記のようなブロックを目にすることになるでしょう。

```cpp
and this style encased in a block . . .
```

. . . and that just means you are looking at some code.

これらのスタイル単にこれらの部分がコードであることを示してます。

### Comments

### コメント

Now please press *Edit* (Figure 7) at the top left of the code editor.

では左上の「Edit」（図7）を押してください。

![図7](images/ideone-edit.png "Figure 7")

You will see a slightly different editing configuration but the same template code will still be editable at the top. We will now edit the code. Find line 5, where it says:

少しエディタの形が変わりましたが、同じテンプレートのコードが表示され編集可能になっています。これからコードを編集します。5行目に下記のように書かれているのを見てください。


```cpp
// your code goes here .
```

A line beginning with a double forward slash is called a comment. You may type anything you need to in order to annotate your code in a way you understand. Sometimes it's useful to “comment out code” by placing two forward-slashes before it, because that deactivates the C++ code without deleting it. Comments in C++ can also take up multiple lines, or insert like a tag. The syntax for beginning and ending comment-mode is different. Everything between the `/* and the */` becomes a comment:

二つのスラッシュで始まる行はコメントと呼ばれています。コードには、分かりやすいように好きなように注釈を付けることができます。時にはコードの前位にスラッシュを二つ書き加えて「コメントアウト」するのも役に立ちます。こうするとC++のコードを、削除せずに無効にすることができます。C++のコメントは複数の行にまたがったり、タグのように付け加えることもできます。コメントモードの開始と終了のための構文は別にあります。「/\*」と「\*/」に挟まれた部分はすべてコメントとして扱われます。


```cpp
/*
this is a multi-line comment.
still in comment mode.
*/
```

Please delete the code on line 5 and replace it with the following statement:

5行目を削除して、下記の命令文で置き換えてください。

```cpp
cout << "Hello World" << endl;
```

This line of code tells the computer to say "Hello World" into an implied text-space known as *standard output* (aka. *stdout*). When writing a program, it is safe to expect *stdout* to exist. The program will be able to "print" text into it. Other times, it's just a window pane in your coding tool~~,~~ only used ~~to troubleshoot~~ for troubleshooting **[t: better phrasing?]**.

このコードはコンピュータに「Hello World」という文字列を標準出力（standard output、stdout）と呼ばれる、暗黙的に決まっているテキストの出力先に送るように指示します。プログラムを書いている時には、プログラムが文字列を書き出すことのできる、何らかの標準出力が存在すると考えてよいでしょう。それはあなたのコーディングツールのウィンドウペインの1つでデバッグのためだけに使われるかもしれません。

You may put almost anything between those quotes. The quoted phrase is a called a *string* of text. More specifically, it is a *c-string literal*. We will cover more on strings later in this chapter. In the code, the chunk `cout <<` part means "send the following stuff to stdout in a formatted way." The last chunk `<< endl` means "add a carriage return (end-of-line) character to the end of the hello world message." Finally, at the very end of this line of code, you see a semicolon (;).

引用符の間にはほとんど何でも書くことができます。引用符の間の文字は文字列（string）と呼ばれます。もっと厳密に言うとこれは、「cの文字リテラル」です。文字列についてはこの章で後ほどより深く取り上げます。このコードの `cout <<` の部分は、「この後続く内容を整形して標準出力に送れ」という意味です。後の `<< endl` はこの挨拶の文の終わりに「キャリッジリターン（終行文字）を付け加えろ」という意味です。そして行の一番最後にはセミコロン「;」があります。

In C++, semicolons are like a full stop or period at the end of the sentence. We must type a semicolon after each statement, and usually this is at the end of the line of code. If you forget to type that semicolon, the compile fails. Semicolons are useful because they allow multiple statements to share one line, or a single statement to occupy several lines, freeing the programmer to be flexible and expressive with one's whitespace. By adding a semicolon you ensure that the compiler does not get confused: you help it out and show it where the statement ends. When first learning C or C++, forgetting the semicolon can be an extremely common mistake, and yet it is necessary for the code to compile. Please take extra care in making sure your code statements end in semicolons.

C++ではセミコロンは文末のピリオドのようなものです。命令文の後には必ずセミコロンを打たなくてはなりません。これは普通、行の終わりになります。セミコロンを打ち忘れるとコンパイルは失敗します。セミコロンは便利で、このおかげでプログラマは、1つの行に複数の命令文を書いたり、1つの命令文を複数行にわたって書くなど、空間を柔軟に使って表現することができます。セミコロンを付け加えることで、コンパイラが混乱しないように、どこで命令文が終わるのかを明確に示しているのです。セミコロンを忘れるのはCやC++の学び始めに非常に良く起きるミスですが、セミコロンはコードがコンパイルされるために必要です。良く注意して命令文がセミコロンで終わっているのを確かめるようにしてください。


While you typed, perhaps you noticed the text became multi-colored all by itself. This convenient feature is called *syntax-coloring* (or syntax-highlighting) and can subconsciously enhance one's ability to read the code, troubleshoot malformed syntax, and assist in searching. Each tool will have its own syntax coloring system so if you wish to change the colors, please expect that it's not the same thing as a word processor, whose coloring is something you add to the document yourself. A code editor will not let me assign the font "TRON.TTF" with a glowing aqua color to *just* `endl` (which means end-of-line). Instead, I can choose a special style for a whole category of syntax, and see all parts of my code styled that way as long as it's that type of code. In this case, both `cout` and `endl` are considered keywords and so the tool colors them black. If these things show up as different colors elsewhere, please trust that it's the same code as before, since different code editors provide different syntax coloring. The entire code should now look like this:

コードを打っている間、テキストに勝手に色がついていくのに気付いたでしょう。この便利な機能はシンタックスカラーリング（またはシンタックスハイライト）と呼ばれていて、コードを読んだり、文法の間違いを直したり、何かを見つけたりするのを無意識のうちに助けてくれます。ツールごとにそれぞれのシンタックスカラーリングの仕組みがあります。これはワードプロセッサーの文書に色を着ける機能とは違うものだと考えてください。コードエディターは `endl`（行の終わりを意味します） だけを明るい水色のTRON.TTFにしたいと思ってもそうはさせてくれません。その代わりに、構文上のカテゴリーに対して特別なスタイルを選ぶことができ、コードの同じ種類の部分に全てに選んだスタイルを適用させることができます。今の例では、`cout` と `endl` は両方ともキーワード（予約語）と見做されるので、ツールはこれらを黒い文字で表示します。違うコードエディターは違うシンタックスカラーリングをするので、もし別の場所でこれらのキーワードが別の色で表示されているのを見ても、コードとしては同じものだと信じてください。コード全体は下記のようになっているはずです。


```cpp
#include <iostream.h>
using namespace std;

int main(){
	cout << "Hello World" << endl;
	return 0;
}
```

Now press the green *ideone it!* button at the bottom right corner and watch the output console, which is the bottom half of the code editor, just above that green button. You will see orange status messages saying things like “Waiting for compilation,” “Compilation,” and “Running”. Shortly after, the program will execute in the cloud and the standard output should show up on that web page. You should see the new message in Figure 8.

では右下にある緑の「ideone it!」ボタンを押し、コードエディターの下半分にある出力コンソールを見てください。オレンジ色で、「Waiting for compilation」、「Compilation」、「Running」というステータスが表示されます。程なくプログラムはクラウド上で実行され標準出力に送った内容がページ上に表示されます。図8のようにメッセージが表示されているはずです。

![図8](images/hello-world.png "Figure 8: Hello World appears in output window")

You made it this far. Now give yourself a pat on the back. You just wrote your first line of C++ code; you analyzed it, compiled it, ran it, and saw the output.

目標達成です。自分で自分を褒めてあげましょう。あなたはC++で初めての一業を書き上げ、分析し、コンパイルして、実行し、結果が出力されるの見たのです。

## Beyond Hello World
## Hello World を超えて

Now that we've gotten our feet wet, let's go back and analyze the other parts of the code. The first line is an include statement:

一歩目を踏み出したところで、ちょっと戻ってコードの他の部分を分析してみましょう。一行目はinclude文です。

```cpp
#include <iostream>
```

Similar to *import* in Java and CSS, `#include` is like telling the compiler to cut and paste some other useful code from a file called *iostream.h* at that position in the file, so you can depend on its code in your new code. In this case, iostream.h *provides* `cout` and `endl` as tools I can use in my code, just by typing their names. In C++, a filename ending in **.h** is called a header file, and it contains code you would include in an actual C++ implementation file, whose filename would end in **.cpp**. There are many standard headers built into C++ that provide various basic services – in fact too many to mention here. If that wasn't enough, it's also commonplace to add an external library to your project, including its headers. You may also define your own header files as part of the code you write, but the syntax is slightly different:

JavaやCSSの「import」と同様に `#include` はコンパイラに、「iostream.h」というファイルから役に立つコードをあなたの新しいコードの中で使得るよう切り取ってくるように指示しています。この例ではiostream.hは `cout` と `endl` を名前をタイプするだけで使えるように提供してくれています。C++では名前が「.h」で終わるファイルはヘッダファイルと呼ばれ、実際のC++の実装ファイルに取り込む（include）するコードを格納しています。C++には多すぎてここでは触れられないくらいの標準のヘッダが組み込まれていて、様々な機能を提供しています。もしそれでも足りなければ、外部のライブラリをヘッダをインクルードしてプロジェクトに加えることも一般的に行われています。あなた自身のコードの一部として自分自身でヘッダを定義することもできますが、その場合には少し違う構文を使います。

```cpp
#include "MyCustomInclude.h"
```

In openFrameworks, double quotes are used to include header files that are not part of the system installation.

openFrameworksではダブルクォートをシステム標準ではないヘッダファイルを取り込むのために用います。


### What's with the # ?
### #について

It's a whole story, but worth understanding conceptually. The include statement is not really C++ code (notice the absence of semicolon). It is part of a completely separate compiler pass called *preprocessor*. It happens before your actual programmatic instructions are dealt with. They are like instructions for the code compiler, as opposed to instructions for the computer to run after the compile. Using a pound/hash symbol before these *preprocessor directives*, one can clearly spot them in the file, and for good reason too. They should be seen as a different language, mixed in with the real C++ code. There aren't many C++ preprocessor directives — they are mostly concerned with herding other code. Here are some you might see.

長い話になりますが、概念を理解しておくだけの価値はあります。include分は実際にはC++のコードではありません（セミコロンがついていませんね）。これは全く別の「プリプロセッサ」と呼ばれるものの一部です。この処理は実際のプログラムの命令が処理される前に実行されます。プリプロセッサは、コンパイル後にコンピューターに実行させるための命令ではなく、コンパイラに対する指示のようなものです。#（ハッシュ、またはパウンド）をこれらのプリプロセッサ用の指示（preprocessor directive）に付け加えることで、いい意味ではっきり見分けられるようになります。これらの指示は本物のC++のコードに混ぜられた別の言語見做されるべきなのです。C++のプリプロセッサはたくさんはありません。多くは他のコードを集めてくるためのものです。下記に幾つかあなたが見かける可能性のあるものを挙げます。

`#define`
`#elif`
`#else`
`#endif`
`#error`
`#if`
`#ifdef`
`#include`
`#line`
`#pragma`
`#undef`

Let's do an experiment. In the code editor, please comment out the include directive on line 1, then run the code. To comment out the line of code, insert two adjacent forward-slashes at the beginning of the line.

1つ実験をしてみましょう。コードエディターで1行めの指示をコメントアウトしてコードを実行してみてください。行をコメントアウトするには、行頭にスラッシュを2つ続けて挿入します。

```cpp
//#include <iostream>
```

The syntax coloring will change to all green, meaning it's now just a comment. Run the code by pressing the big green button at the bottom right, and you'll see something new in the output pane.

行全体がただのコメントになったことを示して、シンタックスカラーリングが緑色に変わります。右下の大きな緑のボタンを押してコードを実行しましょう。Outputペインになにか表示されるはずです。

```
prog.cpp: In function 'int main()':
prog.cpp:5:2: error: 'cout' was not declared in this scope
  cout << "Hello World" << endl;
  ^
prog.cpp:5:27: error: 'endl' was not declared in this scope
  cout << "Hello World" << endl;
                           ^
```

The compiler found an error and did not run the program. Instead, in an attempt to help you fix it, the compiler is showing you where it got confused. The first part, *prog.cpp*: tells you the file that contains the error. In this case, ideone.com saved your code into that default file name. Next, it says `In function 'int main()'`: file showing you the specific section of the code that contains the error, in this case, between the {curly brace} of a function called *main*. (We will talk about functions and curly braces later). On the next line, we see `prog.cpp:5:2:`. The 5 is how many lines from the top of the file, and 2 is how many characters rightward from the beginning of the line. Next, we see `error: 'cout' was not declared in this scope`. That is a message describing what it believes is wrong in the code. In this case, it's fairly correct. iostream.h is gone, and therefore no `cout` is provided to us, and so when we try to send "Hello World", the compile fails. On the next couple of lines, you see the line of code containing the fallacious `cout`, plus an extra little up-caret character on the line beneath it, and that is supposed to be an arrow pointing at a character in the code. In this case, the arrow should be sitting beneath the 'c' in `cout`. The system is showing you visually which token is at fault. A second error is shown, and this time, the compiler complains that there is no endl. Of course, we know that in order to fix the error, we need to include `<iostream.h>` so let us do that now. Please un-comment line 1 and re-run the code.

コンパイラはエラーを発見したので、プログラムの実行を行いませんでした。その代わりに、間違いの修正を助けるため、コンパイラはどこで混乱したのかを示してくれています。最初の「prog.cpp」はエラーが含まれているファイルを指しています。この例では、ideone.comはあなたのコードをデフォルトのファイル名で保存しています。次に　`In function 'int main()'`　と書かれています。これはエラーが含まれている特定の箇所を示しています。この場合は「main」という名前の関数の {波括弧}の間です（関数と波括弧については後ほど説明します）。次の行には`prog.cpp:5:2:`とあります。この5はファイルの初めから何行目かを、2は行の初めから右に数えて何文字めかを表しています。さらに `error: 'cout' was not declared in this scope` と表示されています。これはコンパイラがコードのどこが間違っていると考えているか説明するメッセージです。この例のメッセージはかなり正しいと言えます。iostream.hがなくなり、`cout` は提供されていないので「Hello World」を送ろうとした時にコンパイルが失敗するのです。続く数行にはこの間違った `cout` と、その下に小さなキャレット（^）が見えます。このキャレットはコードの中の文字を指し示しす矢印の役割をします。この例では矢印は `cout` の「c」の下に居るはずです。システムがどの文字が間違っているのかを視覚的に示してくれているのです。2つ目のエラーも表示されていて、こちらではコンパイラはendlがないと文句を言っています。当然ながら私達は、エラーを修正するには `<iostream.h>` をincludeすれば良いということを知っています。やってみましょう。一行目のコメントを外してもう一度コードを実行してください。


```cpp
#include <iostream>
```

When using openFrameworks, you have choice of tools and platforms. Each one shows you an error in a different way. Sometimes the editor will open up and highlight the code for you, placing an error talk bubble for more info. Other times, the editor will show nothing, but the compile output will show a raw error formatted similarly to the one above. While sometimes useful that we receive several errors from a compile, it can save a lot of grief if you focus on understanding and fixing the very first error that got reported. After fixing the top error, it is likely that all subsequent errors will elegantly disappear, having all been covered by your first fix.  By commenting out that single line of code at the top, we caused two errors.

openFrameworksは様々なツールやプラットフォームで使うことができます。エラーの表示方法はそれぞれ異なります。エディターが開いてコードをハイライト表示してくれることもあれば、より多くの情報を表示するために吹き出しが使われることもあります。エディターには何も表示されず、コンパイル用の出力に生のエラーが上の例と同じような形で表示されることもあるでしょう。一度のコンパイルでいくつかのエラーが表示され、時としてそれが役に立つこともありますが、一番最初に表示されたエラーを集中的に読み解き修正した方がずっと楽ができるかもしれません。最初のエラーを修正するとそれによって、他のエラー見事に消えてくれることがあります。上の例では1行目をコメントアウトすることで2つのエラーが起きました。

### Namespaces at First Glance
### 初めての名前空間

Moving on to line 2, we see:

```cpp
using namespace std;
```

Let's say you join a social website and it asks you to choose a username. My name is Joshua Nimoy — username might be JNIMOY. I submit the page and it returns an error, telling me that username is already taken, and I have to choose another, since my father, Joseph Nimoy, registered before I did and he's got JNIMOY. And so I must use my middle initial T, and create a unique username, JTNIMOY. I just created and resolved a *namespace conflict*. A namespace is a group of unique names — none are identical. It's possible to have identical names, as long as they are a part of two separate namespaces. Namespaces help programmers avoid stepping on each other's toes by overwriting one another's symbols or hogging the good names. Namespaces also provide a neat and tidy organization system to help us find what we're looking for. In openFrameworks, everything starts with `of` . . . like `ofSetBackground` and `ofGraphics`. This is one technique to do namespace separation because it's less likely that any other names created by other programmers would begin with `of`. The same technique is used by OpenGL. Every name in the OpenGL API (Application Programming Interface) begins with `gl` like `glBlendFunc` and `glPopMatrix`. In C++ however, it is not necessary to have a strictly disciplined character prefix for your names, as the language provides its own namespacing syntax. In line 2, `using namespace std;` is telling the compiler that this .cpp file is going to use all the names in the `std` namespace. Spoiler-alert! those two names are `cout` and `endl`. Let us now do an experiment and comment out line 2, then run the code. What sort of error do you think the compiler will return?

ソーシャル系のウェブサイトでユーザ名を選ぶように言われたとしましょう。私の名前はJoshua Nimoyなのでユーザ名はJNIMOYにします。送信ボタンを押すと、そのユーザ名は既に使われているというエラーが表示されたので他の名前を選ばなくてはなりません。父のJoseph Nimoyが先にJNIMOYで登録していたのです。私のミドルネームのイニシャルであるTを使ってまだ使われていないJTNIMOYというユーザ名にします。こうして私は名前空間の衝突（namespace conflict）を解決したのです。名前空間は一意な名前の集まりです。同じものは1つとしてありません。異なる2つの名前空間に属していれば、同じ名前が2つ存在しても構いません。名前空間はプログラマが他の人が書いた名前を上書きしたり、便利な名前を独り占めしたりしてお互いの邪魔をしてしまわないように助けてくれます。名前空間はまた、きちんと組織だった整理法を提供することで、欲しいものを見つける手助けもしてくれます。openFrameworksではすべての名前は `ofSetBackground`、 `ofGraphics`といったように `of` から始まります。これは、他のプログラマが `of` で始まる名前をつける可能性が低いことを利用した、名前空間を分けるテクニックの1つです。同じテクニックはOpenGLでも使われています。OpenGLのAPI（Application Programming Interface）はすべて `glBlendFunc`、`glPopMatrix` といったように `gl` から始まります。C++ではしかし、名前を付けるときに必ず接頭辞を規則として用いなくてはいけないわけではありません。C++には独自の名前空間のための構文があるからです。2行目の `using namespace std;` はコンパイラに、この.cppファイルは `std` 名前空間に属する名前を使うということを伝えています。先に種を明かしてしまうとこれは `cout` と `endl` のことです。ちょっとした実験として2行目をコメントアウトしてコードを実行してみましょう。コンパイラはどんなエラーを返すと思いますか。


```cpp
/* using namespace std; */
```

It's a very similar error as before, where it cannot find `cout` or `endl`, but this time, there are suggested alternatives added to the message list.

前に見たものととてもよく似た `cout` または `endl` が見つからないというエラーですが、今回はメッセージに代替案が付け加わりました。

```
prog.cpp:5:2: note: suggested alternative:
In file included from prog.cpp:1:0:
/usr/include/c++/4.8/iostream:61:18: note:   'std::cout'
   extern ostream cout;  /// Linked to standard output
                  ^
```

The compiler says, "Hey, I searched for `cout` and I did find it in one of the namespaces included in the file. Here it is. `std::cout`" and in this case, the compiler is correct. It wants us to be *more explicit* with the way we type `cout`, so we express its namespace `std` (standard) on the left side, connected by a double colon (::). it's sort of like calling myself `Nimoy::Joshua`. Continuing our experiment, edit line 5 so that `cout` and `endl` have explicit namespaces added.

コンパイラは、「`cout`を検索したら、読み込んだファイルの中にある名前空間の1つで　`std::cout`　ってのを見つけたよ。」と言っています。今回はコンパイラの言っていることが正解です。コンパイラは `cout` と打つ時に、その左側にそれが属する名前空間である `std` （standard）を2重のコロン（::）で繋げて明示して欲しい、と主張しているのです。自分のことを `Nimoy::Joshua` と呼ぶような感じです。実験を続けて5行めを編集して、 `cout` と `endl` の前に明示的に名前空間を付け加えてみましょう。

```cpp
std::cout << "Hello World" << std::endl;
```

When you run the code, you will see it compiles just fine, and succeeds in printing "Hello World". Even the line that says `using namespace std;` is still commented out. Now imagine you are writing a program to randomly generate lyrics of a song. Obviously, you would be using `cout` quite a bit. Having to type `std::` before all your `cout`s would get really tedious, and one of the reasons a programming language adds these features is to reduce typing. So although line 2 `using namespace std;` was not necessary, having it in place (along with other `using namespace` statements) can keep one's C++ code easy to type and read, through implied context.

これを実行すると何の問題もなくコンパイルされて、「Hello World」と表示されるはずです。`using namespace std;` はまだコメントアウトされているのにです。ここであなたが歌の歌詞をランダムに生成するプログラムを書いているところを想像してください。当然、 `cout` を何度も使うことになるでしょう。全部の `cout` の前にいちいち `std::` と打つのはとても面倒です。プログラム言語にこういった機能がある理由の1つはタイピングの量を減らす為です。2行めの `using namespace std;` は必ずしも必要ではないけれど、これ（と、その他の `using namespace` で始まる文）を書いて暗黙的に文脈が示すことで、C++のコードを打ちやすく、また読みやすく保つことができるのです。

Say I'm at a Scrabble party in Manhattan, and I am the only Josh. People can just call me Josh when it's my turn to play. However, if Josh Noble joins us after dinner, it gets a bit confusing and we start to call the Joshes by first and last name for clarity. In C++, the same is also true. I would be `Nimoy::Josh` and he would be `Noble::Josh`. It's alright to have two different `cout` names, one from the `std` namespace, and another from the `improved` namespace, as long as both are expressed with explicit namespaces; `std::cout` and `improved::cout`. In fact, the compiler will complain if you don't.

マンハッタンでスクラブルのパーティーに来て、自分の名前をJoshとだけ書いたら、手番が来た時に他の人は私のことをJoshと呼ぶでしょう。しかし、ディナーの後にJosh Nobleが加わったとしたらちょっと紛らわしいので、はっきりさせる為に2人のJoshをファーストネームとラストネームの両方で呼ぶようになるでしょう。片方が `std` 名前空間に属していて、もう片方が `improved` に属しているのならば、 `cout` という名前が2つあっても構いません。名前空間は `std::cout`、`improved::cout` と明示的に示されている必要があります。もし書かなかった場合、コンパイラは文句を言うでしょう。

You will see more double-colon syntax (::) when I introduce classes.

後ほどクラスについて説明する箇所でまた、2重のコロン（::）を使った構文を見ることになります。


## Functions
## 関数

Moving on, let us take a look at line 4:

先に進んで、4行目を見てみましょう。

```cpp
int main() {
```

This is the first piece of code that has a beginning and an end, such that it "wraps around" another piece of code. But more importantly, a function *represents* the statements enclosed within it. The closing end of this *function* is the closing curly brace on line 7:

これは他のコードを「包み込む」ような、始まりと終わりがあるコードの始まりの部分です。さらに大事なことに、関数は中に含まれている命令文を「代表して」示しています。この「関数」の終わりは7行めの波括弧が閉じる箇所です。

```cpp
}
```

In C++, we enclose groups of code statements inside functions, and each function can be seen as a little program inside the greater program, as in the simplified diagram in figure 9.

C++では関数の中に命令文の集まりをまとめて書きます。図9で簡単なダイアグラムが示すように、それぞれの関数は大きなプログラムの中の小さなプログラムだとみなすことができます。


![図9: Many Functions](images/program-anatomy.png "Figure 9. A program contains many functions, and each function contains zero or more statements.")

Each of these functions has a name by which we can call it. To call a function is to execute the code statements contained inside that function. The basic convenience in doing this is less typing, and we will talk about the other advantages later. Like a board game, a program has a starting position. More precisely, the program has an *entry-point* expected by the compiler to be there. That entry-point is a function called *main*. The code you write inside the *main* function is the first code that executes in your program, and therefore it is responsible for calling any other functions in your program. Who calls your *main* function? The operating system does! Let's break down the syntax of the main function in this demo. Again, for all you Processing coders, this is old news.

それぞれの関数には呼び出すための名前が付いています。中に含まれている命令を実行するために関数を呼び出します。もっとも基本的なメリットはタイピングの量が少なくて済むことです。他のメリットについては後ほど説明します。ボードゲームのように、プログラムにはスタート地点があります。もっと正確に言うと、コンパイラはプログラムに「エントリーポイント」があることを期待しています。エントリーポイントは「main」と名付けられた関数です。「main」関数は、その中に書かれたコードがプログラムの中で最初に実行されるコードになるので、プログラムの中の他の全ての関数を呼び出す責任があります。誰が「main」関数を呼び出すのでしょう。オペレーションシステムです。このデモの中のmain関数の構文を分析してみましょう。Processingを使っている人にはお馴染みでしょう。


![図10: The Function](images/function-anatomy.png)

When defining a function, the first token is the advertised return type. Functions can optionally return a value, like an answer to a question, a solution to a problem, the result of a task, or the product of a process. In this case, *main* promises to return an `int`, or *integer* type, which is a whole number with no fraction or decimal component. Next token is the name of our function. The system expects the word "main" in all lower-case, but you will later define your own functions and we will get into naming. Next is an opening and closing parenthesis. Yes, it seems kind of strange to have it there, since there is nothing inside it. Later, we will see what goes in there — but never leave out the pair of parentheses with functions because in a certain way, that is the major hint to the human that it's a function. In fact, from now on, when I refer to a function by name. I'll suffix it with a ( ), for example `main()` when the function requires no parameter and I'll suffix it with a (...), for example `main(...)`, when the function requires one or more parameters

関数を定義するときに最初に書くのは、戻り値の型の宣言です。質問に対する答え、問題に対する解、ある仕事をした結果、といったように、関数は任意で戻り値を返すことができます。この例では「main」は `int`、つまり分数や小数部分を含まない「整数」型の値を返すことを約束しています。次に来るのは関数の名前です。ここでは「main」と全て小文字で書かれていること必要があります。後ほど自分でも関数を定義することになるので、命名方法についてもそこで説明します。次は始め丸括弧と終わり丸括弧です。中に何も書かれていないので、ここに括弧
があるのは変な感じがしますね。後ほどこの中に何が書けるのかは説明しますが、とにかく関数につける括弧は省略しないようにしてください。ある意味、括弧は読む人にとってそれが関数であることを示す重要なヒントなのです。実際にここから私が関数のことを名前で示す際には、引数のない関数の場合は `main()`、1つかそれ以上の引数が必要な場合は `main(...)` と()をつけるようにします。

Next, we see an opening curly bracket. Sometimes this opening curly bracket is on the same line as the preceding closing parenthesis, and other times, you will see it on its own new line. It depends on the personal style of the coder, project, or group — and both are fine. For a complete reference on different indent styles, see the Wikipedia article on Indent Style (http://en.wikipedia.org/wiki/Indent_style).

そのあとには始め波括弧があります。この波括弧はその前の終わり丸括弧と同じ行に書かれることもあれば、別の行に書かれることもあります。これはコーダーやプロジェクト、グループのスタイルによるもので、どちらでも問題ありません。様々なスタイルについてはまとめて知りたい場合は、Wikipediaのインデントスタイルについての項（http://en.wikipedia.org/wiki/Indent_style）をご覧ください。


In between this opening curly bracket and the closing one, we place our code statements that actually tell the computer to go do something. In this example, I only have one statement, and that is the required `return`. If you leave this out for a function whose return type is `int`, then the compiler will complain that you broke your promise to return an int. In this case, the operating system interprets a 0 as "nothing went wrong". Just for fun, see what happens when you change the 0 to a 1, and run the code.

始め波括弧と終わり波括弧の間にはコンピュータが実際に行う何かを伝えるための命令文を書きます。上の例では、命令文は必須である `return` 1つしかありません。もしこれを戻り値の型が `int` になっている関数で省略すると、コンパイラは整数を返すという約束を破ったと文句を言ってくるでしょう。この例ではオペレーティングシステムは0を「何も問題なく実行された」という意味だと解釈します。ちょっとした遊びとして、0を1に書き換えてコードを実行したら何が起きるか見てみましょう。

## Custom Functions

## カスタム関数

We will now define our own function and make use of it as a word template. Type the sample code into your editor and run it.

それではオリジナルの関数を定義して、それをテンプレートとして使ってみましょう。サンプルコードをエディターに入力して実行してください。

```cpp
#include <iostream>
using namespace std;

void greet(string person){
	cout << "Hi there " << person << "." << endl;
}

int main() {
	greet("moon");
	greet("red balloon");
	greet("comb");
	greet("brush");
	greet("bowl full of mush");
	return 0;
}
```

The output shows a familiar bedtime story.

下記のように出力されすはずです。

```
Hi there moon.
Hi there red balloon.
Hi there comb.
Hi there brush.
Hi there bowl full of mush.
```

In this new code, notice the second function `greet(...)` which looks the same but different from `main()`. It has the same curly brackets to hold the code block, but the return type is different. It has the same pair of parentheses, but this time there is something inside. And what about that required return statement? The *void* keyword is used in place of a return type when a function does not return anything. So, since `greet(...)` has a *void* return type, the compiler will not complain should you leave out the `return`. In the parentheses, you see `string person`. This is a parameter, an input-value for the function to use. In this case, it's a bit like find-and-replace. Down in `main()`, you see I call `greet(...)` five times, and each time, I put a different string in quotes between the parentheses. Those are *arguments*.

As an aside, to help in the technicality of discerning between when to call them *arguments* and when to call them *parameters*, see this code example:

このコードには `main()` と同じように見える別の関数、`greet(...)` があります。コードを挟み込む波括弧があるのは同じですが、戻り値の型が違います。同様に丸括弧がありますが、今回は間に何か書いてあります。必須だった `return` 文はどうでしょう。関数が何も返さない場合には、戻り値の型を指定する箇所で「void」キーワードを使います。`greet(...)` には「void」が戻り値の型として指定されているので、コンパイラは `return` が書かれていなくても文句を言いません。括弧の中には `string person` と書かれています。これはパラメーター、つまり関数が使うための入力値です。ここでは検索置換のようなことをしています。`main()` の中では `greet(...)` が5回呼び出されています。呼び出しの度に括弧の間に、クオーテーションマークに挟まれた異なる文字列が書かれています。これらは「引数」と呼ばれています。

```cpp

void myFunction(int parameter1, int parameter2){
	//todo: code
}

int main(){
	int argument1 = 4;
	int argument2 = 5;
	myFunction(argument1,argument2);
	return 0;
}

```

Getting back to the previous example, those five lines of code are all ***function calls***. They are telling `greet(...)` to execute, and passing it the one string argument so it can do its job. That one string argument is made available to `greet(...)`'s inner code via the argument called `person`. To see the order of how things happen, take a look at Figure 11.

![図11. Function Call Flow](images/function-call.png "Figure 11. Function Call Flow")

The colorful line in Figure 11 is the path drawn by an imaginary playback head that steps over the code as it executes. We start at the blue part and go in through the main entry-point, then encounter `greet(...)`, which is where a *jump* happens. As the line turns green, it escapes out of `main()` temporarily so it can go follow along `greet(...)` for a while. About where the line turns yellow, you see it finished executing the containing code inside `greet(...)` and does a second jump (the return) this time going back to the previous saved place, where it continues to the next statement. The most obvious advantage we can see in this example is the reduction of complexity from that long `cout` statement to a simple call to `greet(...)`. If we must call `greet(...)` five times, having the routine *encapsulated* into a function gives it convenience power. Let's say you wanted to change the greeting from "Good night" to "Show's over ". Rather than updating all the lines of code you cut-and-pasted, you could just edit the one function, and all the uses of the function would change their behavior along with it, in a synchronized way. Furthermore, code can grow to be pretty complex. It helps to break it down into small routines, and use those routines as your own custom building blocks when thinking about how to build the greater software. By using functions, you are liberated from the need to meticulously represent every detail of your system; therefore a function is one kind of *abstraction* just like abstraction in art. This sort of abstraction is called *encapsulation of complexity* because it's like taking the big complex thing and putting it inside a nice little capsule, making that big complex thing seem smaller and simpler. It's a very powerful idea — not just in code.

## Encapsulation of Complexity

Imagine actor Laurence Fishburne wearing tinted pince-nez glasses, offering you two options that are pretty complicated to explain. On the one hand, he is willing to help you escape from the evil Matrix so that you may fulfill your destiny as the hacker hero, but it involves living life on life's terms and that is potentially painful but whatever. The story must go on and by the way, there is a pretty girl. On the other hand, he is also willing to let you forget this all happened, and mysteriously plant you back in your tiny apartment where you can go on living a lie, none the wiser. These two options are explained in the movie *The Matrix* and then the main character is offered the choice in the form of colored pills, as a way to simplify an otherwise wordy film scenario. The two complex choices are encapsulated into a simple analogy that is much easier for movie audiences to swallow. See Figure 12.

![図12. Red Pill and Blue Pill from The Matrix](images/red-blue-pills.png "Figure 12. Red Pill and Blue Pill from The Matrix")

Rather than repeating back the entire complicated situation, Neo (the main character) needed only to swallow one of the pills. Even if it were real medicine, the idea of encapsulating complexity still applies. Most of us do not have the expertise to practice medicine in the most effective way, and so we trust physicians and pharmacologists to create just the right blend of just the right herbs and chemicals. When you swallow a pill, it is like calling that function because you have the advantage of not needing to understand the depths of the pill. You simply trust that the pill will cause an outcome. The same is true with code. Most of the time, a function was written by someone else, and if that person is a good developer, you are free to remain blissfully ignorant of their function's inner workings as long as you grasp how to properly call their function. In this way, you are the *higher-level* coder, meaning that you simply call the function but you did not write it. Someone who creates a project in openFrameworks is sitting on the shoulders of the openFrameworks layer. openFrameworks sits on the shoulders of the OpenGL Utility Toolkit, which sits on OpenGL itself, and so on. In other words, an openFrameworks project is a *higher-level* application of C++, a language with a reputation for *lower-level* programming. As illustrated in Figure 13, I sometimes run into a problem when I tell people I wrote an interactive piece in C++.

![図13. Standing on Shoulders of Giants](images/shoulders-of-giants.png "Figure 13. Standing on Shoulders of Giants")

There are a few advantages to using C++ over the other options (mostly scripting) for your new media project. The discussion can get quite religious (read: heated) among those who know the details. If you seek to learn C++, then usually it is because you seek faster runtime performance, because C++ has more libraries that you can snap into your project, or because your mentor is working in that language. An oF project is considered higher-level because it is working with a greater encapsulation of complexity, and that is something to be proud of.

## Variables (part 1)

> A “thing” is a “think”, a unit of thought
>
> -- Alan Watts


Please enter the following program into ideone and run it.

```cpp
#include <iostream>
using namespace std;

int main(){
	cout << "My friend is " << 42 << " years old." << endl;
	cout << "The answer to the life the universe and everything is " << 42 << "." << endl;
	cout << "That number plus 1 is " << (42+1) << "." << endl;
	return 0;
}
```

The output looks like this:

```
My friend is 42 years old.
The answer to the life the universe and everything is 42.
That number plus 1 is 43.
```

We understand from a previous lesson that stuff you put between the `<<` operators will get formatted into the `cout` object, and magically end up in the output console. Notice in the last line, I put a bit of light arithmetic (42+1) between parentheses, and it evaluated to 43. That is called an *expression*, in the mathematics sense. These three lines of code all say something about the number 42, and so they all contain a *literal* integer. A literal value is the contents typed directly into the code; some would say "hard wired" because the value is fixed once it is compiled in with the rest.

If I want to change that number, I can do what I know from word processing, and "find-and-replace" the 42 to a new value. Now what if I had 100,000 particles in a 3D world. Some have 42s that need changing, but other 42s that should not be changed? Things can get both heavy and complex when you write code. The most obvious application of *variables* is that they are a very powerful find-and-replace mechanism, but you'll see that variables are useful for more than that. So let's declare an integer at the top of the code and use it in place of the literal 42s.

```cpp
#include <iostream>
using namespace std;

int main(){

	int answer = 42;

	cout << "My friend is " << answer << " years old." << endl;
	cout << "The answer to the life the universe and everything is " << answer << "." << endl;
	cout << "That number plus 1 is " << (answer+1) << "." << endl;
	return 0;
}
```

Now that I am using the variable `answer`, I only need to change that one number in my code, and it will show up in all three sentences as 42. That can be more elegant than find-and-replace. Figure 18 shows the syntax explanation for declaring and initializing a variable on the same line.

![図18. Variable declaration and initialization](images/variable-declaration.png "Figure 18. Variable declaration and initialization")

It is also possible to declare a variable and initialize it on two separate lines. That would look like:

```cpp
int answer;
answer = 42;
```

In this case, there is a moment after you declare that variable when its answer may be unpredictable and glitchy because in C (unlike Java), fresh variables are not set to zero for free — you need to do it. If you don't, the variable can come up with unpredictable values — computer memory-garbage from the past. So, unless you intend to make glitch art, please always initialize your variable to some number upon declaring it, even if that number is zero.

### Naming your variable

Notice the arrow below saying "must be a valid name". We invent new names to give our namespaces, functions, variables, and other constructs we define in code (classes, structs, enums, and other things I haven't taught you). The rules for defining a new identifier in code are strict in a similar way that choosing a password on a website might be.

+ Your identifier must contain only letters, numbers, and underscores.
+ it cannot begin with a number, but it can certainly begin with an underscore.
+ The name cannot be the same as one of the language keywords (for example, the word `void`)

The following identifiers are okay.

```
a
A
counter1
_x_axis
perlin_noise_frequency
_         // a single underscore is fine
___       // several underscores are fine
```

Notice lowercase a is a different identifier than uppercase A. Identifiers in C++ are case-sensitive.
The following identifiers are not okay.

```cpp
1infiniteloop         // should not start with a number
transient-mark-mode   // dashes should be underscores
@jtnimoy              // should not contain an @
the locH of sprite 1  // should not contain spaces
void                  // should not be a reserved word
int                   // should not be a reserved word
```

naming your variable `void_int`, although confusing, would not cause any compiler errors because the underscore joins the two keywords into a new identifier. Occasionally, you will find yourself running into `unqualified id` errors. Here is a list of C++ reserved keywords to avoid when naming variables. C++ needs them so that it can provide a complete programming language.

```
alignas alignof and and_eq asm auto bitand bitor bool break case catch
char char16_t char32_t class compl const constexpr const_cast continue
decltype default delete do double dynamic_cast else enum explicit
export extern false final float for friend goto if inline int long
mutable namespace new noexcept not not_eq nullptr operator or or_eq
override private protected public register reinterpret_cast return
short signed sizeof static static_assert static_cast struct switch
template this thread_local throw true try typedef typeid typename
union unsigned using virtual void volatile wchar_t while xor xor_eq
```

### Naming conventions

> Differences of habit and language are nothing at all if our aims are identical and our hearts are open.
>
> **--Albus Dumbledore**


Identifiers (variables included) are written with different styles to indicate their various properties, such as type of construct (variable, function, or class?), data type (integer or string?), scope (global or local?), level of privacy, etc. You may see some identifiers capitalized at the beginning and using `CamelCase`, while others remain all `lower_case_using_underscores_to_separate_the_words`. Global constants are found to be named with `ALL_CAPS_AND_UNDERSCORES`. Another way of doing lower-case naming is to start with a lowercase `letterThenCamelCaseFromThere`. You may also see a hybrid, like `ClassName__functionName__variable_name`. These different styles can indicate different categories of identifiers.

More obsessively, programmers may sometimes use what is affectionately nicknamed *Hungarian Notation*, adding character badges to an identifier to say things about it but also reduce the legibility, for example `dwLightYears` and `szLastName`. Naming conventions are not set in stone, and certainly not enforced by the compiler. Collaborators generally need to agree on these subtle naming conventions so that they don't confuse one another, and it takes discipline on everyone's part to remain consistent with whatever convention was decided. The subject of naming convention in code is still a comically heated debate among developers, just like deciding which line to put the curly brace, and whether to use tabs to indent. Like a lot of things in programming, someone will always tell you you're doing it wrong. That doesn't necessarily mean you are doing it wrong.

### Variables change

We call them variables because their values *vary* during runtime. They are most useful as a bucket where we put something (let's say water) for safe keeping. As that usually goes, we end up going back to the bucket and using some of the water, or mixing a chemical into the water, or topping up the bucket with more water, etc. A variable is like an empty bucket where you can put your stuff. Figure 19 shows a bucket from the game *Minecraft*.

![図19. Bucket, courtesy of Mojang AB](images/minecraft-bucket.png "Figure 19. Bucket, courtesy of Mojang AB")

If a computer program is like a little brain, then a variable is like a basic unit of remembrance. Jotting down a small note in my sketchbook is like storing a value into a variable for later use. Let's see an example of a variable changing its value.

```cpp
#include <iostream>
using namespace std;

int main(){
	int counter = 0;
	cout << counter;
	counter = 1;
	cout << counter;
	counter = 2;
	cout << counter;
	counter = 3;
	cout << counter;
	counter = 4;
	cout << counter;
	counter = 5;
	cout << counter;
	return 0;
}
```

The output should be `012345`. Notice the use of the equal sign. It is different than what we are accustomed to from arithmetic. In the traditional context, a single equal sign means the expressions on both sides would evaluate to the same value. In C, that is actually a double equal (==) and we will talk about it later. A single equal sign means "Solve the expression on the right side and store the answer into the variable named on the left side". It takes some getting used to if you haven't programmed before. If I were a beginning coder (as my inner child is perpetually), I would perhaps enjoy some alternative syntax to command the computer to store a value into a variable. Something along the lines of: `3 => counter` as found in the language *ChucK* by Princeton sound lab, or perhaps something a bit more visual, as my repurposing of the Minecraft crafting table in figure 20.

![図20. Minecraft crafting table repurposed for variable assignment](images/minechuck.png "Figure 20. Minecraft crafting table repurposed for variable assignment")

The usefulness of having the variable name on the left side rather than the right becomes apparent in practice since the expressions can get quite lengthy! Beginning a line with `varname =` ends up being easier for the eyeball to scan because it's guaranteed to be two symbols long before starting in on whatever madness you plan on typing after the equals sign.

Analyzing the previous code example, we see the number increments by 1 each time before it is output. I am repeatedly storing literal integers into the variable. Since a programming language knows basic arithmetic, let us now try the following modification:

```cpp
#include <iostream>
using namespace std;

int main(){
	int counter = 0;
	cout << counter;
	counter = counter + 1;
	cout << counter;
	counter = counter + 1;
	cout << counter;
	counter = counter + 1;
	cout << counter;
	counter = counter + 1;
	cout << counter;
	counter = counter + 1;
	cout << counter;
	return 0;
}
```

The output should still be `012345`. By saying `counter = counter + 1`, I am incrementing `counter` by 1. More specifically, I am using `counter` in the right-hand "addition" expression, and the result of that (one moment later) gets stored into `counter`. This seems a bit funny because it talks about `counter` during two different times. It reminds me of the movie series, *Back to the Future*, in which Marty McFly runs into past and future versions of himself. See Figure 21.

![図21. The future Marty uses the past Marty](images/futuremarty.png "Figure 21. The future Marty uses the past Marty")

Great Scott, that could make someone dizzy! But after doing it a few times, you'll see it doesn't get much more complicated than what you see there. This is a highly *practical* use of science fiction, and you probably aren't attempting to challenge the fabric of spacetime (unless you are Kyle McDonald, or maybe a Haskell coder<!-- i mean these things as a high compliment, not as mockery -->). The point here is to modify the contents of computer memory, so we have `counter` from one instruction ago, in the same way that there might already be water in our bucket when we go to add water to it. Figure 22 shows `bucket = bucket + water`.

![図22. bucket = bucket + water](images/minecraft-inc.png "Figure 22. bucket = bucket + water")

Incrementing by one, or adding some value to a variable is in fact so commonplace in all programming that there is even syntactic sugar for it. *Syntactic Sugar* is a redundant grammar added to a programming language for reasons of convenience. It helps reduce typing, can increase comprehension or expressiveness, and (like sugar) makes the programmer happier. The following statements all add 1 to `counter`.

```cpp
counter = counter + 1; // original form
counter += 1;          // "increment self by" useful because it's less typing.
counter++;             // "add 1 to self" useful because you don't need to type a 1.
++counter;             // same as above, but with a subtle difference.
```

Let's test this in the program.

```cpp
#include <iostream>
using namespace std;

int main(){
	int counter = 0;
	cout << counter;
	counter++;
	cout << counter;
	counter++;
	cout << counter;
	counter++;
	cout << counter;
	counter++;
	cout << counter;
	counter++;
	cout << counter;
	return 0;
}
```

Yes, it's a lot less typing, and there are many ways to make it more concise. Here is one way.

```cpp
#include <iostream>
using namespace std;

int main(){
	int counter = 0;
	cout << counter++;
	cout << counter++;
	cout << counter++;
	cout << counter++;
	cout << counter++;
	cout << counter++;
	return 0;
}
```

The answer is still `012345`. The postfix incrementing operator will increment the variable even while it sits inside an expression. Now let's try the prefix version.

```cpp
#include <iostream>
using namespace std;

int main(){
	int counter = 0;
	cout << ++counter;
	cout << ++counter;
	cout << ++counter;
	cout << ++counter;
	cout << ++counter;
	cout << ++counter;
	return 0;
}
```

If you got the answer `123456`, that is no mistake! The prefix incrementing operator is different from its postfix sister in this very way. With `counter` initialized as 0, `++counter` would evaluate to 1, while `counter++` would still evaluate to 0 (but an incremented version of `counter` would be left over for later use). The output for the following example is `1112`.

```cpp
#include <iostream>
using namespace std;

int main(){
	int counter = 0;
	cout << ++counter; // 1: increments before evaluating
	cout << counter;   // 1: has NOT changed.
	cout << counter++; // 1: increments after evaluating
	cout << counter;   // 2: evidence of change.
	return 0;
}
```

For arithmetic completeness, I should mention that the subtractive *decrementing* operator (counter--) also exists. Also, as you might have guessed by now, if one can say `counter + 1`, then a C compiler would also recognize the other classic arithmetic like `counter - 3` (subtraction), `counter * 2` (asterisk is multiplication), `counter / 2` (division), and overriding the order of operations by using parentheses, such as `(counter + 1) / 2` evaluating to a different result than `counter + 1 / 2`. Putting a negative sign before a variable will also do the right thing and negate it, as if it were being subtracted from zero. C extends this basic palette of maths operators with boolean logic and bitwise manipulation; I will introduce them in Variables part 2.

There are a few more essentials to learn about variables, but we're going to take what we've learned so far and run with it in the name of fun. In the meantime, give yourself another pat on the back for making it this far! You learned what variables are, and how to perform basic arithmetic on them. You also learned what the ++ operator does when placed before and after a variable name.

The C++ language gets its name from being the C language plus one.

## Conclusion

Congratulations on getting through the first few pages of this introduction to C++. With these basic concepts, you should be able to explore plenty far on your own, but I will admit that it is not enough to prepare you to comprehend the code examples in the rest of ofBook. Because of limited paper resources, what you've seen here is a "teaser" chapter for a necessarily lengthier introduction to the C++ language. That version of this chapter got so big that it is now its own book — available unabridged on the web, and possibly in the future as its own companion book alongside ofBook. Teaching the C++ language to non-programmers is indeed a large subject all itself, which could not be effectively condensed to 35 pages, let alone the 100+ page book it grew to be. If you're serious about getting into openFrameworks, I highly recommend you stop and read the unabridged version of this chapter before continuing in ofBook, so that you may understand what you are reading. You will find those materials [here](https://github.com/openframeworks/ofBook/blob/master/chapters/cplusplus_basics/unabridged.md)

## PS.

Stopping the chapter here is by no means intended to separate what is important to learn about C++ from what is not important. We have simply run out of paper. In lieu of how important the rest of this intro to C++ is, and based on ofZach's teaching experience, here is more of what you'll find in the unabridged version:

+ Variables exist for different periods of time - some for a long time, and some for a small blip in your program's lifecycle. This subject of *scope* is covered in the unabridged version of this book, entitled *Variables (part 2)*.

+ Variables have a *data type*. For example, one holds a number while another holds some text. More about that in *Fundamental Types*.

+ It's important to reiterate that unlike Processing, variables do not necessarily start with a zero value. You must initialize them with your desired value, and otherwise there's no telling what will be waiting there for you. You'll find additional discussion of this phenomenon in the introduction to arrays.

> The best way to predict your future is to create it.
>
> **--Abraham Lincoln**
