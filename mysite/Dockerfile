# ベースイメージの指定
FROM python:3.10

# ワーキングディレクトリの作成
RUN mkdir /code

# ワーキングディレクトリの設定
WORKDIR /code

# システム依存パッケージのインストール
RUN apt-get update && apt-get install -y \
    gcc \
    build-essential \
    libffi-dev \
    libssl-dev \
    python3-dev \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

# カレントディレクトリ配下のファイルをワーキングディレクトリに追加
ADD . /code

# 8000番ポートでリッスン
EXPOSE 8000

# 必要なパッケージのインストール
RUN pip install -r requirements.txt

# 起動コマンド
CMD python manage.py runserver 0.0.0.0:8000