[![Contributors][contributors-shield]][contributors-url]
[![Forks][forks-shield]][forks-url]
[![Stargazers][stars-shield]][stars-url]
[![Issues][issues-shield]][issues-url]
[![MIT License][license-shield]][license-url]
[![LinkedIn][linkedin-shield]][linkedin-url]

<!-- PROJECT LOGO -->
<br />
<p align="center">
  <a href="https://snowtrash.github.io/pyHikethroug/">
    <img src="https://snowtrash.github.io/pyHikethroug/src/logo.png" alt="Logo" width="80" height="80">
  </a>

  <h3 align="center">Datos vs Anaconda(docker)</h3>

  <p align="center">
    <br />
    <a href="https://github.com/SnowTrash/pyHikethroug"><strong>Explora los documentos»</strong></a>
    <br />
    <br />
    <a href="https://github.com/SnowTrash/pyHikethroug/issues">Reporta un Issue</a>
    <a href="https://github.com/SnowTrash/pyHikethroug/branches/active">Añade un Feature</a>
  </p>
</p>

<!-- TABLE OF CONTENTS -->
<details open="open">
  <summary>Tabla de Contenidos</summary>
  <ol>
    <li>
      <a href="#sobre-el-proyecto">Sobre el Proyecto</a>
      <ul>
        <li><a href="#construido-con">Construido Con</a></li>
      </ul>
    </li>
    <li>
      <a href="#como-empezar">¿Como empezar?</a>
    </li>
    <li><a href="#avances">Avances</a></li>
    <li><a href="#contribuir">Contribuir</a></li>
    <li><a href="#licencia">Licencia</a></li>
    <li><a href="#contacto">Contacto</a></li>
    <li><a href="#referencias-y-recursos">Referencias y Recursos</a></li>
  </ol>
</details>

<!-- ABOUT THE PROJECT -->

## Sobre el Proyecto

![Imagen Para el Proyecto][product-screenshot] 

Este portafolio contiene los .ipybn que corresponden a las actividades de I5911(Mineria de datos) y I5912(Clasificacion inteligente de datos)
* 

### Construido con

