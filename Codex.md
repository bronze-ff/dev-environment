# Guia: WSL + Node (NVM) + Codex

Passo a passo para preparar o ambiente no Windows utilizando WSL e instalar o Codex com npm global sem dor de cabeça.

## 1) Ativar o WSL
1. Abra o **PowerShell como Administrador** (menu Iniciar → PowerShell → botão direito → Executar como administrador).
2. Rode o comando e reinicie quando terminar:

```powershell
wsl --install
```

3. Ao reiniciar, a instalação do Ubuntu inicia automaticamente. Crie seu usuário e senha quando solicitado.

## 2) Preparar o Ubuntu (WSL)
Abra o terminal do **Ubuntu (WSL)** e execute:

```bash
sudo apt update && sudo apt upgrade -y
```

## 3) Instalar o Node via NVM
Usar o NVM evita problemas de permissão ao instalar pacotes globais.

```bash
# Instala o NVM
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.7/install.sh | bash

# Carrega o NVM na sessão atual (sem precisar reabrir o terminal)
export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"

# Instala o Node LTS (já inclui npm)
nvm install --lts
```

## 4) Instalar o Codex (CLI)
Com o Node configurado no WSL, instale o Codex globalmente:

```bash
npm i -g @openai/codex
```

Pronto. A instalação via WSL evita os erros de permissão e PATH comuns no Windows ao usar `npm -g`.