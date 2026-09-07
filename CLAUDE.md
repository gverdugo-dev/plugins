# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Qué es este repo

Marketplace **público** de plugins y skills de Claude Code de Gonzalo Verdugo. Solo contiene lo que
ya está terminado y probado: el desarrollo ocurre en el repo privado
`gverdugo-dev/plugins-lab` (marketplace `gv-plugins-lab`) y de ahí se promociona aquí.

- Marketplace: `gv-plugins`
- Repo: `gverdugo-dev/plugins` (**público**)
- Es un submódulo del contenedor `personal-public-resources`

**Este repo es público.** Todo lo que se commitee queda visible para cualquiera y, aunque se borre
después, puede haber sido clonado. Antes de cada commit, revisar que no entren rutas locales,
nombres de clientes, credenciales, capturas ni notas internas. Si algo no está listo para que lo
lea un desconocido, va a `plugins-lab`, no aquí.

## Estructura

```
plugins/
├── .claude-plugin/marketplace.json   # manifiesto del marketplace gv-plugins
├── CLAUDE.md
├── README.md
└── plugins/
    └── <plugin>/
        ├── .claude-plugin/plugin.json
        ├── skills/<skill>/SKILL.md
        ├── agents/<agente>.md         # opcional
        └── README.md
```

## Instalar

```bash
claude plugin marketplace add gverdugo-dev/plugins
claude plugin install <plugin>@gv-plugins
```

## Recibir un plugin desde plugins-lab

1. Copiar `plugins/<nombre>/` desde `plugins-lab` a la misma ruta de aquí.
2. Registrarlo en el array `plugins` de `.claude-plugin/marketplace.json` con
   `"source": "./plugins/<nombre>"`. **Nunca `"."`**: el validador lo rechaza.
3. Repasar el contenido con ojos de desconocido (ver el aviso de arriba) y comprobar que el plugin
   trae su `README.md` explicando qué hace y cómo se usa.
4. Validar antes de commitear:
   ```bash
   claude plugin validate .
   claude plugin validate ./plugins/<nombre>
   ```
5. Añadirlo a la tabla del `README.md`, commitear, y borrarlo de `plugins-lab` en el mismo momento:
   un plugin vive en un repo o en el otro, nunca en los dos.

Los `plugin.json` van **sin campo `version`**: la versión es el SHA del commit, así que publicar una
actualización es hacer push.

## Convenciones

- **Idioma**: castellano en `description`, documentación y comunicación. Inglés en código,
  comentarios, docstrings, nombres de archivo y mensajes de commit.
- **Sin em-dashes** (`—`, `–`) en comentarios ni docstrings, ni emojis dentro de un comentario.
- **Naming**: kebab-case para carpetas, plugins, skills y archivos `.md`.
- **Commits**: no añadir `Co-Authored-By` salvo petición explícita.

## Agent skills

### Issue tracker

Las issues y specs de este repo viven en GitHub Issues de `gverdugo-dev/plugins` y se gestionan
con la CLI `gh` (las PRs externas no cuentan como peticiones). Ver `docs/agents/issue-tracker.md`.

### Triage labels

Se usan las cinco etiquetas por defecto con su nombre canónico: `needs-triage`, `needs-info`,
`ready-for-agent`, `ready-for-human` y `wontfix`. Ver `docs/agents/triage-labels.md`.

### Domain docs

Single-context: un `CONTEXT.md` y un `docs/adr/` en la raíz del repo, creados bajo demanda cuando
haga falta. Ver `docs/agents/domain.md`.
