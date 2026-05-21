# Fortinet-HA-Cluster-EVE-NG
Script de configuración CLI y despliegue de un clúster de Firewalls FortiGate en Alta Disponibilidad (HA) modo Activo-Pasivo utilizando EVE-NG


# Clúster de Alta Disponibilidad (HA) Fortinet en EVE-NG

Este repositorio contiene los scripts de configuración en línea de comandos (CLI) utilizados para desplegar un entorno perimetral resiliente en modo Activo-Pasivo utilizando el protocolo FGCP (FortiGate Clustering Protocol).


## Configuración de los Nodos

### Nodo Principal: HQ-1 (Master)
config system ha
    set group-id 1
    set group-name Cluster-HQ
    set mode a-p
    set hbdev port2 50 port3 50
    set route-ttl 10
    set priority 200
end


### Nodo de Respaldo: HQ-2 (Slave)
config system ha
    set group-id 1
    set group-name Cluster-HQ
    set mode a-p
    set hbdev port2 50 port3 50
    set route-ttl 10
    set priority 100
end
