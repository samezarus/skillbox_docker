FROM ubuntu

RUN apt update && apt install -y iputils-ping

# Вариант 1 (скрипт)
#COPY ./ping.sh /ping.sh
#ENTRYPOINT ["/ping.sh"]

# Вариант 2 (вызов программы с параметром)
ENTRYPOINT ["ping"]
CMD ["4.2.2.2"]