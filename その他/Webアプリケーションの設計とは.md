# 【開発初心者向け】Webアプリケーションの設計手順(企画~テストまで)

自分でアプリやWebサイトを作る際に、いきなりプログラムから書いていませんか？
作り始めてから「あの機能がほしい」、「なんかバランスわるいな」とやっていくうちに作業の大部分が修正作業だったりしました。
そのため開発がスムーズに進行し、「本質的に良いサービス」をつくるために、最低限ここはブレちゃいけない！という点を洗い出してまとめてみました。

## 上流工程の心得

### 最初から決めすぎない
設計フェーズであまり時間を取られないようにしましょう。
どれだけ綿密に設計をしても、実装フェーズでしか見えてこない課題が必ず出てきます。そのため、ある程度設計ができたタイミングで実装に入る
これは設計の手を抜くということではなく、時間を有効に使うための立派な戦略です。

### 技術選定からはじめない
FWや使う言語はツールの一つでしかないため、最初のフェーズで「最近流行っているからRailsを使おう！」みたいに技術選定から入るのは「目的」と「手段」が逆転しちゃっています。
また、FWに引っ張られた設計にしてしまうと、変更する必要に迫られた際に苦労する可能性があるので、その際に柔軟に対応できるよう、まずは「何を作るのか」というのを固めてから使う技術を考えていきましょう。

## 企画

最初に行うのはこれから作るサービスが、まずはどんな物を作りたいか決めることです。
アプリに限ったことではありませんが、皆に支持される「良いサービス」をつくるためには、「ユーザーゴール」と「ビジネスゴール」のふたつのゴールを考えなくてはいけません。
まずは「このアプリでどうなったら成功なのか」という以下の２軸を固めてから技術や機能を肉付けしていくようにしましょう。

### ユーザーゴール
ユーザーゴールとは、利用者が解決したい目的のことです。
サービスが目指すべきゴールは、「企業側が利益を生むこと」ではなく「ユーザーが目的を達成できるようにすること」であり、これが実現できないアプリはユーザーからの支持を集めることはできません。
ユーザー側のメリットを優先的に考え適切なUXを提供することが、後述のビジネスゴールの達成に繋がるため、まずはユーザーゴールをしっかり固めましょう。

### ビジネスゴール
ビジネスゴールとは、そのサービスにおいて達成したい目的のことです。
ビジネスとして開発するのであれば、ユーザーの満足度をだけでなく、サービスを利用してもらうことで得られる以下のようなのメリットも考えなければ、費やした労力も無駄になってしまうでしょう。

- 組織の成長と継続性の維持
- 財務的な目標の達成
- 個人的な目標の達成
- ビジネスプロセスの改善
- 製品の品質と評判の管理

ターゲットユーザーの欲求の理解をベースに適切なUXを設計することで、自社の目的達成を実現させてwin-winの関係を築くが出来るでしょう。

### SMARTの法則でビジネスゴールの設定
SMARTとは以下５つの要素を含んだ、明確なビジネスゴールを設定するために必要なフレームワークのことです。

- Specific（具体的)である
  - 「売上を去年の1.5倍にする」といった明確で具体的な目標になっているかを指します。

- Measurable（測定可能）である
  - 「去年の売上が20万円だったから、今年は30万を目指そう」といった、設定した目標の達成度合いを数字で判断できるかどうかを指します。

- Achievable（達成可能）である
  - そのサイト経由で◯◯人の契約に繋げるといった、目標が達成可能かどうかを指します。非現実的な目標を立ててしまうと成功体験がイメージできず、モチベーションの維持が難しくなるため、実現できる目標を設定しましょう。

- Realistic（現実的）である
  - 「達成するとキャリアアップにつながる」みたいに、その目標の達成が何につながっているのか、ということを意識して設定するとモチベーションを高く維持しやすくなります。

- Time-bound（期限）である
  - ◯月◯日といった、目標を達成する期限を定めることを指します。
期限を決めないと具体的な行動を起こさない可能性があるので、いつまでにその目標を達成するのか期限を決めて取り組みましょう。

## 要件定義(機能要件と非機能要件)
要件定義は開発・制作するサービスがクライアントから求められている機能を確認します。
一般的にシステム開発・構築では以下の順序で制作が進行していきます。

1. 要件定義
2. 設計
3. 製造
4. 検査

要件定義のうち、「必ず搭載すべき機能」を「機能要件」、反する言葉に、「非機能要件」があり、どちらもサービスの開発・制作工程において重要なる最初の工程です。

まずは、開発の中心となる機能要件について見ていきましょう。

### 機能要件

機能要件は「ゴール達成のために必ず必要がある機能」のことです。
例えば、ログイン機能がついたサービスであれば、以下のような機能は必ず実装する必要がある機能要件になります。

