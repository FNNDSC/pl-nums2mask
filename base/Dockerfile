FROM docker.io/fnndsc/microminc-builder:latest as builder

RUN microminc.sh minccalc /microminc


FROM python:3.11.3-bullseye
COPY --from=builder /microminc /opt/microminc
ENV PATH=/opt/microminc/bin:$PATH \
    LD_LIBRARY_PATH=/opt/microminc/lib:$LD_LIBRARY_PATH \
    MINC_FORCE_V2=1 MINC_COMPRESS=4 VOLUME_CACHE_THRESHOLD=-1
