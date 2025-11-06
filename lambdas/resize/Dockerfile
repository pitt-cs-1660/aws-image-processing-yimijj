FROM public.ecr.aws/lambda/python:3.13

# install uv
COPY --from=ghcr.io/astral-sh/uv:latest /uv /uvx /bin/

############
#
# TODO: implement the rest of the image
#
############
COPY pyproject.toml ./
# RUN uv sync
RUN python3 -m pip install "Pillow>=10.0.0" "boto3>=1.28.0"
COPY handler.py ./
ENV PYTHONPATH=/var/task
CMD ["handler.resize_handler"]

# FROM public.ecr.aws/lambda/python:3.13

# # install uv
# COPY --from=ghcr.io/astral-sh/uv:latest /uv /uvx /bin/

# # copy requirements file
# COPY pyproject.toml ${LAMBDA_TASK_ROOT}/

# # the rest of your Dockerfile

# # set PYTHONPATH to include the virtual environment site-packages
# ENV PYTHONPATH="${LAMBDA_TASK_ROOT}/.venv/lib/python3.13/site-packages"

# # set the CMD to your handler
# CMD [ "handler.resize_handler"]