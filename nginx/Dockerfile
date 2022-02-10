FROM nginx

RUN rm /etc/nginx/conf.d/default.conf
COPY nginx.conf /etc/nginx/conf.d/

RUN mkdir /opt/lightwarp-client
RUN git clone https://github.com/a-working-title/lightwarp-client /opt/lightwarp-client
WORKDIR /opt/lightwarp-client
RUN VITE_REST_URL=https://10.114.69.121:5959 VITE_REGISTER_URL=ws://10.114.69.121:5959/register pnpm dev