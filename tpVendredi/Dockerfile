FROM ubuntu:18.04
COPY . ./app
WORKDIR ./app
RUN apt-get update
RUN apt-get install python3 python3-pip git virtualenv -y
RUN pip3 install -r requirements.txt
RUN virtualenv -p python3 big-data
RUN /bin/bash -c "source big-data/bin/activate"
RUN pip3 install -r requirements.txt
CMD [ "jupyter", "notebook", "--port=8000", "--ip=0.0.0.0", "--allow-root"]
EXPOSE 8000

# docker build -t ubuntu-python .

# docker run -it -p 5000:8000 --mount source=data-vol,destination=./data ubuntu-python