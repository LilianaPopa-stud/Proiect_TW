<!DOCTYPE html>
<html lang="ro" xmlns="http://www.w3.org/1999/html">
<head>
  <meta charset="utf-8">

</head>
<body prefix="schema: https://schema.org">
<header>
  <div class="banner">
    <img src="../img/scholarly-html.svg" alt="Scholarly logo" style="width:227px;height:50px;">
    <div class="status">CoCo project</div>
  </div>
  <h1>Consumer Confidence Visualizer</h1>
</header>

<div role="contentinfo"><ol role="directory">
  <li><a href="#abstract"><span>1. </span>Descrierea proiectului</a></li>
  <li><a href="#introduction"><span>2. </span>Introducere</a></li>
  <li><a href="#structure"><span>3. </span>Structura</a><ol role="directory">
    <li><a href="#TehnologiiUtilizate"><span>3.1 </span>Tehnologii utilizate</a></li>
    <li><a href="#Pagini"><span>3.2 </span>Pagini</a>
  </ol></li><li><a href="#functionalitate"><span>4. </span>Funcționalități</a></li>
  <li><a href="#backend"><span>5. </span>Noțiuni speciale</a></li>
  <li><a href="#user"><span>6. </span>Experiența utilizatorului</a></li>
  <li><a href="#diagrame"><span>7. </span>Diagrame</a></li>
  <li><a href="#autori"><span>8. </span>Autori</a></li>
  <li><a href="#github"><span>9. </span>Link GitHub</a></li>
  <li><a href="#resurse"><span>10. </span>Resurse</a></li>
</ol>
</div>
<section id="abstract">
  <h2><span>1. </span>Descrierea proiectului</h2>
  <p>
    CoCo (Consumer Confidence Visualizer) este o aplicație web care permite utilizatorilor să vizualizeze date privitoare la Consumer Confidence Index (CCI). Aplicația oferă posibilitatea de a vizualiza datele în 5 moduri diferite (harta, core chart, bar chart, line chart, tabel) și de a le exporta în formatele CSV, WebP si SVG.
  </p>
</section>
<section id="introduction" role="doc-introduction">
  <h2><span>2. </span>Introducere</h2>
  <p>
    Proiectul este un instrument Web de vizualizare flexibilă a datelor vizând Consumer Confidence în perioada 1960-2023. Statisticile și vizualizările generate – în 5 maniere (harta, core chart, bar chart, line chart, tabel) – pot fi exportate în formatele CSV, WebP si SVG.
    Datele utilizate se pot găsi la adresa <a href="https://www.oecd-ilibrary.org/economics/consumer-confidence-index-cci/indicator/english_46434d78-en#:~:text=This%20consumer%20confidence%20indicator%20provides,unemployment%20and%20capability%20of%20savings.%22">https://www.oecd-ilibrary.org/economics/consumer-confidence-index-cci/indicator/english_46434d78-en#:~:text=This%20consumer%20confidence%20indicator%20provides,unemployment%20and%20capability%20of%20savings.%22</a>.
  </p>
</section>
<section id="structure">
  <h2><span>3. </span>Structură</h2>
  <section id="TehnologiiUtilizate">
    <h3><span>3.1 </span>Tehnologii utilizate</h3>
    <section id="html_css">
      <h4><span>3.1.1 </span>HTML & CSS</h4>
      <p>
        Pentru a crea interfața aplicației am folosit HTML și CSS.
      </p>
    </section>
    <section id="javascript">
      <h4><span>3.1.2 </span>Javascript</h4>
      <p>
        JavaScript este utilizat pentru a crea diagrame (folosind Google Charts) și pentru a stabili conexiunea
        și comunicarea între aplicație și baza de date.
      </p>
    </section>
    <section id="sqlite">
      <h4><span>3.1.3 </span>Sqlite</h4>
      <p>
        Pentru stocarea și extragerea datelor va fi utilizată o bază de date Sqlite.
      </p>
    </section>
    <section id="HTTP">
      <h4><span>3.1.3 </span>HTTP</h4>
      <p>
        Pentru crearea serverului
      </p>
    </section>
  </section>
