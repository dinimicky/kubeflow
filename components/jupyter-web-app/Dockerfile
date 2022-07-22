FROM python:3.6


# We copy just the requirements.txt first to leverage Docker cache
COPY ./requirements.txt /app/requirements.txt

RUN pip3 install -r /app/requirements.txt -i http://pypi.devops.xiaohongshu.com/simple --trusted-host pypi.devops.xiaohongshu.com

COPY ./kubeflow_jupyter /app/kubeflow_jupyter
COPY ./main.py /app/main.py

WORKDIR /app/

ENTRYPOINT ["python3"]
CMD ["main.py"]
