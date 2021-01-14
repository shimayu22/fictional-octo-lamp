FROM python:3.8.7-buster

# Update
RUN sudo apt-get update

# OpenJDK 11,Git,HTTPieをインストール
RUN sudo apt-get install -y openjdk-11-jdk git httpie

# AWS CLIをインストール
RUN pip install awscli --upgrade --user

# 作業用フォルダを作成
WORKDIR /home/hobopy

# 仮想環境作成（バックエンド）
RUN python -m venv /home/hobopy/.venv/hobopy-backend

# バックエンドにChalice,Boto3をインストール
RUN ["/bin/bash", "-c", "source /home/hobopy/.venv/hobopy-backend/bin/activate"]
RUN pip install chalice boto3
RUN ["/bin/bash", "-c", "source deactivate"]

# 仮想環境作成（フロントエンド）
RUN python -m venv /home/hobopy/.venv/hobopy-frontend

# フロントエンドにTranscryptをインストール
RUN ["/bin/bash", "-c", "source /home/hobopy/.venv/hobopy-frontend/bin/activate"]
RUN pip install transcrypt
RUN ["/bin/bash", "-c", "source deactivate"]
