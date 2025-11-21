
# Guia de Configuração: Nushell + Starship + Zoxide (Windows)

Este guia contém o passo a passo para reproduzir o ambiente de terminal moderno no Windows utilizando Nushell.

## 1. Instalação dos Pacotes
Abra o **PowerShell** ou **CMD** e execute os comandos abaixo para instalar o shell e as ferramentas essenciais via Winget:

```powershell
# Instala o Shell principal
winget install nushell

# Instala o prompt personalizado (visual)
winget install starship

# Instala a navegação inteligente (substituto do cd)
winget install zoxide
```

## 2. Instalação da Fonte (Nerd Font)

O Starship precisa de uma fonte especial para mostrar os ícones.

1. Baixe a fonte **Cascadia Code** (versão Nerd Font):
    
    - Link direto sugerido: [CaskaydiaCove Nerd Font (GitHub)](https://www.google.com/search?q=https://github.com/ryanoasis/nerd-fonts/releases/latest)
        
    - Procure pelo arquivo `.zip` do **CascadiaCode**.
        
2. Extraia o arquivo.
    
3. Instale o arquivo: **`CaskaydiaCoveNerdFont-Regular.ttf`**.
    
    - _Dica: Evite as versões "Mono" ou "Propo" para evitar ícones pequenos ou desalinhados._
        

---

## 3. Configurar o Windows Terminal

1. Abra o **Windows Terminal**.
    
2. Vá em **Configurações (`Ctrl + ,`)**.
    
3. **Definir como Padrão:**
    
    - Na aba "Inicialização", mude o "Perfil padrão" para **Nushell**.
        
4. **Configurar a Fonte:**
    
    - No menu lateral, vá em **Perfis** > **Nushell** > **Aparência**.
        
    - Em "Tipo de fonte", selecione **CaskaydiaCove NF**.
        
    - Clique em **Salvar**.
        

---

## 4. Inicializar as Ferramentas (Dentro do Nushell)

Agora, abra uma aba do **Nushell** e execute estes comandos para gerar os arquivos de inicialização do Starship e do Zoxide:

```
# Gera o arquivo de init do Starship
starship init nu | save -f ~/.starship.nu

# Gera o arquivo de init do Zoxide
zoxide init nushell | save -f ~/.zoxide.nu
```

## 5. Editar o Arquivo de Configuração (`config.nu`)

Precisamos avisar o Nushell para carregar as ferramentas e remover o banner de boas-vindas.

1. Abra o arquivo de configuração:
    
    Snippet de código
    
    ```
    notepad $nu.config-path
    ```
    
2. Vá até o **final do arquivo** e cole o seguinte bloco de código:
    
    Snippet de código
    
    ```
    # --- Configurações Pessoais ---
    
    # Remove o banner de boas-vindas
    $env.config.show_banner = false
    
    # Carrega o Zoxide (Navegação inteligente)
    source ~/.zoxide.nu
    
    # Carrega o Starship (Prompt visual)
    source ~/.starship.nu
    ```
    
3. Salve o arquivo e reinicie o terminal.
    
---

## (Opcional) Ferramentas Extras Recomendadas

Kit de ferramentas modernas escritas em Rust para complementar o Nushell:

PowerShell

```
# Visualizador de arquivos (cat com cores)
winget install bat

# Busca ultra rápida em arquivos (grep melhorado)
winget install ripgrep

# Buscador difuso (Fuzzy Finder)
winget install fzf

# Interface gráfica para Git no terminal
winget install lazygit
```