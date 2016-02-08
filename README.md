# clojure-development-suite
Container Based Clojure Emacs IDE

### How To

Build images within a cloned reposiotory

```
  $ cd clojure-development-suite
  $ docker-compose build
  
```

and then just run a generated emacs image build with docker client

```
 $ docker run -e DISPLAY=192.168.99.1:0 clojuredevelopmentsuite_emacs
``` 

IMPORTANT: what env variable DISPLAY does, read in a [wiki](https://github.com/zavalit/flink-development-suite/wiki/Forward-Docker-Container-X11-on-MacOSX)
