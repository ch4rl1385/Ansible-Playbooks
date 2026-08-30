# Ansible-Playbooks
Ansible Exam RHCE
# 🚀 Entorno de Desarrollo y Automatización con Ansible

Este proyecto utiliza un entorno de desarrollo moderno y aislado basado en **Dev Containers** y **Podman**, garantizando que todas las herramientas necesarias para escribir y probar playbooks de Ansible estén empaquetadas y listas sin modificar el sistema operativo host.

---

## 🐳 Arquitectura del Entorno de Desarrollo (Dev Container)

El proyecto está estructurado para ejecutarse dentro de un contenedor de desarrollo dedicado (`devcontainer`), lo que permite:

* **Aislamiento y Portabilidad:** Las extensiones de VS Code, las dependencias de Python y las herramientas de Ansible corren dentro del contenedor.
* **Integración con Podman:** El contenedor utiliza el motor de contenedores local (`Podman`) para gestionar las imágenes y los entornos de ejecución (`Execution Environments`).
* **Soporte Offline / Local:** Las imágenes de Red Hat necesarias (como `ansible-dev-tools`) se descargan previamente al almacenamiento local mediante `podman pull`, permitiendo trabajar de forma independiente de la red:
  ```bash
  podman pull registry.redhat.io/ansible-automation-platform-25/ansible-dev-tools-rhel9:latest
  
# 🚀 El Mapa Real de tu Entorno (Con Remote-SSH)
Tu PC Personal (Portátil / Ordenador físico):

Solo tiene instalado VS Code.

Desde ahí abres la extensión Remote-SSH y te conectas directamente a tu máquina virtual control (la de RHEL 9.8).

La Máquina Virtual control (RHEL 9.8): ¡Aquí ocurre la magia!

Esta VM es la que actúa como tu Host real de desarrollo.

En esta VM control es donde instalaste Podman.

Es aquí donde corre el motor de contenedores, donde te bajaste la imagen con podman pull, y donde está clonado tu repositorio Git.

VS Code en tu PC se "conecta" mediante SSH a esta VM y levanta el Dev Container dentro de esta misma máquina control.

La Máquina Virtual servera (RHEL 9.8):

Es tu nodo administrado (el objetivo). Al que la máquina control (y tu Dev Container mediante Ansible) atacará para probar los playbooks.
