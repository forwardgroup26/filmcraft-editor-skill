# filmcraft-editor-skill

Skill do Claude Code que transforma o Claude em editor de vídeo usando o [FilmCraft](https://github.com/storytold/filmcraft), um editor não linear gratuito e de código aberto, escrito em Rust.

A skill ensina o fluxo de edição completo (montagem, corte, enquadramento vertical, cor, texto, legendas, áudio e exportação) pelos comandos do `filmcraft-cli`, com as armadilhas que foram descobertas testando de verdade, como o JSON que o PowerShell 5.1 corrompe e os tempos que precisam estar em ticks.

## Instalar

1. Instale o [FilmCraft](https://getartcraft.com/apps/filmcraft) (testado na v0.17.0, Windows).
2. Copie a pasta `filmcraft-editor` para `~/.claude/skills/` (no Windows, `C:\Users\<você>\.claude\skills\`).
3. Opcional: registre o servidor MCP do FilmCraft:
   ```
   claude mcp add --scope user filmcraft -- "<pasta do FilmCraft>\filmcraft-cli.exe" mcp
   ```
4. Abra uma sessão nova. A skill é ativada quando você pedir para editar, cortar, legendar ou exportar um vídeo.

## O que a skill cobre

- Fluxo de 16 passos, do briefing à entrega
- fps igual ao do material principal, resolução que nunca aumenta e presets de exportação por plataforma
- Legendas manuais e automáticas, áudio com loudness de -14 LUFS e ducking de música
- Revisão visual por quadros renderizados antes de entregar

Os padrões de estilo (tabela "Padrões de edição" no `SKILL.md`) são ponto de partida: ajuste ao seu gosto.

## Aviso

Projeto independente, não afiliado ao FilmCraft nem ao ArtCraft. Os valores de desempenho foram medidos em um único PC.
