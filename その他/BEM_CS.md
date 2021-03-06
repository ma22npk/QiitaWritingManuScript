# CSSルールチートシート

メンテナンス性が高い HTML と CSS を書く
HTML と CSS のコーディングでは、メンテナンス性を高くすることが何よりも大切だと考えています。

メンテナンス性が高い HTML と CSS とは
メンテナンス性が高い HTML と CSS は以下の4点のポイントがあります。

わかりやすい
探しやすい
再利用しやすい
拡張しやすい
本記事では、上記を満たす書き方をコーディング規約に組み込むことで、メンテナンス性の高い HTML と CSS を実現することを目的としています。


### CSSの有効性

可能な場合は有効なCSSを使用してください。

CSSバリデーターのバグを処理したり、独自の構文を必要としたりしない限り、有効なCSSコードを使用してください。

W3CCSSバリデーター などのツールを使用 してテストします。

有効なCSSを使用することは、測定可能なベースライン品質属性であり、効果がなく削除できるCSSコードを見つけることができ、適切なCSSの使用を保証します。

## IDとクラスの命名

意味のある、または一般的なIDとクラス名を使用します。

表示名や不可解な名前の代わりに、問題の要素の目的を反映する、またはその他の一般的なIDとクラス名を常に使用してください。

要素の目的を反映した具体的な名前を使用することをお勧めします。これらの名前は最も理解しやすく、変更される可能性が最も低いためです。

一般名は、兄弟と異なる意味がない、または意味がない要素の単なるフォールバックです。通常、「ヘルパー」として必要です。

機能名または総称名を使用すると、不要なドキュメントまたはテンプレートが変更される可能性が低くなります。

/ *非推奨：無意味* / ＃yee-1901 {}


/ *非推奨：プレゼンテーション* / 。ボタン-緑{} 。クリア{}

/ *推奨：特定* / #gallery {} #login {} 。ビデオ{}




/ *推奨：汎用* / 。aux {} 。alt {}

## IDとクラス名のスタイル

できるだけ短く、必要なだけ長いIDとクラス名を使用してください。

IDまたはクラスが何であるかを、できるだけ簡潔に伝えてください。

このようにIDとクラス名を使用すると、許容可能なレベルの理解とコード効率に貢献します。

/ *非推奨* / #navigation {} 。atr {}

/ *推奨* / #nav {} 。著者{}

## タイプセレクター

タイプセレクタでIDとクラス名を修飾することは避けてください。

必要な場合を除いて（たとえばヘルパークラスの場合）、IDまたはクラスと組み合わせて要素名を使用しないでください。

不要な祖先セレクターを回避することは、パフォーマンス上の理由から役立ちます。

/ *非推奨* / 
ul #example {} 
div 。エラー{}
/ *推奨* / #example {} 。エラー{}

4.1.5省略形のプロパティ
可能な場合は省略形のプロパティを使用します。

CSSは、値が1つだけ明示的に設定されている場合でも、可能な限り使用する必要があるさまざまな省略形の プロパティ（などfont）を提供します。

省略形のプロパティを使用すると、コードの効率と理解に役立ちます。

/ *推奨しない* /
ボーダー-トップ-スタイル：なし。
フォント-家族：パラティーノ、ジョージア、セリフ。
フォント-サイズ：100 ％; 
行-高さ：1.6 ; 
パディング-下：2em ; 
パディング-左：1em ; 
パディング-右：1em ; 
パディング-     上：0 ; 
/ *推奨* / 
border - top ：0 ; 
フォント：100 ％/ 1.6パラティーノ、ジョージア、セリフ。
パディング：0 1em 2em ;     
4.1.60および単位
必要な場合を除き、「0」の値の後の単位指定は省略してください。

0必要な場合を除いて、値の後に単位を使用しないでください。

