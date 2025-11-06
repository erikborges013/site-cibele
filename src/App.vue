<template>
  <div id="app">
    <header class="navbar">
      <div class="container">
        <a href="#" class="logo">Cibele Evâny</a>
        <nav>
          <ul>
            <li><a href="#hero">Início</a></li>
            <li><a href="#about">Sobre</a></li>
            <li><a href="#gallery">Galeria</a></li>
            <li><a href="#services">Serviços</a></li>
            <li><a href="#contact">Contato</a></li>
          </ul>
        </nav>
      </div>
      <BotaoWhatsapp />
    </header>

    <main>
      <section id="hero" class="hero-section">
        <div class="hero-content">
          <h1>Capturando Momentos, Criando Memórias</h1>
          <p>Fotografia profissional para todos os seus momentos especiais.</p>
          <a href="#gallery" class="cta-button">Veja meu trabalho</a>
        </div>
      </section>

      <section id="about" class="content-section">
        <div class="container">
          <h2>Sobre Mim</h2>
          <p>
            Fotógrafa de Retratos a + de 10 Anos no mercado Realizo seu sonho
            com seriedade e compromisso Vamos alinhar as expectativas e fazer
            acontecer Aguardo o seu contato.
          </p>
        </div>
      </section>

      <section id="gallery" class="content-section bg-light">
        <div class="container">
          <h2>Galeria</h2>
          <p>Uma amostra dos meus trabalhos recentes.</p>
          <div class="gallery-grid">
            <div
              v-for="image in galleryImages"
              :key="image.id"
              class="gallery-item"
            >
              <img :src="image.url" :alt="image.alt" />
            </div>
          </div>
        </div>
      </section>

      <section id="services" class="content-section">
        <div class="container">
          <h2>Serviços</h2>
          <div class="services-grid">
            <div class="service-card">
              <h3>Retratos</h3>
              <p>
                Sessões individuais, de casais ou família, capturando sua
                essência.
              </p>
            </div>
            <div class="service-card">
              <h3>Eventos</h3>
              <p>
                Cobertura de eventos corporativos, festas, casamentoss e
                celebrações.
              </p>
            </div>
          </div>
        </div>
      </section>
    </main>

    <footer class="footer">
      <div class="container">
        <div class="social-links">
          <a
            href="https://www.instagram.com/fotografaembertioga?igsh=cHQzaXA2dXB5MnNr"
            >Instagram</a
          >
        </div>
        <p>
          &copy; {{ new Date().getFullYear() }} Cibele Evâny Fotografia. Todos
          os direitos reservados.
        </p>
      </div>
    </footer>
  </div>
</template>

<script setup>
import { ref, reactive, defineComponent } from "vue";
import BotaoWhatsapp from "./components/BotaoWhatsapp.vue";

// --- Lógica da Galeria ---
// Substitua por suas próprias imagens. Use 'require' se as imagens estiverem locais (em /src/assets)
// Ex: { id: 1, url: require('@/assets/foto1.jpg'), alt: 'Descrição da Foto 1' }
const galleryImages = ref([
  {
    id: 1,
    url: require("@/assets/imagem-1.jpeg"),
    alt: "Descrição da Foto 1",
  },
  {
    id: 2,
    url: require("@/assets/imagem-2.jpeg"),
    alt: "Descrição da Foto 2",
  },
  {
    id: 3,
    url: require("@/assets/imagem-3.jpeg"),
    alt: "Descrição da Foto 3",
  },
  {
    id: 4,
    url: require("@/assets/imagem-4.jpeg"),
    alt: "Descrição da Foto 4",
  },
  {
    id: 5,
    url: require("@/assets/imagem-5.jpeg"),
    alt: "Descrição da Foto 5",
  },
  {
    id: 6,
    url: require("@/assets/imagem-6.jpeg"),
    alt: "Descrição da Foto 6",
  },
]);

// --- Lógica do Formulário ---
</script>

<style>
/* --- Reset Básico & Estilos Globais --- */
* {
  box-sizing: border-box;
  margin: 0;
  padding: 0;
}

:root {
  --primary-color: #2c3e50;
  --secondary-color: #3498db;
  --light-gray: #f4f4f4;
  --text-color: #333;
  --light-text: #fff;
}

html {
  scroll-behavior: smooth;
}

body {
  font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, Helvetica,
    Arial, sans-serif;
  line-height: 1.6;
  color: var(--text-color);
}

.container {
  max-width: 1100px;
  margin: 0 auto;
  padding: 0 2rem;
}

