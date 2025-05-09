# Instalação do PowerShell 7 com PowerToys e Complementos

Este guia descreve como instalar o PowerShell 7.4 usando o PowerToys com o módulo `CommandNotFound`, e como configurar complementos úteis como `oh-my-posh`, `eza` e `zoxide`.

---

## Pré-requisitos

- Windows 10 ou superior
- [Microsoft PowerToys](https://learn.microsoft.com/en-us/windows/powertoys/)
- Acesso administrativo ao sistema

---

## Passo 1: Instalando o PowerShell 7 via PowerToys

1. **Baixe o PowerToys**:
   - Faça o download do instalador do PowerToys [aqui](https://github.com/microsoft/PowerToys/releases) (Pode ser instalado por winget).

   - Instale o PowerToys seguindo as instruções.

2. **Instale o PowerShell 7.4**:
   - Abra o Terminal do Windows.
   - Execute o seguinte comando para instalar o PowerShell 7.4:
     ```powershell
     winget install --id Microsoft.Powershell --source winget
     ```
     Obs.: Pode ser instalado como demonstrado no video pela interface

   - Confirme a instalação executando:
     ```powershell
     pwsh --version
     ```

4. **Instale o Módulo `CommandNotFound`**:
   - Execute o comando:
     ```powershell
     Install-Module -Name CommandNotFound -Scope CurrentUser
     ```
     Obs.: Pode ser instalado como demonstrado no video pela interface

   - Reinicie o terminal para aplicar as mudanças.

---

## Passo 2: Instalando Complementos

### 1. **Oh My Posh**

Oh My Posh é uma ferramenta para personalizar o prompt do PowerShell.

- Instale o módulo via Winget:
  ```powershell
  winget install --id JanDeDobbeleer.OhMyPosh -s winget
  ```
- Configure o tema incluindo linha no PROFILE:
  ```powershell
  oh-my-posh init pwsh --config https://raw.githubusercontent.com/JanDeDobbeleer/oh-my-posh/main/themes/powerline.omp.json | Invoke-Expression
  ```
  Obs.: Temas pode ser escolhido na documentação [aqui](https://ohmyposh.dev/docs/themes)


### 2. **Eza**

Eza é uma alternativa moderna ao comando `ls`.

- Instale via Winget:
  ```powershell
  winget install eza-community.eza
  ```
- Verifique a instalação:
  ```powershell
  eza --version
  ```

### 3. **Zoxide**

Zoxide é um substituto rápido e eficiente para `cd`.

- Instale via Winget:
  ```powershell
  winget install --id ajeetdsouza.zoxide --source winget
  ```
- Configure no seu perfil:
  ```powershell
  Invoke-Expression (& { (zoxide init powershell | Out-String) })
  ```
- Verifique a instalação:
  ```powershell
  zoxide --version
  ```

---

## Conclusão

Após seguir este guia, você terá o PowerShell 7.4 configurado com o módulo `CommandNotFound` e os complementos `oh-my-posh`, `eza` e `zoxide`. Essas ferramentas melhorarão sua produtividade e a experiência de uso no terminal. Reinicie o terminal para garantir que todas as configurações estejam aplicadas.
