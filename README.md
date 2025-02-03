# 🤖 Bot de Staff com Contagem de Mensagens e Sistema de Configuração

Um bot para Discord desenvolvido em **Node.js** e **Discord.js**, projetado para gerenciar a contagem de mensagens da staff, atribuir cargos automaticamente quando metas são atingidas e fornecer um painel de configurações via comandos.

---

## 📌 Recursos
✅ **Contagem automática de mensagens** para usuários registrados.  
✅ **Atribuição de cargos** ao atingir metas de mensagens.  
✅ **Registro e gerenciamento de staff** via comando `/menu`.  
✅ **Logs detalhados** de milestones no canal configurado.  
✅ **Persistência de dados** no arquivo `messageCounts.json`.  

---

## 🛠 Instalação

### 1️⃣ Clonar o repositório
```bash
git clone https://github.com/seu-usuario/seu-repositorio.git
cd seu-repositorio
```

### 2️⃣ Instalar dependências
```bash
npm install
```

### 3️⃣ Configurar o bot
1. **Edite o arquivo `config/config.json`** e adicione seus tokens, IDs do servidor e canais.

---

## 🔧 Configuração do `config.json`
O arquivo `config.json` contém as configurações essenciais:

```json
{
  "token": "SEU_BOT_TOKEN",
  "clientId": "SEU_CLIENT_ID",
  "guildId": "SEU_GUILD_ID",
  "generalChatId": "123456789012345678",
  "logChannelId": "987654321098765432",
  "roles": {
    "movChat": "1189721657225519185"
  },
  "milestones": [
    { "count": 3000, "roleId": "845828215141826640", "emoji": "🌾", "name": "Camponeses" },
    { "count": 4500, "roleId": "845828217221939200", "emoji": "🛠️", "name": "Artesãos" },
    { "count": 6000, "roleId": "845828214567469086", "emoji": "🏹", "name": "Arqueiros" }
  ]
}
```

---

## 🚀 Executando o bot

### 1️⃣ Registrar comandos no Discord
```bash
node deploy-commands.js
```
✅ Se o registro for bem-sucedido, aparecerá no console:
```plaintext
🔄 Iniciando o registro de X comandos.
✅ Comandos registrados com sucesso.
```

### 2️⃣ Iniciar o bot
```bash
node index.js
```
✅ O bot deve exibir no console:
```plaintext
✅ Bot iniciado como SeuBot#1234
```

---

## 📜 Comandos Disponíveis

| Comando          | Descrição                                      |
|-----------------|----------------------------------------------|
| `/menu`         | Abre o painel de configuração do bot.       |
| `/setmsgs @user 1000` | Define a contagem de mensagens de um usuário. |
| `/checkmsgs @user` | Exibe a quantidade de mensagens de um usuário. |

📌 **O `/menu` permite:**  
- Adicionar/remover staff ao sistema.  
- Visualizar as configurações do bot.  

---

## 🏆 Funcionamento das Milestones
O bot concede automaticamente **cargos** conforme o número de mensagens enviadas no canal geral:

📌 **Exemplo de Milestones:**
- **3.000 mensagens** → 🌾 Camponeses  
- **4.500 mensagens** → 🛠️ Artesãos  
- **6.000 mensagens** → 🏹 Arqueiros  

Quando um usuário atinge uma milestone, ele recebe uma **mensagem de parabéns** e o cargo é adicionado.

---

## 📝 Estrutura do Projeto

```
/meu-bot/
├── index.js                 # Código principal do bot
├── deploy-commands.js       # Script para registrar os slash commands
├── commands/                # Pasta com comandos do bot
│   ├── menu.js              # Menu de configuração do bot
│   ├── setmsgs.js           # Comando para definir mensagens de usuários
│   ├── checkmsgs.js         # Comando para verificar mensagens
├── config/                  # Pasta para arquivos de configuração
│   ├── config.json          # Configuração principal do bot
├── data/                    # Pasta para armazenar dados persistentes
│   ├── messageCounts.json   # Contagem de mensagens por usuário
├── package.json             # Dependências do projeto
└── README.md                # Documentação do projeto
```

---

## 🛠 Tecnologias Utilizadas
- **[Node.js](https://nodejs.org/)**
- **[Discord.js v14](https://discord.js.org/)**
- **JavaScript**
- **JSON para persistência de dados**

---

## 📞 Suporte
Caso tenha dúvidas ou precise de ajuda, entre em contato via **Issues** no GitHub ou no meu Discord!

---

## 📜 Licença
Este projeto está licenciado sob a licença **MIT**. Sinta-se livre para modificar e usar. 🤖✨
