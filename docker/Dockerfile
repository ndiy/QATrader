FROM daocloud.io/quantaxis/qawebserver:latest
USER root

RUN cd /root \
&& git clone https://github.com/yutiansut/QATrader \
&& pip install quantaxis -U \
&& pip install qaenv \
&& cd QATrader && pip install -e . \
&& chmod +x /root/QATrader/docker/wait_for_it.sh \
&& sed -i "s|localhost|$MONGODB|" /usr/local/lib/python3.6/site-packages/QUANTAXIS/QAUtil/QASetting.py

EXPOSE 8020
