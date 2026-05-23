# Laboratorio - Seguridad en Aplicaciones Web
## Unidad 9 - Post-Contenido 1
**Estudiante:** Juan David Pulido  
**Materia:** Programación Web  
**Universidad Francisco de Paula Santander**

---

## Descripción
Sistema de autenticación completo con Spring Security 6, registro de usuarios 
con BCrypt, login basado en formulario y autorización por roles ADMIN y USER.

---

## Requisitos
- Java 21
- MySQL 8.0
- Maven

---

## Configuración de MySQL
1. Instalar MySQL 8.0
2. Crear la base de datos:
```sql
CREATE DATABASE estudiantes_db;
```
3. Insertar usuario ADMIN con hash BCrypt:
```sql
INSERT INTO usuarios (nombre, email, contrasenia, rol, activo)
VALUES ('Administrador', 'admin@universidad.edu',
'$2a$12$[hash generado]', 'ROLE_ADMIN', 1);
```

---

## Configurar application.properties
```properties
spring.datasource.url=jdbc:mysql://localhost:3306/estudiantes_db
spring.datasource.username=root
spring.datasource.password=TU_PASSWORD
spring.jpa.hibernate.ddl-auto=update
```

---

## Usuarios de prueba
| Rol | Email | Contraseña |
|-----|-------|------------|
| ADMIN | admin@universidad.edu | admin123 |
| USER | juan@test.com | 1234 |

---

## Ejecutar el proyecto
1. Clonar el repositorio
2. Configurar application.properties con tu contraseña de MySQL
3. Ejecutar SeguridadApplication.java

---

## Capturas
- Formulario de login: /login
- Dashboard USER: /dashboard
- Panel ADMIN: /admin
- Error 403: al intentar acceder a /admin como USER
- Hash BCrypt en MySQL: columna contrasenia de la tabla usuarios