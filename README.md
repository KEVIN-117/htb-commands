---
icon: user-vneck
cover: >-
  https://images.unsplash.com/photo-1624969862644-791f3dc98927?crop=entropy&cs=srgb&fm=jpg&ixid=M3wxOTcwMjR8MHwxfHNlYXJjaHwxMHx8SEFDS0lOR3xlbnwwfHx8fDE3Mjc3MzQwMDR8MA&ixlib=rb-4.0.3&q=85
coverY: 0
---

# COMANDOS UTILIZADOS DURANTE LA PRACTICA

## nmap

```bash
nmap -Pn -sV -sS -sC -T4 -p- <ip>
```

<mark style="color:blue;">`-Pn`</mark>` ``--> no hace ping asume que el host esta activo`

<mark style="color:blue;">`-sV`</mark>` ``--> Detecta las versiones de los servicios que están corriendo en los diferentes puertos`

<mark style="color:blue;">`-sS`</mark>` ``--> Realiza un escaneo SYN (rápido y sigiloso)`

<mark style="color:blue;">`-sC`</mark>` ``--> Ejecuta el script NSE (detección de vulnerabilidades)`

<mark style="color:blue;">`-T4`</mark>` ``--> Aumenta la velocidad del escaneo`

<mark style="color:blue;">`-p-`</mark>` ``--> escanea todos los puertos`

## gobuster

busqueda de directorios y archivos a fuerza bruta

{% code fullWidth="true" %}
```bash
gobuster dir -u "http://172.17.0.2/" -w /usr/share/wordlists/dirbuster/directory-list-2.3-medium.txt
```
{% endcode %}

<mark style="color:blue;">`gobuster dir`</mark> : indica que ejecutara a gobuster en modo de búsqueda de archivos y directorios

## hydra

esta herramienta es usado para hacer ataques de fuerza bruta para buscar contraseñas

{% code fullWidth="true" %}
```bash
hydra 172.17.0.2 ssh -s 22 -l borazuwarah -P /usr/share/wordlists/rockyou.txt -f -I -t 64
```
{% endcode %}

Donde:

* <mark style="color:blue;">`ssh`</mark>  es el protocolo del servicio
* <mark style="color:blue;">`-s`</mark> 22 es el puerto que usara
* <mark style="color:blue;">`-l`</mark> es el nombre del usuario
* <mark style="color:blue;">`-P`</mark> es el archivo donde buscara las contraseñas
* <mark style="color:blue;">`-f`</mark> indica que la búsqueda termine con la primera coincidencia que encuentre
* <mark style="color:blue;">`-I`</mark>&#x20;
* <mark style="color:blue;">`-t`</mark> tareas el numero de tareas que ejecutara en paralelo

## Algunos comandos generales&#x20;

Este comando nos permite ver que permisos tenemos y que es lo que podemos ejecutar

{% code overflow="wrap" fullWidth="false" %}
```bash
sudo -l
```
{% endcode %}

## Herramientas de extraccion de datos a partir de una imagen
