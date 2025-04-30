<template>
    <div class="container">
      <h1>📄 CURRÍCULUM VITAE – Luis Angel Peña Zuñiga</h1>
      <div class="sub">Líder Técnico en Desarrollo de Software</div>
      <div class="sub">Especialista en Migraciones, Cloud Solutions y Biometría</div>
  
      <p class="contact">
        📍 Guadalajara, Jal. |
        📧 <a href="mailto:pezu.luis01@gmail.com">pezu.luis01@gmail.com</a> |
        📱 3328247811
      </p>
      <p class="contact">
        <a href="https://github.com/Craken420" target="_blank" class="icon-link github">
          <i class="fab fa-github fa-lg"></i> GitHub
        </a>
        <a href="https://www.linkedin.com/in/luis-angel-pe%C3%B1a-zu%C3%B1iga-707221188/" target="_blank" class="icon-link linkedin">
          <i class="fab fa-linkedin fa-lg"></i> LinkedIn
        </a>
        <a href="https://stackoverflow.com/users/10688370/luis-angel-pena-zuniga" target="_blank" class="icon-link stackoverflow">
          <i class="fab fa-stack-overflow fa-lg"></i> Stack Overflow
        </a>
      </p>
  
      <section v-for="(section, index) in sections" :key="index" class="section">
        <h2>{{ section.icon }} {{ section.title }}</h2>
        <template v-if="section.type === 'paragraph'">
          <p>{{ section.content }}</p>
        </template>
        <template v-else-if="section.type === 'list'">
          <ul>
            <li v-for="(item, i) in section.items" :key="i" v-html="item"></li>
          </ul>
        </template>
        <template v-else-if="section.type === 'projects'">
          <div class="project" v-for="(project, i) in section.projects" :key="i">
            <strong>{{ project.title }}:</strong> {{ project.description }}
          </div>
        </template>
      </section>
  
      <section>
        <h2>⚙️ Habilidades Técnicas</h2>
        <div class="skills-grid">
          <ul v-for="(group, i) in skills" :key="i">
            <li v-for="skill in group" :key="skill.name">
              <i :class="skill.icon"></i> {{ skill.name }}
            </li>
          </ul>
        </div>
      </section>
    </div>
  </template>
  
  <script setup>
  const sections = [
    {
      icon: '🧭',
      title: 'Perfil Profesional',
      type: 'paragraph',
      content:
        'Líder técnico con 7+ años de experiencia en desarrollo e integración de soluciones empresariales. Especializado en migraciones tecnológicas, arquitecturas híbridas on-premise/cloud, aplicaciones serverless, biometría y modernización de sistemas legacy. Capaz de estabilizar entornos críticos, liderar equipos multidisciplinarios y construir soluciones robustas en AWS y SAP.',
    },
    {
      icon: '🏆',
      title: 'Logros Relevantes',
      type: 'list',
      items: [
        '🔁 Migración completa de ERP Intelisis v3500 a v5000 y transición a SAP Business Application Studio, integrando CPIs y entornos híbridos.',
        '🧩 Arquitectura serverless multiruntime (Python + Node.js) con AWS Lambda, SAM CLI y API Gateway.',
        '🧠 Refactorización de SQL que redujo tiempos de consulta de horas a segundos.',
        '✋ Migración de sistema biométrico de C# con WebSocket a Node.js con librería nativa.',
        '🧰 Estabilización de apps en IIS y optimización de recursos y servicios externos.',
        '🚀 Ascenso a Líder Técnico liderando equipo de 6 personas en migración cloud.',
      ],
    },
    {
      icon: '📌',
      title: 'Proyectos Clave',
      type: 'projects',
      projects: [
        { title: 'Control de Huellas (.blop)', description: 'Reingeniería de solución C# a stack moderno (AWS + Node + Python + Vue + Postgres).' },
        { title: 'Infraestructura Biométrica', description: 'Gestión e integración de dispositivos en apps Windows/Web con soporte multi-dispositivo.' },
        { title: 'SAP-AWS Integration', description: 'Consumo de APIs SAP + CPIs + SQL/Postgres desde AWS vía Lambda.' },
        { title: 'Unificación de entornos Git', description: 'Consolidación y estabilización de entornos críticos en IIS.' },
      ],
    },
    {
      icon: '👥',
      title: 'Liderazgo y Gestión',
      type: 'list',
      items: [
        'Coordinación de equipos técnicos (hasta 6 personas).',
        'Estrategias de migración a la nube y modernización tecnológica.',
        'Organización de repositorios y control de versiones.',
      ],
    },
    {
      icon: '🌱',
      title: 'Soft Skills',
      type: 'list',
      items: [
        'Resolución de problemas complejos.',
        'Liderazgo técnico y mentoring.',
        'Comunicación inter-áreas y trato con proveedores.',
        'Trabajo bajo presión.',
        'Aprendizaje acelerado: "No lo sé, pero lo puedo aprender. No lo domino, pero lo puedo dominar."',
      ],
    },
    {
      icon: '🌐',
      title: 'Idiomas',
      type: 'list',
      items: ['Español: Nativo', 'Inglés: Intermedio – Lectura técnica fluida, comunicación funcional.'],
    },
    {
      icon: '💻',
      title: 'Contribuciones a la Comunidad',
      type: 'list',
      items: ['Proyectos y prácticas en GitHub.', 'Participación y soluciones en Stack Overflow.'],
    },
  ]
  
  const skills = [
    [
      { name: 'Python (avanzado)', icon: 'fab fa-python' },
      { name: 'Node.js', icon: 'fab fa-node-js' },
      { name: 'C# (experto)', icon: 'fas fa-code' },
      { name: 'JavaScript', icon: 'fab fa-js' },
      { name: 'SQL Server, PostgreSQL (avanzado)', icon: 'fas fa-database' },
    ],
    [
      { name: 'Vue.js', icon: 'fab fa-vuejs' },
      { name: 'Angular', icon: 'fab fa-angular' },
      { name: 'Delphi (migración)', icon: 'fas fa-retweet' },
      { name: 'FastAPI', icon: 'fas fa-rocket' },
      { name: 'Windows Forms, Web Forms', icon: 'fas fa-window-restore' },
    ],
    [
      { name: 'AWS Lambda, SAM CLI, API Gateway, Docker', icon: 'fab fa-aws' },
      { name: 'SAP HANA Cloud, SAP Business Application Studio, CPIs', icon: 'fas fa-cloud' },
      { name: 'IIS (migración, seguridad, tuning)', icon: 'fas fa-server' },
      { name: 'Git, CI/CD pipelines, serverless', icon: 'fab fa-git-alt' },
      { name: 'Integración: SAP + SQL Server + PostgreSQL', icon: 'fas fa-project-diagram' },
      { name: 'Biometría: U.are.U 4500/5300, migración C# a Node.js', icon: 'fas fa-fingerprint' },
    ],
  ]
  </script>
  
  <style scoped>
  @import url('https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.5.0/css/all.min.css');
  @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;600;700&display=swap');
  
  * {
    box-sizing: border-box;
    margin: 0;
    padding: 0;
  }
  
  body, .container {
    font-family: 'Inter', sans-serif;
    background: #f4f4f9;
    color: #333;
    padding: 20px;
    line-height: 1.6;
  }
  
  .container {
    max-width: 960px;
    margin: auto;
    background: white;
    padding: 40px;
    border-radius: 16px;
    box-shadow: 0 4px 20px rgba(0,0,0,0.1);
  }
  
  h1 {
    font-size: 28px;
    font-weight: 700;
    margin-bottom: 5px;
  }
  
  h2 {
    font-size: 20px;
    color: #2c3e50;
    border-bottom: 2px solid #ddd;
    margin-top: 30px;
    padding-bottom: 5px;
  }
  
  .sub {
    font-weight: 600;
    color: #555;
  }
  
  .contact {
    font-size: 14px;
    margin: 10px 0 20px;
    color: #555;
  }
  
  .icon-link {
    margin-right: 15px;
    text-decoration: none;
  }
  
  .github {
    color: #333;
  }
  .linkedin {
    color: #0e76a8;
  }
  .stackoverflow {
    color: #f48024;
  }
  
  .section {
    margin-top: 25px;
  }
  
  .skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(240px, 1fr));
    gap: 16px;
    margin-top: 10px;
  }
  
  ul {
    list-style: disc;
    padding-left: 20px;
  }
  
  .project {
    margin-bottom: 10px;
  }
  </style>
  