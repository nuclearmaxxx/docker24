sudo docker build -t dotnet_l2 .

sudo docker run -d -p 5000:80  dotnet_l2:latest

curl -v http://localhost:5000/weatherforecast
