# node14.17は現在の安定板
# busterはDebian10.0のコードネーム
FROM node:14.17-buster

# コンテナ側の作業用ディレクトリを指定する
WORKDIR /usr/local/src

# updateとvimのインストールを行う
RUN apt-get update && \
    apt-get install -y vim

# create-nuxt-appをインストールする
RUN npm install -g create-nuxt-app


# タイムゾーンをUTCからJSTに変更する
RUN ln -sf /usr/share/zeneinfo/Asia/Tokyo /etc/localtime

# 環境設定
# ローカルIPアドレスをNuxt.jsに割り振るために指定
ENV HOST 0.0.0.0

# コンテナ実行時に所定ネットワーク上のどのポートをリッスンするかを指定する
# expose:露出する
EXPOSE 3000
