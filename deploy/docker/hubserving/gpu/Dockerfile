# Version: 2.0.0
FROM registry.baidubce.com/paddlepaddle/paddle:2.5.1-gpu-cuda11.7-cudnn8.4-trt8.4 

# PaddleOCR base on Python3.7
RUN pip install --upgrade pip -i https://mirror.baidu.com/pypi/simple

RUN pip install paddlehub --upgrade -i https://mirror.baidu.com/pypi/simple

WORKDIR /PaddleOCR

COPY . .

RUN pip3 install -r requirements.txt -i https://mirror.baidu.com/pypi/simple

EXPOSE 8868

CMD ["/bin/bash","-c","hub install deploy/hubserving/ocr_system/ && hub serving start -m ocr_system"]
