Build docker image
docker build -t devops-with-me:v1 .

Run image
docker run -d -p9090:80 devops-with-me:v1

localhost:9090
