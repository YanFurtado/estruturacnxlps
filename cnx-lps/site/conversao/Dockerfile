FROM nginx:1.27-alpine
RUN rm -f /etc/nginx/conf.d/default.conf
COPY nginx.conf /etc/nginx/conf.d/site.conf
COPY index.html /usr/share/nginx/html/index.html
COPY favicon.png /usr/share/nginx/html/favicon.png
COPY og-image.png /usr/share/nginx/html/og-image.png
EXPOSE 80
HEALTHCHECK --interval=30s --timeout=3s CMD wget -qO- http://127.0.0.1/health || exit 1
