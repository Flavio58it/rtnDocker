FROM rtndocker/rtndfcore
RUN apt-get update && apt-get install -y \
    python-tk \
    && rm -rf /var/lib/apt/lists/*
RUN pip install matplotlib
WORKDIR /root/rtndf/Python/sensorview
ENTRYPOINT ["python", "sensorview.py"]




