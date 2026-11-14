# Bitácora de trabajo: TA-IND-01

## Jueves 12 de noviembre de 2026

- **Qué hice:** Leí la guía de la tarea y elegí analizar Kubernetes, comparado con Docker Swarm. Instalé kind y kubectl para poder levantar un clúster de Kubernetes en mi PC, y después WSL 2 y Docker Desktop, que kind necesita. Creé el repositorio y subí la carátula y la estructura del informe con las primeras referencias. En la noche levanté mi clúster «benites» con kind (un nodo de plano de control y dos trabajadores) y tomé las primeras 4 capturas: la creación del clúster, los 3 nodos en Ready, los componentes del plano de control y los nodos corriendo como contenedores de Docker.
- **Problema que se me presento:** Mi PC no tenía WSL bien instalado. `wsl --install` se quedaba colgado con el error `Wsl/CallMsi/Install/REGDB_E_CLASSNOTREG`. Cuando quise actualizar WSL con winget salió otro error, el 0x80073d28, porque pedía permisos de administrador.
- **Cómo lo resolví:** Con ayuda de Claude revisé qué faltaba. Las funciones de Windows "Subsistema de Windows para Linux" y "Plataforma de máquina virtual" estaban deshabilitadas, así que las habilité con `dism`, reinicié el PC e instalé WSL desde una PowerShell como administrador. Después instalé Docker Desktop y comprobé que funcionaba con `docker run hello-world`.
- **Tiempo dedicado:** unas 2 horas y media.

## Viernes 13 de noviembre de 2026

- **Qué hice:** Dibujé a mano el primer esquema de la arquitectura de mi clúster. Hice el experimento de apagar el nodo `benites-worker` con una aplicación de 4 réplicas, con un monitor que guardaba el estado cada 5 segundos, y tomé las capturas 05 a 10. Kubernetes detectó la caída en 50 segundos y reubicó los pods 300 segundos después; revisé en la documentación oficial que esos son los valores por defecto. Pasé el esquema a draw.io, tomé las capturas de los fragmentos que cito de tres artículos y armé con Claude el borrador del informe, que revisé.
- **Problema que se me presentó:** Al guardar las capturas del experimento, algunas quedaron con doble extensión (`.png.png`) y otras se quedaron en la carpeta de capturas de Windows. Tampoco sabía cómo sacar las horas exactas de cada momento del experimento con exactitud.
- **Cómo lo resolví:** Ordené y renombré las capturas en la carpeta del repositorio. Las horas las saqué de la salida del monitor (`experimento/salida-experimento.txt`) y las comparé con los eventos que registra Kubernetes (`kubectl get events`), y coincidieron.
- **Tiempo dedicado:** alrededor de unas 4 a 5 horas, ya que por las lluvias se me fue la luz como 2 veces en ese momento en medio del proceso.
