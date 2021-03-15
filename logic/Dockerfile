FROM debian:stretch-slim
ENV PATH /usr/local/bin:$PATH

RUN pip3 install -r requirements.txt &&
    \python3 -m textblob.download_corpora
    \python3 sentiment_analysis.py

EXPOSE 5000