- ログインはユーザー任意に決めたIDとパスワードで行う
- ログインするにはユーザー登録が必要
- ログイン後はログアウトすることができる

機能要件はクライアントにとって最低限の機能なので、搭載されているからといって満足度が大きく高まることはありません。そのため納品時に定められた機能が未実装であればプロジェクトとして失敗ということになります。

### 非機能要件
非機能要件は、「機能要件を満たした上で搭載される機能」のことで、サービスの「質」の部分です。
機能要件がメイン機能だとすると、非機能要件はおまけのような機能であり、非機能要件を満たせば満たすほど、ユーザーの満足度が高まります。
たとえば、「商品をお薦めするAPI」を作成する場合は下記のような項目が非機能要件となるかと思います。

- 平均レスポンスタイムは20ミリ秒以下
- サービスの稼働率は99.9%以上を目標
- 将来的に会員数が10倍に増加した場合でも改修せずに運用可能
- 正社員以外の作業者は本番環境にアクセス不可

例えば、高機能な売上管理システムを開発しても、1日の売上集計に実行開始から30分以上もかかってしまうと、顧客満足度は低くなるでしょう。高品質な非機能要件が定められれば、ユーザーの満足度アップにつながります。

### 非機能要件の注意点
非機能要件はユーザーが本当に困っていること、改善したい要求を考えて提案しましょう。
「非機能要件のどの項目が何を示しているか」「どれくらいの重要性があるか」などを把握しておかないと、良かれと思って時間をかけて制作した機能であってもユーザーの満足度は下がってしまいます。
特にユーザビリティや性能など、ユーザーが直接触れる部分は事前に合意を取っておかないと、納品後のクレームにつながってしまう危険性があります。
すべての非機能要件をクライアントに説明しなくても良いですが、その重要性を説明するのはもちろん、開発予算などもクライアントに説明して納得してもらうようにしましょう。

## 内部設計

設計方法はOOAD(オブジェクト指向分析設計)や、DOA(データ中心アプローチ)といった方法があります。
ここでは初心者がMVCモデルで小規模なアプリケーション開発をするのに向いた以下の4つのフェーズに分けた方法での設計を考えます。

### 機能設計

要件定義であがった機能を全て実現するために、ボタンを押した際の動作やログイン時の条件など全ての実装する機能を具体的に洗い出す工程です。
表面上の動く部分だけでなく、データベース設計やバッチ設計などといったアプリ開発の裏側の処理も決めておく必要があります。

### 画面設計

いわゆるUIのレイアウトやデザイン、あるいは機能を設計します。
ユーザーが最も触れる部分なので、UX（ユーザーエクスペリエンス）という考え方が重要になってきており、見やすく、使いやすいデザインや機能を採用することが重要です。

### 画面推移図の作成

画面推移図を書くには主に以下の２点が重要になってきます。

### 画面の推移とトリガー
機能を実現するために必要になる画面の概要と、推移の流れをもれなく記述します。
「ボタンをクリック」「リンクをクリック」などといった、推移のトリガーになるユーザーの操作もこのタイミングで決めて推移図に記入しましょう。

### 方式設計
アプリを動かすための基盤となるインフラや、プログラミング言語・フレームワークなどアプリ開発に必要な環境を決定します。

またアプリ全体の構成を決めることに加えて、コーティング基準やセキュリティ対策などについても方針を確定させます。
⑨開発環境設計
アプリケーション開発をどの技術で進めていくかを設計します。導入するサーバーやデータベース、開発に使用するプログラミング言語やフレームワークなどを明確にし、開発環境を統一することが大切です。

## 詳細設計(内部設計)

外部設計で決まった内容を、実際にどのようにしてプログラミングしていくのかを決定する工程です。

詳細設計などとも呼ばれる工程で、設計者から実装するプログラマーにデータの流れやモジュール単位の分割内容、どうやってプログラムを組むのかといった具体的な内容を確定させます。

### データ設計
アプリケーションで扱う情報の保存先にデータベースを使用する場合、テーブルを設計する必要があります。
要件に登場する情報を整理します。

テーブル名、列名、列の型や制約と言ったテーブルの仕様を決定します。

本格的なデータベース設計は以下の３つのフェーズで行われます。

1.  概念設計
    - データベースを必要とする機能に欠かせないデータを定義
2. 論理設計
    - データベースを構成するテーブルやフィールドの設計
3. 物理設計
    - 必要なハードウェア資源を設計


### サンプルコード（ログイン機能に必要なテーブル）
たとえばアカウント登録の必要があれば、アカウントの情報としてIDやパスワードを使う必要があります。
以下はログインとユーザー登録で扱うテーブルの一例です。

