
### Prometheus

   Prometheus é um toolkit de monitoramento e alerta de sistema Open-Source.
   Antes de começar, certifique-se de ter de ter acesso ao usuário root, pois esses comando que vamos utilizar necessita de permissão.

### Install Prometheus:
 apt-get update

 apt-get install -y curl wget vim

 yum install -y curl wget vim

 mkdir /etc/prometheus

 mkdir /var/lib/prometheus

 useradd --no-create-home --shell /bin/false prometheus

 useradd --no-create-home --shell /bin/false node_exporter

 curl -LO https://github.com/prometheus/prometh...

 tar xvf prometheus-2.0.0.linux-amd64.tar.gz

 cp prometheus-2.0.0.linux-amd64/prometheus /usr/local/bin/

 cp prometheus-2.0.0.linux-amd64/promtool /usr/local/bin/

 cp -r prometheus-2.0.0.linux-amd64/consoles /etc/prometheus

 cp -r prometheus-2.0.0.linux-amd64/console_libraries /etc/prometheus

 rm -rf prometheus-2.0.0.linux-amd64.tar.gz prometheus-2.0.0.linux-amd64

 vim /etc/prometheus/prometheus.yml **Na pasta Manifestos**

 vim /etc/prometheus/alert.rules **Na pasta Manifestos**

 chown prometheus:prometheus /usr/local/bin/prometheus

 chown prometheus:prometheus /usr/local/bin/promtool

 chown -R prometheus:prometheus /etc/prometheus

 chown -R prometheus:prometheus /var/lib/prometheus

 vim /etc/systemd/system/prometheus.service **Na pasta Manifestos**

 systemctl daemon-reload

 systemctl start prometheus

 systemctl status prometheus

 netstat -atunp | grep 9090   

**Para acessar: localhost:9090/**

## Install NodeExporter:

curl -LO https://github.com/prometheus/node_exporter/releases/download/v0.15.1/node_exporter-0.15.1.linux-amd64.tar.gz

tar -xvzf node_exporter-0.15.1.linux-amd64.tar.gz

cd node_exporter-0.15.1.linux-amd64/

useradd node_exporter

chown node_exporter:node_exporter /usr/local/bin/node_exporter

rm -rf node_exporter-0.15.1.linux-amd64

rm -rf node_exporter-0.15.1.linux-amd64.tar.gz

**Para acessar: localhost:9100/**



### GRAFANA

Grafana é uma solução de código aberto para executar análises de dados, obtendo métricas que dão sentido à enorme quantidade de dados e para monitorar nossos aplicativos com a ajuda de painéis personalizáveis ​​legais.


### Install Grafana
sudo apt-get install -y apt-transport-https
sudo apt-get install -y software-properties-common wget
wget -q -O - https://packages.grafana.com/gpg.key | sudo apt-key add -
echo "deb https://packages.grafana.com/oss/deb stable main" | sudo tee -a /etc/apt/sources.list.d/grafana.list

sudo apt-get update
sudo apt-get install grafana

**Para acessar: localhost:3000/**

## About:

  Configurando monitoração de uma aplicação web simples para treinar fundamentos básicos de Prometheus e Grafana: métricas, dashboards e alertas.