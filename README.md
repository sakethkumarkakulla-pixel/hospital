# hospital
<!DOCTYPE html>
<!--
  CarePoint Multispeciality Hospital — Care That Never Stops - student HTML & CSS project
  This ONE file contains both the HTML structure and the full CSS (<style> block).
  Photos are loaded from the "images" folder next to this file - keep the images
  folder in the same directory (and you may rename this file to index.html).
-->

<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>CarePoint Multispeciality Hospital — Care That Never Stops</title>
<meta name="description" content="CarePoint Multispeciality Hospital offers 24/7 emergency care, expert doctors across 8 departments, modern facilities and online appointment booking.">
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Fraunces:wght@600;700&family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<style>
/* ============================================================
   CarePoint Multispeciality Hospital
   Pure HTML + CSS student project · Responsive (desktop / tablet / mobile)
   ============================================================ */
:root {
  --bg: #f4f8fb;
  --surface: #ffffff;
  --ink: #10303f;
  --ink-soft: #51707f;
  --blue: #0e5a8a;
  --blue-dark: #0a4468;
  --teal: #16a3a3;
  --red: #d64545;
  --red-dark: #b73535;
  --green: #2e9e6b;
  --line: #d9e6ef;
  --shadow: 0 12px 30px rgba(14, 90, 138, .12);
  --radius: 14px;
  --font-head: "Fraunces", Georgia, serif;
  --font-body: "Inter", "Segoe UI", system-ui, sans-serif;
}

* { margin: 0; padding: 0; box-sizing: border-box; }
html { scroll-behavior: smooth; }
body { font-family: var(--font-body); background: var(--bg); color: var(--ink); line-height: 1.65; }
img { max-width: 100%; display: block; }
.container { width: min(1160px, 92%); margin-inline: auto; }
h1, h2, h3 { font-family: var(--font-head); line-height: 1.25; }
h2 { font-size: clamp(1.7rem, 3vw, 2.4rem); }