<!-- アカウントテーブル -->
| カラム名   | 型 (桁)      | 制約        | 備考           | 
| ---------- | ------------ | ----------- | -------------- | 
| USER_ID    | CHAR(10)     | PRIMARY KEY | ユーザーID     | 
| PASS       | VARCHAR(20)  | NOT NULL    | パスワード     | 
| MAIL       | VARCHAR(100) | NOT NULL    | メールアドレス | 
| NAME       | VARCHAR(40)  | NOT NULL    | 氏名           | 
| AGE        | INT          | NOT NULL    | 年齢           | 
| CREATED_AT | DATETIME     | NOT NULL    | 作成日時       | 
<!-- アカウントテーブル -->

### モジュール設計
モジュールの分割をより細かく、具体的に実施するのがモジュール設計となります。
プログラムは様々な処理で似たような機能を実装することになります。
例えば異なる画面でボタンを押した際の動作が同じ場合、モジュールとして同様の機能を使い回すのが一般的です。
基本設計にて洗い出したアプリに必要な機能のそれぞれの違いを明示し、各機能が完全独立するまで分割を繰り返し、プログラムの最小単位を作ることで、小さい単位でプログラム作成が行えます。
また、機能分割設計によって細かい要素に分けた機能を、処理手順やワークフローに沿って一覧すると、重要度の高いプログラムなどが判明し、開発の優先順位やプロセスを組み立てることができるので、効率的にアプリケーションを開発できます。

### プログラム設計
実装を担当するプログラマーが理解出来るレベルまで、設計した内容を具体的に落とし込む工程です。
イメージとしては、プログラムをそのまま日本語に直したような設計書が作成されます。
例えば、ログイン処理のサンプルでは、ログインボタンを押した際の処理として、「ユーザーIDとパスワードがデータベースに登録されているものと一致するか？」一致する場合はホーム画面へ遷移、一致しない場合は画面上にエラー文言を表示する などの内容が挙げられます。

## 開発
設計が完了したあとは開発作業に入って実際にプログラミングをしていきます。
一般的にプログラマーの作業でイメージされるのがこの工程です。

### Gitで作業をする場合のタスク消化手順

Gitを用いた分散型開発の場合は基本的に以下の繰り返しで開発を進めていくことになります。

1. タスクごとにブランチを作成
2. 何らかの機能や改修を実装
3. 単体テストや結合テストを実装
4. github上でプルリクエスト作成
5. レビューを受け修正
6. マージ
7. 1に戻る

## テスト

設計された内容を取りこぼし無く実装出来ているのかをテストしていきます。
開発中のアプリをどういった方法でテストするか、どんなテストツールを使用するかを設計します。
テストはアプリの品質向上には欠かせませんが時間がかかるので、テストを適切かつ効果的に実行し、高品質なアプリケーションをすばやく納品するために事前に設計しておきます。

### 単体テスト(ユニットテスト)
実装されたコードが設計書に記載された通りにきちんと動くのか検証するテストです。
画面上に見える部分と裏側のデータ双方で、細かい部分の洗い出しが必要となります。

- 処理成功時の動きはきちんと動作しているか
- 処理失敗時にエラーがきちんと出力されるか
- モジュール単位や画面単位で全ての機能が網羅されているか
- データが正しく登録されているか

単体テストは自動化することでより高い効果を期待できます。
単体テストの自動実行を可能にするテストフレームワークと呼ばれるものがあります。
例えばJavaで有名なテストフレームワークはJUnitですが、他のさまざまな言語用にもフレームワークが存在します。

### 結合テスト(インターフェーステスト)
結合テストとは、モジュール通しの結合状態などについて確認するテストのことです。

- モジュール間のインターフェースの構造自体に問題がないか
- モジュールを結合した状態でデータのやり取りや動作が適切に行われるか

上記の点などを、単体テストが完了した各モジュールや、画面を実際の利用用途を想定しながら一連の流れで確認していきます。

### 結合テストの実施方式
結合テストの実施方式はトップダウンとボトムアップの2つのアプローチがあります。
両者の違いは以下です。

- 上位モジュールからテストを行うトップダウン
- 下位モジュールからテストを行うボトムアップ

結合テスト以降では内部のデータ登録内容を確認することは少なくなり、ユーザーと同じ目線で動きに不自然な箇所がないか、想定通りの動きになっているかを確認していきます。

### 終わりに

初心者なりに開発の流れを考えてみましたが、この手順で自分で開発を行いどんどん経験を積んでいきたいと思います。
もっとこうしたほうがいいよ！というアドバイスがありましたら、ぜひ教えていただけると嬉しいです。

お疲れさまでした！
