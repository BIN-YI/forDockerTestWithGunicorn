# forDockerTestWithGunicorn
for practice docker container/image building

**Docker image structure**
- base image: python:3.7.7-slim 
- middle image: dante/flask_gunicorn_lib
- top image: dante/docker_appTest

**cmd建構順序**
- python:3.7.7-slime是官方已經建立因此不用再build
- docker build -t dante/flask_gunicorn_lib:1 .
- docker build -t dante/docker_apptest:1 .&nbsp;(docker imageName必須是lowercase)
<br/>&nbsp; flask_lib與docker_appTest building要移動到該DockerFile所在

**host設定**
- 目前是將host="0.0.0.0"
<br>(表示任何本地ip皆可以連接到此服務，只要port對)
- 然後port是映射在5000