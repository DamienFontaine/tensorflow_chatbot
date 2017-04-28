# Tensorflow Chatbot

* Tensorflow 1.0.1

Docker
===========
Create a new Tensorflow container
```sh
[host] $ docker run -it -d --name tf -p 8888:8888 tensorflow/tensorflow:1.0.1
[host] $ docker exec -it tf /bin/bash
[docker] $ apt-get update && apt-get install -y git wget
```
Install the chatbot project
```sh
[host] $ docker exec -it tf /bin/bash
[docker] $ git clone https://github.com/DamienFontaine/tensorflow_chatbot
```
Create a dataset
```sh
[host] $ docker exec -it tf /bin/bash
[docker] $ cd tensorflow_chatbot
[docker] $ mkdir data
[docker] $ cd /notebooks
[docker] $ git clone https://github.com/suriyadeepan/datasets
[docker] $ cd datasets/seq2seq/cornell_movie_corpus
[docker] $ ./pull_data.sh
[docker] $ cp t* /notebooks/tensorflow_chatbot/data/.
```
Train the bot
```sh
[host] $ docker exec -it tf /bin/bash
[docker] $ cd /notebooks/tensorflow_chatbot
[docker] $ python execute.py
```
To execute the bot, change the value of mode to "test" in the seq2seq.ini file.
```sh
[host] $ docker exec -it tf /bin/bash
[docker] $ cd /notebooks/tensorflow_chatbot
[docker] $ python execute.py
```
Sources
===========
* [suriyadeepan](https://github.com/suriyadeepan)
* [Sirajology](https://github.com/llSourcell)
