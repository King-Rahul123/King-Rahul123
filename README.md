<!-- Glossy Animated Background -->
<?xml version="1.0" encoding="utf-8"?>
<svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 1400 360" preserveAspectRatio="xMidYMid slice">
  <defs>
    <!-- Color palette -->
    <linearGradient id="mainGrad" x1="0" x2="1">
      <stop offset="0" stop-color="#ff7a59"/>
      <stop offset="0.45" stop-color="#ff4b1f"/>
      <stop offset="1" stop-color="#1fddff"/>
    </linearGradient>

    <!-- Back depth gradient -->
    <radialGradient id="vignette" cx="50%" cy="35%" r="80%">
      <stop offset="0%" stop-color="#000" stop-opacity="0"/>
      <stop offset="100%" stop-color="#000" stop-opacity="0.22"/>
    </radialGradient>

    <!-- Soft glossy highlight -->
    <linearGradient id="glossStrip" x1="0" x2="1">
      <stop offset="0" stop-color="#ffffff" stop-opacity="0.0"/>
      <stop offset="0.35" stop-color="#ffffff" stop-opacity="0.18"/>
      <stop offset="0.66" stop-color="#ffffff" stop-opacity="0.05"/>
      <stop offset="1" stop-color="#ffffff" stop-opacity="0.0"/>
    </linearGradient>

    <!-- Bevel to simulate 3D edge -->
    <linearGradient id="bevel" x1="0" x2="0" y1="0" y2="1">
      <stop offset="0" stop-color="#ffffff" stop-opacity="0.14"/>
      <stop offset="0.55" stop-color="#000000" stop-opacity="0.06"/>
      <stop offset="1" stop-color="#000000" stop-opacity="0.12"/>
    </linearGradient>

    <!-- Blur + screen blend for gloss -->
    <filter id="softBlur" x="-50%" y="-50%" width="200%" height="200%">
      <feGaussianBlur stdDeviation="30" result="b"/>
      <feBlend in="SourceGraphic" in2="b" mode="screen"/>
    </filter>

    <!-- Subtle inner glow -->
    <filter id="innerGlow" x="-50%" y="-50%" width="200%" height="200%">
      <feGaussianBlur stdDeviation="12" result="g"/>
      <feComposite in="g" in2="SourceAlpha" operator="in" result="shine"/>
      <feMerge>
        <feMergeNode in="shine"/>
        <feMergeNode in="SourceGraphic"/>
      </feMerge>
    </filter>

    <!-- Animated shimmer mask -->
    <linearGradient id="shimmer" x1="0" x2="1">
      <stop offset="0" stop-color="#ffffff" stop-opacity="0"/>
      <stop offset="0.5" stop-color="#ffffff" stop-opacity="0.6"/>
      <stop offset="1" stop-color="#ffffff" stop-opacity="0"/>
    </linearGradient>

    <clipPath id="roundedClip">
      <rect x="24" y="20" rx="22" ry="22" width="1352" height="320"/>
    </clipPath>

    <!-- Tiny floating circles used for parallax -->
    <g id="bubble">
      <circle r="30" fill="#fff" opacity="0.08"/>
    </g>
  </defs>

  <!-- Outer background (animated gradient base) -->
  <rect width="1400" height="360" fill="url(#mainGrad)"/>

  <!-- Layered soft shapes for subtle depth -->
  <g opacity="0.14">
    <ellipse cx="300" cy="220" rx="380" ry="120" fill="#000" />
    <ellipse cx="1100" cy="120" rx="320" ry="90" fill="#000" />
  </g>

  <!-- Main glossy panel (rounded) -->
  <g clip-path="url(#roundedClip)">
    <!-- base glossy plate -->
    <rect x="24" y="20" rx="22" ry="22" width="1352" height="320" fill="url(#mainGrad)"/>

    <!-- inner soft shadow to suggest depth -->
    <rect x="24" y="20" rx="22" ry="22" width="1352" height="320" fill="black" opacity="0.06"/>

    <!-- subtle bevel -->
    <rect x="24" y="20" rx="22" ry="22" width="1352" height="320" fill="url(#bevel)" opacity="0.5"/>

    <!-- blurred glossy overlay -->
    <rect x="24" y="20" rx="22" ry="22" width="1352" height="320" fill="url(#glossStrip)" filter="url(#softBlur)" opacity="0.9"/>

    <!-- animated shimmering light passing -->
    <rect x="-500" y="-60" width="600" height="480" transform="rotate(-18)" fill="url(#shimmer)" opacity="0.65">
      <animate attributeName="x" dur="8.6s" values="-500;1400" repeatCount="indefinite"/>
      <animate attributeName="opacity" dur="4.3s" values="0.42;0.78;0.42" repeatCount="indefinite"/>
    </rect>

    <!-- additional thinner highlight -->
    <rect x="-500" y="10" width="420" height="200" transform="rotate(-10)" fill="url(#shimmer)" opacity="0.35">
      <animate attributeName="x" dur="12s" values="-500;1600" repeatCount="indefinite"/>
      <animate attributeName="y" dur="10s" values="10;40;10" repeatCount="indefinite"/>
    </rect>

    <!-- floating bubbles (parallax) -->
    <g opacity="0.12" transform="translate(0,0)">
      <use href="#bubble" x="120" y="60">
        <animateTransform attributeName="transform" attributeType="XML" type="translate"
          values="0 0; 180 -12; 0 0" dur="14s" repeatCount="indefinite"/>
      </use>
      <use href="#bubble" x="420" y="120">
        <animateTransform attributeName="transform" attributeType="XML" type="translate"
          values="0 0; -120 18; 0 0" dur="11s" repeatCount="indefinite"/>
        <animate attributeName="opacity" values="0.06;0.14;0.06" dur="9s" repeatCount="indefinite"/>
      </use>
      <use href="#bubble" x="980" y="40">
        <animateTransform attributeName="transform" attributeType="XML" type="translate"
          values="0 0; 200 30; 0 0" dur="18s" repeatCount="indefinite"/>
      </use>
      <use href="#bubble" x="1180" y="180" transform="scale(0.9)">
        <animateTransform attributeName="transform" attributeType="XML" type="translate"
          values="0 0; -240 -18; 0 0" dur="16s" repeatCount="indefinite"/>
      </use>
    </g>

    <!-- soft inner vignette for focus -->
    <rect x="24" y="20" rx="22" ry="22" width="1352" height="320" fill="url(#vignette)"/>

  </g>

  <!-- Text content — centered and styled -->
  <g transform="translate(0,0)">
    <text x="70" y="120" font-family="Poppins, Segoe UI, Roboto, sans-serif" font-size="34" fill="#ffffff" font-weight="700" letter-spacing="0.2">
      Rahul Kumar Adak
    </text>

    <text x="70" y="160" font-family="Inter, Roboto, sans-serif" font-size="18" fill="#ffffff" opacity="0.95">
      🚀 Full Stack Developer · MERN Enthusiast · Open Source Contributor
    </text>

    <!-- thin divider -->
    <rect x="70" y="172" width="540" height="1" fill="#ffffff" opacity="0.06"/>
    <!-- short tagline -->
    <text x="70" y="200" font-family="Inter, Roboto, sans-serif" font-size="14" fill="#ffffff" opacity="0.9">
      Building modern dashboards, web apps & delightful user experiences.
    </text>
  </g>

  <!-- small footer gloss / reflection at bottom right -->
  <g transform="translate(0,0)" opacity="0.22">
    <ellipse cx="1120" cy="300" rx="210" ry="36" fill="#ffffff">
      <animate attributeName="rx" values="210;220;210" dur="12s" repeatCount="indefinite"/>
    </ellipse>
  </g>

