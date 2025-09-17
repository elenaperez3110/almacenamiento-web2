# almacenamiento-web2
Web estática educativa sobre tipos de almacenamiento de datos
<!doctype html>
<html lang="es">
<head>
  <meta charset="utf-8" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  <title>Almacenamiento de datos — Guía educativa</title>
  <meta name="description" content="Web educativa estática sobre tipos de almacenamiento de datos: bloque, archivo, objeto y columna; comparativas, glosario y quiz." />
  <link rel="icon" href="data:image/svg+xml,<svg xmlns=%22http://www.w3.org/2000/svg%22 viewBox=%220 0 100 100%22><text y=%22.9em%22 font-size=%2290%22>💾</text></svg>">
  <!-- Tailwind via CDN (sin build) -->
  <script src="https://cdn.tailwindcss.com"></script>
  <style>
    /* Ajustes mínimos extra si los necesitas */
    .visually-hidden { position:absolute; width:1px; height:1px; padding:0; margin:-1px; overflow:hidden; clip:rect(0,0,0,0); white-space:nowrap; border:0; }
  </style>
</head>
<body class="bg-slate-50 text-slate-900 antialiased">
  <!-- Header -->
  <header class="bg-white border-b border-slate-200">
    <div class="max-w-6xl mx-auto px-4 py-4 flex items-center justify-between">
      <a href="#" class="text-xl font-bold tracking-tight">Almacenamiento de datos</a>
      <nav aria-label="Principal" class="hidden sm:block">
        <ul class="flex gap-6 text-sm">
          <li><a class="hover:underline" href="#filtro">Filtro</a></li>
          <li><a class="hover:underline" href="#tarjetas">Tarjetas</a></li>
          <li><a class="hover:underline" href="#comparativa">Tabla comparativa</a></li>
          <li><a class="hover:underline" href="#glosario">Glosario</a></li>
          <li><a class="hover:underline" href="#quiz">Quiz</a></li>
        </ul>
      </nav>
    </div>
  </header>

  <main id="content" class="max-w-6xl mx-auto px-4 py-8">
    <section class="mb-8">
      <h1 class="text-3xl font-bold mb-2">Guía rápida de tipos de almacenamiento</h1>
      <p class="text-slate-700">Aprende a distinguir <strong>bloque</strong>, <strong>archivo</strong>, <strong>objeto</strong> y <strong>columna</strong>; compara sus propiedades y valida lo aprendido con un pequeño quiz.</p>
    </section>

    <!-- FILTRO -->
    <section id="filtro" class="mb-12">
      <h2 class="text-2xl font-semibold mb-4">Filtro de contenidos</h2>
      <form class="grid sm:grid-cols-2 lg:grid-cols-4 gap-4 items-end" aria-describedby="filtro-ayuda">
        <div>
          <label for="search" class="block text-sm font-medium mb-1">Buscar por texto</label>
          <input id="search" type="search" placeholder="latencia, objetos, POSIX…" class="w-full rounded-md border border-slate-300 px-3 py-2 shadow-sm focus:outline-none focus:ring focus:ring-sky-200" />
        </div>
        <fieldset class="sm:col-span-2">
          <legend class="block text-sm font-medium mb-1">Tipo</legend>
          <div class="flex flex-wrap gap-3">
            <label class="inline-flex items-center gap-2">
              <input type="checkbox" class="filter-type rounded" value="bloque" checked>
              <span>Bloque</span>
            </label>
            <label class="inline-flex items-center gap-2">
              <input type="checkbox" class="filter-type rounded" value="archivo" checked>
              <span>Archivo</span>
            </label>
            <label class="inline-flex items-center gap-2">
              <input type="checkbox" class="filter-type rounded" value="objeto" checked>
              <span>Objeto</span>
            </label>
            <label class="inline-flex items-center gap-2">
              <input type="checkbox" class="filter-type rounded" value="columna" checked>
              <span>Columna</span>
            </label>
          </div>
        </fieldset>
        <div class="flex gap-3">
          <button type="button" id="btnClear" class="rounded-md bg-slate-200 px-3 py-2 text-sm hover:bg-slate-300">Limpiar</button>
          <button type="button" id="btnReset" class="rounded-md bg-sky-600 px-3 py-2 text-sm text-white hover:bg-sky-700">Restablecer</button>
        </div>
      </form>
      <p id="filtro-ayuda" class="text-xs text-slate-500 mt-2">El filtro afecta a las tarjetas de abajo.</p>
    </section>

    <!-- TARJETAS -->
    <section id="tarjetas" class="mb-16">
      <h2 class="text-2xl font-semibold mb-6">Tarjetas por tipo</h2>
      <div id="cardsGrid" class="grid sm:grid-cols-2 lg:grid-cols-4 gap-6">
        <!-- Bloque -->
        <article class="card rounded-xl border border-slate-200 bg-white p-4 shadow-sm"
          data-type="bloque" data-tags="latencia baja, iops, bases de datos, vm, san">
          <div class="text-3xl mb-2">🧱</div>
          <h3 class="font-semibold text-lg">Bloque</h3>
          <p class="text-sm text-slate-700">Direcciones de bloques sin sistema de archivos. Ideal para <strong>bases de datos</strong> y <strong>VMs</strong> por su baja latencia y alto IOPS.</p>
          <ul class="mt-3 text-sm list-disc ml-5">
            <li>Latencia: muy baja</li>
            <li>Acceso: por bloques</li>
            <li>Ejemplos: iSCSI, FC, NVMe-oF</li>
          </ul>
        </article>

        <!-- Archivo -->
        <article class="card rounded-xl border border-slate-200 bg-white p-4 shadow-sm"
          data-type="archivo" data-tags="posix, home, nfs, smb, compartido">
          <div class="text-3xl mb-2">📁</div>
          <h3 class="font-semibold text-lg">Archivo</h3>
          <p class="text-sm text-slate-700">Estructura de directorios y archivos. Conveniente para <strong>colaboración</strong> y acceso POSIX.</p>
          <ul class="mt-3 text-sm list-disc ml-5">
            <li>Latencia: baja</li>
            <li>Acceso: por rutas</li>
            <li>Ejemplos: NFS, SMB</li>
          </ul>
        </article>

        <!-- Objeto -->
        <article class="card rounded-xl border border-slate-200 bg-white p-4 shadow-sm"
          data-type="objeto" data-tags="s3, http, escalabilidad, lago de datos, multimedia, backup">
          <div class="text-3xl mb-2">🪣</div>
          <h3 class="font-semibold text-lg">Objeto</h3>
          <p class="text-sm text-slate-700">Datos como objetos con metadatos y <em>bucket</em>. Escala masiva, acceso por API/HTTP.</p>
          <ul class="mt-3 text-sm list-disc ml-5">
            <li>Latencia: media</li>
            <li>Acceso: por clave</li>
            <li>Ejemplos: S3, GCS, Azure Blob</li>
          </ul>
        </article>

        <!-- Columna -->
        <article class="card rounded-xl border border-slate-200 bg-white p-4 shadow-sm"
          data-type="columna" data-tags="analítica, compresión, lectura masiva, columnar, parquet, orc">
          <div class="text-3xl mb-2">📊</div>
          <h3 class="font-semibold text-lg">Columna</h3>
          <p class="text-sm text-slate-700">Diseñado para análisis: almacena por columnas para comprimir y escanear más rápido.</p>
          <ul class="mt-3 text-sm list-disc ml-5">
            <li>Latencia: orientado a lectura analítica</li>
            <li>Acceso: por columnas</li>
            <li>Ejemplos: Parquet, ORC, ClickHouse</li>
          </ul>
        </article>
      </div>
      <p id="emptyMsg" class="hidden mt-6 text-sm text-slate-500">No hay resultados con el filtro actual.</p>
    </section>

    <!-- TABLA COMPARATIVA -->
    <section id="comparativa" class="mb-16">
      <h2 class="text-2xl font-semibold mb-4">Tabla comparativa</h2>
      <div class="overflow-x-auto rounded-xl border border-slate-200 bg-white">
        <table class="min-w-full text-sm">
          <thead class="bg-slate-100">
            <tr>
              <th class="px-4 py-3 text-left font-semibold">Criterio</th>
              <th class="px-4 py-3 text-left font-semibold">Bloque</th>
              <th class="px-4 py-3 text-left font-semibold">Archivo</th>
              <th class="px-4 py-3 text-left font-semibold">Objeto</th>
              <th class="px-4 py-3 text-left font-semibold">Columna</th>
            </tr>
          </thead>
          <tbody>
            <tr class="border-t">
              <td class="px-4 py-3">Latencia</td>
              <td class="px-4 py-3">Muy baja</td>
              <td class="px-4 py-3">Baja</td>
              <td class="px-4 py-3">Media</td>
              <td class="px-4 py-3">Alta (batch)</td>
            </tr>
            <tr class="border-t">
              <td class="px-4 py-3">Acceso</td>
              <td class="px-4 py-3">Bloques</td>
              <td class="px-4 py-3">Rutas (POSIX)</td>
              <td class="px-4 py-3">Clave/objeto</td>
              <td class="px-4 py-3">Columnas</td>
            </tr>
            <tr class="border-t">
              <td class="px-4 py-3">Casos típicos</td>
              <td class="px-4 py-3">DBs, VMs</td>
              <td class="px-4 py-3">Home, compartido</td>
              <td class="px-4 py-3">Lago de datos, backups</td>
              <td class="px-4 py-3">BI/Analytics</td>
            </tr>
            <tr class="border-t">
              <td class="px-4 py-3">Escalabilidad</td>
              <td class="px-4 py-3">Media/Alta</td>
              <td class="px-4 py-3">Media</td>
              <td class="px-4 py-3">Muy alta</td>
              <td class="px-4 py-3">Alta (lectura)</td>
            </tr>
            <tr class="border-t">
              <td class="px-4 py-3">Protocolos</td>
              <td class="px-4 py-3">iSCSI, FC, NVMe-oF</td>
              <td class="px-4 py-3">NFS, SMB</td>
              <td class="px-4 py-3">HTTP/S3 API</td>
              <td class="px-4 py-3">Parquet/ORC (formato)</td>
            </tr>
          </tbody>
        </table>
      </div>
    </section>

    <!-- GLOSARIO -->
    <section id="glosario" class="mb-16">
      <h2 class="text-2xl font-semibold mb-4">Glosario</h2>
      <dl class="grid sm:grid-cols-2 gap-6">
        <div class="p-4 bg-white rounded-xl border border-slate-200">
          <dt class="font-semibold">IOPS</dt>
          <dd class="text-sm text-slate-700">Operaciones de entrada/salida por segundo. Indicador de rapidez para cargas pequeñas.</dd>
        </div>
        <div class="p-4 bg-white rounded-xl border border-slate-200">
          <dt class="font-semibold">Throughput</dt>
          <dd class="text-sm text-slate-700">Cant. de datos transferidos por unidad de tiempo (MB/s, GB/s).</dd>
        </div>
        <div class="p-4 bg-white rounded-xl border border-slate-200">
          <dt class="font-semibold">Latencia</dt>
          <dd class="text-sm text-slate-700">Tiempo de respuesta por operación. Crucial para transaccional.</dd>
        </div>
        <div class="p-4 bg-white rounded-xl border border-slate-200">
          <dt class="font-semibold">Erasure coding</dt>
          <dd class="text-sm text-slate-700">Técnica de protección de datos que distribuye fragmentos con paridad.</dd>
        </div>
        <div class="p-4 bg-white rounded-xl border border-slate-200">
          <dt class="font-semibold">Tiering</dt>
          <dd class="text-sm text-slate-700">Mover datos entre “tiers” (hot/warm/cold) según su uso y coste.</dd>
        </div>
      </dl>
    </section>

    <!-- QUIZ -->
    <section id="quiz" class="mb-24">
      <h2 class="text-2xl font-semibold mb-4">Quiz rápido</h2>
      <form id="quizForm" class="space-y-6">
        <fieldset class="bg-white rounded-xl border border-slate-200 p-4">
          <legend class="font-semibold mb-2">1) ¿Qué tipo elegirías para una base de datos transaccional con alta IOPS?</legend>
          <label class="block"><input type="radio" name="q1" value="bloque" class="mr-2">Bloque</label>
          <label class="block"><input type="radio" name="q1" value="archivo" class="mr-2">Archivo</label>
          <label class="block"><input type="radio" name="q1" value="objeto" class="mr-2">Objeto</label>
          <label class="block"><input type="radio" name="q1" value="columna" class="mr-2">Columna</label>
        </fieldset>

        <fieldset class="bg-white rounded-xl border border-slate-200 p-4">
          <legend class="font-semibold mb-2">2) Necesitas almacenar millones de fotos y servirlas por HTTP.</legend>
          <label class="block"><input type="radio" name="q2" value="bloque" class="mr-2">Bloque</label>
          <label class="block"><input type="radio" name="q2" value="archivo" class="mr-2">Archivo</label>
          <label class="block"><input type="radio" name="q2" value="objeto" class="mr-2">Objeto</label>
          <label class="block"><input type="radio" name="q2" value="columna" class="mr-2">Columna</label>
        </fieldset>

        <fieldset class="bg-white rounded-xl border border-slate-200 p-4">
          <legend class="font-semibold mb-2">3) Quieres acelerar informes de BI que escanean muchas columnas específicas.</legend>
          <label class="block"><input type="radio" name="q3" value="bloque" class="mr-2">Bloque</label>
          <label class="block"><input type="radio" name="q3" value="archivo" class="mr-2">Archivo</label>
          <label class="block"><input type="radio" name="q3" value="objeto" class="mr-2">Objeto</label>
          <label class="block"><input type="radio" name="q3" value="columna" class="mr-2">Columna</label>
        </fieldset>

        <div class="flex items-center gap-3">
          <button type="button" id="btnQuiz" class="rounded-md bg-emerald-600 px-4 py-2 text-white hover:bg-emerald-700">Corregir</button>
          <span id="quizResult" class="text-sm text-slate-700"></span>
        </div>
      </form>
    </section>
  </main>

  <!-- Footer -->
  <footer class="bg-white border-t border-slate-200">
    <div class="max-w-6xl mx-auto px-4 py-6 text-sm text-slate-600">
      © 2025 — CC BY 4.0 · Hecho con Tailwind CDN · Sin build
    </div>
  </footer>

  <!-- JS inline: filtro y quiz -->
  <script>
    // --- Filtro ---
    const searchInput = document.getElementById('search');
    const typeChecks = Array.from(document.querySelectorAll('.filter-type'));
    const cards = Array.from(document.querySelectorAll('.card'));
    const emptyMsg = document.getElementById('emptyMsg');
    const btnClear = document.getElementById('btnClear');
    const btnReset = document.getElementById('btnReset');

    function applyFilter() {
      const q = (searchInput.value || '').toLowerCase().trim();
      const activeTypes = new Set(typeChecks.filter(c => c.checked).map(c => c.value));
      let visibleCount = 0;

      cards.forEach(card => {
        const t = card.dataset.type;
        const tags = (card.dataset.tags || '').toLowerCase();
        const text = (card.innerText || '').toLowerCase();
        const matchesType = activeTypes.has(t);
        const matchesQuery = !q || tags.includes(q) || text.includes(q);
        const show = matchesType && matchesQuery;
        card.style.display = show ? '' : 'none';
        if (show) visibleCount++;
      });

      emptyMsg.classList.toggle('hidden', visibleCount !== 0);
    }

    searchInput?.addEventListener('input', applyFilter);
    typeChecks.forEach(c => c.addEventListener('change', applyFilter));
    btnClear?.addEventListener('click', () => { searchInput.value = ''; applyFilter(); });
    btnReset?.addEventListener('click', () => {
      searchInput.value = '';
      typeChecks.forEach(c => c.checked = true);
      applyFilter();
    });
    applyFilter();

    // --- Quiz ---
    const btnQuiz = document.getElementById('btnQuiz');
    const quizResult = document.getElementById('quizResult');

    btnQuiz?.addEventListener('click', () => {
      const answers = {
        q1: 'bloque',
        q2: 'objeto',
        q3: 'columna'
      };
      let score = 0, total = Object.keys(answers).length;

      for (const q of Object.keys(answers)) {
        const checked = document.querySelector(`input[name="${q}"]:checked`);
        if (checked && checked.value === answers[q]) score++;
      }
      quizResult.textContent = `Puntuación: ${score}/${total} — ${score === total ? '¡Perfecto!' : 'Sigue practicando 😄'}`;
    });
  </script>
</body>
</html>
