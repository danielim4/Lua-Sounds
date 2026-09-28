# Lua-Sounds

Aplicativo Windows leve e discreto que toca um som aleatório em horários definidos. Ele roda em segundo plano e inicia automaticamente com o Windows.

Não há janela, notificações ou ícone na bandeja: o único comportamento perceptível é a reprodução do áudio nos horários configurados.

## Como funciona

- Os horários são definidos em `configs.lua`.
- Os arquivos de áudio ficam em `sounds/`.
- Em cada horário, o aplicativo escolhe aleatoriamente um arquivo WAV da pasta.
- Se o computador estiver desligado, suspenso ou o programa não estiver ativo naquele horário, o som não toca depois para compensar.
- Ao iniciar o Windows ou o aplicativo, nenhum som é reproduzido automaticamente.

## Configuração

Crie ou edite `configs.lua` ao lado de `app.exe`:

```lua
return {
  horarios = {
    "08:00",
    "12:00",
    "18:30",
  }
}
```

Os horários usam o relógio local do Windows e o formato `HH:MM`.

Adicione arquivos `.wav` à pasta `sounds/`. Caso ela esteja vazia, nenhum som será reproduzido.

## Instalação

Quando o projeto for publicado no GitHub, a instalação será feita por um comando PowerShell. O instalador baixa os arquivos, instala-os em `%LOCALAPPDATA%\LuaSounds` e configura a inicialização automática para o usuário atual.

Depois de instalado, o aplicativo funciona offline e não depende de internet, GitHub ou PowerShell.
