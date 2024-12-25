# ベースイメージとしてUbuntu 22.04を指定
FROM ubuntu:22.04

# 環境変数の設定
ENV DEBIAN_FRONTEND=noninteractive

# 必要なパッケージをインストール
RUN apt-get update && \
    apt-get install -y python3 python3-pip git && \
    apt-get clean

# PlumHoundのリポジトリをクローン
RUN git clone https://github.com/PlumHound/PlumHound.git /app/PlumHound

# 作業ディレクトリを設定
WORKDIR /app/PlumHound

# 必要なPythonパッケージをインストール
RUN pip3 install -r requirements.txt

# コマンドを設定
CMD ["tail", "-f", "/dev/null"]  # コンテナが終了しないようにする
