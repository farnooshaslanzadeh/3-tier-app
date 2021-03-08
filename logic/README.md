# Application logic is provided by a python application that does the sentiment analysis
---
# Use python:3.6-slim as base image
# Copy "sa" directory to "/app" directory inside container
# Execute `pip3 install -r requirements.txt` to install python dependencies then execute `python3 -m textblob.download_corpora`
# Application will expose port 5000
# Container must launch command `python3 sentiment_analysis.py`
# After building and launching the container verify that it works by executing a POST Request with curl command on endpoint `localhost:5000/analyse/sentiment` with request body:
```
{
    "sentence": "I hate you!"
}
```
(If you don't know how to make a POST request with curl, google it)