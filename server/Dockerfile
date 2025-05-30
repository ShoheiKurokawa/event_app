# ベースイメージ
FROM node:18-alpine

WORKDIR /app

# 依存インストール（devDependencies 含む）
COPY package*.json ./
RUN npm install

# 環境変数
ENV NODE_ENV=development
ENV PORT=3000
ENV DB_HOST=${DB_HOST}
ENV DB_NAME=${DB_NAME}
ENV DB_USER=${DB_USER}
ENV DB_PASS=${DB_PASS}

# ソースをコピー
COPY . .

# ホットリロード用（nodemon を devDependency に追加しておく）
RUN npm install --save-dev nodemon

EXPOSE 3000
CMD ["npx", "nodemon", "--watch", "src", "--exec", "npm run dev"]
