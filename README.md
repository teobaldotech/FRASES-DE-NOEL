# 🎄 Magia do Natal — Frases, Cartões e Surpresas

Aplicação web interativa em arquivo único (`index.html`) com temática natalina, desenvolvida em **HTML5**, **Tailwind CSS** e **JavaScript (ES6+)**, estruturada para navegação fluida entre telas, geração de mensagens sem repetição, criação de cartões personalizados e integração com **Google AdMob** via **Capacitor** para Android.

---

## ✨ Funcionalidades Principais

* **Efeito de Neve Dinâmico**: partículas animadas cobrindo a viewport sem bloquear a interação com os controles.
* **Tela de Capa (`screen-cover`)**: acesso direto a *Ver Frases*, *Criar Cartão*, *Surpresa do Papai Noel* e ao modal *Mensagem Especial*.
* **Mural de Frases (`screen-phrases`)**:
  * Filtros por categoria: *Todas*, *Família*, *Amigos*, *Romance* e *Curtas (Status)*.
  * **Gerador sem repetição (`generateUniquePhrase`)**: sorteia frases da categoria ativa evitando repetições até esgotar o ciclo, exibindo contador de progresso (`vistas/total`) e reiniciando o ciclo automaticamente.
  * Ações rápidas para **copiar** (com fallback para ambientes sem `navigator.clipboard`) ou **enviar direto ao Criador de Cartões**.
* **Criador de Cartões (`screen-card-maker`)**:
  * Pré-visualização ao vivo com campos *Para*, *Mensagem* e *De*.
  * Seleção de adesivos festivos (`🎄`, `🎅`, `🎁`, `⭐`, `⛄`) ou URL personalizada de imagem com fallback automático.
  * 6 temas visuais (*Clássico*, *Floresta*, *Luxo Dourado*, *Noite Estelar*, *Neve Alpina* e *Rosa Natalino*).
  * Compartilhamento por cópia formatada ou envio direto via **WhatsApp**.
* **Surpresa do Papai Noel (`screen-surprise`)**:
  * Mensagens tradicionais sem repetição cíclica (`generateSantaMessage(false)`).
  * Desbloqueio de **Bênção VIP do Noel** (`unlockVipSantaSurprise`) conectado a anúncio premiado (*Rewarded*).
* **Camada Google AdMob (`admobBridge`)**:
  * **Banner adaptativo inferior**: oculto na capa (`screen-cover`) e exibido nas telas internas com ajuste de margem inferior (`pb-24`) no `<body>`.
  * **Interstitial**: disparado a cada 3 cliques em *Nova Frase* (`interstitialEvery: 3`), com recarga automática após fechamento.
  * **Rewarded**: libera a *Bênção VIP do Noel* após concessão da recompensa, com fallback seguro quando executado diretamente no navegador web.

---

## 🛠️ Tecnologias Utilizadas

* **HTML5** & **JavaScript (ES6+)**
* **Tailwind CSS** (via CDN)
* **FontAwesome 6.4.0** (via CDN)
* **Google Fonts** (`Mountains of Christmas`, `Playfair Display` e `Poppins`)
* **Capacitor** + **`@capacitor-community/admob`** (para empacotamento Android e anúncios nativos)

---

## 📁 Estrutura do Projeto

```text
magia-do-natal/
├── index.html          # Aplicação completa (estrutura, estilos, lógica e ponte AdMob)
└── README.md           # Documentação do projeto
