

<script setup>

import { projets } from './data/projets.js'

const competences = [
  { nom: 'HTML5', categorie: 'Front-end' },
  { nom: 'CSS3', categorie: 'Front-end' },
  { nom: 'JavaScript', categorie: 'Front-end' },
  { nom: 'Vue.js', categorie: 'Framework front-end' },
  { nom: 'PHP', categorie: 'Back-end' },
  { nom: 'Laravel', categorie: 'Framework back-end' },
  { nom: 'SQLite', categorie: 'Base de données' },
  { nom: 'Git', categorie: 'Gestion de versions' },
  { nom: 'GitHub', categorie: 'Gestion de versions' },
  { nom: 'Vercel', categorie: 'Hébergement et déploiement' },
  { nom: 'Render', categorie: 'Hébergement et déploiement' },
  { nom: 'o2switch', categorie: 'Hébergement web' },
  { nom: 'WordPress', categorie: 'CMS' },
]


</script>

<template>
  <header class="header">
    <nav class="navbar">
      <a href="#" class="logo">Cedrick<span>.dev</span></a>

      <ul class="menu">
        <li><a href="#accueil">Accueil</a></li>
        <li><a href="#apropos">À propos</a></li>
        <li><a href="#competences">Compétences</a></li>
        <li><a href="#projets">Projets</a></li>
        <li><a href="#contact">Contact</a></li>
      </ul>
    </nav>
  </header>

  <main>
    <section id="accueil" class="hero">
      <div class="hero-content">
        <p class="intro">Bonjour, je suis</p>

        <h1>Cedrick Fotso</h1>

        <h2>Développeur web junior</h2>

        <p class="description">
          Étudiant en BES Webdeveloper, je conçois et développe des sites et applications web
          modernes. Découvrez mes projets et mon évolution dans le développement web.
        </p>

        <div class="hero-buttons">
          <a href="#projets" class="btn-primary">Voir mes projets</a>
          <a href="#contact" class="btn-secondary">Me contacter</a>
        </div>
      </div>
    </section>

    <section id="apropos" class="about">
      <div class="about-container">
        <h2>À propos de moi</h2>

        <p class="about-subtitle">
          Découvrez mon parcours et ma passion pour le développement web.
        </p>

        <div class="about-content">
          <h3>Mon parcours</h3>

          <p>
            Actuellement étudiant en BES Webdeveloper, je développe mes compétences dans la création
            de sites internet et d'applications web.
          </p>

          <p>
            Au fil de ma formation, j'ai évolué de la réalisation de sites HTML/CSS vers le
            développement d'applications utilisant JavaScript, Vue.js, PHP et Laravel.
          </p>

          <p>
            Je recherche actuellement un stage en développement web afin de mettre mes connaissances
            en pratique, découvrir le fonctionnement d'une équipe professionnelle et continuer à
            progresser.
          </p>
        </div>
      </div>
    </section>


<section id="competences" class="skills">
  <div class="skills-container">
    <h2>Mes compétences</h2>

    <p class="skills-subtitle">
      Les technologies et outils que j'utilise pour développer
      et déployer mes projets web.
    </p>

    <div class="skills-grid">
      <div
        v-for="competence in competences"
        :key="competence.nom"
        class="skill-card"
      >
        <h3>{{ competence.nom }}</h3>
        <p>{{ competence.categorie }}</p>
      </div>
    </div>
  </div>
</section>


<section id="projets" class="projects">
  <div class="projects-container">
    <h2>Mes projets</h2>

    <p class="projects-subtitle">
      Découvrez mes réalisations et mon évolution
      dans le développement web.
    </p>

    <div class="projects-grid">
      <article
        v-for="projet in projets"
        :key="projet.id"
        class="project-card"
      >
        <h3>{{ projet.titre }}</h3>

        <p class="project-description">
          {{ projet.description }}
        </p>

        <div class="project-technologies">
          <span
            v-for="technologie in projet.technologies"
            :key="technologie"
          >
            {{ technologie }}
          </span>
        </div>

        <div class="project-links">
          <a :href="projet.github" target="_blank" rel="noopener noreferrer">
            GitHub
          </a>

          <a :href="projet.demo" target="_blank" rel="noopener noreferrer">
            Voir le site
          </a>
        </div>
      </article>
    </div>
  </div>
</section>


  </main>
</template>

<style scoped>
.header {
  background-color: white;
  border-bottom: 1px solid #e5e7eb;
}

.navbar {
  max-width: 1200px;
  margin: auto;
  padding: 24px;
  display: flex;
  justify-content: space-between;
  align-items: center;
}

.logo {
  font-size: 26px;
  font-weight: bold;
  color: #111827;
  text-decoration: none;
}

.logo span {
  color: #2563eb;
}

.menu {
  display: flex;
  gap: 30px;
  list-style: none;
}

