# Bot de Vendas de Salas Free Fire

Bot Discord para vender saldo de salas, criar carrinho privado, confirmar pagamento manual, configurar perfil do cliente e criar salas pela API SalasBot FF.

## O que tem nesta versão

- Painel de vendas editável.
- Botão para comprar salas.
- Canal privado de pedido só para cliente, dono/staff e bot.
- Confirmação manual de pagamento.
- Saldo por cliente.
- `/saldo` para ver saldo.
- `/perfil` para configurar senha fixa, tempo de GO e prefixo do cliente.
- Prefixo individual por cliente, exemplo: `.cr`, `!cr`, `?cr`, `,cr`.
- Painel de escolha de modo igual ao exemplo, com menu de seleção.
- Atalho direto: `.cr 1`, `.cr1`, `.cs 2`, `.cs2`.
- Criação de sala pela API.
- Embed da sala criada com ID, senha, modo, GO, Time 1 e Time 2.
- Botão `Atualizar jogadores` para buscar quem entrou na sala pela API.

## Arquivos importantes

```txt
src/
data/
package.json
.env.example
.gitignore
README.md
```

Nunca envie `.env` para o GitHub.

## Como configurar

Crie um arquivo `.env` baseado no `.env.example`:

```env
DISCORD_TOKEN=seu_token_do_bot
CLIENT_ID=id_do_bot
GUILD_ID=id_do_servidor
SALAS_API_KEY=sua_key_da_api
BASE_URL=https://salas-bot.freefireapi.online
```

## Intents obrigatórias no Discord Developer Portal

Para os comandos por prefixo funcionarem, ative:

```txt
Bot > Privileged Gateway Intents > Message Content Intent
```

Também deixe o bot com permissão de:

```txt
Ver canais
Enviar mensagens
Ler histórico de mensagens
Gerenciar canais
Usar comandos de aplicação
Incorporar links
```

## Instalar e ligar

```bash
npm install
npm start
```

## Comandos de admin

```txt
/config-vendas painel
/config-vendas botao
/config-vendas canais
/config-vendas preco
/config-vendas ver
/painel-vendas
```

Use `/config-vendas canais` para colocar:

- Cargo dono/staff.
- Categoria dos pedidos.
- Canal de logs.

## Comandos do cliente

```txt
/saldo
/perfil
/criar-sala
```

No `/perfil`, o cliente configura:

- Senha fixa.
- Tempo de GO.
- Prefixo.

Exemplo:

```txt
Prefixo: .
Senha: 33
Tempo GO: 5
```

Depois ele pode usar no chat:

```txt
.cr
.cs
.cr 1
.cr1
.cs 2
.cs2
```

Se usar só `.cr` ou `.cs`, o bot manda um painel para escolher o modo.

Se usar `.cr 1`, o bot cria direto o modo 1.

## Modos do painel

```txt
1 - 4x4 Padrão Apostado
2 - 4x4 5 Gelo
3 - Gel Infinito
4 - Capa Nv3
5 - Full Capa
```

## Jogadores na sala

Depois de criar a sala, o bot manda o embed com:

```txt
ID da sala
Senha
Modo
GO
Time 1
Time 2
Nome dos jogadores
```

Se os jogadores ainda não tiverem entrado, vai aparecer `Aguardando jogadores...`.

Clique em `Atualizar jogadores` para buscar novamente na API.
