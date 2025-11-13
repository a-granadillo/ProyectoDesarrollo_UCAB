\# Plataforma Integral para Gestión de Eventos (Desarrollo de Software)



Este proyecto implementa una "Plataforma Integral para Gestión de Eventos, Reservas y Servicios" utilizando un enfoque de microservicios con Arquitectura Hexagonal y DDD.



---



\## 🏛️ Arquitectura de Microservicios



El repositorio está organizado como un "Monorepo" con la siguiente estructura:



\* \*\*`ProyectoEventos.sln`\*\*: La solución principal que agrupa todos los proyectos.

\* \*\*`Gateway.API/`\*\*: El API Gateway principal (RF 1). Valida todos los tokens de Keycloak.

\* \*\*`Usuarios/`\*\*: Carpeta contenedora del microservicio \*\*Gestión de Usuarios (RF 2)\*\*.

&nbsp;   \* `Usuarios.Presentacion/`

&nbsp;   \* `Usuarios.Aplicacion/`

&nbsp;   \* `Usuarios.Dominio/`

&nbsp;   \* `Usuarios.Infraestructura/`

\* \*\*`Eventos/`\*\*: Carpeta contenedora del microservicio \*\*Gestión de Eventos (RF 3)\*\*.

&nbsp;   \* `Eventos.Presentacion/`

&nbsp;   \* `Eventos.Aplicacion/`

&nbsp;   \* `Eventos.Dominio/`

&nbsp;   \* `Eventos.Infraestructura/`



---



\## 🚀 Cómo Ejecutar el Proyecto



Para ejecutar el entorno de desarrollo, se necesitan 4 terminales:



1\.  \*\*Iniciar Servicios de Fondo (Keycloak):\*\*

&nbsp;   ```bash

&nbsp;   docker start keycloak-dev

&nbsp;   ```



2\.  \*\*Iniciar el Gateway (Terminal 1):\*\*

&nbsp;   \*(Desde la raíz `Proyecto Desarrollo/`)\*

&nbsp;   ```bash

&nbsp;   cd Gateway.API

&nbsp;   dotnet run

&nbsp;   ```



3\.  \*\*Iniciar Microservicio de Usuarios (Terminal 2):\*\*

&nbsp;   \*\_(Puerto 5001 definido en el Gateway)\_\*

&nbsp;   \*(Desde la raíz `Proyecto Desarrollo/`)\*

&nbsp;   ```bash

&nbsp;   cd Usuarios/Usuarios.Presentacion

&nbsp;   dotnet run --urls=http://localhost:5001

&nbsp;   ```



4\.  \*\*Iniciar Microservicio de Eventos (Terminal 3):\*\*

&nbsp;   \*\_(Puerto 5002 definido en el Gateway)\_\*

&nbsp;   \*(Desde la raíz `Proyecto Desarrollo/`)\*

&nbsp;   ```bash

&nbsp;   cd Eventos/Eventos.Presentacion

&nbsp;   dotnet run --urls=http://localhost:5002

&nbsp;   ```

