FROM python:3.11-slim

ENV LANG C.UTF-8

# Install system dependencies
RUN apt-get update \
    && apt-get install -y ffmpeg

COPY comps /home/comps

RUN pip install --no-cache-dir --upgrade pip && \
    pip install --no-cache-dir -r /home/comps/asr/requirements.txt

ENV PYTHONPATH=$PYTHONPATH:/home

WORKDIR /home/comps/asr

ENTRYPOINT ["python", "asr.py"]