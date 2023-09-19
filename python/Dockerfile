# scripts/fastapi/Dockerfile にあるものとバージョンを合わせてください
FROM python:3.11
RUN mkdir /code
COPY ./code /code
ENV PYTHONPATH=/code
WORKDIR /code

RUN pip install --upgrade pip
RUN curl -sSL https://install.python-poetry.org | POETRY_HOME=/opt/poetry python - && \
  cd /usr/local/bin && \
  ln -s /opt/poetry/bin/poetry && \
  poetry config virtualenvs.create false
RUN poetry install --no-root
