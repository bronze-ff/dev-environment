# Guia: Nushell + Starship + Zoxide (Windows)

Passo a passo para montar o terminal moderno no Windows usando Nushell.

## 1) Instalar os pacotes principais
Execute no **PowerShell** ou **CMD** (via Winget):

```powershell
winget install nushell       # Shell
winget install starship      # Prompt visual
winget install zoxide        # Navegação inteligente (substituto do cd)
```

## 2) Instalar a Nerd Font
O Starship precisa de fonte com ícones.

1. Baixe **CaskaydiaCove Nerd Font** (Cascadia Code Nerd Font) em [ryanoasis/nerd-fonts - releases](https://github.com/ryanoasis/nerd-fonts/releases/latest).
2. Extraia o `.zip` e instale `CaskaydiaCoveNerdFont-Regular.ttf`.
   - Evite as versões Mono/Propo para não encolher os ícones.

## 3) Configurar o Windows Terminal
1. Abra o **Windows Terminal** → `Ctrl + ,` para ir em Configurações.
2. Em **Inicialização**, defina **Nushell** como perfil padrão.
3. Em **Perfis > Nushell > Aparência**, selecione a fonte **CaskaydiaCove NF** e salve.

## 4) Gerar arquivos de inicialização (no Nushell)
Abra uma aba do **Nushell** e rode:

```nu
starship init nu | save -f ~/.starship.nu
zoxide init nushell | save -f ~/.zoxide.nu
```

## 5) Editar `config.nu`
Adicionar carregamento das ferramentas e remover o banner.

1. Abrir o arquivo de configuração:

```nu
notepad $nu.config-path
```

2. No final do arquivo, adicionar:

```nu
# --- Configurações Pessoais ---
$env.config.show_banner = false
source ~/.zoxide.nu
source ~/.starship.nu
source ~/.carapace.nu
```

3. Salvar e reiniciar o terminal.

## Extras (opcional)
Ferramentas úteis (todas via Winget):

```powershell
winget install bat      # cat com cores
winget install ripgrep  # busca muito rápida (grep melhorado)
winget install fzf      # fuzzy finder
winget install lazygit  # interface de Git no terminal
winget install carapace # autocompletes para CLIs
```
