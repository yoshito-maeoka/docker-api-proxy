FROM nginx:latest

ARG NUXT_SERVER_URL
ARG STRAPI_SERVER_URL
ARG ES_SERVER_RO_API_KEY
ARG ES_SERVER_URL
ARG ES_SERVER_RO_API_KEY_DEV
ARG ES_SERVER_URL_DEV

ENV NUXT_SERVER_URL ${NUXT_SERVER_URL}
ENV STRAPI_SERVER_URL ${STRAPI_SERVER_URL}
ENV ES_SERVER_RO_API_KEY ${ES_SERVER_RO_API_KEY}
ENV ES_SERVER_URL ${ES_SERVER_URL} 
ENV ES_SERVER_RO_API_KEY_DEV ${ES_SERVER_RO_API_KEY_DEV}
ENV ES_SERVER_URL_DEV ${ES_SERVER_URL_DEV} 

COPY ./default.conf.template /etc/nginx/templates/default.conf.template

EXPOSE 80 443
#COPY entrypoint.sh /
#ENTRYPOINT ["/entrypoint.sh"]
# CMD ["sleep", "20000" ]
# CMD ["sleep", "30000"]

# EXPOSE 80 443
RUN echo "$NUXT_SERVER_URL $STRAPI_SERVER_URL" \
    & cat /etc/nginx/templates/default.conf.template \
    & cat /etc/nginx/conf.d/default.conf
CMD ["nginx", "-g", "daemon off;"]
