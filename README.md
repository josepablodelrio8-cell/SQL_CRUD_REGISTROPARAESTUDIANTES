<div align="center">

![Android](https://img.shields.io/badge/Android-3DDC84?style=for-the-badge&logo=android&logoColor=white)
![Kotlin](https://img.shields.io/badge/Kotlin-7F52FF?style=for-the-badge&logo=kotlin&logoColor=white)
![SQLite](https://img.shields.io/badge/SQLite-003B57?style=for-the-badge&logo=sqlite&logoColor=white)
![Material Design](https://img.shields.io/badge/Material%20Design-757575?style=for-the-badge&logo=material-design&logoColor=white)
![API 24+](https://img.shields.io/badge/API-24%2B-brightgreen?style=for-the-badge)

> Aplicación Android nativa para gestionar registros de estudiantes usando **SQLite** como base de datos local. Implementa operaciones **CRUD** completas con una interfaz limpia y moderna.

</div>

---


---

## ✨ Funcionalidades

- ➕ **Insertar** estudiante con nombre y email
- 📋 **Listar** todos los registros almacenados localmente
- ✏️ **Editar** nombre y email desde un diálogo emergente con campos precargados
- 🗑️ **Eliminar** un registro directamente desde la lista con un solo toque
- 👤 **Avatar con iniciales** generado automáticamente (ej: "Ana García" → AG)
- 📊 **Contador dinámico** en la barra inferior: total de registros y nombre del último ingresado
- ✅ **Validación** de campos vacíos al insertar o modificar
- 🔄 **Actualización automática** de la lista tras cada operación

---

## 🗂️ Estructura del Proyecto

```
App05CRUD/
└── app/src/main/
    ├── java/com/example/app05crud/
    │   ├── MainActivity.kt           # Actividad principal, lógica de UI
    │   ├── AdminSQLiteOpenHelper.kt  # Base de datos: INSERT, SELECT, UPDATE, DELETE
    │   ├── StudentAdapter.kt         # Adapter ListView con botones Editar y Eliminar
    │   └── StudentModel.kt           # Modelo de datos (id, name, email)
    │
    └── res/
        ├── layout/
        │   ├── activity_main.xml       # Pantalla principal
        │   ├── card_items_std.xml      # Tarjeta de cada estudiante en la lista
        │   └── dialog_edit_student.xml # Diálogo Material para editar
        └── drawable/
            └── bg_avatar.xml           # Fondo circular del avatar
```

---

## 🏗️ Arquitectura

```
┌─────────────────────────────────┐
│          MainActivity           │  ← Controla UI y flujo de datos
│  - addStudent()                 │
│  - getStudent()                 │
└────────────┬────────────────────┘
             │ usa
             ▼
┌─────────────────────────────────┐
│     AdminSQLiteOpenHelper       │  ← Capa de datos (SQLite)
│  - insertStudent()              │
│  - getAllStudent()              │
│  - updateStudent()              │
│  - deleteStudent()              │
└────────────┬────────────────────┘
             │ base de datos local
             ▼
        [ student.db ]
        tbl_student (id, name, email)

┌─────────────────────────────────┐
│        StudentAdapter           │  ← Renderiza la lista
│  - getView()                    │
│  - showEditDialog()             │  ← Dialogo de edicion
│  - onDelete callback            │
│  - onUpdate callback            │
└─────────────────────────────────┘
```

---

## 🚀 Cómo ejecutar el proyecto

### Requisitos

- Android Studio **Hedgehog** o superior
- JDK 11
- Android SDK API **24** mínimo (Android 7.0)
- Dispositivo o emulador con API 24+

### Pasos

```bash
# 1. Clona el repositorio
git clone https://github.com/josepablodelrio8-cell/App05CRUD.git

# 2. Abre Android Studio
# File → Open → selecciona la carpeta App05CRUD

# 3. Espera que Gradle sincronice automáticamente

# 4. Corre en emulador o dispositivo físico
# Run → Run 'app'   (Shift + F10)
```

> ⚠️ Si ves error `compileSdk`, instala **Android SDK 36** desde Android Studio → SDK Manager.

---

## 🛠️ Stack Técnico

| Componente | Tecnología |
|-----------|------------|
| Lenguaje | Kotlin |
| UI | XML Layouts + Material Components |
| Base de datos | SQLite via `SQLiteOpenHelper` |
| Lista | `ListView` + `ArrayAdapter` personalizado |
| Dialogo edición | `AlertDialog` con `TextInputLayout` |
| Min SDK | API 24 (Android 7.0) |
| Target SDK | API 36 |

---

## 📋 Esquema de Base de Datos

```sql
CREATE TABLE tbl_student (
    id    INTEGER PRIMARY KEY AUTOINCREMENT,
    name  TEXT,
    email TEXT
);
```

Base de datos local: `student.db` · Versión: `2`

---

## 📸 Capturas de pantalla

<!--
  💡 CÓMO AGREGAR CAPTURAS:
  1. En el emulador → botón de cámara → toma screenshot
  2. O desde Android Studio: View → Tool Windows → Logcat → Screenshot
  3. Crea una carpeta /screenshots/ en tu repo y sube las imágenes ahí
  4. Reemplaza las URLs con rutas relativas, ej: ![main](screenshots/main.png)
-->

| Pantalla Principal | Lista de Estudiantes | Dialogo de Edición |
|---|---|---|
| ![main](https://via.placeholder.com/200x400/F5F5F5/3F51B5?text=Screenshot) | ![list](https://via.placeholder.com/200x400/F5F5F5/3F51B5?text=Screenshot) | ![dialog](https://via.placeholder.com/200x400/F5F5F5/3F51B5?text=Screenshot) |

---

## 👨‍💻 Autor

<div align="center">

**Pablo José Del Río Mayta**
Lima, Perú 🇵🇪

[![GitHub](https://img.shields.io/badge/GitHub-josepablodelrio8--cell-181717?style=for-the-badge&logo=github)](https://github.com/josepablodelrio8-cell)
[![LinkedIn](https://img.shields.io/badge/LinkedIn-Pablo%20Del%20Río-0A66C2?style=for-the-badge&logo=linkedin&logoColor=white)](https://www.linkedin.com/in/TU-URL-AQUI)

</div>

---

## 📄 Licencia

Este proyecto está bajo la licencia **MIT** — libre para usar, copiar y modificar con atribución.

---

<div align="center">
<img src="https://capsule-render.vercel.app/api?type=waving&color=0:1a237e,100:3F51B5&height=80&section=footer"/>
</div>
