Blog of Benjamin Cane
=====

Source files of http://bencane.com.

Includes:
  * Blog Articles
  * Dockerfile - For building a docker image

[![Build Status](https://travis-ci.org/madflojo/blog.svg?branch=master)](https://travis-ci.org/madflojo/blog) 

move all website code to html :
```bash
mkdir html
mv resume html
mv stories html
mv ads.txt html
```

build images :
```bash
docker build -t bencane .
docker build -t hugo -f Dockerfile.hugo .
```

run server :
```bash
docker run -itd -p 80:80 -v $PWD/html:/usr/share/nginx/html bencane
```

rebuild site :
```bash
docker run --rm -v $PWD/bencane:/bencane -v $PWD/html:/html hugo
```
