# Flujo de Trabajo (Git Workflow)

Para garantizar la estabilidad de la rama principal y la calidad del código, el desarrollo se gestiona mediante ramas de trabajo y **Pull Requests (PR)**.

> **Regla de contribución:** Está prohibido realizar commits o push directamente a la rama `main`. Cualquier integración debe realizarse mediante un PR revisado y aprobado.

---

## Procedimiento de Contribución

### 1. Sincronizar con `main`
Antes de iniciar cualquier desarrollo, asegúrate de tener la versión más reciente del repositorio remoto:

```bash
git checkout main
git pull origin main
```

### 2. Crear una rama de trabajo
Crea una nueva rama a partir de `main`. Utiliza prefijos estándar y nombres descriptivos (ej. `feat/login`, `fix/header-overflow`):

```bash
git checkout -b <tipo>/<descripcion-corta>
```

### 3. Confirmar cambios (Commits)
Realiza commits atómicos con mensajes claros y descriptivos:

```bash
git add .
git commit -m "feat: descripción concisa del cambio introducido"
```

### 4. Publicar la rama en el repositorio remoto
Sube los cambios a tu rama en GitHub:

```bash
git push -u origin <nombre-de-la-rama>
```

### 5. Abrir el Pull Request (PR)
1. Accede al repositorio en GitHub y selecciona **Compare & pull request**.
2. Configura la rama destino en `main` y la de origen en tu rama de trabajo.
3. Completa el título y detalla en la descripción qué cambios se implementan o qué *issue* resuelve.
4. Asigna los revisores correspondientes y crea el PR.

### 6. Revisión y Merge
- El PR pasará por un proceso de revisión de código (*Code Review*).
- Si se solicitan modificaciones, realiza los cambios y haz `push` sobre la misma rama; el PR se actualizará automáticamente.
- Una vez aprobado el PR (y superadas las comprobaciones de CI/CD si aplican), se integrará (*merge*) a `main` y se procederá al borrado de la rama de trabajo.
