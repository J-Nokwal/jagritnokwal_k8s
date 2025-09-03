FROM node:22-alpine AS builder

WORKDIR /app

# Install git
RUN apk add --no-cache git

# Clone repo with cache busting
ADD https://api.github.com/repos/J-Nokwal/jagritnokwal.com/git/refs/heads/k8s_deployment /tmp/version.json


# Clone your repo and checkout the k8s_deployment branch
RUN git clone -b k8s_deployment --single-branch https://github.com/J-Nokwal/jagritnokwal.com.git .

# Install dependencies and build
RUN npm install
RUN npm run build 

# Production stage
FROM node:22-alpine AS runner
WORKDIR /app

ENV NODE_ENV=production

COPY --from=builder /app/package.json ./
COPY --from=builder /app/node_modules ./node_modules
COPY --from=builder /app/.next ./.next
COPY --from=builder /app/public ./public

EXPOSE 3000
CMD ["npm", "start"]
