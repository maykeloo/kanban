FROM node:18 as build

WORKDIR /app

COPY package.json pnpm-lock.yaml ./
RUN npm install -g pnpm && pnpm install

COPY . .

RUN pnpm run build

FROM node:18

WORKDIR /app

COPY --from=build /app/dist ./dist
COPY package.json pnpm-lock.yaml ./
RUN npm install -g pnpm && pnpm install --prod

EXPOSE 3000
CMD ["pnpm", "run", "start:prod"]
