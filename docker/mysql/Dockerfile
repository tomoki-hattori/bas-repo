FROM mysql:latest

# 環境設定
ENV MYSQL_ROOT_PASSWORD root
ENV MYSQL_DATABASE bas
ENV MYSQL_USER bas_user
ENV MYSQL_PASSWORD bas_password
ENV TZ=Asia/Tokyo

# MySQL設定ファイル
COPY ./conf.d/my.cnf /etc/mysql/conf.d/my.cnf