.menu a {
  text-decoration: none;
  color: #374151;
  font-weight: 500;
}

.menu a:hover {
  color: #2563eb;
}

.hero {
  min-height: 85vh;
  display: flex;
  align-items: center;
  justify-content: center;
  padding: 80px 24px;
  background-color: #f8fafc;
}

.hero-content {
  max-width: 800px;
  text-align: center;
}

.intro {
  font-size: 20px;
  color: #2563eb;
  font-weight: 600;
}

.hero h1 {
  font-size: 56px;
  color: #111827;
  margin: 16px 0;
}

.hero h2 {
  font-size: 28px;
  color: #475569;
  margin-bottom: 24px;
}

.description {
  font-size: 18px;
  line-height: 1.8;
  color: #64748b;
  margin-bottom: 36px;
}

.hero-buttons {
  display: flex;
  justify-content: center;
  gap: 16px;
}

.btn-primary,
.btn-secondary {
  padding: 14px 28px;
  border-radius: 8px;
  text-decoration: none;
  font-weight: 600;
}

.btn-primary {
  background-color: #2563eb;
  color: white;
}

.btn-secondary {
  border: 2px solid #2563eb;
  color: #2563eb;
}

.btn-primary:hover {
  background-color: #1d4ed8;
}

.btn-secondary:hover {
  background-color: #eff6ff;
}

.about {
  padding: 100px 24px;
  background-color: white;
}

.about-container {
  max-width: 1000px;
  margin: 0 auto;
}

.about h2 {
  font-size: 36px;
  text-align: center;
  color: #111827;
  margin-bottom: 16px;
}

.about-subtitle {
  text-align: center;
  color: #64748b;
  font-size: 18px;
  margin-bottom: 50px;
}

.about-content {
  max-width: 800px;
  margin: 0 auto;
}

.about-content h3 {
  font-size: 24px;
  color: #2563eb;
  margin-bottom: 20px;
}

.about-content p {
  font-size: 17px;
  line-height: 1.9;
  color: #475569;
  margin-bottom: 20px;
}


.skills {
  padding: 100px 24px;
  background-color: #f8fafc;
}

.skills-container {
  max-width: 1100px;
  margin: 0 auto;
}

.skills h2 {
  font-size: 36px;
  text-align: center;
  color: #111827;
  margin-bottom: 16px;
}

.skills-subtitle {
  text-align: center;
  color: #64748b;
  font-size: 18px;
  margin-bottom: 50px;
}

.skills-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
  gap: 24px;
}

.skill-card {
  background-color: white;
  padding: 30px 20px;
  border-radius: 12px;
  text-align: center;
  border: 1px solid #e5e7eb;
  transition: transform 0.3s ease;
}

.skill-card:hover {
  transform: translateY(-5px);
  box-shadow: 0 8px 20px rgba(0, 0, 0, 0.06);
}

.skill-card h3 {
  color: #2563eb;
  font-size: 22px;
  margin-bottom: 12px;
}

.skill-card p {
  color: #64748b;
  font-size: 14px;
}

/* Adaptation aux petits écrans */
@media (max-width: 600px) {
  .skills {
    padding: 60px 20px;
  }

  .skills h2 {
    font-size: 28px;
  }

  .skills-subtitle {
    font-size: 16px;
  }

  .skills-grid {
    grid-template-columns: 1fr;
    gap: 16px;
  }
}


.projects {
  padding: 100px 24px;
  background-color: white;
}

.projects-container {
  max-width: 1100px;
  margin: 0 auto;
}

.projects h2 {
  font-size: 36px;
  color: #111827;
  text-align: center;
  margin-bottom: 16px;
}

.projects-subtitle {
  text-align: center;
  font-size: 18px;
  color: #64748b;
  margin-bottom: 50px;
}

.projects-grid {
  display: grid;
  grid-template-columns: repeat(auto-fit, minmax(260px, 1fr));
  gap: 24px;
}

.project-card {
  border: 1px solid #e5e7eb;
  border-radius: 12px;
  padding: 28px;
  background-color: #ffffff;
  display: flex;
  flex-direction: column;
  gap: 18px;
}

.project-card h3 {
  font-size: 23px;
  color: #111827;
}

.project-description {
  color: #64748b;
  line-height: 1.7;
}

.project-technologies {
  display: flex;
  flex-wrap: wrap;
  gap: 8px;
}

.project-technologies span {
  background-color: #eff6ff;
  color: #2563eb;
  padding: 6px 12px;
  border-radius: 20px;
  font-size: 13px;
}

.project-links {
  display: flex;
  gap: 12px;
  margin-top: auto;
}

.project-links a {
  padding: 10px 16px;
  border-radius: 8px;
  background-color: #2563eb;
  color: white;
  text-decoration: none;
  font-size: 14px;
}

.project-links a:hover {
  background-color: #1d4ed8;
}


</style>
