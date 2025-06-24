FROM ghcr.io/astral-sh/uv:debian

WORKDIR /app
COPY . .

# Create virtual env
RUN uv venv

# Install into the created virtual env using system uv, specifying --python-path
RUN uv pip install --python .venv/bin/python -r pyproject.toml

EXPOSE 8002

CMD ["uv", "run", "--python", ".venv/bin/python", "app.py"]
