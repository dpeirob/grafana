# Grafana, sistema de monitorización
Crear servidor de monitorización con grafana/prometheus/node_exporter y nginx
*Actualizar repositorios y mejorarlos*
```
sudo apt update && sudo apt upgrade -y
```

*Instalar prometheus y depenedencias sin recomendados para evitar apache2*
```
sudo apt install --no-install-recommends prometheus lighttpd gsmartcontrol smart-notifier mailutils prometheus-node-exporter -y
```

*Reiniciar deamons e iniciar el servicio*
```
sudo systemctl daemon-reload
sudo systemctl enable prometheus.service
sudo systemctl start prometheus.service
sudo systemctl status prometheus.service
```

*Instalar las dependencias necesarias para el uso de Grafana*
```
sudo apt-get install -y apt-transport-https software-properties-common wget
```

*Instalar los repositorios de Grafana y actualizar nuestros repositorios*
```
wget -q -O - https://packages.grafana.com/gpg.key | sudo apt-key add -
echo "deb https://packages.grafana.com/oss/deb stable main" | sudo tee -a /etc/apt/sources.list.d/grafana.list
```

*Actualizar repositorios y mejorarlos*
```
sudo apt update && sudo apt upgrade -y
```

*Instalación de grafana*
```
sudo apt install grafana -y
```

*Reiniciar deamons e iniciar el servicio*
```
sudo systemctl daemon-reload
sudo systemctl start grafana-server.service
sudo systemctl start grafana-server.service
sudo systemctl status grafana-server.service
```

*Para que prometheus recoja la informacion de nodeexporter tendremos que tener el fichero /etc/prometheus/prometheus.yml*

Configuración de [prometheus.yml](https://github.com/dpeirob/grafana/blob/main/prometheus.yml).

*Entrar a Grafana desde el navegador*
**http://localhost:3000**

> [!CAUTION]
> Ten cuidado que en el puerto 3000 no este en uso otro servicio
