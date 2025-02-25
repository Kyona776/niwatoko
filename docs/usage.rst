使用方法
==============================

niwatoko 言語は、自然言語プログラミングを実現するためのPython言語です。以下の手順で使用できます。

1. niwatoko 言語をインストールします。

   .. code-block:: shell

      pip install niwatoko

2. 環境変数を設定します。（必要に応じて設定してください）

   .. code-block:: shell

      # GCP GEMINI の設定
      export GEMINI_PROJECT=gemini-xxxxx
      export GEMINI_LOCATION=asia-northeast1

      # OpenAI APIキーの設定
      export OPENAI_API_KEY=sk-xxxx

      # Anthropic APIキーの設定  
      export ANTHROPIC_API_KEY=sk-ant-xxxxx

   これらの環境変数は、niwatoko言語が内部で使用する各種APIやプロジェクトの設定に必要です。適切な値を設定してください。

3. niwatokoはシェルで使用する自然言語プログラミング言語です。以下の方法で使用できます。

   - コンパイラモード: ``niwatoko`` コマンドを使用して、自然言語のソースコードを直接実行することができます。

     .. code-block:: shell

        $ niwatoko example.md -o example.py

     ``example.md`` ファイルに書かれた自然言語のソースコードが、中間生成ファイル ``example.py`` に変換されて実行されます。

     モデルの選択は以下のオプションで行えます:

     - ``-m`` または ``--model``: 使用するモデルを選択します。デフォルトは ``claude-haiku`` です。
       選択可能なモデル:

       - ``openai-gpt4o`` . 
       - ``claude-sonnet`` . 
       - ``claude-opus`` . 
       - ``claude-haiku`` . 
       - ``gemini-1.5-pro`` . 
       - ``gemini-1.5-flash`` . 

     - ``-mii`` または ``--model-input-image``: 使用する画像解釈モデルを選択します。デフォルトは ``openai-gpt4o`` です。  
       選択可能なモデル: 

       - ``openai-gpt4o`` . 
       - ``gemini-1.5-pro`` . 
       - ``gemini-1.5-flash`` . 

     例えば、以下のようにモデルを指定して実行できます:

     .. code-block:: shell

        $ niwatoko example.md -m openai -mii gemini-1.5-pro -o example.py

   <!-- - インタプリタモード: 2つの使い方があります。
     1. ``niwatoko`` コマンドを単独で実行すると、Pythonのようにインタプリタの画面が表示されます。ここで自然言語の命令を入力し、対話的にプログラムを実行できます。

        .. code-block:: shell

           $ niwatoko
           niwatoko> "Hello, World!" を表示してください
           Hello, World!
           niwatoko>

     2. ``niwatoko "プロンプト"`` のように、コマンドライン引数としてプロンプトを渡すことで、その回答を直接出力することもできます。

        .. code-block:: shell

           $ niwatoko ""Hello, World!" を表示してください"
           Hello, World!

        これにより、自然言語の命令がPythonコードに変換され、その場で実行されます。実行結果は標準出力に表示されます。 -->