</section>
<section id="Pagini">
  <h3><span>3.2 </span>Pagini</h3>
  <section id="home">
    <h4>Site-ul este compus din 5 pagini, iar navigarea între ele se poate face folosind bara de navigare.</h4>
    <ul>
      <li><a href="INDEX.html">Home (pagina principala a aplicatiei)</a></li>
        <li><a href="Charts.html"> Charts (pagina ce permite vizualizarea datelor)</a></li>
      <li><a href="Report.html">Report (raportul)</a></li>
      <li><a href="Contact.html">Contact (pagină ce permite vizualizarea datelor de contact ale autorilor)</a></li>
      <li><a href="AdminLogIn.html">Admin Panel (permite administratorilor sa se autentifice pentru a face modificari in baza de date)</a></li>
    </ul>
  </section>
</section>
<section id="functionalitate">
  <h2><span>4. </span>Funcționalitate</h2>
  <ol>
    <li>Maniere de vizualizare a datelor:</li>
    <ul>
      <li>Combo chart: afiseaza CCI-ul pentru o selecție de țări și un interval de timp dat (prin comparație)</li>
      <li>Bar chart: Afisează CCI-ul pentru o singură țară, în intervalul de timp cerut </li>
      <li>Line chart: afiseaza CCI-ul pentru o selecție de țări in intervalul de timp dorit (luni, ani) </li>
      <li>Tabel: afiseaza CCI-ul pentru oricate țări pentru intervalul de timp dorit </li>
      <li>Hartă: afișează CCI-ul pentru fiecare țară pentru o anumită dată (an,luna) </li>
    </ul>
    <li>Exportarea datelor: Utilizatorii pot exporta datele privind Consumer Confidence Index în diferite formate, cum ar fi CSV, WebP și SVG. Această funcționalitate permite utilizatorilor să descarce datele și să le utilizeze în alte aplicații sau să le partajeze cu alți utilizatori.
   </li>
  </ol>
</section>

<section id="backend">
  <h2><span>5. </span>Arhitectura si procesul de construire al aplicatiei</h2>
    <p>
      Aplicația CoCo este dezvoltată pe baza unei arhitecturi tipice client-server, unde clientul reprezintă partea de frontend a aplicației,
      iar serverul reprezintă partea de backend. Frontend-ul este responsabil pentru afișarea interfeței utilizatorului și interacțiunea cu utilizatorii,
      în timp ce backend-ul gestionează logica de afișare a datelor, procesarea datelor și comunicarea cu baza de date.
  <h3><span> 5.1 </span> Backend - API & Admin Panel</h3>
  Backend-ul aplicației CoCo va fi dezvoltat folosind PHP, un limbaj de scripting popular pentru dezvoltarea aplicațiilor web.
  PHP oferă funcții și librării potrivite pentru a comunica cu baza de date și pentru a procesa datele primite de la frontend. Backend-u este responsabil pentru următoarele funcționalități:
    <ol>
        <li>Interacțiunea cu baza de date: Backend-ul trebuie să comunice cu baza de date pentru a obține datele privind Consumer Confidence Index și pentru a efectua operațiile de inserare, actualizare sau ștergere a datelor în baza de date</li>
        <li>Gestionarea cererilor de la frontend: Backend-ul trebuie să primească și să răspundă la cererile primite de la frontend,
          fie că este vorba de cereri pentru afișarea datelor, filtrarea sau sortarea datelor, sau cereri pentru exportul datelor în formatele CSV, WebP sau SVG.</li>
        <li>Generarea datelor necesare pentru afișarea paginilor:  Backend-ul trebuie să proceseze datele primite de la baza de date și să le pregătească pentru a fi afișate în frontend. Acest lucru poate include transformarea datelor în formatul potrivit pentru diverse tipuri de grafice sau pentru a fi afișate într-un tabel, precum și aplicarea de filtre sau sortări asupra datelor.</li>
        <li>Autentificarea administratorilor</li>
        <li>Validarea datelor: Backend-ul trebuie să valideze datele primite de la frontend pentru a se asigura că acestea sunt corecte și complete,
          înainte de a le procesa sau de a le stoca în baza de date. Validarea datelor poate include verificarea formatului datelor,
          a limitelor de valori acceptate sau a oricăror reguli specifice legate de Consumer Confidence Index.</li>
  </ol>
  <h3><span> 5.2 </span> Charts</h3>
  Aplicatia permite vizualizarea a 5 tipuri de reprezentari grafice (realizate prin intermediul Google Charts):
  <ol>
    <li>Map</li>
    <li>Table</li>
    <li>Bar Chart</li>
    <li>Combo Chart</li>
    <li>Line Chart</li>
  </ol>
  Utilizatorul va primi o lista adaptata inputului sau (luna, an, tara). In functie de input, se va afisa o lista de reprezentari grafice disponibile.
  Reprezentarile grafice se randeaza si afiseaza in timp real (prin requesturi la API si parsarea datelor corespunzatoare). Orice modificari vor fi afisate fara a fi necesara
  reincarcarea paginii.
  In aceeasi maniera adaptiva, fiecare reprezentare grafica poate fi exportata. (i.e. un tabel va putea fi exportat doar in format csv). Formatele disponibile sunt:
  <ol>
    <li>CSV : se realizeaza prin manipularea informatiilor din tabel si inserarea de virgula</li>
    <li>WEBP: se realizeaza prin capturarea canvas-ului pe care a fost "desenata" reprezentarea</li>
    <li>SVG : se realizeaza prin serializarea si transformarea in xml a reprezentarii (vectorizare)</li>
  </ol>
  <h3><span> 5.3 </span> Manipularea inputului de la user</h3>
  In cadrul aplicatiei, utilizatorul se poate decide asupra 3 campuri:
  <ol>
    <li> Tarile pentru care doreste sa vizualizeze informatiile</li>
    <li> Anul si luna pentru care doreste sa vizualizeze informatiile</li>
    <li> Modul de vizualizare (sugerat)</li>
  </ol>

  <h3><span> 5.4 </span> Frontend and design</h3>
  Pentru realizarea designului aplicatiei, am folosit HTML5, CSS si Javascript. Designul este simplu si potrivit pentru functionalitatea aplicatiei.