</svg>

<!-- Header Banner -->
<img src="https://capsule-render.vercel.app/api?type=waving&color=0:ff4b1f,100:1fddff&height=180&section=header&text=Rahul%20Kumar%20Adak&fontSize=45&fontColor=ffffff&animation=fadeIn&fontAlignY=35" width="100%"/>

<h3 align="center">🚀 Full Stack Developer | MERN Enthusiast | Open Source Contributor</h3>

---

## 🌟 About Me  
💡 Passionate about building **modern dashboards, web apps, and open-source projects**  
🌱 Currently mastering **React, Node.js, MongoDB, TailwindCSS**  
⚡ Fun fact: I love solving problems with clean UI + smart backend  
📫 Reach me at: **your email here**  

---

## 🔧 Tech Stack  

<p align="center">
  <!-- Frontend -->
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/react/react-original.svg" alt="React" width="50" height="50"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg" alt="HTML5" width="50" height="50"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg" alt="CSS3" width="50" height="50"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg" alt="JavaScript" width="50" height="50"/>
  
  <!-- Backend -->
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nodejs/nodejs-original.svg" alt="Node.js" width="50" height="50"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/express/express-original.svg" alt="Express.js" width="50" height="50" style="background-color:white; padding:5px; border-radius:8px;"/>
  <img src="https://www.svgrepo.com/show/353657/django-icon.svg" alt="Django" width="50" height="50" />

  <!-- Database -->
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/mongodb/mongodb-original.svg" alt="MongoDB" width="50" height="50"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/firebase/firebase-plain.svg" alt="Firebase" width="50" height="50"/>
  
  <!-- Languages -->
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/python/python-original.svg" alt="Python" width="50" height="50"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/c/c-original.svg" alt="C" width="50" height="50"/>
  
  <!-- Tools -->
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/git/git-original.svg" alt="Git" width="50" height="50"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/github/github-original.svg" alt="GitHub" width="50" height="50" style="background-color:white; padding:5px; border-radius:8px;"/>
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/vscode/vscode-original.svg" alt="VS Code" width="50" height="50"/>
</p>

---

## 📊 GitHub Analytics  

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api?username=rahuladak&show_icons=true&theme=radical&hide_border=true" height="160px"/>
  <img src="https://github-readme-streak-stats.herokuapp.com/?user=rahuladak&theme=radical&hide_border=true" height="160px"/>
</p>

<p align="center">
  <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=rahuladak&layout=compact&theme=radical&hide_border=true" height="160px"/>
</p>

---

## 🚀 Featured Projects  

- 📌 [Premium Dashboard](https://github.com/rahuladak/dashboard)  
- 🎬 [Movie Script Generator](https://github.com/rahuladak/movie-script)  
- 🌐 [Portfolio Hub](https://github.com/King-Rahul123/Portfolio-Hub.git)  

---

## 🌐 Connect with Me  

<p align="center">
  <a href="https://www.linkedin.com/in/rahul-adak-b93463303?utm_source=share&utm_campaign=share_via&utm_content=profile&utm_medium=android_app"><img src="https://img.shields.io/badge/LinkedIn-blue?logo=linkedin&logoColor=white&style=for-the-badge"></a>
  <a href="mailto:adakrahul123@gmail.com"><img src="https://img.shields.io/badge/Email-D14836?logo=gmail&logoColor=white&style=for-the-badge"></a>
  <a href="https://your-portfolio-link"><img src="https://img.shields.io/badge/Portfolio-24292f?logo=githubpages&logoColor=white&style=for-the-badge"></a>
</p>

---

<!-- Footer Banner -->
<img src="https://capsule-render.vercel.app/api?type=waving&color=0:1fddff,100:ff4b1f&height=120&section=footer" width="100%"/>