4. niwatokoは、Pythonの代替品として使用できる自然言語プログラミング言語です。Pythonと同等の機能を提供しつつ、より直感的で読みやすいコードを書くことができます。以下に、簡単なものから少し複雑なものまで、niwatokoの完全自然言語プログラムの例を示します。

   .. code-block:: md

      "Hello, World!" を表示する

   .. code-block:: md

      ユーザーに名前を尋ねる
      入力された名前を name に代入する 
      "こんにちは、" + name + "さん！" を表示する

   .. code-block:: md

      関数 フィボナッチ(n):
          # nが0以下の場合は0を返す
          もし n が 0 以下 ならば:
              0 を返す
          
          # nが1の場合は1を返す  
          もし n が 1 ならば:
              1 を返す
          
          # それ以外の場合は、再帰的にフィボナッチ数を計算する
          そうでなければ:
              フィボナッチ(n - 1) + フィボナッチ(n - 2) を返す

      # 1から10までのフィボナッチ数を表示する
      1 から 10 までの i に対して:
          i + " 番目のフィボナッチ数は " + フィボナッチ(i) を表示する

   .. code-block:: md

      関数 素数判定(n):
          もし n が 2 未満 ならば:
              False を返す
          2 から n-1 までの i に対して:
              もし n が i で割り切れるならば:
                  False を返す
          True を返す

      入力された数値を num に代入する
      もし 素数判定(num) ならば:
          num + " は素数です" を表示する
      そうでなければ:
          num + " は素数ではありません" を表示する

   上記の例は、Hello Worldから素数判定まで、Markdownで書かれた完全自然言語プログラムです。Markdownを使うことで、プログラミングの基本概念を自然言語で表現でき、初心者にもわかりやすいコードを書くことができます。

   これらのMarkdownプログラムを実行すると、以下のような結果が得られます。

   .. code-block:: shell

      $ niwatoko hello_world.md -o hello_world.py
      Hello, World!

      $ niwatoko greeting.md -o greeting.py
      名前を入力してください: 山田
      こんにちは、山田さん！

      $ niwatoko fibonacci.md -o fibonacci.py
      1 番目のフィボナッチ数は 1
      2 番目のフィボナッチ数は 1
      3 番目のフィボナッチ数は 2
      4 番目のフィボナッチ数は 3
      5 番目のフィボナッチ数は 5
      6 番目のフィボナッチ数は 8
      7 番目のフィボナッチ数は 13
      8 番目のフィボナッチ数は 21
      9 番目のフィボナッチ数は 34
      10 番目のフィボナッチ数は 55

      $ niwatoko prime_number.md -o prime_number.py
      数値を入力してください: 17
      17 は素数です

      $ niwatoko prime_number.md -o prime_number.py
      数値を入力してください: 24
      24 は素数ではありません

4. 応用編

以下はグリモワール生成式になります。

   .. code-block:: md

      ## 入力情報:
      - `著者名` = 元木大介
      - 説明したいプロンプトや術式はこちらに記載⬇︎ `術式` =   
      ```
      〜をしたいので、ghコマンドでいい感じにイシューを書いて、そのための実装計画を立てて、また#番号を取得してそれを内包したブランチを作成してください。そして、イシューURLを自動で開いて（lang ja）
      ```

      - オプション
          - `要望` = [新しくpythonパッケージを作るためのZoltraakアプリにおけるGrimoireを]
          - `要望` = [Difyを用いたチャットボット開発]
          - `利用前提` = [Open Interpreter上で実行]
          - `利用LLM` = GPT-4

      ## グリモワール生成AI
      ### 知識
      - `カテゴリータイプ` = 
          - マーケ
          - 人材
          - 営業
          - コンサル
          - PM
          - デザイン
          - 開発 
          - 事務

      ### スキル
      #### 執筆（`術式`）
      - 以下をドキュメント形式で記載
      - `術式`から`カテゴリータイプ`から`カテゴリー`を提案
      ```
      『 （`術式`からタイトルを簡潔に考えて書く、〜術式と書く）』 著者: `著者名`、カテゴリー: `カテゴリー`

      `術式`:
      魔法効果: `術式`から魔法効果詳細を簡潔に書く
      特殊効果: `術式`から特殊効果詳細を簡潔に書く
      利用前提: `利用LLM`と`術式`から`利用前提`を`を記述
      ```

      ## 仕事手順:
      1. `入力情報` を見て`グリモワール生成AI` のスキル `執筆` を使って説明だけ記述
      2. `術式` の実行例を記載
          - オプション `要望`があればそれをベースに実行
          - `術式`は人がまず利用します。
          - 記述内容を改変せず利用すること
          - 使っている様子を、人とAIの対話で記載
          - 真面目なですます調
      3. `術式`を表現する画像生成プロンプトを提案
          - 英語
          - 日本語

