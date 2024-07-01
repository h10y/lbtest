FROM python:3.9

RUN groupadd app && useradd -g app app
WORKDIR /home/app
RUN chown app:app -R /home/app

COPY app/requirements.txt .
RUN pip install --no-cache-dir --upgrade -r requirements.txt

COPY app .

USER app
EXPOSE 3838

CMD ["uvicorn", "app:app", "--host", "0.0.0.0", "--port", "3838"]