/* ---------- buttons & chips ---------- */
.btn {
  display: inline-block; padding: .8rem 1.6rem; border-radius: 999px;
  font-weight: 600; font-size: .95rem; text-decoration: none; border: 2px solid transparent;
  cursor: pointer; transition: transform .18s ease, box-shadow .18s ease, background .18s ease;
}
.btn-primary { background: var(--blue); color: #fff; }
.btn-primary:hover { background: var(--blue-dark); transform: translateY(-2px); box-shadow: var(--shadow); }
.btn-ghost { background: rgba(255, 255, 255, .12); border-color: rgba(255, 255, 255, .7); color: #fff; }
.btn-ghost:hover { background: rgba(255, 255, 255, .25); transform: translateY(-2px); }
.btn-outline { border-color: var(--blue); color: var(--blue); background: transparent; }
.btn-outline:hover { background: var(--blue); color: #fff; transform: translateY(-2px); }
.btn-sm { padding: .5rem 1.2rem; font-size: .85rem; }
.btn-block { width: 100%; }
.chip {
  background: rgba(255, 255, 255, .14); border: 1px solid rgba(255, 255, 255, .4);
  color: #fff; padding: .35rem .9rem; border-radius: 999px; font-size: .8rem;
  backdrop-filter: blur(4px);
}

/* ---------- emergency top strip ---------- */
.topstrip { background: var(--red); color: #fff; font-size: .85rem; padding: .45rem 0; }
.topstrip-inner { display: flex; justify-content: space-between; gap: 1rem; flex-wrap: wrap; }
.emergency-line strong { font-weight: 700; letter-spacing: .5px; }

/* ---------- navbar ---------- */
.navbar {
  position: sticky; top: 0; z-index: 50;
  background: rgba(244, 248, 251, .94); backdrop-filter: blur(8px);
  border-bottom: 1px solid var(--line);
}
.nav-inner { display: flex; align-items: center; justify-content: space-between; min-height: 66px; }
.brand { font-family: var(--font-head); font-size: 1.5rem; font-weight: 700; color: var(--ink); text-decoration: none; }
.brand span { color: var(--teal); }
.nav-links { display: flex; align-items: center; gap: 1.3rem; }
.nav-links a { color: var(--ink); text-decoration: none; font-weight: 500; font-size: .93rem; }
.nav-links a:hover { color: var(--teal); }
.nav-toggle { display: none; }
.nav-burger { display: none; cursor: pointer; width: 30px; height: 24px; position: relative; }
.nav-burger span, .nav-burger span::before, .nav-burger span::after {
  content: ""; position: absolute; left: 0; width: 100%; height: 3px;
  background: var(--ink); border-radius: 2px; transition: .25s;
}
.nav-burger span { top: 10px; }
.nav-burger span::before { top: -8px; }
.nav-burger span::after { top: 8px; }

/* ---------- hero ---------- */
.hero { min-height: 78vh; display: flex; align-items: center; background: url("images/hero-aerial.jpg") center/cover no-repeat; }
.hero-overlay { width: 100%; background: linear-gradient(95deg, rgba(10, 48, 72, .88) 25%, rgba(10, 48, 72, .55) 70%, rgba(10, 48, 72, .2)); }
.hero-content { padding: 5rem 0; max-width: 620px; color: #fff; }
.hero-kicker { color: #8be0e0; font-weight: 600; letter-spacing: 2px; text-transform: uppercase; font-size: .8rem; margin-bottom: 1rem; }
.hero h1 { font-size: clamp(2.2rem, 5vw, 3.4rem); margin-bottom: 1rem; }
.hero-sub { color: #dcebf5; font-weight: 300; margin-bottom: 2rem; }
.hero-actions { display: flex; gap: 1rem; flex-wrap: wrap; margin-bottom: 1.8rem; }
.hero-chips { display: flex; gap: .7rem; flex-wrap: wrap; }

/* ---------- sections ---------- */
.section { padding: 5.5rem 0; }
.section-head { text-align: center; max-width: 640px; margin: 0 auto 3rem; }
.kicker { color: var(--teal); font-weight: 700; letter-spacing: 2px; text-transform: uppercase; font-size: .8rem; margin-bottom: .5rem; }
.section-sub { color: var(--ink-soft); margin-top: .8rem; }

/* ---------- about ---------- */
.about { background: var(--surface); }
.about-grid { display: grid; grid-template-columns: 1fr 1fr; gap: 3.5rem; align-items: center; }
.about-text p { color: var(--ink-soft); margin-bottom: 1rem; }
.about-text h2 { margin-bottom: 1.2rem; }
.stats { display: grid; grid-template-columns: repeat(4, 1fr); gap: 1rem; margin-top: 1.8rem; }
.stat { background: var(--bg); border: 1px solid var(--line); border-radius: var(--radius); text-align: center; padding: 1rem .4rem; }
.stat strong { display: block; font-size: 1.5rem; color: var(--blue); font-family: var(--font-head); }
.stat span { font-size: .74rem; color: var(--ink-soft); }
.about-media { display: grid; gap: 1rem; }
.about-media img { border-radius: var(--radius); box-shadow: var(--shadow); width: 100%; height: 230px; object-fit: cover; }

/* ---------- departments ---------- */
.dept-grid { display: grid; grid-template-columns: repeat(4, 1fr); gap: 1.4rem; }
.dept-card {
  background: var(--surface); border: 1px solid var(--line); border-radius: var(--radius);
  padding: 1.6rem 1.4rem; text-decoration: none; color: var(--ink);
  box-shadow: 0 5px 16px rgba(14, 90, 138, .06);
  transition: transform .2s ease, box-shadow .2s ease, border-color .2s ease;
}
.dept-card:hover { transform: translateY(-6px); box-shadow: var(--shadow); border-color: var(--teal); }
.dept-icon {
  display: inline-flex; align-items: center; justify-content: center;
  width: 52px; height: 52px; border-radius: 14px; background: var(--bg);
  border: 1px solid var(--line); color: var(--blue); font-weight: 700;
  letter-spacing: 1px; font-size: 1.05rem; margin-bottom: 1rem;
}
.dept-card h3 { font-size: 1.15rem; margin-bottom: .4rem; }
.dept-card p { font-size: .85rem; color: var(--ink-soft); }
.dept-card.emergency { border: 2px solid var(--red); }
.dept-card.emergency .dept-icon { color: var(--red); border-color: var(--red); background: #fdf0f0; }

/* ---------- doctors ---------- */
.doc-grid { display: grid; grid-template-columns: repeat(4, 1fr); gap: 1.6rem; }
.doc-card {
  background: var(--surface); border: 1px solid var(--line); border-radius: var(--radius);
  overflow: hidden; box-shadow: 0 5px 16px rgba(14, 90, 138, .06);
  transition: transform .2s ease, box-shadow .2s ease;
}
.doc-card:hover { transform: translateY(-6px); box-shadow: var(--shadow); }
.doc-card img { height: 280px; width: 100%; object-fit: cover; object-position: top; }
.doc-body { padding: 1.2rem 1.3rem 1.4rem; }
.doc-body h3 { font-size: 1.2rem; }
.doc-spec { color: var(--teal); font-weight: 600; font-size: .84rem; margin: .2rem 0 .5rem; }
.doc-meta { color: var(--ink-soft); font-size: .8rem; margin-bottom: 1rem; }

/* ---------- services ---------- */
.services { background: var(--surface); }
.services-grid { display: grid; grid-template-columns: 1fr 1.1fr; gap: 3.5rem; align-items: center; }
.services-media img { border-radius: var(--radius); box-shadow: var(--shadow); }
.services-text h2 { margin-bottom: 1.2rem; }
.service-list { list-style: none; display: grid; gap: 1rem; }
.service-list li { background: var(--bg); border: 1px solid var(--line); border-radius: 12px; padding: 1rem 1.2rem; font-size: .9rem; color: var(--ink-soft); }
.service-list strong { color: var(--ink); display: block; margin-bottom: .2rem; }

/* ---------- health tips ---------- */
.health-grid { display: grid; grid-template-columns: repeat(4, 1fr); gap: 1.4rem; }
.health-card {
  background: var(--surface); border: 1px solid var(--line); border-radius: var(--radius);
  padding: 1.6rem 1.4rem; box-shadow: 0 5px 16px rgba(14, 90, 138, .06); position: relative;
}
.health-tag {
  position: absolute; top: -14px; left: 20px; background: var(--green); color: #fff;
  font-size: .72rem; font-weight: 700; letter-spacing: 1px; text-transform: uppercase;
  padding: .3rem .9rem; border-radius: 999px;
}
.health-card h3 { font-size: 1.12rem; margin: .6rem 0 .5rem; }
.health-card p { font-size: .86rem; color: var(--ink-soft); }

/* ---------- appointment ---------- */
.appointment { background: linear-gradient(135deg, #0a4468, #0e5a8a); }
.appt-grid { display: grid; grid-template-columns: 1.4fr 1fr; gap: 2.5rem; align-items: start; }
.appt-form { background: var(--surface); border-radius: var(--radius); padding: 2.2rem; box-shadow: var(--shadow); }
.appt-form h2 { margin-bottom: 1.5rem; }
.appt-form label { display: block; font-size: .85rem; font-weight: 500; margin-bottom: 1rem; }
.appt-form input, .appt-form select, .appt-form textarea {
  width: 100%; margin-top: .35rem; padding: .7rem .9rem; border: 1px solid var(--line);
  border-radius: 10px; background: var(--bg); font-family: inherit; font-size: .9rem; color: var(--ink);
}
.appt-form input:focus, .appt-form select:focus, .appt-form textarea:focus {
  outline: none; border-color: var(--teal); box-shadow: 0 0 0 3px rgba(22, 163, 163, .14);
}
.form-row { display: grid; grid-template-columns: 1fr 1fr; gap: 1rem; }
.form-row label { margin-bottom: 0; }
.form-row + .form-row, .form-row + label { margin-top: 1rem; }
.appt-form textarea { margin-top: 1rem; }
.appt-form .btn { margin-top: .4rem; }
.form-note { font-size: .78rem; color: var(--ink-soft); margin-top: .8rem; text-align: center; }
.emergency-box {
  background: rgba(255, 255, 255, .08); border: 1px solid rgba(255, 255, 255, .25);
  border-radius: var(--radius); padding: 1.8rem; color: #fff; backdrop-filter: blur(4px);
}
.emergency-box h3 { color: #fff; margin-bottom: 1.2rem; font-size: 1.3rem; }
.emergency-box ul { list-style: none; display: grid; gap: .8rem; margin-bottom: 1.2rem; }
.emergency-box li {
  display: flex; justify-content: space-between; align-items: center; gap: 1rem;
  border-bottom: 1px dashed rgba(255, 255, 255, .25); padding-bottom: .6rem; font-size: .88rem;
}
.emergency-box strong { color: #ffd9d9; font-size: 1rem; white-space: nowrap; }
.emg-note { font-size: .82rem; color: #dcebf5; }
.emg-note::before { content: "✓ "; color: #8be0e0; font-weight: 700; }

/* ---------- footer ---------- */
.footer { background: #0c2836; color: #bfd6e2; padding: 3.5rem 0 0; }
.footer-grid { display: grid; grid-template-columns: 2fr 1fr 1fr; gap: 2.5rem; padding-bottom: 2.5rem; }
.footer-brand { font-size: 1.5rem; color: #fff; margin-bottom: .7rem; }
.footer-brand span { color: var(--teal); }
.footer h4 { color: #fff; margin-bottom: .9rem; font-family: var(--font-body); font-weight: 600; font-size: .95rem; }
.footer-grid a { display: block; color: #bfd6e2; text-decoration: none; font-size: .88rem; margin-bottom: .5rem; }
.footer-grid a:hover { color: #8be0e0; }
.footer-grid p { font-size: .88rem; }
.footer-bottom { border-top: 1px solid rgba(255, 255, 255, .12); padding: 1.2rem 0; }
.footer-bottom p { font-size: .78rem; color: #8aa6b5; text-align: center; }

/* ---------- responsive ---------- */
@media (max-width: 980px) {
  .dept-grid, .health-grid { grid-template-columns: repeat(2, 1fr); }
  .doc-grid { grid-template-columns: repeat(2, 1fr); }
  .about-grid, .services-grid { grid-template-columns: 1fr; gap: 2.5rem; }
  .appt-grid { grid-template-columns: 1fr; }
  .footer-grid { grid-template-columns: 1fr 1fr; }
}
@media (max-width: 640px) {
  .section { padding: 3.5rem 0; }
  .dept-grid, .health-grid, .doc-grid, .stats { grid-template-columns: 1fr 1fr; }
  .footer-grid { grid-template-columns: 1fr; }
  .form-row { grid-template-columns: 1fr; }
  .hero { min-height: 70vh; }

  .nav-burger { display: block; }
  .nav-links {
    display: none; position: absolute; top: 66px; left: 0; right: 0;
    background: #fff; flex-direction: column; align-items: stretch; gap: 0;
    border-bottom: 1px solid var(--line); box-shadow: var(--shadow); padding: .6rem 4%;
  }
  .nav-links a { padding: .85rem .4rem; border-bottom: 1px solid var(--line); }
  .nav-links a:last-child { border-bottom: none; margin-top: .5rem; text-align: center; }
  .nav-toggle:checked ~ .nav-links { display: flex; }
  .nav-toggle:checked + .nav-burger span { background: transparent; }
  .nav-toggle:checked + .nav-burger span::before { transform: rotate(45deg); top: 0; }
  .nav-toggle:checked + .nav-burger span::after { transform: rotate(-45deg); top: 0; }
}

</style>
</head>
<body>

<!-- ===== Emergency top strip ===== -->
<div class="topstrip">
  <div class="container topstrip-inner">
    <span>Open 24 × 7 · All Departments</span>
    <span class="emergency-line">Emergency: <strong>108</strong> · Ambulance: <strong>+91 98470 00108</strong></span>
  </div>
</div>

<!-- ===== Navigation ===== -->
<header class="navbar">
  <div class="container nav-inner">
    <a href="#home" class="brand">Care<span>Point</span></a>
    <input type="checkbox" id="nav-toggle" class="nav-toggle">
    <label for="nav-toggle" class="nav-burger" aria-label="Toggle menu"><span></span></label>
    <nav class="nav-links">
      <a href="#home">Home</a>
      <a href="#about">About</a>
      <a href="#departments">Departments</a>
      <a href="#doctors">Doctors</a>
      <a href="#health">Health Tips</a>
      <a href="#appointment" class="btn btn-primary btn-sm">Book Appointment</a>
    </nav>
  </div>
</header>

<!-- ===== Hero ===== -->
<section id="home" class="hero">
  <div class="hero-overlay">
    <div class="container hero-content">
      <p class="hero-kicker">NABH Accredited · Multispeciality Hospital</p>
      <h1>Care That Never Stops</h1>
      <p class="hero-sub">From everyday health check-ups to advanced surgery, our team of
        60+ specialists is ready for you and your family — every hour of every day.</p>
      <div class="hero-actions">
        <a href="#appointment" class="btn btn-primary">Book an Appointment</a>
        <a href="#departments" class="btn btn-ghost">View Departments</a>
      </div>
      <div class="hero-chips">
        <span class="chip">✓ 24/7 Emergency &amp; Trauma</span>
        <span class="chip">✓ In-house Pharmacy</span>
        <span class="chip">✓ Cashless Insurance</span>
      </div>
    </div>
  </div>
</section>

<!-- ===== About ===== -->
<section id="about" class="section about">
  <div class="container about-grid">
    <div class="about-text">
      <p class="kicker">About CarePoint</p>
      <h2>Two Decades of Trusted Healthcare</h2>
      <p>Founded in 2004, CarePoint Multispeciality Hospital has grown from a 40-bed
        nursing home into a 250-bed multispeciality hospital serving more than
        90,000 patients every year. We combine experienced doctors, modern
        diagnostic technology and honest, transparent care.</p>
      <p>Our promise is simple: treat every patient like family, explain every
        option clearly, and never compromise on safety or hygiene.</p>
      <div class="stats">
        <div class="stat"><strong>250</strong><span>Beds &amp; ICU units</span></div>
        <div class="stat"><strong>60+</strong><span>Specialist doctors</span></div>
        <div class="stat"><strong>8</strong><span>Departments</span></div>
        <div class="stat"><strong>90k</strong><span>Patients yearly</span></div>
      </div>
    </div>
    <div class="about-media">
      <img src="images/about.jpg" alt="CarePoint hospital building exterior">
      <img src="images/facility.jpg" alt="CarePoint facility wing with medical signage">
    </div>
  </div>
</section>

<!-- ===== Departments ===== -->
<section id="departments" class="section departments">
  <div class="container">
    <div class="section-head">
      <p class="kicker">Departments</p>
      <h2>Specialised Care Under One Roof</h2>
      <p class="section-sub">Eight full-time departments supported by a 24/7 laboratory,
        radiology suite and pharmacy.</p>
    </div>
    <div class="dept-grid">
      <a href="#appointment" class="dept-card">
        <span class="dept-icon">CA</span>
        <h3>Cardiology</h3>
        <p>ECG, echo, angiography and cardiac rehabilitation programmes.</p>
      </a>
      <a href="#appointment" class="dept-card">
        <span class="dept-icon">OR</span>
        <h3>Orthopedics</h3>
        <p>Joint replacement, sports injuries and fracture clinics.</p>
      </a>
      <a href="#appointment" class="dept-card">
        <span class="dept-icon">PE</span>
        <h3>Pediatrics</h3>
        <p>Child health clinics, immunisation and NICU support.</p>
      </a>
      <a href="#appointment" class="dept-card">
        <span class="dept-icon">NE</span>
        <h3>Neurology</h3>
        <p>Stroke care, epilepsy monitoring and headache clinics.</p>
      </a>
      <a href="#appointment" class="dept-card">
        <span class="dept-icon">DE</span>
        <h3>Dermatology</h3>
        <p>Skin, hair and allergy care with laser treatment options.</p>
      </a>
      <a href="#appointment" class="dept-card">
        <span class="dept-icon">GY</span>
        <h3>Gynecology</h3>
        <p>Antenatal care, deliveries and women's wellness programmes.</p>
      </a>
      <a href="#appointment" class="dept-card">
        <span class="dept-icon">EN</span>
        <h3>ENT</h3>
        <p>Hearing tests, sinus care and day-care ENT surgeries.</p>
      </a>
      <a href="#appointment" class="dept-card emergency">
        <span class="dept-icon">EM</span>
        <h3>Emergency &amp; Trauma</h3>
        <p>Rapid-response team, ambulances and ICU backup — 24 × 7.</p>
      </a>
    </div>
  </div>
</section>

<!-- ===== Doctors ===== -->
<section id="doctors" class="section doctors">
  <div class="container">
    <div class="section-head">
      <p class="kicker">Our Doctors</p>
      <h2>Meet the Specialists</h2>
    </div>
    <div class="doc-grid">
      <article class="doc-card">
        <img src="images/doc1.jpg" alt="Dr. James Chen, Cardiologist">
        <div class="doc-body">
          <h3>Dr. James Chen</h3>
          <p class="doc-spec">Cardiologist · MD, DM (Cardio)</p>
          <p class="doc-meta">18 yrs experience · Mon–Sat, 10 AM – 2 PM</p>
          <a href="#appointment" class="btn btn-outline btn-sm">Consult</a>
        </div>
      </article>
      <article class="doc-card">
        <img src="images/doc4.jpg" alt="Dr. Sofia Ramirez, Pediatrician">
        <div class="doc-body">
          <h3>Dr. Sofia Ramirez</h3>
          <p class="doc-spec">Pediatrician · MD (Child Health)</p>
          <p class="doc-meta">12 yrs experience · Mon–Fri, 9 AM – 1 PM</p>
          <a href="#appointment" class="btn btn-outline btn-sm">Consult</a>
        </div>
      </article>
      <article class="doc-card">
        <img src="images/doc5.jpg" alt="Dr. Emily Watson, Dermatologist">
        <div class="doc-body">
          <h3>Dr. Emily Watson</h3>
          <p class="doc-spec">Dermatologist · MD (Skin &amp; VD)</p>
          <p class="doc-meta">9 yrs experience · Tue–Sun, 11 AM – 4 PM</p>
          <a href="#appointment" class="btn btn-outline btn-sm">Consult</a>
        </div>
      </article>
      <article class="doc-card">
        <img src="images/doc3.jpg" alt="Dr. Daniel Okafor, Orthopedic Surgeon">
        <div class="doc-body">
          <h3>Dr. Daniel Okafor</h3>
          <p class="doc-spec">Orthopedic Surgeon · MS (Ortho)</p>
          <p class="doc-meta">15 yrs experience · Mon–Sat, 4 PM – 8 PM</p>
          <a href="#appointment" class="btn btn-outline btn-sm">Consult</a>
        </div>
      </article>
    </div>
  </div>
</section>

<!-- ===== Services & facilities ===== -->
<section class="section services">
  <div class="container services-grid">
    <div class="services-media">
      <img src="images/services.jpg" alt="CarePoint emergency entrance and outpatient wing">
    </div>
    <div class="services-text">
      <p class="kicker">Medical Services</p>
      <h2>Modern Facilities, Human Touch</h2>
      <ul class="service-list">
        <li><strong>24/7 Emergency &amp; Ambulance</strong> — GPS-tracked ambulances with paramedic support, average response under 12 minutes in city limits.</li>
        <li><strong>Diagnostics &amp; Lab</strong> — NABL-accredited lab, digital X-ray, CT, MRI and ultrasound with same-day reports.</li>
        <li><strong>ICU &amp; Critical Care</strong> — 36-bed ICU with ventilators and round-the-clock intensivist coverage.</li>
        <li><strong>Pharmacy &amp; Insurance Desk</strong> — In-house pharmacy open 24 hours; cashless treatment with 20+ insurers.</li>
        <li><strong>Health Check-up Packages</strong> — Annual master health checks, corporate packages and senior-citizen plans.</li>
      </ul>
    </div>
  </div>
</section>

<!-- ===== Health info ===== -->
<section id="health" class="section health">
  <div class="container">
    <div class="section-head">
      <p class="kicker">Health Information</p>
      <h2>Everyday Tips From Our Doctors</h2>
    </div>
    <div class="health-grid">
      <article class="health-card">
        <span class="health-tag">Heart</span>
        <h3>Walk 30 Minutes a Day</h3>
        <p>A brisk 30-minute daily walk lowers blood pressure and heart-disease risk.
          If you are over 40, get your BP and cholesterol checked once a year.</p>
      </article>
      <article class="health-card">
        <span class="health-tag">Kids</span>
        <h3>Keep Vaccines on Schedule</h3>
        <p>Follow the national immunisation chart and never skip booster doses.
          Our pediatrics OPD runs a free reminder service by SMS.</p>
      </article>
      <article class="health-card">
        <span class="health-tag">Wellness</span>
        <h3>Sleep 7–8 Hours</h3>
        <p>Consistent sleep improves immunity, memory and mood. Avoid screens one
          hour before bed and keep your bedroom cool and dark.</p>
      </article>
      <article class="health-card">
        <span class="health-tag">Emergency</span>
        <h3>Know the Warning Signs</h3>
        <p>Chest pain, sudden weakness on one side, slurred speech or breathlessness
          — do not wait. Call 108 immediately; early treatment saves lives.</p>
      </article>
    </div>
  </div>
</section>

<!-- ===== Appointment ===== -->
<section id="appointment" class="section appointment">
  <div class="container appt-grid">
    <form class="appt-form" action="#" method="post">
      <p class="kicker">Appointments</p>
      <h2>Book Your Visit Online</h2>
      <div class="form-row">
        <label>Patient Name <input type="text" name="name" placeholder="e.g. Nikhil Menon" required></label>
        <label>Phone Number <input type="tel" name="phone" placeholder="+91 98765 00000" required></label>
      </div>
      <div class="form-row">
        <label>Department
          <select name="dept">
            <option>Cardiology</option><option>Orthopedics</option><option>Pediatrics</option>
            <option>Neurology</option><option>Dermatology</option><option>Gynecology</option>
            <option>ENT</option><option>General Check-up</option>
          </select>
        </label>
        <label>Preferred Doctor
          <select name="doctor">
            <option selected>No preference</option><option>Dr. James Chen</option>
            <option>Dr. Sofia Ramirez</option><option>Dr. Emily Watson</option>
            <option>Dr. Daniel Okafor</option>
          </select>
        </label>
      </div>
      <div class="form-row">
        <label>Preferred Date <input type="date" name="date" required></label>
        <label>Preferred Time
          <select name="slot">
            <option>Morning (9 AM – 1 PM)</option><option selected>Afternoon (1 PM – 5 PM)</option>
            <option>Evening (5 PM – 8 PM)</option>
          </select>
        </label>
      </div>
      <label>Briefly Describe Your Concern
        <textarea name="note" rows="3" placeholder="Symptoms, previous reports, allergies…"></textarea>
      </label>
      <button type="submit" class="btn btn-primary btn-block">Confirm Appointment Request</button>
      <p class="form-note">Our front desk will call to confirm your slot within 30 minutes.</p>
    </form>

    <aside class="emergency-box">
      <h3>Emergency Contacts</h3>
      <ul>
        <li><span>Ambulance (24 × 7)</span><strong>108</strong></li>
        <li><span>Hospital Reception</span><strong>+91 484 245 9000</strong></li>
        <li><span>Appointment Desk</span><strong>+91 484 245 9090</strong></li>
        <li><span>Blood Bank</span><strong>+91 484 245 9111</strong></li>
        <li><span>Pharmacy (24 × 7)</span><strong>+91 484 245 9222</strong></li>
      </ul>
      <p class="emg-note">In a life-threatening emergency, call 108 first — then let us
        know. Our team prepares before you arrive.</p>
    </aside>
  </div>
</section>

<!-- ===== Footer ===== -->
<footer class="footer">
  <div class="container footer-grid">
    <div>
      <p class="brand footer-brand">Care<span>Point</span></p>
      <p>Wellness Avenue, Sector 12,<br>Kochi, Kerala 682021<br>info@carepoint.example</p>
    </div>
    <div>
      <h4>Hospital</h4>
      <a href="#about">About Us</a>
      <a href="#departments">Departments</a>
      <a href="#doctors">Our Doctors</a>
    </div>
    <div>
      <h4>Patients</h4>
      <a href="#appointment">Book Appointment</a>
      <a href="#health">Health Tips</a>
      <a href="#appointment">Emergency Contacts</a>
    </div>
  </div>
  <div class="container footer-bottom">
    <p>© 2026 CarePoint Multispeciality Hospital · Student HTML &amp; CSS Project · Images for educational use</p>
  </div>
</footer>

</body>
</html>
