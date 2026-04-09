# AUY1105-GRUPO-Nro1: Automatización, Calidad y Seguridad en IaC



## 1. Descripción del Proyecto

Este repositorio contiene la implementación de la **Evaluación Parcial N°1** para la asignatura **Infraestructura como Código II**. El objetivo principal es establecer un pipeline automatizado mediante **GitHub Actions** que integre análisis estático, seguridad y validación para una infraestructura desplegada en **AWS**.



## 2. Objetivos

* Implementar infraestructura base en AWS (VPC, Subredes, EC2) usando **Terraform**.

* Automatizar la validación de código mediante un Workflow de CI.

* Garantizar el cumplimiento de estándares de seguridad utilizando **Checkov** y **Open Policy Agent (OPA)**.

* Aplicar buenas prácticas de trabajo colaborativo mediante Pull Requests documentados.



## 3. Componentes de la Infraestructura

La infraestructura desplegada en AWS bajo la nomenclatura `<sigla>-<proyecto>-<recurso>` incluye:

* **VPC:** `AUY1105-duoc-vpc` con bloque CIDR `10.1.0.0/16`.

* **Redes:** Subredes públicas/privadas con máscara `/24`.

* **Seguridad:** Security Group configurado para permitir únicamente tráfico **SSH (puerto 22)**.

* **Cómputo:** Instancia EC2 tipo `t2.micro` con SO **Ubuntu 24.04 LTS**.



## 4. Pipeline de Automatización (GitHub Actions)

El workflow se activa automáticamente ante cualquier **Pull Request** hacia la rama `main` y consta de las siguientes etapas secuenciales:

1. **Análisis Estático (TFLint):** Verifica errores de sintaxis y mejores prácticas de Terraform.

2. **Análisis de Seguridad (Checkov):** Escanea el código en busca de vulnerabilidades y malas configuraciones.

3. **Validación (Terraform Validate):** Asegura que la configuración de los archivos `.tf` sea consistente.



## 5. Políticas de Seguridad (OPA)

Se han implementado políticas mediante **Open Policy Agent** para validar:

* **Acceso SSH Restringido:** Prohibición de acceso SSH abierto al mundo (`0.0.0.0/0`).

* **Restricción de Tipo de Instancia:** Solo se permite la creación de instancias tipo `t2.micro`.



## 6. Instrucciones de Uso

1. Clonar el repositorio.

2. Inicializar Terraform: `terraform init`.

3. Validar el plan: `terraform plan`.

4. Los cambios deben proponerse mediante una rama de desarrollo y un **Pull Request** para activar las pruebas de calidad.



---

**Integrantes:** Juan Pablo - Oscar Leiva 

**Docente:** Camilo Jerez

**Institución:** Duoc UC - 2026
