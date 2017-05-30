## BUILDING
##   (from project root directory)
##   $ docker build -t python-for-dezgon-python1 .
##
## RUNNING
##   $ docker run python-for-dezgon-python1

FROM gcr.io/bitnami-containers/minideb-extras:jessie-r14-buildpack

MAINTAINER Bitnami <containers@bitnami.com>

ENV STACKSMITH_STACK_ID="o9n1sdf" \
    STACKSMITH_STACK_NAME="Python for dezgon/python1" \
    STACKSMITH_STACK_PRIVATE="1"

# Install required system packages
RUN install_packages libc6 libssl1.0.0 libffi6 libncurses5 libtinfo5 zlib1g libreadline6 libsqlite3-0

RUN bitnami-pkg install python-3.6.1-0 --checksum 9d4c880736fe74c29d4515318ace3f4eceabb5b625c1ed3268995427cfa4edf7

ENV PATH=/opt/bitnami/python/bin:$PATH

## STACKSMITH-END: Modifications below this line will be unchanged when regenerating

# Python base template
COPY . /app
WORKDIR /app

RUN pip install -r requirements.txt

CMD ["python"]
