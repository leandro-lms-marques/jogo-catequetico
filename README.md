# 🌟 Jornada da Fé — Jogo Catequético

Quiz interativo de catequese católica para crianças, com 100 perguntas e sincronização entre dispositivos via Firebase.

🔗 **Jogar:** `https://leandro-lms-marques.github.io/jogo-catequetico/`

---

## 🚀 Ativar Sincronização Entre Dispositivos (Firebase)

Por padrão, o jogo salva os dados apenas no navegador (localStorage). Para sincronizar automaticamente entre celular, tablet e computador, configure o Firebase:

### 1. Criar projeto no Firebase (2 minutos, grátis)

1. Acesse https://console.firebase.google.com
2. Clique **"Adicionar projeto"**
3. Dê um nome (ex: `jornada-da-fe`)
4. Desative o Google Analytics (não precisa)
5. Clique **"Criar projeto"**

### 2. Criar o Realtime Database

1. No menu lateral, vá em **"Criação" → "Realtime Database"**
2. Clique **"Criar banco de dados"**
3. Escolha o local: **`us-central1`** ou **`southamerica-east1`** (São Paulo)
4. Em regras de segurança, selecione **"Iniciar no modo de teste"** (permite leitura/escrita por 30 dias)
5. Clique **"Ativar"**

### 3. Pegar as credenciais

1. No menu lateral, vá em **"Visão geral do projeto"**
2. Clique no ícone **`</>`** (Web)
3. Registre o app com o apelido `jogo-catequetico`
4. **Copie o objeto `firebaseConfig`** que aparece
5. Cole no arquivo `index.html`, substituindo o placeholder `FIREBASE_CONFIG`
6. Exemplo do que você vai colar:
```js
const FIREBASE_CONFIG = {
  apiKey: "AIzaSyABC123...",
  authDomain: "seu-projeto.firebaseapp.com",
  databaseURL: "https://seu-projeto-default-rtdb.firebaseio.com",
  projectId: "seu-projeto",
  storageBucket: "seu-projeto.appspot.com",
  messagingSenderId: "123456789",
  appId: "1:123456789:web:abc123..."
};
```

### 4. Ajustar regras de segurança (recomendado)

Após 30 dias, as regras de teste expiram. Para manter o banco funcionando, vá em **Realtime Database → Regras** e cole:

```json
{
  "rules": {
    "families": {
      "$familyCode": {
        ".read": true,
        ".write": true
      }
    }
  }
}
```

### 5. Publicar no GitHub Pages

```bash
git add index.html
git commit -m "config: firebase credentials"
git push
```

---

## 📱 Como usar a sincronização

1. Em cada dispositivo, abra o link do jogo
2. Na tela inicial, digite o **mesmo código de família** (ex: `familia2024`)
3. Clique **"Conectar e Sincronizar"**
4. Pronto! Rankings, cartas e progresso aparecem em todos os dispositivos ☁️

O código da família fica salvo — da próxima vez o jogo conecta automaticamente.

---

## 🎮 Funcionalidades

- **100 perguntas** com referências do Catecismo e passagens bíblicas
- **6 regiões** temáticas para explorar
- **24 cartas de santos** colecionáveis (com "como imitar")
- **Anjo companheiro** que reage às respostas
- **Cenas bíblicas** contextuais entre perguntas
- **Power-ups**: 50-50, Pular, Dica Bíblica
- **Sistema de níveis** com XP e subida de nível
- **Questionário discursivo** ao final de cada região
- **Ranking** entre todos os perfis
- **PIN de proteção** em cada perfil
- **Exportar/Importar** dados manualmente
- **Sincronização automática** via Firebase ☁️

---

## 🔐 PINs

- Cada perfil criado tem um **PIN de 4 dígitos**
- Só quem sabe o PIN pode apagar o perfil
- **PIN mestre do admin: `2708`** — apaga qualquer perfil
