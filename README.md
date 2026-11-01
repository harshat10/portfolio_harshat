# Ex01 Portfolio
## Date:
### AIM
To create a Portfolio using HTML and CSS.

### ALGORITHM
#### STEP 1
Create an HTML file (index.html)

#### STEP 2
Create a CSS file (style.css)

#### STEP 3
Include a navigation bar with links to different sections.

#### STEP 4
Add structured sections for introduction, about, projects, and contact details.

#### STEP 5
Define global styles for fonts, colors, and layout.

#### STEP 6
Style the header, navigation bar, and sections.

#### STEP 7
Use Flexbox or CSS Grid for layout design.

#### STEP 8
Add hover effects and transitions for interactivity.

#### STEP 9
Add Images and Media.

#### STEP 10
Use optimized images for a professional look.

#### STEP 11
Open the HTML file in a browser to check layout and functionality.

#### STEP 12
Fix styling issues and refine content placement.

#### STEP 13
Deploy the Portfolio.

#### STEP 14
Upload to GitHub Pages for free hosting.

### PROGRAM
```
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <meta name="description" content="Harshat's personal portfolio — Computer Science Engineering, songwriting, music composition and production.">
  <title>Harshat | Personal Portfolio</title>
  <style>
    *{margin:0;padding:0;box-sizing:border-box;scroll-behavior:smooth}
    :root{--primary:#ff0000;--secondary:#00c8ff;--accent:#ffbd59;--background:#f8f8ff;--surface:#fff;--text:#25243a;--muted:#73738a;--border:#e9e7f5;--shadow:0 12px 35px rgba(61,47,120,.09)}
    body{font-family:Arial,Helvetica,sans-serif;background:var(--background);color:var(--text);line-height:1.7}
    a{text-decoration:none;color:inherit}img{max-width:100%;display:block}
    .container{width:min(1120px,90%);margin:auto}
    header{position:sticky;top:0;z-index:1000;background:rgba(255,255,255,.92);backdrop-filter:blur(14px);border-bottom:1px solid var(--border)}
    nav{min-height:76px;display:flex;justify-content:space-between;align-items:center;gap:25px}
    .logo{font-size:1.5rem;font-weight:800;color:var(--primary)}.logo span{color:var(--secondary)}
    .nav-links{display:flex;align-items:center;gap:25px;list-style:none}
    .nav-links a{font-size:.92rem;font-weight:600;transition:color .3s}.nav-links a:hover{color:var(--primary)}
    .menu-button{display:none;border:none;background:var(--primary);color:white;padding:10px 13px;border-radius:10px;font-size:1.2rem;cursor:pointer}
    .hero{min-height:88vh;display:grid;grid-template-columns:1.2fr .8fr;align-items:center;gap:60px;padding:75px 0}
    .eyebrow{display:inline-block;background:#eeeaff;color:var(--primary);padding:8px 15px;border-radius:30px;font-size:.85rem;font-weight:700;margin-bottom:22px}
    .hero h1{font-size:clamp(2.8rem,6vw,5rem);line-height:1.12;letter-spacing:-2px;margin-bottom:20px}
    .hero h1 span{color:var(--primary)}
    .hero p{max-width:580px;color:var(--muted);font-size:1.08rem;margin-bottom:28px}
    .button-group{display:flex;flex-wrap:wrap;gap:14px}
    .button{display:inline-block;padding:13px 22px;border-radius:12px;font-weight:700;transition:.3s;border:2px solid transparent;cursor:pointer}
    .button-primary{background:var(--primary);color:white}.button-primary:hover{background:#5a3ee0;transform:translateY(-3px)}
    .button-outline{border-color:var(--border);background:white}.button-outline:hover{border-color:var(--primary);color:var(--primary);transform:translateY(-3px)}
    .hero-image{position:relative;display:flex;justify-content:center;align-items:center}
    .image-background{width:min(360px,100%);aspect-ratio:1;border-radius:45% 55% 55% 45% / 45% 45% 55% 55%;background:linear-gradient(135deg,#d9d0ff,#ffd6e2,#ffe9bd);display:flex;justify-content:center;align-items:center;padding:15px;box-shadow:var(--shadow)}
    .image-background img{width:100%;height:100%;object-fit:cover;border-radius:inherit;border:5px solid white}
    .image-placeholder{width:100%;height:100%;border-radius:inherit;display:flex;align-items:center;justify-content:center;flex-direction:column;background:linear-gradient(135deg,#7357ff,#ff719a);color:white;text-align:center;padding:20px}
    .image-placeholder span{font-size:5rem}.image-placeholder p{color:white;font-weight:700;margin:0}
    .floating-card{position:absolute;background:white;padding:13px 18px;border-radius:15px;box-shadow:var(--shadow);font-weight:700;font-size:.9rem}
    .floating-one{top:12%;left:-8%}.floating-two{bottom:12%;right:-7%}
    section{padding:85px 0;scroll-margin-top:75px}
    .section-heading{text-align:center;margin-bottom:45px}
    .section-heading span{color:var(--primary);font-size:.85rem;font-weight:800;text-transform:uppercase;letter-spacing:2px}
    .section-heading h2{font-size:clamp(2rem,4vw,3rem);margin:8px 0}
    .section-heading p{color:var(--muted);max-width:620px;margin:auto}
    .about-grid{display:grid;grid-template-columns:1fr 1fr;gap:35px;align-items:stretch}
    .about-card,.info-card,.skill-card,.project-card,.education-card,.goal-card,.contact-card,.achievement{background:var(--surface);border:1px solid var(--border);border-radius:22px;padding:30px;box-shadow:var(--shadow)}
    .about-card h3,.info-card h3{font-size:1.35rem;margin-bottom:15px}
    .about-card p,.info-card p{color:var(--muted);margin-bottom:15px}
    .info-list{list-style:none}.info-list li{display:flex;justify-content:space-between;gap:20px;padding:12px 0;border-bottom:1px solid var(--border)}
    .info-list li:last-child{border-bottom:none}.info-list strong{color:var(--text)}.info-list span{color:var(--muted);text-align:right}
    .skills-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:22px}
    .skill-card{transition:transform .3s,border-color .3s}.skill-card:hover,.project-card:hover,.education-card:hover{transform:translateY(-6px);border-color:#c9beff}
    .skill-icon{width:55px;height:55px;display:grid;place-items:center;border-radius:16px;background:#eeeaff;font-size:1.7rem;margin-bottom:18px}
    .skill-card:nth-child(2) .skill-icon{background:#ffe6ed}.skill-card:nth-child(3) .skill-icon{background:#fff0d7}
    .skill-card h3{margin-bottom:10px}.skill-card p{color:var(--muted);font-size:.95rem}
    .skill-tags{display:flex;flex-wrap:wrap;gap:8px;margin-top:16px}
    .tag{padding:6px 11px;border-radius:20px;background:#f1efff;color:#5944c7;font-size:.78rem;font-weight:700}
    .education-list{display:grid;gap:20px;max-width:850px;margin:auto}
    .education-card{display:flex;gap:22px;align-items:flex-start;transition:.3s}
    .education-icon{min-width:55px;height:55px;display:grid;place-items:center;background:#eeeaff;border-radius:16px;font-size:1.6rem}
    .education-card h3{margin-bottom:5px}.education-card h4{color:var(--primary);font-size:.95rem;margin-bottom:7px}.education-card p{color:var(--muted)}
    .education-date{display:inline-block;color:var(--muted);font-size:.82rem;margin-top:8px}
    .projects-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:25px}
    .project-card{overflow:hidden;transition:.3s}
    .project-visual{min-height:190px;border-radius:16px;display:grid;place-items:center;font-size:4rem;margin-bottom:22px;background:linear-gradient(135deg,#e7e1ff,#fce0ea)}
    .project-card:nth-child(2) .project-visual{background:linear-gradient(135deg,#d9f7ed,#dce8ff)}
    .project-card:nth-child(3) .project-visual{background:linear-gradient(135deg,#fff0d8,#ffe0e6)}
    .project-card:nth-child(4) .project-visual{background:linear-gradient(135deg,#dce8ff,#e7e1ff)}
    .project-card h3{font-size:1.3rem;margin-bottom:10px}.project-card p{color:var(--muted);margin-bottom:18px}
    .achievements-grid{display:grid;grid-template-columns:repeat(3,1fr);gap:22px}
    .achievement{text-align:center;padding:25px}.achievement span{font-size:2.3rem}.achievement h3{margin:12px 0 8px}.achievement p{color:var(--muted);font-size:.93rem}
    .interests{display:flex;justify-content:center;flex-wrap:wrap;gap:14px}
    .interest{padding:14px 20px;background:white;border:1px solid var(--border);border-radius:30px;font-weight:700;box-shadow:var(--shadow)}
    .goals-grid{display:grid;grid-template-columns:repeat(2,1fr);gap:24px}.goal-card h3{margin-bottom:12px}.goal-card p{color:var(--muted)}
    .goal-card:first-child{border-top:5px solid var(--primary)}.goal-card:last-child{border-top:5px solid var(--secondary)}
    .contact-wrapper{display:grid;grid-template-columns:.9fr 1.1fr;gap:30px}
    .contact-card h3{font-size:1.4rem;margin-bottom:15px}.contact-card p{color:var(--muted);margin-bottom:18px}
    .contact-detail{padding:14px 0;border-bottom:1px solid var(--border);overflow-wrap:anywhere}.contact-detail:last-child{border-bottom:none}
    .contact-detail strong{display:block;margin-bottom:3px}.contact-detail a{color:var(--primary)}
    .contact-form{display:grid;gap:15px}.contact-form label{font-weight:700;font-size:.9rem}
    .contact-form input,.contact-form textarea{width:100%;padding:13px 15px;margin-top:6px;border:1px solid var(--border);border-radius:11px;font:inherit;outline:none;background:#fcfbff}
    .contact-form input:focus,.contact-form textarea:focus{border-color:var(--primary)}.contact-form textarea{min-height:125px;resize:vertical}
    footer{padding:28px 0;background:#24213b;color:white;text-align:center}footer p{color:#d1cde4;font-size:.9rem}footer a{color:#c6baff}
    @media(max-width:850px){.nav-links{gap:14px}.hero{gap:35px}.skills-grid,.achievements-grid{grid-template-columns:repeat(2,1fr)}.floating-one{left:0}.floating-two{right:0}}
    @media(max-width:650px){
      .menu-button{display:block}
      .nav-links{display:none;position:absolute;top:76px;left:0;width:100%;background:white;padding:20px 5%;flex-direction:column;align-items:flex-start;border-bottom:1px solid var(--border)}
      .nav-links.active{display:flex}.hero{grid-template-columns:1fr;text-align:center;padding:60px 0}
      .hero p{margin-left:auto;margin-right:auto}.button-group{justify-content:center}.hero-image{grid-row:1;margin-bottom:15px}
      .image-background{width:270px}.floating-one{left:2%}.floating-two{right:2%}
      .about-grid,.skills-grid,.projects-grid,.achievements-grid,.goals-grid,.contact-wrapper{grid-template-columns:1fr}
      section{padding:65px 0}.about-card,.info-card,.skill-card,.project-card,.education-card,.goal-card,.contact-card{padding:23px}
      .info-list li{flex-direction:column;gap:3px}.info-list span{text-align:left}.education-card{gap:15px}.section-heading{margin-bottom:30px}
    }
  </style>
</head>
<body>
  <header>
    <nav class="container" aria-label="Main navigation">
      <a href="#home" class="logo">Harshat<span>.</span></a>
      <button class="menu-button" id="menuButton" aria-label="Toggle navigation" aria-expanded="false">☰</button>
      <ul class="nav-links" id="navLinks">
        <li><a href="#home">Home</a></li><li><a href="#about">About</a></li>
        <li><a href="#education">Education</a></li><li><a href="#skills">Skills</a></li>
        <li><a href="#projects">Projects</a></li><li><a href="#contact">Contact</a></li>
      </ul>
    </nav>
  </header>

  <main>
    <section class="container hero" id="home">
      <div class="hero-content">
        <span class="eyebrow">WELCOME TO MY PORTFOLIO</span>
        <h1>Hi, I'm <span>Harshat</span></h1>
        <p>
          A Computer Science Engineering student, songwriter, and aspiring music director
          passionate about Tamil music, music production, and technology. I enjoy turning
          creative ideas into original music while building my skills in software and computing.
        </p>
        <div class="button-group">
          <a href="#projects" class="button button-primary">Explore My Work →</a>
          <a href="#contact" class="button button-outline">Contact Me</a>
        </div>
      </div>
      <div class="hero-image">
        <div class="image-background">
          <!-- Replace profile.jpg with your own photograph -->
          <img src="Harshat.jpg" alt="Portrait of Harshat"
               onerror="this.style.display='none'; this.nextElementSibling.style.display='flex';">
          <div class="image-placeholder" style="display:none;">
            <span>🎧</span><p>Add your photo as profile.jpg</p>
          </div>
        </div>
        <div class="floating-card floating-one">♫ Songwriter</div>
        <div class="floating-card floating-two">⌘ Computer Science</div>
      </div>
    </section>

    <section id="about">
      <div class="container">
        <div class="section-heading">
          <span>About Me</span><h2>Creativity meets technology.</h2>
          <p>Building my future through computer science, songwriting, and music production.</p>
        </div>
        <div class="about-grid">
          <article class="about-card">
            <h3>My Story</h3>
            <p>
              I'm Harshat, a Computer Science Engineering student with a strong passion for
              songwriting, composing, and producing music. I enjoy exploring melodies, rhythms,
              sound design, and the process of turning an idea into a complete song.
            </p>
            <p>
              Inspired by Tamil film music and the storytelling power of background scores,
              my long-term ambition is to become a music director. Alongside music, I'm developing
              my technical skills and exploring how software and AI can support creative work.
            </p>
          </article>
          <aside class="info-card">
            <h3>Personal Profile</h3>
            <ul class="info-list">
              <li><strong>Name</strong><span>Harshat</span></li>
              <li><strong>Department</strong><span>Computer Science Engineering</span></li>
              <li><strong>Creative Focus</strong><span>Songwriting & Composition</span></li>
              <li><strong>Production Interest</strong><span>Mixing, Mastering & Sound Design</span></li>
              <li><strong>Career Goal</strong><span>Music Director</span></li>
            </ul>
          </aside>
        </div>
      </div>
    </section>

    <section id="education">
      <div class="container">
        <div class="section-heading">
          <span>Education</span><h2>My learning journey.</h2>
          <p>Building a strong foundation in computing while continuing to grow as a musician.</p>
        </div>
        <div class="education-list">
          <article class="education-card">
            <div class="education-icon">🎓</div>
            <div>
              <h3>Bachelor's Degree in Computer Science Engineering</h3>
              <h4>Computer Science Engineering (CSE)</h4>
              <p>Developing knowledge in programming, software development, problem-solving, and emerging technologies.</p>
              <span class="education-date">Currently pursuing</span>
            </div>
          </article>
          <article class="education-card">
            <div class="education-icon">🎹</div>
            <div>
              <h3>Independent Music Learning</h3>
              <h4>Songwriting & Music Production</h4>
              <p>Practising composition, music theory, DAW workflows, mixing, and mastering through ongoing creative work.</p>
              <span class="education-date">Ongoing</span>
            </div>
          </article>
        </div>
      </div>
    </section>

    <section id="skills">
      <div class="container">
        <div class="section-heading">
          <span>Skills & Interests</span><h2>What I work on.</h2>
          <p>A developing skill set across music creation and computer science.</p>
        </div>
        <div class="skills-grid">
          <article class="skill-card">
            <div class="skill-icon">♫</div><h3>Songwriting & Composition</h3>
            <p>Creating lyrics, developing melodies, and shaping musical ideas into original song concepts.</p>
            <div class="skill-tags"><span class="tag">Lyrics</span><span class="tag">Melody Writing</span><span class="tag">Music Theory</span></div>
          </article>
          <article class="skill-card">
            <div class="skill-icon">🎛️</div><h3>Music Production</h3>
            <p>Exploring digital production workflows and learning to shape clear, expressive mixes.</p>
            <div class="skill-tags"><span class="tag">FL Studio</span><span class="tag">Arrangement</span><span class="tag">Mixing</span><span class="tag">Mastering</span></div>
          </article>
          <article class="skill-card">
            <div class="skill-icon">⌘</div><h3>Computer Science</h3>
            <p>Strengthening programming fundamentals and exploring software and AI-based project ideas.</p>
            <div class="skill-tags"><span class="tag">Programming</span><span class="tag">Problem Solving</span><span class="tag">AI/ML</span></div>
          </article>
        </div>
      </div>
    </section>

    <section id="projects">
      <div class="container">
        <div class="section-heading">
          <span>Projects & Creative Work</span><h2>Ideas in progress.</h2>
          <p>A selection of my music work and technical concepts.</p>
        </div>
        <div class="projects-grid">
          <article class="project-card">
            <div class="project-visual">🎵</div><h3>Kanmaniyea — Original Song</h3>
            <p>An independent love-song release and an important milestone in my journey as a songwriter and music creator.</p>
            <div class="skill-tags"><span class="tag">Songwriting</span><span class="tag">Composition</span><span class="tag">Music Release</span></div>
          </article>
          <article class="project-card">
            <div class="project-visual">🎙️</div><h3>Song Scale Detection App</h3>
            <p>A project concept that estimates a song's musical scale from a recorded or uploaded vocal melody using audio analysis and a lightweight machine-learning approach.</p>
            <div class="skill-tags"><span class="tag">Audio Analysis</span><span class="tag">Python</span><span class="tag">Machine Learning</span></div>
          </article>
          <article class="project-card">
            <div class="project-visual">💻</div><h3>Computer Science Projects</h3>
            <p>A space for programming assignments, software experiments, and practical concepts developed through my CSE studies.</p>
            <div class="skill-tags"><span class="tag">Programming</span><span class="tag">Software Development</span></div>
          </article>
          <article class="project-card">
            <div class="project-visual">🎚️</div><h3>Music Production Experiments</h3>
            <p>Exploring beats, bass lines, synthesizers, vocal processing, and mixing techniques for original music.</p>
            <div class="skill-tags"><span class="tag">FL Studio</span><span class="tag">Sound Design</span><span class="tag">Audio Production</span></div>
          </article>
        </div>
      </div>
    </section>

    <section id="achievements">
      <div class="container">
        <div class="section-heading">
          <span>Milestones</span><h2>Progress over perfection.</h2>
          <p>Meaningful steps in my ongoing journey as a student and music creator.</p>
        </div>
        <div class="achievements-grid">
          <article class="achievement"><span>🎶</span><h3>Original Music</h3><p>Working on and releasing original music, including the love song Kanmaniyea.</p></article>
          <article class="achievement"><span>✍️</span><h3>Creative Practice</h3><p>Continuously developing songwriting, melody writing, and composition skills.</p></article>
          <article class="achievement"><span>💡</span><h3>Learning by Building</h3><p>Exploring ideas that connect computer science, audio, and creative technology.</p></article>
        </div>
      </div>
    </section>

    <section id="interests">
      <div class="container">
        <div class="section-heading"><span>Beyond the Classroom</span><h2>Interests that inspire me.</h2></div>
        <div class="interests">
          <span class="interest">Tamil Film Music</span><span class="interest">Music Direction</span>
          <span class="interest">Songwriting</span><span class="interest">Piano & Melody</span>
          <span class="interest">Sound Design</span><span class="interest">Creative Technology</span>
        </div>
      </div>
    </section>

    <section id="goals">
      <div class="container">
        <div class="section-heading"><span>Future Goals</span><h2>What I'm working towards.</h2></div>
        <div class="goals-grid">
          <article class="goal-card"><h3>Become a Music Director</h3><p>Keep improving as a songwriter, composer, and producer, with the long-term goal of creating music for Tamil cinema.</p></article>
          <article class="goal-card"><h3>Grow as a Technologist</h3><p>Build strong CSE fundamentals and explore software and AI tools that can solve practical problems and support creative workflows.</p></article>
        </div>
      </div>
    </section>

    <section id="contact">
      <div class="container">
        <div class="section-heading">
          <span>Contact</span><h2>Let's connect.</h2>
          <p>Open to conversations about music, creative collaborations, and technology projects.</p>
        </div>
        <div class="contact-wrapper">
          <article class="contact-card">
            <h3>Get in Touch</h3>
            <p>Have a project idea or want to discuss music? Use the details below after replacing the placeholders with your own links.</p>
            <div class="contact-detail"><strong>Email</strong><a href="mailto:your.email@example.com">your.email@example.com</a></div>
            <div class="contact-detail"><strong>Instagram</strong><a href="https://instagram.com/" target="_blank" rel="noopener noreferrer">Add your Instagram profile link</a></div>
            <div class="contact-detail"><strong>Music</strong><span>Kanmaniyea — add your streaming link</span></div>
          </article>
          <article class="contact-card">
            <h3>Send a Message</h3>
            <form class="contact-form" id="contactForm">
              <label>Your Name<input type="text" name="name" placeholder="Enter your name" required></label>
              <label>Your Email<input type="email" name="email" placeholder="Enter your email" required></label>
              <label>Message<textarea name="message" placeholder="What would you like to discuss?" required></textarea></label>
              <button class="button button-primary" type="submit">Prepare Email →</button>
              <p style="font-size:.8rem;color:var(--muted)">Replace your.email@example.com in the script with your real email address for this form to work.</p>
            </form>
          </article>
        </div>
      </div>
    </section>
  </main>

  <footer><div class="container"><p>© <span id="year"></span> Harshat. Built with creativity and curiosity.</p><p><a href="#home">Back to top ↑</a></p></div></footer>
  <script>
    const menuButton = document.getElementById('menuButton');
    const navLinks = document.getElementById('navLinks');
    menuButton.addEventListener('click', () => {
      const open = navLinks.classList.toggle('active');
      menuButton.setAttribute('aria-expanded', String(open));
    });
    navLinks.querySelectorAll('a').forEach(link => link.addEventListener('click', () => {
      navLinks.classList.remove('active');
      menuButton.setAttribute('aria-expanded', 'false');
    }));
    document.getElementById('year').textContent = new Date().getFullYear();
    document.getElementById('contactForm').addEventListener('submit', event => {
      event.preventDefault();
      const data = new FormData(event.currentTarget);
      const subject = encodeURIComponent('Portfolio enquiry from ' + data.get('name'));
      const body = encodeURIComponent('Name: ' + data.get('name') + '\nEmail: ' + data.get('email') + '\n\n' + data.get('message'));
      window.location.href = 'mailto:your.email@example.com?subject=' + subject + '&body=' + body;
    });
  </script>
</body>
</html>
```
### OUTPUT
![alt text](<Screenshot 2026-11-01 122449.png>)

### RESULT
The program for creating Portfolio using HTML and CSS is executed successfully.
