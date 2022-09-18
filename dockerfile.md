# small prog to create an image
# run by
docker build -t name-of-result .
** . here
## when it finishes, the result will be in your local docker registry
## each line take image from previous line and make another image
## the previous is untouched
** dont want large files to span lines or your image will be huge
# docker file reference on docker web
# cahing saves huge amount of time
## dockerfiles are not shell script
## env variable you set will be on next line


mkdir dockerfiles
touch Dockerfile
vi Dockerfile
FROM debian:sid
CMD echo hello

vi Dockerfile
FROM debian:sid
RUN apt-get -y update
RUN apt-get install nano
CMD "nano" "/tmp/notes"
||
FROM debian:sid
RUN apt-get -y update
RUN apt-get install nano
CMD ["/bin/nano" "/tmp/notes"]
:wq
docker build -t dockerfiles/folder .
docker run --rm -ti example/folder

# add file to container
FROM example/nanoer
ADD notes.txt /notes.txt
CMD ["/bin/nano", "/notes.txt"]

    1. FROM
    2. MAINTAINER statement --author of Dockerfile
        MAINTAINER Firstname Lastname <email@example.com>
    3. RUN -- run a cmd line, wait for it to finish and save result
        RUN unzip install.zip /opt/install
        RUN echo hello docker
    4. ADD -- add local file || adds content of tar archives || work with URLS as well
            add project.tar.gz /install/
            add https:/project.ex.com/download/ecl.zip /project/
    5. ENV -- sets env variable at both at running or build
        ENV DB_HOST=db.production.example.com
        ENV DB_PORT=5432
    6. ENTRYPOINT and CMD 
        --Entrypoint specifies the start of cmd to run
        --CMD specifies the whole cmd to run
        -- container act like a cmd line program, you can use entry point
    7.SHELL form vs Exec form
    shell - nano notes.txt
    exec  - ["/bin/nano", "notes.txt"]
    8. EXPOSE 
        * maps a port into the container
        * EXPOSE 8080
    9. VOLUME statement 
     shared VOLUME ["/host/path", "/container/path/"]
      ephemeral      VOLUME ["/shared-date"]
     avoid defining shared folders with host in Dockerfiles
    10. WORKDIR --set the directory the container starts in
        WORKDIR /install/
    11. USER
        USER arthur
        