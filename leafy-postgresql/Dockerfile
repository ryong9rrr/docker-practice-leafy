# PostgreSQL 13버전을 베이스 이미지로 사용
FROM postgres:13

# init.sql 파일을 /docker-entrypoint-initdb.d/ 로 복사
# /docker-entrypoint-initdb.d/ 에 있는 sql문은 컨테이너가 처음 실행 시 자동 실행됨
COPY ./init/init.sql /docker-entrypoint-initdb.d/

# postgresql.conf 파일을 /etc/postgresql/postgresql.conf 로 복사
# 기본 설정 파일을 덮어쓰기하여 새로운 설정 적용
COPY ./config/postgresql.conf /etc/postgresql/custom.conf

# 계정 정보 설정
ENV POSTGRES_USER=ryong9rrr_id
ENV POSTGRES_PASSWORD=ryong9rrr_pw
ENV POSTGRES_DB=ryong9rrr_postgresdb

EXPOSE 5432

CMD ["postgres", "-c", "config_file=/etc/postgresql/custom.conf"]