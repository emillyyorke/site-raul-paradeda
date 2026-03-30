# 🌐 Site Acadêmico - Professor Raul Benites Paradeda

Uma plataforma web moderna e bilíngue (PT/EN) para o gerenciamento e apresentação do trabalho acadêmico e informações pessoais do Professor Raul Benites Paradeda. O site é focado em **acessibilidade**, **dinamismo de conteúdo** e **responsividade** em diversos dispositivos.

Site hospedado em: https://site-raul-paradeda-flask.onrender.com/pt/
---

## 🌟 Funcionalidades

### Páginas Públicas
- Homepage
- Áreas de Pesquisa
- Projetos
- Publicações
- Orientações
- Contato
- Sobre Mim

### Conteúdo Dinâmico
- Informações do professor, publicações, projetos e orientações carregadas via **APIs do backend**.

### Acessibilidade
- **Modo de Alto Contraste**: Alternância de tema para melhor legibilidade.
- **Ajuste de Fonte**: Aumentar, diminuir e resetar tamanho da fonte.
- **Navegação por Teclado**: Atalhos e navegação intuitiva.

### Interface Bilíngue (PT/EN)
- Alternância com URLs localizadas
- Formatação de datas adaptada ao idioma

### Filtros de Projetos
- Por tipo: Pesquisa, Extensão, Ensino
- Por status: Em Andamento, Concluído, Planejamento, Proposto

### Formulário de Contato
- Envio de mensagens com feedback visual
- Notificação por e-mail configurável

### Painel Administrativo
- Autenticação segura (login/logout)
- CRUD para:
  - Professor
  - Publicações
  - Projetos
  - Orientações
  - Áreas de Pesquisa
  - Mensagens de Contato
- Dashboard com estatísticas básicas

---

## 💡 Arquitetura

- **Monolítica**: Frontend e backend na mesma aplicação Flask.
- **Frontend**: HTML, CSS (Flexbox/Grid, variáveis), JavaScript puro.
- **Backend**: Flask com APIs RESTful.
- **Persistência**: `academic_data.json`.
- **Segurança**: Content-Security-Policy, controle de acesso.

---

## 🛠️ Tecnologias Utilizadas

### Backend
- Python 3.9+
- Flask
- Flask-Babel
- Werkzeug
- Gunicorn
- smtplib

### Frontend
- HTML5
- CSS3 (com variáveis e media queries)
- JavaScript (ES6+)
- Font Awesome

### Outros
- Git / GitHub
- pip
- [Render](https://render.com/) (deploy)

---

## 🚀 Configuração e Instalação (Desenvolvimento Local)

### 1. Clone o repositório

```bash
git clone https://github.com/vsr777/site-raul-paradeda
cd site-raul-paradeda
```

### 2. Crie e ative o ambiente virtual

```bash
python -m venv venv
# Windows:
.env\Scriptsctivate
# Linux/macOS:
source venv/bin/activate
```

### 3. Instale as dependências

```bash
pip install -r requirements.txt
```

### 4. Configure o `.env`

Crie um arquivo `.env` na raiz:

```
SECRET_KEY='sua_chave_secreta_aqui_e_bem_longa_e_aleatoria'
EMAIL_USERNAME='seu_email@gmail.com'
EMAIL_PASSWORD='sua_senha_de_aplicativo_do_gmail'
ADMIN_RECEIVER_EMAIL='email_do_admin@exemplo.com'
```

> ⚠️ Para Gmail, use uma **senha de aplicativo** se a verificação em duas etapas estiver ativa.

### 5. Traduções com Flask-Babel

```bash
flask babel extract -F babel.cfg -o translations/messages.pot --input-paths .
flask babel init -i translations/messages.pot -d translations -l en
flask babel update -i translations/messages.pot -d translations
flask babel compile -d translations
```

> Verifique se `babel.cfg` está na raiz do projeto.

### 6. Execute o servidor

```bash
flask run --port 3001
```

Acesse:
- [http://localhost:3001/pt/](http://localhost:3001/pt/) – Português
- [http://localhost:3001/en/](http://localhost:3001/en/) – Inglês

---

## 🖥️ Uso

### Site Público

- Alternar idioma via botão no cabeçalho
- Aumentar/reduzir/resetar fonte com A-, A, A+
- Alternar contraste 🌑 / ☀️
- Filtrar projetos por tipo e status

### Painel Administrativo

- Acesse: `http://localhost:3001/admin/login`
- Login padrão (local):  
  **Usuário:** `admin`  
  **Senha:** `admin123`

---

## ☁️ Deploy (Render)

1. Crie conta em [https://render.com/](https://render.com/)
2. Crie novo **Web Service** conectado ao GitHub/GitLab
3. Configure:

```
Name: seu-site-professor
Root Directory: .
Runtime: Python 3
Build Command: pip install -r requirements.txt
Start Command: gunicorn flask_admin_enhanced:app
```

4. Adicione as variáveis de ambiente (`.env`)
5. Clique em **Create Web Service**

> ⚠️ No plano gratuito, o serviço dorme após 15 min de inatividade.

---

## 📁 Estrutura do Projeto

```
.
├── .gitattributes
├── academic_data.json
├── admin_template.py
├── flask_admin_enhanced.py
├── requirements.txt
├── README.md
├── static/
│   ├── css/
│   ├── img/
│   └── js/
└── templates/
    ├── areas_pesquisa.html
    ├── contato.html
    ├── index.html
    ├── orientacoes.html
    ├── projetos.html
    ├── publicacoes.html
    └── sobre_mim.html
```

> Também é recomendável incluir: `.gitignore`, `Procfile`, e a pasta `translations/` com `babel.cfg`.

---

## 🤝 Contribuindo

1. Faça um **fork** do repositório.
2. Crie uma nova branch.
3. Envie um **pull request** com suas alterações.

---
