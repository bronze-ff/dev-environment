# Dev Environment

Repositório para reconstruir o meu setup de desenvolvimento no Windows/WSL. Aqui estão os guias e arquivos que uso sempre que formato a máquina.

## Visão geral
- **WSL + Node/NPM + Codex**: instruções em `Codex.md`.
- **Terminal moderno (Nushell + Starship + Zoxide)**: passo a passo em `Nushell.md`.
- **Config do VS Code**: usar `settings.json` como base.

## Como usar
1) Siga `Codex.md` para habilitar o WSL, instalar Node via NVM e configurar o Codex.
2) Configure o terminal conforme `Nushell.md`.
3) Importe as configurações do VS Code:
   - Abra o VS Code → `Ctrl+,` → pesquise por `settings.json`.
   - Substitua pelo conteúdo de `settings.json` deste repo (ajuste temas/fonte se precisar).

## Estrutura
- `Codex.md`: WSL, NVM/Node e instalação do Codex (CLI).
- `Nushell.md`: terminal com Nushell, Starship, Zoxide e fontes Nerd Font.
- `settings.json`: ajustes de UI e produtividade para VS Code no Windows.
