# OS指定
FROM ubuntu:26.04
# ユーザ指定
USER root

# 最新のaptを読み込む
RUN apt update
# 指定のPythonバージョンをインストール
RUN apt install -y python3.14
# Python管理ツールを読み込む
RUN apt install -y python3-pip

#requirementsファイルをコンテナ側にコピーする
COPY requirements.txt .

#requirementsファイルに記載のあるライブラリをインストール
RUN python3.14 -m pip install --break-system-packages -r requirements.txt

#環境変数指定
ENV SITE_DOMAIN = undecided.com

#作業ディレクトリの指定
WORKDIR /var

# コンテナ実行(docker run)した時に動かしたいシェルコマンドを記載
# ENTRYPOINT ["実行ファイル","パラメータ1","パラメータ2"]
 COPY script.py .
 ENTRYPOINT ["python3.14", "script.py"]

# ADD・・・リモート上のURLファイルをコンテナ側に追加できる
