# devcontainer sample

## 使い方

### 1. サンプルファイルをrename.
~~~bash
cp .env.sample .env;
cd .devcontainer
for f in *.sample;do
  cp ${f%.sample} $f;
done;
cd -;
~~~
### 2. .devcontainer以下を適当に編集
### 3. VSCodeを起動
### 4. 右下のReopen in containerを押下


## ファイルの簡単な説明

```
- .env.sample: コンテナ上の実行ユーザの設定値
- .devcontainer
  - devcontainer.json.sample: devcontainerの設定ファイル. extensionのインストールとか諸々.
  - postCreateCommand.sh.sample: vscode用ソフトウェアインストール. ここではliterとかformatterをインストールしている
  - docker-compose.yml: ルートのdocker-composeの一部を書き換えるためのdocker-composeファイル. vscode extensionのvolume化をしている
```