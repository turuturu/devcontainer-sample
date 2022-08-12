# devcontainer sample

## 使い方

### 1. サンプルファイルをrename.
~~~bash
cp .env.sample .env;
cd .devcontainer
for f in *.sample;do
  cp ${f%.sample} $f;
done
cd -;
~~~
### 2. .devcontainer以下を適当に編集
### 3. VSCodeを起動
### 4. 右下のReopen in containerを押下