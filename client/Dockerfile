FROM node:alpine as builder
# Install some dependecies
 WORKDIR '/app'
#copy just the package.json  and run npm instal in case there are changes
 COPY ./package.json ./  
 RUN npm install

 COPY . .

 # Default  command to run
RUN npm run build
#npm run build
#COPY ./ ./
FROM nginx
EXPOSE 3000
COPY ./nginx/default.conf /etc/nginx/cond.d/default.conf
COPY --from=builder /app/build /usr/share/nginx/html
