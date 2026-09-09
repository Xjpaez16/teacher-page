---
name: git-branching-workflow
description: Usa este skill siempre que vayas a crear una rama nueva, hacer un commit, o abrir un Pull Request en este repositorio. Define la convención de nombres de rama, el flujo de branching y las reglas antes de mezclar a main.
---

# Workflow de Git — teacher-page

## Reglas obligatorias

1. **Nunca hacer commits directos a `main`** (salvo el commit inicial de setup del proyecto). Todo cambio va en una rama aparte y se mezcla vía Pull Request.
2. **Una rama = un cambio lógico e independiente**, revisable como unidad. No mezclar varias secciones o tareas distintas en una misma rama (ej. no combinar el navbar y el formulario de testimonios en una sola rama).
3. **Prefijo de rama según el tipo de cambio** (convención Conventional Commits):
   - `feat/` — nueva funcionalidad o sección visual nueva. Ej: `feat/navbar`, `feat/hero`, `feat/testimonios-form`, `feat/admin-login`
   - `fix/` — corrección de un bug existente. Ej: `fix/testimonios-form-validation`
   - `chore/` — configuración, estructura de carpetas, dependencias, tareas de mantenimiento sin funcionalidad nueva. Ej: `chore/project-structure`
   - `docs/` — cambios exclusivos de documentación (README, comentarios extensos, etc.)
4. **El primer commit de cada rama y el mensaje del PR usan el mismo tipo** como prefijo del mensaje (`feat:`, `fix:`, `chore:`, `docs:`), en español, en imperativo presente, describiendo el cambio de forma breve.
5. **Antes de crear una rama nueva, sincronizar con `main`:**
   ```bash
   git checkout main
   git pull origin main
   git checkout -b <tipo>/<nombre-corto-descriptivo>
   ```
6. **Al terminar el cambio:** push de la rama, abrir Pull Request hacia `main`, y verificar que el preview deployment de Vercel se vea correctamente antes de mezclar.
7. **No mezclar un PR si el build o el preview fallan.**
8. Si una tarea claramente involucra más de un cambio lógico, dividirla en varias ramas/PRs pequeños en vez de una rama grande.

## Ejemplos de nombres de rama válidos
- Nueva sección del sitio → `feat/hero`
- Ajuste de estructura de carpetas → `chore/project-structure`
- Bug en validación del formulario → `fix/testimonios-form-validation`
- Actualizar instrucciones del README → `docs/readme-setup`

## Ejemplo de mensaje de commit/PR
```
feat: agrega sección hero con imagen y CTA de WhatsApp
```