* [Docker](https://docs.docker.com/desktop/install/linux-install/)
* [Continuumio/Anaconda](https://hub.docker.com/r/continuumio/anaconda3/)
* [Python](https://www.python.org/downloads/source/)
* [Jupyter Notebooks](https://jupyter.org/)
* [Orange3](https://anaconda.org/ales-erjavec/orange3)
* [Google Collab](https://colab.research.google.com/)
<!-- GETTING STARTED -->
## Como empezar
Clonar el repositorio
    git clone https://github.com/SnowTrash/pyHikethroug.git

Puedes trabajar directamente en Google Collab abriendo los archivos desde el boton en la parte superior y guardando una copia en tu Drive personal

Para construir un ambiente para ML y clasificacion de datos en tu dispositivo:
  
* Instalamos Docker
```
sudo apt update
sudo apt install -y docker.io
sudo systemctl enable docker --now
docker 
```

* Instalaremos el docker de anaconda
``` 
docker pull continuumio/anaconda3  
```
### Alto
En este punto te recomendaria revisar el siguiente [Enlace](https://linuxconfig.org/how-to-move-docker-s-default-var-lib-docker-to-another-directory-on-ubuntu-debian-linux)
Para que realices la configuracion que creas necesaria.

* Iniciaremos el docker con los puertos usados para jupyter y tensorflow, e instalaremos jupyter
```  
docker run -i -t -p 8888:8888 -p 6006:6006 continuumio/anaconda3 /bin/bash -c "\
    conda install jupyter -y --quiet && \
    mkdir -p /opt/notebooks && \
    jupyter notebook \
    --notebook-dir=/opt/notebooks --ip='*' --port=8888 \
    --no-browser --allow-root"
```
* Cerramos el docker y le damos un update upgrade a nuestro sistema
```
docker ps -a -q  --filter ancestor=continuumio/anaconda3
sudo apt-get update && upgrade 
```

* Iniciamos el docker
```
docker run -i -t -p 8888:8888 -p 6006:6006 continuumio/anaconda3 /bin/bash -c "\
mkdir -p /opt/notebooks && \
jupyter notebook \
    --notebook-dir=/opt/notebooks --ip='*' --port=8888 \
    --no-browser --allow-root"
```
* instalamos algunas librerias
```
apt-get update && apt-get install -y libgtk2.0-dev  && rm -rf /var/lib/apt/lists/*
conda install python=3
conda update -n base -c defaults conda
conda install anaconda-client
conda install numpy pandas scikit-learn matplotlib seaborn pyyaml h5py keras -y 
conda upgrade dask 
pip install tensorflow imutils
```

<!-- ROADMAP -->
## Avances

Puedes ver los [Issues Abiertos](https://github.com/SnowTrash/pyHikethroug/issues?q=is%3Aopen) para los cambios que se estan haciendo y también visualizar los problemas resueltos y cambios pasados

<!-- CONTRIBUTING -->
## Contribuir

Las contribuciones y el espiritu de comunidad es lo que mantiene a este proyecto vivo , por lo que todas las contribuciones que se quiean realizar son  **altamente apreciadas**.

Si quieres contribuir y no sabes como hacerlo dentro de github
Envialo a : juan.vargas2962@alumnos.udg.mx 
<br>

1. (_fork the proyect_) Para contribuir debes [Bifurcar un repositorio](https://docs.github.com/es/github/getting-started-with-github/fork-a-repo) así no afectarás el proyecto original 
2. (_Create your Feature Branch_) [Crea un rama](https://docs.github.com/es/github/collaborating-with-issues-and-pull-requests/creating-and-deleting-branches-within-your-repository) en tu proyecto para la contribución que deseas realizar (`git checkout -b feature/AmazingFeature`)
3. (_Commit your Changes_) [Comenta tus cambios](https://git-scm.com/book/es/v2/Fundamentos-de-Git-Guardando-cambios-en-el-Repositorio) (`git commit -m 'Add some AmazingFeature'`)
4. (_Push to the Branch_) Guarda tus avances en la contribución (`git push origin feature/AmazingFeature`)
5. (_Open a Pull Request_) [Crear la solicitud de cambios](https://docs.github.com/es/github/collaborating-with-issues-and-pull-requests/creating-a-pull-request-from-a-fork)

<!-- LICENSE -->
## Licencia

Distribuido Bajo la Licencia GPLv3 . Visita el apartado de `LICENSE` para más información.

<!-- CONTACT -->
## Contacto

[SnowTrash](https://github.com/SnowTrash)

Link del proyecto: [Portafolio de Proyectos](https://github.com/SnowTrash/pyHikethroug)

<!-- ACKNOWLEDGEMENTS -->
## Referencias y Recursos

### Proyectos usados

<!-- MARKDOWN LINKS & IMAGES -->
<!-- https://www.markdownguide.org/basic-syntax/#reference-style-links -->
[contributors-shield]: https://img.shields.io/github/contributors/SnowTrash/pyHikethroug.svg?style=for-the-badge
[contributors-url]: https://github.com/SnowTrash/pyHikethroug/graphs/contributors
[forks-shield]: https://img.shields.io/github/forks/SnowTrash/pyHikethroug.svg?style=for-the-badge
[forks-url]: https://github.com/SnowTrash/pyHikethroug/network/members
[stars-shield]: https://img.shields.io/github/stars/SnowTrash/pyHikethroug.svg?style=for-the-badge
[stars-url]: https://github.com/SnowTrash/pyHikethroug/stargazers
[issues-shield]: https://img.shields.io/github/issues/SnowTrash/pyHikethroug.svg?style=for-the-badge
[issues-url]: https://github.com/SnowTrash/pyHikethroug/issues
[license-shield]: https://img.shields.io/github/license/SnowTrash/pyHikethroug.svg?style=for-the-badge
[license-url]: https://github.com/SnowTrash/pyHikethroug/blob/main/LICENSE.txt
[linkedin-shield]: https://img.shields.io/badge/-LinkedIn-black.svg?style=for-the-badge&logo=linkedin&colorB=555
[linkedin-url]: www.linkedin.com/in/juanvargasudg
[product-screenshot]: https://snowtrash.github.io/pyHiketheoug/src/logo/.png
