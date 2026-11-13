# Bitácora de trabajo: TA-IND-01

## Jueves 12 de noviembre de 2026

- **Qué hice:** Leí la guía de la tarea y elegí analizar Kubernetes, comparado con Docker Swarm. Instalé kind y kubectl para poder levantar un clúster de Kubernetes en mi PC, y después WSL 2 y Docker Desktop, que kind necesita. Creé el repositorio y subí la carátula y la estructura del informe con las primeras referencias.
- **Problema que se me presento:** Mi PC no tenía WSL bien instalado. `wsl --install` se quedaba colgado con el error `Wsl/CallMsi/Install/REGDB_E_CLASSNOTREG`. Cuando quise actualizar WSL con winget salió otro error, el 0x80073d28, porque pedía permisos de administrador.
- **Cómo lo resolví:** Con ayuda de Claude revisé qué faltaba. Las funciones de Windows "Subsistema de Windows para Linux" y "Plataforma de máquina virtual" estaban deshabilitadas, así que las habilité con `dism`, reinicié el PC e instalé WSL desde una PowerShell como administrador. Después instalé Docker Desktop y comprobé que funcionaba con `docker run hello-world`.
- **Tiempo dedicado:** unas 2 horas.
