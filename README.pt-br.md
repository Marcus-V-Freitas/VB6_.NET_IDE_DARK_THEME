# VB6 / .NET IDE Tema Dark

> 🇺🇸 [Read in English](README.md)

[![License](https://img.shields.io/badge/license-MIT-blue)](LICENSE)
![Platform](https://img.shields.io/badge/platform-Windows-blue)
![Target](https://img.shields.io/badge/IDE-VB6%20%7C%20.NET%20Cl%C3%A1ssico-blue)

Um tema dark para as IDEs do Visual Basic 6 e do .NET clássico, aplicado via uma
`VBA6.DLL` modificada e importação de registro. Nenhuma ferramenta de terceiros necessária.

## Motivação

As IDEs do VB6 e do .NET clássico (VB.NET, C# na IDE legada) vêm com um editor de fundo
branco fixo que não pode ser alterado pelas opções da IDE. A única forma de ter um tema dark
de verdade é modificar a `VBA6.DLL` para desbloquear o suporte a cores customizadas e então
importar a paleta de cores via Registro do Windows.

Este repositório empacota a DLL modificada, o arquivo de registro e a configuração de cores
para que toda a instalação leve menos de cinco minutos.

## Conteúdo do Repositório

| Arquivo | Descrição |
|---|---|
| `VBA6.DLL` | DLL modificada com suporte a cores customizadas ativado |
| `Run.reg` | Arquivo de Registro do Windows com a paleta dark |
| `Tema Dark.ini` | Definição bruta da paleta de cores (valores RGBA) |
| `Backup/VBA6.DLL` | DLL original sem modificações para rollback |

## Instalação

> **Pré-requisitos:** Visual Basic 6 ou a IDE clássica do .NET instalada no Windows.

1. Feche a IDE completamente antes de começar.

2. Faça backup da sua `VBA6.DLL` atual (já incluída em `Backup/` como referência):
```
C:\Windows\System32\VBA6.DLL
```

3. Copie a `VBA6.DLL` modificada deste repositório para o mesmo caminho:
```
copy VBA6.DLL C:\Windows\System32\VBA6.DLL
```
> Pode ser necessário assumir a propriedade do arquivo ou executar o comando como Administrador.

4. Dê um duplo clique em `Run.reg` e confirme a importação do registro quando solicitado.

5. Abra a IDE. O editor usará o esquema de cores dark.

## Paleta de Cores

O tema é aplicado com as seguintes cores, definidas em `Tema Dark.ini` e `Run.reg`:

| Elemento | Cor |
|---|---|
| Fundo | `#1E1E1E` (cinza escuro) |
| Texto normal | `#D4D4D4` (cinza claro) |
| Palavras-chave | `#569CD6` (azul) |
| Comentários | `#608B4E` (verde) |
| Strings | `#D69D85` (pêssego) |
| Erros | `#FF0000` (vermelho) |
| Seleção | `#264F78` (azul escuro) |
| Fonte | Consolas 10pt |

## Rollback

Para reverter ao visual original da IDE:

1. Copie `Backup/VBA6.DLL` de volta para `C:\Windows\System32\VBA6.DLL`.
2. Abra as Opções da IDE e redefina as cores do editor manualmente, ou reimporte as
   chaves de registro originais.

## Licença

[MIT](LICENSE)
