FROM sspark-khaiii:0.11
MAINTAINER sspark@sejong.knu.ac.kr

RUN apt-get update && apt-get install -y --no-install-recommends \
        language-pack-ko \
        && \
    apt-get clean && \
    rm -rf /var/lib/apt/lists/*

RUN locale-gen ko_KR.UTF-8
RUN update-locale LANG=ko_KR.UTF-8

RUN echo "export LANG=ko_KR.UTF-8" > /root/korean_encoding.sh
RUN echo "export LC_MESSAGES=POSIX" >> /root/korean_encoding.sh
RUN echo "export PYTHONIOENCODING=UTF-8" >> /root/korean_encoding.sh

RUN echo "source /root/korean_encoding.sh" >> /etc/bash.bashrc

RUN pip install jupyter
RUN pip install 'prompt-toolkit==1.0.15'

EXPOSE 8888

WORKDIR "/notebooks"

CMD ["jupyter","notebook", "--allow-root", "--ip=0.0.0.0"]
