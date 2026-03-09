# 🛡️ TitanTrack: Gym Management System
> **Solución integral para la gestión de zonas de entrenamiento y bioseguridad.**

![Status](https://img.shields.io/badge/Status-Sprint%200%20(An%C3%A1lisis)-orange?style=for-the-badge)
![Tech](https://img.shields.io/badge/C%23-7.3%2B-purple?style=for-the-badge&logo=c-sharp)
![Framework](https://img.shields.io/badge/.NET-Core%20MVC-512BD4?style=for-the-badge&logo=dotnet)
![DB](https://img.shields.io/badge/SQL%20Server-Persistencia-red?style=for-the-badge&logo=microsoft-sql-server)

---

## 📋 Descripción del Proyecto
**TitanTrack** es una plataforma diseñada para optimizar la ocupación de gimnasios modernos. A través de un enfoque de **Socioformación**, el equipo aplica metodologías ágiles para resolver la gestión de aforos y asignación de personal especializado (Coaches) en zonas críticas de entrenamiento.

---

## 🚀 Sprint 0: Product Backlog
Priorizamos el valor de negocio para asegurar que el sistema sea funcional desde la primera iteración.

### 🎯 Historias de Usuario (User Stories)

| ID | Requerimiento Funcional | Prioridad | Criterio de Éxito |
| :--- | :--- | :---: | :--- |
| **HU-01** | **Gestión de Zonas de Entrenamiento** | 🔥 ALTA | CRUD funcional para áreas como Pesas, Cardio y Crossfit. |
| **HU-02** | **Administración de Coaches Expertos** | 🔥 ALTA | Registro de perfiles con especialidad y certificación. |
| **HU-03** | **Control de Reservas y Sesiones** | 🔥 ALTA | Vincular socio + zona + fecha. Evitar duplicidad. |
| **HU-04** | **Monitor de Disponibilidad** | ⚡ MEDIA | Visualización en tiempo real del estado (Abierto/Cerrado). |
| **HU-05** | **Algoritmo de Aforo Máximo** | 🔥 ALTA | Bloqueo automático si el contador de socios llega al límite. |
| **HU-06** | **Protocolo de Mantenimiento** | 🛠️ MEDIA | Deshabilitar zonas para reparaciones sin borrar datos. |

---

 Definición de Entidades (Data Schema)

### 🏋️ Entidad: Zona (Library Resource)
| Atributo | Tipo | Descripción |
| :--- | :--- | :--- |
| `Id` | `int` | Llave primaria (Identity). |
| `Nombre` | `string` | Nombre de la zona (ej. Área Pesas). |
| `AforoMaximo` | `int` | Capacidad permitida. |
| `Estado` | `string` | Disponible, Mantenimiento, Limpieza. |

### 👤 Entidad: Coach (Author)
| Atributo | Tipo | Descripción |
| :--- | :--- | :--- |
| `Id` | `int` | Llave primaria. |
| `NombreCompleto` | `string` | Nombre y Apellido. |
| `Especialidad` | `string` | Área de experto (Yoga, HIIT, etc). |
| `Certificacion` | `string` | Nivel: Senior, Junior, Master. |

### 📅 Entidad: Reserva (Loan)
| Atributo | Tipo | Descripción |
| :--- | :--- | :--- |
| `Id` | `int` | Llave primaria. |
| `Fecha` | `DateTime` | Día de la sesión. |
| `HoraInicio` | `TimeSpan` | Hora programada. |
| `SocioNombre` | `string` | Nombre del cliente. |
| `ZonaId` | `int` | FK -> Relación con la Zona. |
| `CoachId` | `int` | FK -> Relación con el Coach. |

---

## 🏗️ Sprint 1: Refinamiento y Modelado
En esta fase, transformamos los requerimientos en planos técnicos utilizando **PlantUML**.

### 🎨 Diagrama de Casos de Uso
Representación de las interacciones entre Administradores, Coaches y Socios.
![Casos de Uso](./Docs/CasosDeUso/TitanTrack_UseCases.png)

### 🏗️ Diagrama de Clases
Arquitectura de datos para la implementación en SQL Server con Entity Framework.
![Diagrama de Clases](./Docs/Clases/TitanTrack_Classes.png)

---

## 🏗️ Arquitectura del Sistema
Aplicaremos el patrón **MVC (Model-View-Controller)** para garantizar la escalabilidad:
- **Models:** Entidades con Entity Framework Core.
- **Views:** Interfaces dinámicas con Razor Pages y Bootstrap 5.
- **Controllers:** Lógica de negocio y validaciones de seguridad.

---

## 👥 Squad de Desarrollo
| Nombre | Rol | GitHub |
| :--- | :--- | :--- |
| **Romeo Chavez** | Tech Lead / Backend | [@RomeoChavez](https://github.com/RomeoChavez) |


---
* UPDS 2026.*
