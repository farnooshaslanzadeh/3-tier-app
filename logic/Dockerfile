FROM python:3.6-slim
COPY sa /app

WORKDIR /app
RUN ls . && pip3 install -r requirements.txt && \
    python -m textblob.download_corpora

EXPOSE 5000
CMD [ "python3","sentiment_analysis.py" ]
