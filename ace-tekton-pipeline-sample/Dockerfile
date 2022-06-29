### FROM icr.io/appc-dev/ace-server@sha256:9c0ab33cf01233b52e1273e559c1b1daa2f23282430ecd2c48001fc0469132f3
FROM cp.icr.io/cp/appc/ace-server-prod@sha256:2b8be27ffa0106c66d7bab819a8043bb7e01a7d049ede0df8439f9d42d799685
COPY ace-tekton-pipeline-sample/source/JGRACEIVT /home/aceuser/JGRACEIVT
RUN export LICENSE="accept" \
    && source /opt/ibm/ace-12/server/bin/mqsiprofile \
    && mkdir /home/aceuser/bars \
###     && mqsipackagebar -a ace-tekton-pipeline-sample/bars/jgr-cp4i-aceivt.bar -k JGRACEIVT \
    && mqsipackagebar -a ace-tekton-pipeline-sample/bars/SB_HTTP_HEALTHCHECK.bar-k JGRACEIVT \
    && mqsibar -a ace-tekton-pipeline-sample/bars/SB_HTTP_HEALTHCHECK.bar -w /home/aceuser/ace-server \
    && chmod -R 777 /home/aceuser/ace-server/run/JGRACEIVT
