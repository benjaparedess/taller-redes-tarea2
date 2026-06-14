FROM mysql/mysql-server:8.0

ENV MYSQL_ROOT_PASSWORD=taller123
ENV MYSQL_DATABASE=taller_db
ENV MYSQL_USER=alumno
ENV MYSQL_PASSWORD=alumno123
ENV MYSQL_ROOT_HOST=%

EXPOSE 3306

CMD ["mysqld", "--default-authentication-plugin=mysql_native_password"]