# landing-copy

> Copy de página donde cada afirmación tiene una prueba.

**Copy de landing** · Skill para agentes de código de la comunidad [nvvdev](https://github.com/nvv-dev). Funciona en Claude Code como plugin o como skill suelta, y en cualquier agente compatible con el formato abierto [`SKILL.md`](https://agentskills.io).

*English summary at the end.*

## Qué hace

Escribe el copy de una página a partir del mapa de palabras clave y del contexto del producto: titular, subtítulo, llamado a la acción, beneficios, pruebas, objeciones, preguntas y cierre. Da dos o tres variantes de titular, subtítulo y CTA con ángulos distintos y recomienda una. Entrega la lista de afirmaciones con su fuente y marca con `[PROOF NEEDED]` lo que no tiene prueba. Prohibido inventar cifras, testimonios o logos de clientes.

## Objetivo

Páginas que dicen qué hace el producto, para quién y por qué creerle, con las palabras que ya usa el cliente.

## Cuándo usarla

- Al escribir o reescribir una landing, la home o la página de precios
- Cuando el diseño está aprobado y faltan los textos

## Cuándo no

- Posts para redes: usa post-review y el agente de contenido
- Sin contexto del producto ni mapa de palabras clave: créalos primero

## Ejemplo

```text
Escribe el copy de la landing de mantenimiento web con landing-copy usando el mapa de palabras clave.
```

## Cómo se activa

Esta skill **se activa sola**: Claude Code lee su descripción y la carga cuando la tarea coincide. También puedes pedirla por nombre ("usa la skill landing-copy") o invocarla con `/landing-copy:landing-copy` (plugin) o `/landing-copy` (copiada a `.claude/skills/`).

## Instalación

### Opción 1: Claude Code, como plugin (recomendada)

Dentro de Claude Code:

```text
/plugin marketplace add nvv-dev/claude-plugins
/plugin install landing-copy@nvvdev
```

La primera línea agrega el catálogo de nvvdev una sola vez; la segunda instala esta skill. Si prefieres el paquete completo, instala `growth-workflow@nvvdev` en su lugar (incluye esta skill y las demás de [growth-workflow](https://github.com/nvv-dev/growth-workflow)); no instales los dos a la vez.

### Opción 2: Claude Code, copiando la skill

Para un solo proyecto (se comparte con tu equipo por git):

```bash
git clone --depth 1 https://github.com/nvv-dev/landing-copy.git /tmp/landing-copy
mkdir -p .claude/skills
cp -R /tmp/landing-copy/skills/landing-copy .claude/skills/
```

Para todos tus proyectos, cópiala en `~/.claude/skills/` en lugar de `.claude/skills/`.

### Opción 3: otros agentes

Copia la carpeta `skills/landing-copy/` en la carpeta de skills de tu agente (cada agente documenta la suya). Con la CLI [skills](https://github.com/vercel-labs/skills) de Vercel Labs:

```bash
DISABLE_TELEMETRY=1 npx skills add nvv-dev/landing-copy
```

### Verificar

Abre una sesión nueva y pregunta "¿qué skills tienes disponibles?"; `landing-copy` debe aparecer. Con el plugin, `/plugin` la muestra como instalada.

### Actualizar o desinstalar

- Plugin: `/plugin marketplace update nvvdev` para actualizar; `/plugin uninstall landing-copy@nvvdev` para quitarla.
- Copia manual: repite la copia para actualizar, o borra la carpeta `.claude/skills/landing-copy`.

Antes de instalar cualquier skill, incluida esta, conviene leerla: es un solo archivo, [`skills/landing-copy/SKILL.md`](skills/landing-copy/SKILL.md). Ver [vetting-external-skills](https://github.com/nvv-dev/vetting-external-skills).

## Contenido

| Ruta | Qué es |
|---|---|
| `skills/landing-copy/SKILL.md` | La skill: instrucciones en inglés para que los escáneres de seguridad las analicen completas; el agente responde en tu idioma |
| `.claude-plugin/plugin.json` | Manifiesto para instalarla como plugin |
| `.github/workflows/` | Validación de estructura y escaneo con SkillSpector en cada cambio |

## Contribuir

Este repo se **genera** desde [nvv-dev/growth-workflow](https://github.com/nvv-dev/growth-workflow), donde vive la versión canónica. Abre issues y PRs allí. La mejor contribución es un caso real en la sección *Known failures* de la skill, con la regla que lo evita.

## Origen

Escrita desde cero por nvvdev. Inspirada en: [coreyhaines31/marketingskills](https://github.com/coreyhaines31/marketingskills) (copywriting, cro).

## Licencia

MIT.

---

## English

**landing-copy** — Writes page copy from the keyword map and product context - headline, subheadline, benefits, objections, CTA, with variants - where every claim has proof.

Install in Claude Code with `/plugin marketplace add nvv-dev/claude-plugins` and `/plugin install landing-copy@nvvdev`, or copy `skills/landing-copy/` into `.claude/skills/` (project) or `~/.claude/skills/` (personal). Other agents: copy the folder into their skills directory, or run `DISABLE_TELEMETRY=1 npx skills add nvv-dev/landing-copy`. Loads automatically when the task matches its description. Canonical source: [nvv-dev/growth-workflow](https://github.com/nvv-dev/growth-workflow). License: MIT.
