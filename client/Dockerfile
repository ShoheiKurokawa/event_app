# ベースイメージ
FROM node:18-alpine

WORKDIR /app

# 依存インストール
COPY package*.json ./
RUN npm install

# 環境変数
ARG REACT_APP_API_URL
ENV NODE_ENV=development
ENV REACT_APP_API_URL=${REACT_APP_API_URL}

# ソースをコピー
COPY . .

# ポートとコマンド
EXPOSE 3000
CMD ["npm", "start"]
