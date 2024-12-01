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
* Is goign to appear a vim window to set a commit message


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

