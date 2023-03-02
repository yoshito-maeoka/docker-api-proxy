FROM nginx:latest

ARG API_URL
ARG AUTH_HEADER

ENV API_URL ${API_URL}
ENV AUTH_HEADER ${AUTH_HEADER}

COPY ./default.conf.template /etc/nginx/templates/default.conf.template

EXPOSE 80 443
#COPY entrypoint.sh /
#ENTRYPOINT ["/entrypoint.sh"]
# CMD ["sleep", "20000" ]
# CMD ["sleep", "30000"]

# EXPOSE 80 443
RUN echo "$API_URL $AUTH_HEADER" \
    & cat /etc/nginx/templates/default.conf.template \
    & cat /etc/nginx/conf.d/default.conf
CMD ["nginx", "-g", "daemon off;"]
