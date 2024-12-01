# git pull

```bash
$ git pull origin master
* branch            master     -> FETCH_HEAD
fatal: refusing to merge unrelated histories
```

* To solve it use the next command
```bash
git pull --allow-unrelated-histories origin main
```
* Is going to appear a vim window to set a commit message

# Mejores prácticas para el nombramiento de branches (ramas)
En Git, nombrar ramas (branches) de manera consistente y descriptiva es fundamental para mantener un proyecto organizado, especialmente en equipos de trabajo. Aquí te dejo las mejores prácticas para nombrar ramas:

---

### **1. Sé descriptivo y claro:**
El nombre de la rama debe reflejar su propósito o el trabajo que se realizará en ella. Por ejemplo:
- Para una nueva funcionalidad: `feature/nombre-de-la-funcionalidad`
- Para solucionar un bug: `bugfix/id-del-bug-o-descripcion`

---

### **2. Usa un formato consistente:**
Adopta una convención de nombres y úsala siempre. Estas son algunas convenciones comunes:

#### a) **Basado en el propósito:**
- `feature/`: Para el desarrollo de nuevas funcionalidades.
- `bugfix/`: Para corregir errores.
- `hotfix/`: Para cambios urgentes en producción.
- `release/`: Para preparar una nueva versión.
- `chore/`: Para tareas de mantenimiento o ajustes menores.

Ejemplo:  
```bash
feature/nueva-pagina-contacto
bugfix/error-de-login
release/v1.2.0
chore/actualizar-dependencias
```

---

#### b) **Usa kebab-case o snake_case:**
- **kebab-case (recomendado):** Palabras separadas por guiones. Ejemplo: `feature/crear-reporte-ventas`.
- **snake_case:** Palabras separadas por guiones bajos. Ejemplo: `feature/crear_reporte_ventas`.

---

### **3. Opcional: Incluye identificadores de tareas o tickets:**
Si usas herramientas como Jira, GitHub Issues o Trello, puedes incluir el identificador de la tarea para mayor trazabilidad:
- Ejemplo: `feature/JIRA-1234-crear-dashboard`
- Ejemplo: `bugfix/issue-567-arreglar-header`

---

### **4. Evita nombres genéricos:**
No uses nombres como `new`, `test`, `branch1`, ya que no indican el propósito del trabajo. Siempre opta por nombres descriptivos.

---

### **5. Mantén los nombres cortos pero significativos:**
Evita nombres demasiado largos, pero asegúrate de que sean lo suficientemente claros. Por ejemplo, en lugar de:
```bash
feature/agregar-funcionalidad-de-exportar-tablas-con-muchos-datos
```
Puedes usar:
```bash
feature/exportar-tablas
```

---

### **6. No incluyas información redundante:**
Git ya gestiona ramas por contexto, así que evita prefijos innecesarios como `branch-`.

---

### Ejemplo práctico:
Para una tarea que consiste en crear un sistema de login:
```bash
feature/sistema-login
```

Para arreglar un error en la funcionalidad de registro:
```bash
bugfix/arreglo-registro
```

---

# Pasos para crear un nuevo branch

Para corregir los enlaces a carpetas como `css` e `images` en un archivo HTML, lo ideal es crear una rama con un nombre que refleje claramente la tarea. Una convención recomendada para este caso sería usar el prefijo `fix/` seguido de una descripción breve, como `fix/corrige-rutas-enlaces`.

### **Pasos con comandos:**

#### 1. **Crea la nueva rama:**
```bash
git checkout -b fix/corrige-rutas-enlaces
```
Esto crea una nueva rama basada en la actual y cambia a ella.

#### 2. **Haz las correcciones necesarias:**
Edita el archivo HTML y corrige las rutas hacia `css` e `images`.

#### 3. **Confirma los cambios:**
Guarda los archivos y luego realiza los siguientes pasos en Git:
```bash
git add .
git commit -m "Corrige las rutas de los enlaces a css e images"
```

#### 4. **Envía la rama al repositorio remoto:**
```bash
git push origin fix/corrige-rutas-enlaces
```

---

### **Explicación del nombre de la rama:**
- **`fix/`**: Indica que esta rama es para solucionar un problema.
- **`corrige-rutas-enlaces`**: Describe claramente qué problema estás resolviendo.

---

### **Siguientes pasos:**
1. Crea un *pull request* (PR) en tu repositorio remoto (GitHub, GitLab, etc.) para revisar e integrar los cambios.
2. Una vez aprobada y fusionada la PR, puedes eliminar la rama local y remota:
   ```bash
   git branch -d fix/corrige-rutas-enlaces
   git push origin --delete fix/corrige-rutas-enlaces
   ```

---

¿Quieres ayuda para estructurar las rutas correctamente o realizar la integración? 😊


# Pasos para hacer un merge entre `branch` en Git local
En este ejemplo se explicarán los pasos para hacer un merge del branch `fix` al branch `main`.

1. Estar en el branch `main`. Asegurarse estar en el branch `main` ya que es donde se desea fusionar los cambios.

```
git checkout main
```

2. Actualizar el branch `main`. Es buena práctica asegurarse de que el branch `main` está actualizado entes de hacer el **merge** (si estás trabajando con un repositorio remoto)

```
git pull origin main
```

3. Fusionar el branch `fix` en `main`. Si no hay conflictos, Git hará el merge automáticamente y verás un mensaje indicando que el merge fue exitoso.

```
git merge fix
```
---

#### 4. **Resuelve conflictos (si los hay):**
Si hay conflictos, Git te lo indicará y señalará los archivos que necesitan resolución. Para resolverlos:
1. Abre los archivos marcados como conflictivos (busca las secciones entre `<<<<<<<` y `>>>>>>>`).
2. Edita y decide qué cambios conservar.
3. Marca los conflictos resueltos con:
   ```bash
   git add <archivo>
   ```
4. Una vez resueltos todos los conflictos, termina el merge con:
   ```bash
   git commit
   ```

---

#### 5. **Verifica el estado del merge:**
Confirma que el merge fue exitoso y que los cambios del branch `fix` están en `main`:
```bash
git log --oneline --graph
```
Esto muestra un historial compacto del merge.

---

#### 6. **(Opcional) Elimina el branch `fix`:**
Si ya no necesitas el branch `fix`, puedes eliminarlo para mantener tu repositorio limpio:

- Eliminar el branch local:
  ```bash
  git branch -d fix
  ```
- Eliminar el branch remoto (si existe):
  ```bash
  git push origin --delete fix
  ```

---

### **Resumen de comandos principales:**

| paso | acción | comando |
|-|-|-|
| 1 | Cambiar al branch `main`| git checkout main |
| 2 | Actualizar el branch `main`| git pull origin main|
| 3 | Fusionar el branch `fix`en `main`| git merge fix|
| 4 | Resolver conflictos | |
| 5 | Verificar el estado de merge | git log --oneline --graph |
| 6 | Eliminar el branch `fix`| git branch -d fix (local) / git push origin --delete fix (en remoto) |

```bash
git checkout main
git pull origin main
git merge fix
# (Si no hay conflictos, el merge estará completo)
# Opcional: Eliminar branch
git branch -d fix
git push origin --delete fix
```

