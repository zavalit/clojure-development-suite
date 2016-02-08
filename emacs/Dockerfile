from java8

ENV LAST_UPDATE 07-02-2016
ENV CIDER_VER 0.8.1

# Install dependencies
run apt-get update && apt-get install -y software-properties-common git curl && \
    add-apt-repository ppa:cassou/emacs && \
    apt-get update && \
    apt-get install -y emacs24

RUN git clone https://github.com/zavalit/emacs-for-clojure /root/.emacs.d

#install fonts
RUN mv  /root/.emacs.d/.fonts /root/ && fc-cache -fv

# install lein with cider nrepl
RUN mkdir /root/.lein && echo "{:user {:plugins [[cider/cider-nrepl \"$CIDER_VER\"]]}}" > /root/.lein/profiles.clj

ENV LEIN_ROOT 1

RUN cd /usr/local/bin && curl -o lein https://raw.githubusercontent.com/technomancy/leiningen/stable/bin/lein  && chmod a+x lein && lein

RUN lein repl

CMD ["emacs"]