</section>
<section id="user">
  <h2><span>6. </span>Experiența utilizatorului</h2>
  <ol>
    <li>Site-ul are un design minimalist, ceea ce îl face ușor de folosit de catre un utilizator. </li>
    <li>Structura site-ului este una simplă și intuitivă. Pe pagina de landing, utilizatorul are acces la toate funcționalitățile site-ului. </li>
    <li>Utilizatorul poate naviga între paginile site-ului foarte ușor, folosind bara de navigare. </li>
    <li>Pentru a vizualiza diagramele, tabelele și harta nu este nevoie de crearea unui cont. De asemenea, acestea pot fi salvate în diferite formate pentru ca utilizatorul să le poată distribui mai departe sau pentru a putea fi vizualizate mai târziu.</li>
  </ol>
</section>
<section id="diagrame">
  <h2><span>7. </span>Diagrame</h2>
  
    Produsul final este o platforma educativa, mai exact o aplicatie web open-source ce functioneaza independent si este destinata uzului general, fiind dezvoltata pe baza celor doua componente majore amintite mai sus: FRONTEND si BACKEND.
    <p> Mai jos este atasata diagrama generala a aplicatiei ce ilustreaza componentele principale din care este alcatuita: </p>
    <img src="../img/diagram2.png" alt="Image not found">
 
    <p> A doua diagrama ilustreaza functionalitatea aplicatiei intr-un mod mult mai detaliat, oferind o imagine de ansamblu precisa si completa, astfel incat 
      sa creasca nivelul de incredere si de satisfactie al utilizatorului si sa ii permita folosirea aplicației in mod eficient, pentru a beneficia de toate caracteristicile. </p>
    <img src="../img/diagram1.png" alt="Image not found">
</section>
<section id="autori">
  <h2><span>8. </span>Autori</h2>
  <ul>
    <li>Olaru Ana</li>
    <li>Olaru Andreea</li>
    <li>Popa Liliana</li>
  </ul>
</section>
<section id="github">
  <h2><span>9. </span>GitHub Repository</h2>
  <a href="https://github.com/LilianaPopa-stud/Proiect_TW">Click</a>
</section>
<section id="resurse">
  <h2><span>10. </span>Resurse</h2>
  <p class="issue">
    <a href=https://developers.google.com/chart>Google Charts documentation</a>
  </p>
  <p class="issue">
    <a href="https://profs.info.uaic.ro/~busaco/teach/courses/web/web-film.html">Cursuri Tehnologii Web</a>
  </p>
  <p class="issue">
    <a href=https://w3c.github.io/scholarly-html/#semantics>Template Scholarly</a>
  </p>
</section>


</body>
</html>
