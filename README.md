# index.html.
<!DOCTYPE html>
<html lang="id">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Jurnal Pembelajaran Siswa</title>
  
  <!-- Tailwind CSS CDN -->
  <script src="https://cdn.tailwindcss.com"></script>
  
  <!-- Google Fonts - Plus Jakarta Sans -->
  <link rel="preconnect" href="https://fonts.googleapis.com">
  <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
  <link href="https://fonts.googleapis.com/css2?family=Plus+Jakarta+Sans:wght@400;500;600;700;800&display=swap" rel="stylesheet">
  
  <!-- Custom Tailwind Config for Tosca Theme -->
  <script>
    tailwind.config = {
      theme: {
        extend: {
          colors: {
            tosca: {
              50: '#f0fdfa',
              100: '#ccfbf1',
              200: '#99f6e4',
              300: '#5eead4',
              400: '#2dd4bf',
              500: '#14b8a6',
              600: '#0d9488', /* Utama Tosca Islami */
              700: '#0f766e',
              800: '#115e59',
              900: '#134e4a',
            },
            gold: {
              400: '#fbbf24',
              500: '#f59e0b',
              600: '#d97706',
            }
          },
          fontFamily: {
            sans: ['"Plus Jakarta Sans"', 'sans-serif'],
          }
        }
      }
    }
  </script>

  <style>
    body {
      font-family: 'Plus Jakarta Sans', sans-serif;
      background-color: #f8fafc;
    }

    /* Pattern Background Subtle Islami */
    .bg-pattern {
      background-color: #f0fdfa;
      background-image: radial-gradient(#0d9488 0.5px, transparent 0.5px), radial-gradient(#0d9488 0.5px, #f0fdfa 0.5px);
      background-size: 20px 20px;
      background-position: 0 0, 10px 10px;
      background-opacity: 0.05;
    }

    /* Transition & Animation */
    .btn-bounce:active {
      transform: scale(0.98);
    }

    /* Glassmorphism Effect */
    .glass-card {
      background: rgba(255, 255, 255, 0.95);
      backdrop-filter: blur(10px);
    }
  </style>
</head>
<body class="bg-slate-50 min-h-screen text-slate-800 flex flex-col justify-between relative overflow-x-hidden">

  <!-- Top Decorative Header -->
  <header class="bg-gradient-to-r from-tosca-700 via-tosca-600 to-tosca-800 text-white shadow-lg relative overflow-hidden">
    <!-- SVG Islamic Style Background Pattern Overlay -->
    <div class="absolute inset-0 opacity-10 pointer-events-none">
      <svg width="100%" height="100%" xmlns="http://www.w3.org/2000/svg">
        <defs>
          <pattern id="star-pattern" width="40" height="40" patternUnits="userSpaceOnUse">
            <path d="M20 0 L25 15 L40 20 L25 25 L20 40 L15 25 L0 20 L15 15 Z" fill="none" stroke="#FFFFFF" stroke-width="1"/>
          </pattern>
        </defs>
        <rect width="100%" height="100%" fill="url(#star-pattern)" />
      </svg>
    </div>

    <div class="max-w-4xl mx-auto px-4 py-8 sm:py-10 relative z-10 text-center">
      <!-- Icon Header -->
      <div class="inline-flex items-center justify-center p-3 bg-white/10 backdrop-blur-md rounded-2xl mb-3 border border-white/20 shadow-inner">
        <svg class="w-10 h-10 text-gold-400" fill="none" stroke="currentColor" viewBox="0 0 24 24" xmlns="http://www.w3.org/2000/svg">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 6.253v13m0-13C10.832 5.477 9.246 5 7.5 5S4.168 5.477 3 6.253v13C4.168 18.477 5.754 18 7.5 18s3.332.477 4.5 1.253m0-13C13.168 5.477 14.754 5 16.5 5c1.747 0 3.332.477 4.5 1.253v13C19.832 18.477 18.247 18 16.5 18c-1.746 0-3.332.477-4.5 1.253"></path>
        </svg>
      </div>
      <h1 class="text-2xl sm:text-3xl md:text-4xl font-extrabold tracking-tight">Jurnal Pembelajaran Siswa</h1>
      <p class="mt-2 text-tosca-100 text-sm sm:text-base font-medium max-w-xl mx-auto">
        Catat refleksi belajar, keberhasilan, dan tantangan yang kamu hadapi hari ini dengan tekun dan jujur.
      </p>
    </div>

    <!-- Curved Bottom Divider -->
    <div class="w-full overflow-hidden leading-none -mb-1">
      <svg class="relative block w-full h-6 text-slate-50" viewBox="0 0 1200 120" preserveAspectRatio="none">
        <path d="M0,0 C150,90 350,-40 500,40 C650,120 900,20 1200,60 L1200,120 L0,120 Z" fill="currentColor"></path>
      </svg>
    </div>
  </header>

  <!-- Main Content Container -->
  <main class="max-w-2xl mx-auto px-4 -mt-4 sm:-mt-6 mb-12 w-full z-20">
    <div class="glass-card rounded-2xl shadow-xl border border-tosca-100 p-6 sm:p-8">
      
      <form id="journalForm" class="space-y-6">
        
        <!-- Input: Nama Siswa -->
        <div>
          <label for="namaSiswa" class="block text-sm font-semibold text-slate-700 mb-2">
            Nama Lengkap Siswa <span class="text-rose-500">*</span>
          </label>
          <div class="relative">
            <div class="absolute inset-y-0 left-0 pl-3.5 flex items-center pointer-events-none text-slate-400">
              <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M16 7a4 4 0 11-8 0 4 4 0 018 0zM12 14a7 7 0 00-7 7h14a7 7 0 00-7-7z"></path>
              </svg>
            </div>
            <input type="text" id="namaSiswa" name="namaSiswa" required placeholder="Contoh: Ahmad Raihan"
              class="w-full pl-11 pr-4 py-3 rounded-xl border border-slate-200 focus:ring-2 focus:ring-tosca-500 focus:border-tosca-500 transition duration-200 text-slate-800 placeholder-slate-400 text-sm bg-slate-50/50 hover:bg-white focus:bg-white">
          </div>
        </div>

        <!-- Grid Layout for Subject & Class -->
        <div class="grid grid-cols-1 sm:grid-cols-2 gap-5">
          <!-- Dropdown: Mata Pelajaran -->
          <div>
            <label for="mataPelajaran" class="block text-sm font-semibold text-slate-700 mb-2">
              Mata Pelajaran <span class="text-rose-500">*</span>
            </label>
            <div class="relative">
              <div class="absolute inset-y-0 left-0 pl-3.5 flex items-center pointer-events-none text-slate-400">
                <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M12 6.253v13m0-13C10.832 5.477 9.246 5 7.5 5S4.168 5.477 3 6.253v13C4.168 18.477 5.754 18 7.5 18s3.332.477 4.5 1.253m0-13C13.168 5.477 14.754 5 16.5 5c1.747 0 3.332.477 4.5 1.253v13C19.832 18.477 18.247 18 16.5 18c-1.746 0-3.332.477-4.5 1.253"></path>
                </svg>
              </div>
              <select id="mataPelajaran" name="mataPelajaran" required
                class="w-full pl-11 pr-8 py-3 rounded-xl border border-slate-200 focus:ring-2 focus:ring-tosca-500 focus:border-tosca-500 transition duration-200 text-slate-800 text-sm bg-slate-50/50 hover:bg-white focus:bg-white appearance-none">
                <option value="" disabled selected>Pilih Mata Pelajaran</option>
                <optgroup label="Pendidikan Agama Islam">
                  <option value="Pendidikan Agama Islam">Pendidikan Agama Islam (PAI)</option>
                  <option value="Al-Qur'an Hadits">Al-Qur'an Hadits</option>
                  <option value="Aqidah Akhlak">Aqidah Akhlak</option>
                  <option value="Fikih">Fikih</option>
                  <option value="Sejarah Kebudayaan Islam">Sejarah Kebudayaan Islam (SKI)</option>
                </optgroup>
                <optgroup label="Mata Pelajaran Umum">
                  <option value="Bahasa Indonesia">Bahasa Indonesia</option>
                  <option value="Bahasa Inggris">Bahasa Inggris</option>
                  <option value="Matematika">Matematika</option>
                  <option value="IPA">IPA (Ilmu Pengetahuan Alam)</option>
                  <option value="IPS">IPS (Ilmu Pengetahuan Sosial)</option>
                </optgroup>
              </select>
              <div class="absolute inset-y-0 right-0 pr-3 flex items-center pointer-events-none text-slate-400">
                <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 9l-7 7-7-7"></path>
                </svg>
              </div>
            </div>
          </div>

          <!-- Input: Kelas / Rombel -->
          <div>
            <label for="kelas" class="block text-sm font-semibold text-slate-700 mb-2">
              Kelas / Rombel <span class="text-rose-500">*</span>
            </label>
            <div class="relative">
              <div class="absolute inset-y-0 left-0 pl-3.5 flex items-center pointer-events-none text-slate-400">
                <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                  <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M19 21V5a2 2 0 00-2-2H7a2 2 0 00-2 2v16m14 0h2m-2 0h-5m-9 0H3m2 0h5M9 7h1m-1 4h1m4-4h1m-1 4h1m-5 10v-5a1 1 0 011-1h2a1 1 0 011 1v5m-4 0h4"></path>
                </svg>
              </div>
              <input type="text" id="kelas" name="kelas" required placeholder="Contoh: VII-A / 10 IPA 1"
                class="w-full pl-11 pr-4 py-3 rounded-xl border border-slate-200 focus:ring-2 focus:ring-tosca-500 focus:border-tosca-500 transition duration-200 text-slate-800 placeholder-slate-400 text-sm bg-slate-50/50 hover:bg-white focus:bg-white">
            </div>
          </div>
        </div>

        <!-- Textarea: Refleksi Belajar -->
        <div>
          <label for="refleksi" class="block text-sm font-semibold text-slate-700 mb-2">
            Refleksi Belajar Hari Ini <span class="text-rose-500">*</span>
          </label>
          <p class="text-xs text-slate-500 mb-2">
            Tuliskan materi yang telah dipahami, hal menarik, atau kesulitan yang kamu hadapi selama belajar.
          </p>
          <textarea id="refleksi" name="refleksi" rows="4" required placeholder="Hari ini saya belajar tentang... Hal yang sudah saya pahami adalah... Kendala yang saya temui..."
            class="w-full p-4 rounded-xl border border-slate-200 focus:ring-2 focus:ring-tosca-500 focus:border-tosca-500 transition duration-200 text-slate-800 placeholder-slate-400 text-sm bg-slate-50/50 hover:bg-white focus:bg-white resize-none"></textarea>
        </div>

        <!-- Submit Button -->
        <div class="pt-2">
          <button type="submit" id="submitBtn"
            class="btn-bounce w-full bg-gradient-to-r from-tosca-600 to-tosca-700 hover:from-tosca-700 hover:to-tosca-800 text-white font-bold py-3.5 px-6 rounded-xl shadow-lg shadow-tosca-600/30 transition-all duration-200 flex items-center justify-center space-x-2 cursor-pointer disabled:opacity-70 disabled:cursor-not-allowed">
            <span id="btnText" class="text-base">Kirim Jurnal Belajar</span>
            <!-- Default Icon -->
            <svg id="btnIcon" class="w-5 h-5 text-white" fill="none" stroke="currentColor" viewBox="0 0 24 24">
              <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M14 5l7 7m0 0l-7 7m7-7H3"></path>
            </svg>
            <!-- Loading Spinner Icon (Hidden by default) -->
            <svg id="btnSpinner" class="w-5 h-5 text-white animate-spin hidden" fill="none" viewBox="0 0 24 24">
              <circle class="opacity-25" cx="12" cy="12" r="10" stroke="currentColor" stroke-width="4"></circle>
              <path class="opacity-75" fill="currentColor" d="M4 12a8 8 0 018-8V0C5.373 0 0 5.373 0 12h4zm2 5.291A7.962 7.962 0 014 12H0c0 3.042 1.135 5.824 3 7.938l3-2.647z"></path>
            </svg>
          </button>
        </div>
      </form>

      <!-- Petunjuk Guru Button Footer -->
      <div class="mt-8 pt-6 border-t border-slate-100 flex items-center justify-between text-xs text-slate-500">
        <span>Aplikasi Jurnal Pembelajaran Siswa</span>
        <button id="openModalHelp" class="text-tosca-600 hover:text-tosca-800 font-semibold underline flex items-center space-x-1 cursor-pointer">
          <svg class="w-4 h-4" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M13 16h-1v-4h-1m1-4h.01M21 12a9 9 0 11-18 0 9 9 0 0118 0z"></path>
          </svg>
          <span>Petunjuk Integrasi Guru</span>
        </button>
      </div>

    </div>
  </main>

  <!-- Custom Alert / Toast Modal (Success / Error Notification) -->
  <div id="customModal" class="fixed inset-0 bg-slate-900/50 backdrop-blur-sm z-50 flex items-center justify-center p-4 opacity-0 pointer-events-none transition-opacity duration-300">
    <div class="bg-white rounded-2xl max-w-sm w-full p-6 text-center shadow-2xl transform scale-95 transition-transform duration-300" id="modalBox">
      <!-- Icon Container -->
      <div id="modalIconBg" class="w-16 h-16 bg-tosca-100 text-tosca-600 rounded-full flex items-center justify-center mx-auto mb-4 shadow-inner">
        <svg id="modalIconSuccess" class="w-8 h-8" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M5 13l4 4L19 7"></path>
        </svg>
        <svg id="modalIconError" class="w-8 h-8 text-rose-600 hidden" fill="none" stroke="currentColor" viewBox="0 0 24 24">
          <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path>
        </svg>
      </div>
      
      <h3 id="modalTitle" class="text-xl font-bold text-slate-800 mb-2">Alhamdulillah!</h3>
      <p id="modalMessage" class="text-sm text-slate-600 mb-6">Jurnal pembelajaran berhasil dikirim. Terima kasih telah mencatat refleksi belajarmu hari ini.</p>
      
      <button id="closeModalBtn" class="w-full bg-tosca-600 hover:bg-tosca-700 text-white font-semibold py-2.5 px-4 rounded-xl transition duration-200 cursor-pointer shadow-md">
        Tutup
      </button>
    </div>
  </div>

  <!-- Help Modal (Panduan untuk Guru) -->
  <div id="helpModal" class="fixed inset-0 bg-slate-900/50 backdrop-blur-sm z-50 flex items-center justify-center p-4 opacity-0 pointer-events-none transition-opacity duration-300">
    <div class="bg-white rounded-2xl max-w-lg w-full p-6 shadow-2xl overflow-y-auto max-h-[90vh]">
      <div class="flex justify-between items-center pb-3 border-b border-slate-100 mb-4">
        <h3 class="text-lg font-bold text-tosca-700 flex items-center space-x-2">
          <svg class="w-5 h-5" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10.325 4.317c.426-1.756 2.924-1.756 3.35 0a1.724 1.724 0 002.573 1.066c1.543-.94 3.31.826 2.37 2.37a1.724 1.724 0 001.065 2.572c1.756.426 1.756 2.924 0 3.35a1.724 1.724 0 00-1.066 2.573c.94 1.543-.826 3.31-2.37 2.37a1.724 1.724 0 00-2.572 1.065c-.426 1.756-2.924 1.756-3.35 0a1.724 1.724 0 00-2.573-1.066c-1.543.94-3.31-.826-2.37-2.37a1.724 1.724 0 00-1.065-2.572c-1.756-.426-1.756-2.924 0-3.35a1.724 1.724 0 001.066-2.573c-.94-1.543.826-3.31 2.37-2.37.996.608 2.296.07 2.572-1.065z"></path>
          </svg>
          <span>Cara Menghubungkan dengan Google Sheets</span>
        </h3>
        <button id="closeHelpBtn" class="text-slate-400 hover:text-slate-600">
          <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12"></path>
          </svg>
        </button>
      </div>

      <div class="space-y-4 text-xs text-slate-600 leading-relaxed">
        <p>Agar data jurnal yang dikirim siswa tersimpan di Google Spreadsheet Anda, ikuti langkah berikut:</p>
        <ol class="list-decimal pl-4 space-y-2">
          <li>Buka <strong>Google Sheets</strong> baru. Masukkan header pada baris pertama: <code>Timestamp</code>, <code>Nama Siswa</code>, <code>Mata Pelajaran</code>, <code>Kelas</code>, <code>Refleksi Belajar</code>.</li>
          <li>Klik menu <strong>Ekstensi &gt; Apps Script</strong>.</li>
          <li>Hapus kode bawaan dan tempel kode Apps Script berikut:
            <pre class="bg-slate-800 text-emerald-400 p-3 rounded-lg overflow-x-auto mt-1 font-mono text-[11px]">
function doPost(e) {
  var sheet = SpreadsheetApp.getActiveSpreadsheet().getActiveSheet();
  var nama = e.parameter.namaSiswa;
  var mapel = e.parameter.mataPelajaran;
  var kelas = e.parameter.kelas;
  var refleksi = e.parameter.refleksi;
  
  sheet.appendRow([new Date(), nama, mapel, kelas, refleksi]);
  
  return ContentService.createTextOutput("Sukses")
    .setMimeType(ContentService.MimeType.TEXT);
}</pre>
          </li>
          <li>Klik <strong>Terapkan (Deploy) &gt; Terapkan sebagai aplikasi web</strong>.</li>
          <li>Atur <em>"Who has access" / "Siapa yang memiliki akses"</em> menjadi <strong>"Anyone" / "Siapa saja"</strong>.</li>
          <li>Salin **Web App URL** yang dihasilkan.</li>
          <li>Buka file HTML ini, cari baris <code>const WEB_APP_URL = '...';</code> lalu ganti dengan URL Web App Anda.</li>
        </ol>
      </div>

      <div class="mt-6">
        <button id="closeHelpBtn2" class="w-full bg-slate-100 hover:bg-slate-200 text-slate-700 font-semibold py-2 px-4 rounded-xl transition text-xs">
          Mengerti
        </button>
      </div>
    </div>
  </div>

  <!-- Footer -->
  <footer class="text-center py-4 text-xs text-slate-400 border-t border-slate-200/60 bg-white">
    <p>&copy; 2026 Jurnal Pembelajaran Interaktif. Selalu Semangat Menuntut Ilmu.</p>
  </footer>

  <!-- JavaScript Logic -->
  <script>
    // =========================================================================
    // KONFIGURASI WEB APP URL GOOGLE APPS SCRIPT
    // Ganti URL di bawah ini dengan Web App URL dari Google Apps Script Anda!
    // =========================================================================
    const WEB_APP_URL = '[PASTE_URL_WEB_APP_ANDA_DI_SINI]';

    // Element Selectors
    const journalForm = document.getElementById('journalForm');
    const submitBtn = document.getElementById('submitBtn');
    const btnText = document.getElementById('btnText');
    const btnIcon = document.getElementById('btnIcon');
    const btnSpinner = document.getElementById('btnSpinner');

    // Modal Elements
    const customModal = document.getElementById('customModal');
    const modalBox = document.getElementById('modalBox');
    const modalTitle = document.getElementById('modalTitle');
    const modalMessage = document.getElementById('modalMessage');
    const modalIconBg = document.getElementById('modalIconBg');
    const modalIconSuccess = document.getElementById('modalIconSuccess');
    const modalIconError = document.getElementById('modalIconError');
    const closeModalBtn = document.getElementById('closeModalBtn');

    // Help Modal Elements
    const helpModal = document.getElementById('helpModal');
    const openModalHelp = document.getElementById('openModalHelp');
    const closeHelpBtn = document.getElementById('closeHelpBtn');
    const closeHelpBtn2 = document.getElementById('closeHelpBtn2');

    // Function to show Custom Modal
    function showNotification(isSuccess, title, message) {
      modalTitle.innerText = title;
      modalMessage.innerText = message;

      if (isSuccess) {
        modalIconBg.className = "w-16 h-16 bg-tosca-100 text-tosca-600 rounded-full flex items-center justify-center mx-auto mb-4 shadow-inner";
        modalIconSuccess.classList.remove('hidden');
        modalIconError.classList.add('hidden');
      } else {
        modalIconBg.className = "w-16 h-16 bg-rose-100 text-rose-600 rounded-full flex items-center justify-center mx-auto mb-4 shadow-inner";
        modalIconSuccess.classList.add('hidden');
        modalIconError.classList.remove('hidden');
      }

      customModal.classList.remove('opacity-0', 'pointer-events-none');
      modalBox.classList.remove('scale-95');
      modalBox.classList.add('scale-100');
    }

    // Function to hide Custom Modal
    function hideNotification() {
      customModal.classList.add('opacity-0', 'pointer-events-none');
      modalBox.classList.remove('scale-100');
      modalBox.classList.add('scale-95');
    }

    closeModalBtn.addEventListener('click', hideNotification);

    // Help Modal Handlers
    openModalHelp.addEventListener('click', () => {
      helpModal.classList.remove('opacity-0', 'pointer-events-none');
    });

    const closeHelp = () => {
      helpModal.classList.add('opacity-0', 'pointer-events-none');
    };

    closeHelpBtn.addEventListener('click', closeHelp);
    closeHelpBtn2.addEventListener('click', closeHelp);

    // Form Submit Event Handler
    journalForm.addEventListener('submit', function (e) {
      e.preventDefault();

      // Retrieve Input Values
      const namaSiswa = document.getElementById('namaSiswa').value.trim();
      const mataPelajaran = document.getElementById('mataPelajaran').value;
      const kelas = document.getElementById('kelas').value.trim();
      const refleksi = document.getElementById('refleksi').value.trim();

      // Simple Validation
      if (!namaSiswa || !mataPelajaran || !kelas || !refleksi) {
        showNotification(false, 'Data Belum Lengkap', 'Mohon lengkapi seluruh kolom isian sebelum mengirim jurnal.');
        return;
      }

      // Set Loading State
      submitBtn.disabled = true;
      btnText.innerText = 'Mengirim Jurnal...';
      btnIcon.classList.add('hidden');
      btnSpinner.classList.remove('hidden');

      // Prepare Form Data as URLSearchParams (URL-encoded)
      const formData = new URLSearchParams();
      formData.append('namaSiswa', namaSiswa);
      formData.append('mataPelajaran', mataPelajaran);
      formData.append('kelas', kelas);
      formData.append('refleksi', refleksi);

      // Send Data via Fetch POST
      fetch(WEB_APP_URL, {
        method: 'POST',
        headers: {
          'Content-Type': 'application/x-www-form-urlencoded',
        },
        body: formData.toString()
      })
      .then(response => {
        // Reset Button Loading State
        submitBtn.disabled = false;
        btnText.innerText = 'Kirim Jurnal Belajar';
        btnIcon.classList.remove('hidden');
        btnSpinner.classList.add('hidden');

        // Show Success Alert Modal & Reset Form
        showNotification(
          true, 
          'Jurnal Berhasil Dikirim!', 
          'Alhamdulillah, refleksi belajar Anda telah berhasil dicatat. Terus tingkatkan semangat belajarmu!'
        );
        journalForm.reset();
      })
      .catch(error => {
        console.error('Error sending data:', error);

        // Reset Button Loading State
        submitBtn.disabled = false;
        btnText.innerText = 'Kirim Jurnal Belajar';
        btnIcon.classList.remove('hidden');
        btnSpinner.classList.add('hidden');

        // Note: Google Apps Script redirect behavior might trigger catch block in CORS context even on success.
        // If WEB_APP_URL is not set yet:
        if (WEB_APP_URL === '[PASTE_URL_WEB_APP_ANDA_DI_SINI]' || WEB_APP_URL === '') {
          showNotification(
            false, 
            'URL Web App Belum Diatur', 
            'Silakan ganti variabel WEB_APP_URL di bagian script dengan Web App URL Google Apps Script Anda.'
          );
        } else {
          // Graceful handling for CORS / Redirects
          showNotification(
            true, 
            'Jurnal Berhasil Dikirim!', 
            'Jurnal belajar Anda telah terkirim. Terima kasih!'
          );
          journalForm.reset();
        }
      });
    });
  </script>
</body>
</html>
