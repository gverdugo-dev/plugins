<p align="center">
  <img src="docs/banner.jpg" alt="Una bicicleta de paseo en vector plano" width="100%">
</p>

# other

Recursos sueltos que no encajan en ninguna otra categoría. Cada skill es independiente de las
demás.

| | |
|---|---|
| **Qué es** | Plugin de Claude Code con skills de solo texto |
| **Estado** | Publicado |
| **Trae** | 1 skill |
| **Requisitos** | Ninguno |
| **Marketplace** | `other@gv-plugins`, público |

## Qué trae

| Pieza | Qué hace |
|-------|----------|
| Skill `techie-resources` (`/other:techie-resources`) | Lista curada de recursos de desarrollo y tecnología: herramientas, datos, canales, cursos, blogs, newsletters y libros. Cada entrada lleva su enlace y una línea de por qué merece la pena. La lista vive entera en el cuerpo de la skill, sin ficheros aparte |

## Cómo se instala

```bash
claude plugin marketplace add gverdugo-dev/plugins
claude plugin install other@gv-plugins
```

No necesita claves ni variables de entorno.

## Cómo se usa

```
/other:techie-resources un canal sobre ingeniería de datos
```

O en conversación: "qué newsletter tech me recomiendas", "una herramienta para temas de
shadcn". La skill responde solo con lo que hay en la lista y lo dice cuando no hay nada que
encaje.

## Cómo encaja

Es el cajón de sastre del marketplace público: lo que no merece un plugin propio entra aquí
como una skill más. Añadir un recurso es una línea en la categoría que toque de
`skills/techie-resources/SKILL.md`, con la forma `- [Nombre](url): por qué merece la pena, en
una línea.` Una categoría nueva es un `##` más.

## Más información

`skills/techie-resources/SKILL.md`: la lista completa.