フレックス：0px ; / *このフレックスベースのコンポーネントにはユニットが必要です。* / 
flex ：1 1 0px ; / *ユニットがなくてもあいまいではありませんが、IE11で必要です。* /
マージン：0 ; 
パディング：0 ;        
4.1.7先行0
値の先頭の「0」は省略してください。

0-1から1までの値または長さの前にsを付けないでください。

フォント-サイズ：。8em ; 
4.1.816進表記
可能な場合は、3文字の16進表記を使用してください。

それを可能にする色の値の場合、3文字の16進表記はより短く、より簡潔になります。

/ *非推奨* / 
color ：#eebbcc; 
/ *推奨* /
色：#ebc; 


## プレフィックス

アプリケーション固有のプレフィックスを持つプレフィックスセレクター（オプション）。

大規模なプロジェクトや、他のプロジェクトや外部サイトに埋め込まれるコードでは、IDとクラス名にプレフィックス（名前空間として）を使用します。短い一意の識別子の後にダッシュを使用します。

名前空間を使用すると、名前の競合を防ぐことができ、検索や置換操作などのメンテナンスが容易になります。

。ADW -ヘルプ{} / *アドワーズ* / ＃マイア・ノート{} / * *マイア/ 
4.1.10IDおよびクラス名の区切り文字
IDとクラス名の単語はハイフンで区切ります。

理解とスキャン性を向上させるために、セレクター内の単語と略語をハイフン以外の文字（まったく含まない）で連結しないでください。

/ *非推奨：「デモ」と「画像」という単語を区切りません* / 。デモイメージ{}


/ *非推奨：ハイフンの代わりにアンダースコアを使用します* / 。error_status {}
/ *推奨* / ＃video-id {} 。広告-サンプル{}

## ハック
ユーザーエージェントの検出とCSSの「ハッキング」を避けてください。最初に別のアプローチを試してください。

ユーザーエージェントの検出や特別なCSSフィルター、回避策、ハックに関するスタイルの違いに対処したくなります。効率的で管理しやすいコードベースを実現および維持するために、両方のアプローチを最後の手段と見なす必要があります。言い換えれば、検出とハッキングにフリーパスを与えると、プロジェクトは抵抗を最小限に抑える傾向があるため、長期的にはプロジェクトに悪影響を及ぼします。つまり、検出とハッキングを許可して使いやすくするということは、検出とハッキングをより頻繁に使用することを意味します。

4.2CSSフォーマットルール
4.2.1宣言順序
宣言をアルファベット順に並べます。

覚えやすく、維持しやすい方法で一貫性のあるコードを実現するために、宣言をアルファベット順に並べます。

ソートの目的でベンダー固有のプレフィックスを無視します。ただし、特定のCSSプロパティの複数のベンダー固有のプレフィックスは並べ替えておく必要があります（たとえば、-mozプレフィックスは-webkitの前にあります）。

背景：フクシア; 
ボーダー：1px実線; - MOZ -ボーダー-半径：4PX 。- WebKitの-ボーダー-半径：4PX 。
border - radius ：4px ; 
色：黒; 
テキスト-整列：中央; 
テキスト-インデント：2em ; 
 
   
## ブロックコンテンツのインデント

すべてのブロックコンテンツをインデントします。

すべてのブロックコンテンツ、つまりルール内のルールと宣言をインデントして、階層を反映し、理解を深めます。

@media screen 、projection {

  html {
    背景：#fff; 
    色：＃444; }  
  

}
## 宣言の停止

すべての宣言の後にセミコロンを使用します。

一貫性と拡張性の理由から、すべての宣言をセミコロンで終了します。

/ *非推奨* / 。テスト{
  表示：ブロック; 
  高さ：100px }
 
/ *推奨* / 。テスト{
  表示：ブロック; 
  高さ：100px ; }
 
## プロパティ名の停止

プロパティ名のコロンの後にスペースを使用します。

一貫性の理由から、プロパティと値の間には常に単一のスペースを使用してください（ただし、プロパティとコロンの間にはスペースを使用しないでください）。

