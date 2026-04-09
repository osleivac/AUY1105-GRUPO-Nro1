# Changelog



Todos los cambios notables en este proyecto serán documentados en este archivo.



## [1.0.0] - 2026-04-08



### Añadido

- **Infraestructura Base:** Creación de archivos de Terraform (`ec2.tf`, `vpc.tf`, `provider.tf`) para desplegar una instancia EC2 Ubuntu 24.04 y red VPC en AWS.

- **Automatización CI:** Implementación de workflow en GitHub Actions con etapas de TFLint, Checkov y Terraform Validate.

- **Políticas de Seguridad:** Definición de reglas OPA (.rego) para restringir el tipo de instancia a `t2.micro` y bloquear acceso SSH público.

- **Documentación:** Creación de archivo README.md con objetivos y detalles técnicos del proyecto.

- **Configuración de Repositorio:** Inclusión de archivo `.gitignore` para excluir archivos temporales de Terraform y secretos.



### Cambios

- Actualización de la nomenclatura de recursos para cumplir con el formato oficial del curso.



### Corregido

- Resolución de conflictos de archivos locales al sincronizar el repositorio.