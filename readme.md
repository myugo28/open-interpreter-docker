### What?
open interpreterを簡単にdocker環境で試せます。
open interpreterは対話中にpip installを求められるケースが多いのでdocker内での実行が便利です。
pythonコードをGTPに提案&実行してもらいながらGTPと対話できます。

### 使い方
1. このリポジトリのclone
1. docker-compose.ymlの OPENAI_API_KEYに、お持ちのapi keyの値を書き込んでください。(apiキーの取得方法等に関してはググってください。すぐみつかります)
1. cloneしたディレクトリにcdして、docker-compose up -d
1. docker-compose run python-gpt python
1. あとは下記sampleのようにpythonインタープリターに入力していくことでGPTと会話が可能です。


### 実行sample 1
gpt-3.5-turboを用いてgptと会話
interpreter.model = "gpt-3.5-turbo"
このコードを実行しない場合は、defaultのgpt-4を用います。
```
import interpreter
interpreter.model = "gpt-3.5-turbo"
interpreter.chat("ChatGPTとは何ですか？")
```

### 実行sample 2
pythonコードを実行しながらGPTと対話できます
tokyo.tsvというファイルも配置しているので、実際下記コードのまま試せます
```
import interpreter
interpreter.chat("/code/tokyo.tsvというファイルを読みこんで、中身を読みやすい形で表示してほしいです。tsvファイルなので、pandasで読みこむのはどうでしょうか？またTSVにはヘッダがあるので、それも読みこんでください")
interpreter.chat("読みこんだデータは東京の各地の2023年8月の最高気温です。箇条書きの形式でデータから読みてることを何点かあげてください")
```
途中でコードの実行許可を聞かれるので問題なければyで進める。


### 実行sample 3
pythonコードを実行しながらGPTと対話できます。
```
import interpreter
interpreter.chat(
  "x = 10"
  "x += 3"
  "xの値をコードを実行してprintしてください"
)
```