h1,
h2,
h3 {
  line-height: 1.2;
  margin-bottom: 1rem;
}

a {
  text-decoration: none;
  color: var(--secondary-color);
}

/* --- Componentes Reutilizáveis --- */
.content-section {
  padding: 4rem 0;
  text-align: center;
}

.bg-light {
  background-color: var(--light-gray);
}

.cta-button {
  display: inline-block;
  background-color: var(--secondary-color);
  color: var(--light-text);
  padding: 0.8rem 1.5rem;
  border-radius: 5px;
  font-weight: bold;
  transition: background-color 0.3s ease;
  border: none;
  cursor: pointer;
}

.cta-button:hover {
  background-color: #2980b9;
}

/* --- 1. Header & Navegação --- */
.navbar {
  background-color: rgba(44, 62, 80, 0.9);
  color: var(--light-text);
  padding: 1rem 0;
  position: fixed;
  width: 100%;
  top: 0;
  z-index: 1000;
  box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
}

.navbar .container {
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.navbar .logo {
  font-size: 1.5rem;
  font-weight: bold;
  color: var(--light-text);
}

.navbar nav ul {
  list-style: none;
  display: flex;
}

.navbar nav li {
  margin-left: 1.5rem;
}

.navbar nav a {
  color: var(--light-text);
  font-weight: bold;
  transition: color 0.3s ease;
}

.navbar nav a:hover {
  color: var(--secondary-color);
}

/* --- 2. Seção Hero --- */
.hero-section {
  min-height: 100vh;
  background-image: linear-gradient(rgba(0, 0, 0, 0.5), rgba(0, 0, 0, 0.5)),
    url("./assets/imagem-banner.jpeg");
  background-size: cover;
  background-position: center;
  color: var(--light-text);
  display: flex;
  flex-direction: column;
  justify-content: center;
  align-items: center;
  text-align: center;
  padding: 0 1rem;
}

.hero-content h1 {
  font-size: 3rem;
  margin-bottom: 1rem;
}

.hero-content p {
  font-size: 1.25rem;
  margin-bottom: 2rem;
}

/* --- 3. Seção Sobre --- */

#about p {
  max-width: 700px;
  margin: 0 auto;
}

/* --- 4. Seção Galeria --- */
.gallery-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
  gap: 1rem;
  margin-top: 2rem;
}

.gallery-item img {
  width: 100%;
  height: 250px;
  object-fit: cover;
  display: block;
  border-radius: 5px;
  transition: transform 0.3s ease, box-shadow 0.3s ease;
}

.gallery-item img:hover {
  transform: scale(1.05);
  box-shadow: 0 10px 20px rgba(0, 0, 0, 0.2);
}

/* --- 5. Seção Serviços --- */
.services-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(280px, 1fr));
  gap: 1.5rem;
  margin-top: 2rem;
}

.service-card {
  background: #fff;
  padding: 2rem;
  border-radius: 5px;
  box-shadow: 0 5px 15px rgba(0, 0, 0, 0.1);
  text-align: left;
}

.service-card h3 {
  color: var(--secondary-color);
}

/* --- 6. Seção Contato --- */
.contact-form {
  max-width: 600px;
  margin: 2rem auto 0;
  text-align: left;
}

.form-group {
  margin-bottom: 1.5rem;
}

.form-group label {
  display: block;
  margin-bottom: 0.5rem;
  font-weight: bold;
}

.form-group input,
.form-group textarea {
  width: 100%;
  padding: 0.8rem;
  border: 1px solid #ccc;
  border-radius: 5px;
  font-family: inherit;
}

.form-group textarea {
  resize: vertical;
}

.contact-form .cta-button {
  width: 100%;
  font-size: 1rem;
}

/* --- 7. Footer --- */
.footer {
  background-color: var(--primary-color);
  color: var(--light-text);
  text-align: center;
  padding: 2rem 0;
}

.social-links {
  margin-bottom: 1rem;
}

.social-links a {
  color: var(--light-text);
  margin: 0 0.5rem;
  font-size: 1.2rem;
  transition: color 0.3s ease;
}

.social-links a:hover {
  color: var(--secondary-color);
}

/* --- Responsividade --- */
@media (max-width: 768px) {
  .hero-content h1 {
    font-size: 2.2rem;
  }

  .navbar .container {
    flex-direction: column;
  }

  .navbar nav {
    margin-top: 0.5rem;
  }

  .navbar nav li {
    margin-left: 0.8rem;
  }
}
</style>
