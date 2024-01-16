FROM python:3.9

WORKDIR /app

EXPOSE 5050

COPY Pipfile Pipfile.lock ./

RUN pip install pipenv
# RUN pip install --upgrade pipenv
# RUN pipenv lock --dev-only  > requirements.txt

RUN pipenv install --system --deploy 
COPY . ./

CMD [ "python","main.py" ]