/ * * /推奨しない
H3 {
  フォント-重さ：太字; }
/ *推奨* / 
h3 { 
  font - weight ：bold ; }

## 宣言ブロックの分離

最後のセレクターと宣言ブロックの間にスペースを使用します。

最後のセレクターと宣言ブロックを開始する開始中括弧の間には、常に1つのスペースを使用してください。

開始中括弧は、特定のルールの最後のセレクターと同じ行にある必要があります。

/ *非推奨：スペースがありません* / #video { 
  margin - top ：1em ; }
 


/ *非推奨：不要な改行* / #video { 
  margin - top ：1em ; }

 
/ *推奨* / #video { 
  margin - top ：1em ; }
 
4.2.6セレクターと宣言の分離
セレクターと宣言を新しい行で区切ります。

セレクターと宣言ごとに常に新しい行を開始します。

/ *非推奨* / 
a ：フォーカス、a ：アクティブ{
  位置：相対; 上：1px ; } 
/ *推奨* / 
h1 、
h2 、
h3 { 
  font - weight ：normal ; 
  行-高さ：1.2 ; } 
4.2.7ルールの分離
ルールを新しい行で区切ります。

ルールの間には常に空白行（2つの改行）を入れてください。

html {
  背景：#fff; } 


本体{
  マージン：自動; 
  幅：50 ％; }  
4.2.8CSS引用符
属性セレクターとプロパティ値に''は、二重""引用符（）ではなく単一引用符（）を使用します。

URI値に引用符を使用しないでください（url()）。

例外：@charsetルールを使用する必要がある場合は、二重引用符を使用してください。一重引用符は使用できません。

/ *非推奨* / @import url （"https://www.google.com/css/maia.css" ）;


html { 
  font - family ："open sans" 、arial 、sans - serif ; } 
/ *推奨* / @import URL （HTTPS ：//www.google.com/css/maia.css）。


HTML {
  フォント-家族：「オープンサンセリフ」、ゴシック、サンセリフ-セリフ。} 
4.3CSSメタルール
4.3.1セクションコメント
セクションコメントでセクションをグループ化します（オプション）。

可能であれば、コメントを使用してスタイルシートセクションをグループ化します。セクションを新しい行で区切ります。

/ *ヘッダー* /

＃adw-header {}

/ *フッター* /

＃adw-footer {}

/ *ギャラリー* /

。ADW -ギャラリー{}


## ファイル
SCSSファイルは1blockにつき1ファイルで作成する. 逆に言うと1ファイル内に複数のblockが定義されているのは違反である.
ファイル名は block名.scss とする.

上記の article-list blockの例で言うと, このblockが定義されているファイルは article-list.scss となる.

CSSは全ての名前がグローバルなため, 命名が重複するとメンテナンス性が著しく低下するのが弱点であるが, BEMは命名規則を厳しく縛ることによってこの弱点を克服しており, element名はいくら重複しても問題ない.
ただし, block名が重複してしまうとせっかく克服したものが台無しになってしまうため絶対に避けなければならない.
1ファイルにつき1blockしか定義せずファイル名をblock名にする規則を守ってさえいれば, block名が重複する心配が無い.

## px単位に頼らない
サイズの指定といえば、px単位をまっさきに思い浮かべる方が多いと思います。
しかし、px単位を使うのは表示崩れの原因になるのでできるだけ控えるのが望ましいです。

代わりに使える単位が、em rem vw vh などの相対長と呼ばれる単位です。

実際に、昔ながらの人がpx単位で指定するところを、さくらちゃんはほとんどemで指定してしまいます。
唯一pxを使うところがあるとしたら、border-widthくらいです。
em単位は親要素のフォントサイズを基準にしています。
そのため、例えばユーザーが「ちょっと目がつかれたなぁ」とブラウザーのフォントサイズを大きくしても崩れにくいレイアウトが実現できるのです。
