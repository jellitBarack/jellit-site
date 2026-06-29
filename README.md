# Jellit Site

Site institucional e landing page da marca **Jellit** para divulgação de serviços técnicos em Java, Spring Boot, APIs REST, microsserviços, Kafka, AWS, arquitetura, code review e mentoria.

A marca Jellit combina o apelido **Jel** com **IT**, posicionando Jefferson S. Santos como especialista em soluções técnicas sob demanda.

## Estrutura do projeto

```text
jellit-site/
├── index.html                  # Página inicial / landing page
├── services.html               # Página de serviços
├── about.html                  # Sobre a marca e trajetória
├── cases.html                  # Cases genéricos sem dados confidenciais
├── blog.html                   # Lista de conteúdos técnicos
├── blog-api-rest.html          # Artigo sobre APIs REST
├── blog-timeout-microservicos.html
├── blog-code-review-java.html
├── contact.html                # Contato e formulário seguro
├── css/styles.css              # Estilos principais responsivos
├── js/app.js                   # WhatsApp, menu, formulário e PWA
├── assets/img/jellit-logo.jpeg # Logotipo oficial
├── docs/DEPLOY.md              # Guia de publicação gratuita
├── docs/SEGURANCA.md           # Segurança e antispam
├── robots.txt                  # Regras de indexação
├── sitemap.xml                 # Mapa do site
├── site.webmanifest            # PWA
└── .github/workflows/pages.yml # Deploy automático GitHub Pages
```

## Funcionalidades

- Site 100% estático: HTML, CSS e JavaScript puro.
- Hospedagem gratuita no GitHub Pages.
- Logo oficial Jellit aplicado no header, hero e favicon.
- Botões de WhatsApp com mensagens personalizadas por serviço.
- Formulário seguro que prepara uma mensagem no WhatsApp.
- Estrutura pronta para EmailJS caso queira envio direto por e-mail.
- SEO com meta tags, Open Graph, Schema.org, sitemap e robots.txt.
- PWA básico para instalação no celular.
- Layout responsivo para desktop e mobile.
- Documentação de segurança e implantação.

## Como acessar localmente

Opção simples:

1. Extraia o ZIP.
2. Abra o arquivo `index.html` no navegador.

Opção recomendada com servidor local:

```bash
cd jellit-site
python3 -m http.server 8080
```

Acesse:

```text
http://localhost:8080
```

## Como publicar gratuitamente no GitHub Pages

### 1. Criar conta no GitHub

1. Acesse o GitHub.
2. Crie sua conta ou faça login.
3. Ative autenticação em dois fatores para maior segurança.

### 2. Criar repositório

1. Clique em **New repository**.
2. Nome sugerido: `jellit-site`.
3. Deixe como **Public** para usar GitHub Pages gratuitamente com facilidade.
4. Clique em **Create repository**.

### 3. Enviar arquivos

Pelo navegador:

1. Clique em **uploading an existing file**.
2. Arraste todos os arquivos da pasta `jellit-site`.
3. Clique em **Commit changes**.

Ou por Git:

```bash
git init
git add .
git commit -m "Publica site Jellit"
git branch -M main
git remote add origin https://github.com/jellitBarack/jellit-site.git
git push -u origin main
```

### 4. Ativar GitHub Pages

1. Acesse o repositório.
2. Vá em **Settings > Pages**.
3. Em **Build and deployment**, selecione **GitHub Actions**.
4. Vá na aba **Actions** e aguarde o workflow finalizar.

### 5. Acessar o site

A URL terá este formato:

```text
https://jellitBarack.github.io/jellit-site/
```

## Ajustes obrigatórios antes de publicar

Substitua `SEU-USUARIO` pelo seu usuário do GitHub nos arquivos:

- `robots.txt`
- `sitemap.xml`
- todos os `<link rel="canonical">` nos arquivos HTML, se desejar precisão máxima de SEO
- variável `site` em `js/app.js`

## WhatsApp

O telefone está configurado em `js/app.js`:

```javascript
phone: '5541987142736'
```

As mensagens ficam em:

```javascript
const serviceMessages = { ... }
```

Cada botão usa um atributo como:

```html
<a data-wa="api">Solicitar orçamento</a>
```

## E-mail e EmailJS

Por segurança e simplicidade, o formulário padrão abre uma mensagem no WhatsApp. Para envio por e-mail direto usando GitHub Pages, configure o EmailJS:

1. Crie uma conta no EmailJS.
2. Conecte seu Gmail.
3. Crie um template com campos `name`, `email`, `service` e `message`.
4. Copie `serviceId`, `templateId` e `publicKey`.
5. Edite `js/app.js`.
6. Altere:

```javascript
emailjs: {
  enabled: false,
  serviceId: 'SEU_SERVICE_ID',
  templateId: 'SEU_TEMPLATE_ID',
  publicKey: 'SUA_PUBLIC_KEY'
}
```

Para ativar envio real por EmailJS, também é necessário incluir a SDK e adaptar o submit. A versão atual prioriza WhatsApp para velocidade e menor risco de spam.

## Segurança

Boas práticas incluídas:

- Site estático sem backend exposto.
- Nenhum segredo no frontend.
- Formulário com honeypot.
- Limite de caracteres nos campos.
- Aviso para não enviar dados sensíveis.
- Páginas sem dependências complexas.
- Nenhuma coleta silenciosa de dados.

Nunca publique:

- `.env`
- tokens
- secrets
- chaves AWS
- chaves SSH
- dumps de banco
- dados de clientes

## Estratégia de uso em 48 horas

1. Publique o site.
2. Teste todos os botões de WhatsApp.
3. Compartilhe a URL em LinkedIn, Workana, 99Freelas, Fiverr, Upwork, GitHub, Reddit, Dev.to, Medium e comunidades técnicas.
4. Use ofertas específicas: bug Spring Boot, API REST, Kafka, AWS, arquitetura, code review e mentoria.
5. Responda rápido e peça contexto técnico objetivo.

## Personalização

### Trocar logo

Substitua:

```text
assets/img/jellit-logo.jpeg
```

Mantenha o mesmo nome para não precisar alterar os HTMLs.

### Alterar cores

Edite as variáveis em `css/styles.css`:

```css
:root {
  --bg: #07111f;
  --brand: #24aadb;
  --brand2: #8fd8ee;
}
```

### Adicionar serviço

1. Edite `index.html` e `services.html`.
2. Adicione um novo card.
3. Crie uma mensagem correspondente em `js/app.js`.

## Licença

Uso pessoal/profissional da marca Jellit.
