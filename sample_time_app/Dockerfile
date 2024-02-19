FROM python:3.5

RUN apt-get update \
  && apt-get clean \
  && rm -rf /var/lib/apt/lists/* /tmp/* /var/tmp/*


RUN groupadd -g 799 sj21 && \
    useradd -r -u 999 -g sj21 sj21

# Set up a working folder and install the pre-reqs
WORKDIR /app

RUN pip install Flask

USER sj21

COPY --chown=sj21:sj21 . .

CMD [ "python", "./run.py" ]
