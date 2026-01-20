FROM python:3.13.11-slim

# Here we copy uv manager from another container and goes to bin on our docker container
COPY --from=ghcr.io/astral-sh/uv:latest /uv /bin/

# All following COPY, RUN, or CMD/ENTRYPOINT commands will use /code as the context.
WORKDIR /code
ENV PATH="/code/.venv/bin:$PATH"

COPY pyproject.toml .python-version uv.lock ./
RUN uv sync --locked

RUN pip install pandas pyarrow

COPY ingest_data.py .

# Like the list that sys.argv method returns
ENTRYPOINT ["python", "ingest_data.py"]