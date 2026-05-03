# Challenge Alura Foro Hub

<div align="center">

![Java](https://img.shields.io/badge/Java-17+-orange?style=for-the-badge&logo=java&logoColor=white)
![Spring Boot](https://img.shields.io/badge/Spring%20Boot-6DB33F?style=for-the-badge&logo=spring&logoColor=white)
![Maven](https://img.shields.io/badge/Maven-C71A36?style=for-the-badge&logo=apache-maven&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

*Aplicación de foro desarrollada como parte de un desafío de Alura*

[Demo](#-instalación-y-ejecución) • 
[Documentación](#-documentación-de-la-api) • 
[Contribuir](#-contribuciones) • 
[Licencia](#-licencia)

</div>

---

## Características principales

<table>
<tr>
<td>

**Gestión de usuarios**
- Registro y autenticación
- Perfiles personalizables
- Control de acceso

</td>
<td>

**Sistema de discusión** 
- Creación de temas
- Mensajes y respuestas
- Hilos de conversación

</td>
</tr>
<tr>
<td>

🔌 **API RESTful**
- Endpoints bien documentados
- Formato JSON estándar
- Códigos de estado HTTP

</td>
<td>

**Persistencia de datos**
- Base de datos relacional
- JPA/Hibernate
- Migraciones automáticas

</td>
</tr>
</table>

---

## 🛠️ Stack tecnológico

### Backend
- **☕ Java 17+** - Lenguaje de programación principal
- **🌱 Spring Boot** - Framework de desarrollo
- **📦 Maven** - Gestión de dependencias y construcción
- **🗄️ Spring Data JPA** - Persistencia y ORM

### Base de datos
- **🐬 MySQL** / **🐘 PostgreSQL** / **💾 H2** (según configuración)
- **🔄 Hibernate** - ORM y mapeo objeto-relacional

### Seguridad (opcional)
- **🔐 Spring Security** - Autenticación y autorización
- **🎫 JWT** - Tokens de autenticación

---

## 🚀 Instalación y ejecución

### Prerrequisitos
- Java 17 o superior
- Maven 3.6+
- Base de datos (MySQL, PostgreSQL o H2)

### Pasos de instalación

1. **Clonar el repositorio**
   ```bash
   git clone https://github.com/Rodrigo-Salva/challenge-Alura-foro-hub.git
   ```

2. **Navegar al directorio**
   ```bash
   cd challenge-Alura-foro-hub
   ```

3. **Configurar la base de datos** (opcional)
   ```properties
   # application.properties
   spring.datasource.url=jdbc:mysql://localhost:3306/foro_hub
   spring.datasource.username=tu_usuario
   spring.datasource.password=tu_contraseña
   ```

4. **Ejecutar la aplicación**
   ```bash
   mvn spring-boot:run
   ```

5. **¡Listo!** 🎉
   - API disponible en: `http://localhost:8080`
   - Documentación Swagger: `http://localhost:8080/swagger-ui.html`

---

## 📖 Documentación de la API

La API RESTful proporciona endpoints para interactuar con todas las entidades del foro:

### 👥 Usuarios

| Método | Endpoint | Descripción |
|--------|----------|-------------|
| `GET` | `/usuarios` | Listar todos los usuarios |
| `POST` | `/usuarios` | Crear un nuevo usuario |
| `GET` | `/usuarios/{id}` | Obtener usuario por ID |
| `PUT` | `/usuarios/{id}` | Actualizar usuario |
| `DELETE` | `/usuarios/{id}` | Eliminar usuario |

### 💭 Temas

| Método | Endpoint | Descripción |
|--------|----------|-------------|
| `GET` | `/temas` | Listar todos los temas |
| `POST` | `/temas` | Crear un nuevo tema |
| `GET` | `/temas/{id}` | Obtener tema por ID |
| `PUT` | `/temas/{id}` | Actualizar tema |
| `DELETE` | `/temas/{id}` | Eliminar tema |

### 💬 Mensajes

| Método | Endpoint | Descripción |
|--------|----------|-------------|
| `GET` | `/mensajes` | Listar todos los mensajes |
| `POST` | `/mensajes` | Publicar nuevo mensaje |
| `GET` | `/mensajes/{id}` | Obtener mensaje por ID |
| `PUT` | `/mensajes/{id}` | Actualizar mensaje |
| `DELETE` | `/mensajes/{id}` | Eliminar mensaje |

### 🔐 Autenticación

| Método | Endpoint | Descripción |
|--------|----------|-------------|
| `POST` | `/auth/login` | Iniciar sesión (JWT) |
| `POST` | `/auth/register` | Registrar usuario |

---

## 📋 Formato de respuesta

### Estructura estándar
```json
{
  "timestamp": "2023-01-01T12:00:00Z",
  "status": 200,
  "data": {
    // Contenido específico de la respuesta
  },
  "message": "Operación exitosa"
}
```

### Códigos de estado HTTP

| Código | Significado |
|--------|-------------|
| `200` ✅ | Operación exitosa |
| `201` 🆕 | Recurso creado |
| `400` ❌ | Solicitud inválida |
| `401` 🚫 | No autorizado |
| `404` 🔍 | Recurso no encontrado |
| `500` ⚠️ | Error interno del servidor |

---

## 📊 Documentación interactiva

Accede a la documentación completa de la API:

- **📚 Swagger UI**: [`http://localhost:8080/swagger-ui.html`](http://localhost:8080/swagger-ui.html)
- **🔧 OpenAPI**: [`http://localhost:8080/v3/api-docs`](http://localhost:8080/v3/api-docs)

---

## 📂 Estructura del proyecto

```
challenge-Alura-foro-hub/
├── 📁 src/
│   ├── 📁 main/
│   │   ├── 📁 java/           # Código fuente principal
│   │   │   └── 📁 com/alura/forohub/
│   │   │       ├── 📁 controller/    # Controladores REST
│   │   │       ├── 📁 model/         # Entidades JPA
│   │   │       ├── 📁 repository/    # Repositorios de datos
│   │   │       ├── 📁 service/       # Lógica de negocio
│   │   │       └── 📁 config/        # Configuraciones
│   │   └── 📁 resources/      # Configuración y recursos
│   │       ├── application.properties
│   │       └── 📁 db/migration/      # Scripts SQL
│   └── 📁 test/               # Pruebas unitarias e integración
├── 📄 pom.xml                 # Configuración Maven
├── 📄 README.md               # Este archivo
└── 📄 .gitignore              # Archivos ignorados por Git
```

---

## 🧪 Testing

### Ejecutar pruebas
```bash
# Todas las pruebas
mvn test

# Pruebas específicas
mvn test -Dtest=UsuarioControllerTest

# Con coverage
mvn jacoco:report
```

### Tipos de pruebas incluidas
- ✅ **Pruebas unitarias** - Lógica de negocio
- 🔗 **Pruebas de integración** - API endpoints
- 📊 **Pruebas de persistencia** - Repositorios JPA

---

## 🤝 Contribuciones

¡Las contribuciones son bienvenidas! Aquí te explico cómo participar:

### 🔀 Cómo contribuir

1. **Fork** el proyecto
2. **Crea** una rama para tu feature (`git checkout -b feature/AmazingFeature`)
3. **Commit** tus cambios (`git commit -m 'Add some AmazingFeature'`)
4. **Push** a la rama (`git push origin feature/AmazingFeature`)
5. **Abre** un Pull Request

### 📋 Pautas

- Sigue las convenciones de código existentes
- Incluye pruebas para nuevas funcionalidades
- Actualiza la documentación si es necesario
- Usa mensajes de commit descriptivos

---

## 🐛 Reportar problemas

¿Encontraste un bug? ¡Ayúdanos a solucionarlo!

1. **Verifica** que no exista ya un issue similar
2. **Abre** un nuevo issue con una descripción detallada
3. **Incluye** pasos para reproducir el problema
4. **Adjunta** capturas de pantalla si es relevante

---

## 📈 Roadmap

### 🎯 Próximas características

- [ ] 🔍 Búsqueda avanzada de temas
- [ ] 📧 Sistema de notificaciones por email
- [ ] 🏷️ Sistema de etiquetas/tags
- [ ] ⭐ Sistema de puntuación y reputación
- [ ] 🌐 Internacionalización (i18n)
- [ ] 📱 API para aplicación móvil

### 🔧 Mejoras técnicas

- [ ] 📊 Métricas y monitoreo con Actuator
- [ ] 🐳 Dockerización completa
- [ ] ☁️ Deploy en la nube (AWS/Azure)
- [ ] 🔄 Pipeline CI/CD
- [ ] 📝 Documentación con Gitbook

---

## 📄 Licencia

Este proyecto está licenciado bajo la **Licencia MIT** - consulta el archivo [LICENSE](LICENSE) para más detalles.

```
MIT License

Copyright (c) 2025 Rodrigo Salva

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.
```

---

## 👨‍💻 Autor

<div align="center">

**Rodrigo Salva**

[![GitHub](https://img.shields.io/badge/GitHub-100000?style=for-the-badge&logo=github&logoColor=white)](https://github.com/Rodrigo-Salva)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/rodrigo-daniel-salva-saccatoma)

*Desarrollado con ❤️ para el Challenge de Alura*

---

### ⭐ ¡Si te gusta este proyecto, dale una estrella!

</div>

---

<div align="center">
  <sub>Built with 🔥 by <a href="https://github.com/Rodrigo-Salva">Rodrigo Salva</a> • Challenge Alura 2025</sub>
</div>
