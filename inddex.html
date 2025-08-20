<!DOCTYPE html>
<html lang="de">
<head>
   <meta charset="UTF-8">
   <meta name="viewport" content="width=device-width, initial-scale=1.0">
   <title>Autonomes Frühwarnsystem</title>
   <script src="https://cdn.tailwindcss.com"></script>
   <style>
       @import url('https://fonts.googleapis.com/css2?family=Inter:wght@400;500;600;700&display=swap');
       body {
           font-family: 'Inter', sans-serif;
           background-color: #1a1c29;
           color: #e0e0e0;
           padding: 1rem;
           min-height: 100vh;
           display: flex;
           flex-direction: column;
           align-items: center;
       }
       .card {
           background-color: #272a39;
           border-radius: 1.5rem;
           padding: 1.5rem;
           box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
           margin-bottom: 1.5rem;
       }
       .dot {
           width: 1rem;
           height: 1rem;
           border-radius: 50%;
       }
       .status-dot {
           width: 1.5rem;
           height: 1.5rem;
           margin-right: 0.5rem;
       }
       .green { background-color: #4ade80; }
       .yellow { background-color: #facc15; }
       .orange { background-color: #fb923c; }
       .red { background-color: #ef4444; }
       .level-text {
           font-size: 1.5rem;
           font-weight: bold;
       }
       .modal {
           display: none;
           position: fixed;
           z-index: 1000;
           left: 0;
           top: 0;
           width: 100%;
           height: 100%;
           background-color: rgba(0,0,0,0.7);
           justify-content: center;
           align-items: center;
       }
       .modal-content {
           background-color: #272a39;
           padding: 2rem;
           border-radius: 1.5rem;
           width: 90%;
           max-width: 400px;
           text-align: center;
       }
       .modal-close {
           float: right;
           cursor: pointer;
           font-size: 1.5rem;
           line-height: 1;
       }
       .spinner {
           border: 4px solid rgba(255, 255, 255, 0.3);
           border-top: 4px solid #4a90e2;
           border-radius: 50%;
           width: 32px;
           height: 32px;
           animation: spin 1s linear infinite;
       }
       @keyframes spin {
           0% { transform: rotate(0deg); }
           100% { transform: rotate(360deg); }
       }
       .news-item {
           display: flex;
           align-items: flex-start;
           padding: 0.75rem;
           background-color: #313444;
           border-radius: 0.75rem;
           margin-bottom: 0.5rem;
       }
       .news-item-dot {
           width: 0.75rem;
           height: 0.75rem;
           border-radius: 50%;
           flex-shrink: 0;
           margin-top: 0.25rem;
           margin-right: 0.75rem;
       }
       .news-item-content h3 {
           font-weight: bold;
           font-size: 0.9rem;
           line-height: 1.2;
       }
       .news-item-content p {
           font-size: 0.8rem;
           color: #b0b0b0;
           margin-top: 0.25rem;
       }
       .source-url {
           font-size: 0.7rem;
           color: #4a90e2;
           text-decoration: none;
           word-break: break-all;
       }
       .emergency-info-list li {
           background-color: #313444;
           border-left: 4px solid;
           border-radius: 0.5rem;
           padding: 0.75rem;
           margin-bottom: 0.5rem;
       }
       .chat-container {
           height: 300px;
           overflow-y: auto;
           display: flex;
           flex-direction: column;
           gap: 0.75rem;
           padding: 0.5rem;
       }
       .chat-message {
           max-width: 80%;
           padding: 0.75rem 1rem;
           border-radius: 1.5rem;
           word-wrap: break-word;
       }
       .user-message {
           background-color: #4a90e2;
           align-self: flex-end;
           border-bottom-right-radius: 0.5rem;
       }
       .ai-message {
           background-color: #313444;
           align-self: flex-start;
           border-bottom-left-radius: 0.5rem;
       }
       .chat-input-area {
           display: flex;
           gap: 0.5rem;
           margin-top: 1rem;
       }
       .button-spinner {
           border: 2px solid rgba(255, 255, 255, 0.3);
           border-top: 2px solid #fff;
           border-radius: 50%;
           width: 16px;
           height: 16px;
           animation: spin 1s linear infinite;
       }
       @keyframes spin {
           0% { transform: rotate(0deg); }
           100% { transform: rotate(360deg); }
       }
       .toggle-switch {
           position: relative;
           display: inline-block;
           width: 60px;
           height: 34px;
       }
       .toggle-switch input {
           opacity: 0;
           width: 0;
           height: 0;
       }
       .slider {
           position: absolute;
           cursor: pointer;
           top: 0;
           left: 0;
           right: 0;
           bottom: 0;
           background-color: #444;
           transition: .4s;
           border-radius: 34px;
       }
       .slider:before {
           position: absolute;
           content: "";
           height: 26px;
           width: 26px;
           left: 4px;
           bottom: 4px;
           background-color: white;
           transition: .4s;
           border-radius: 50%;
       }
       input:checked + .slider {
           background-color: #4a90e2;
       }
       input:checked + .slider:before {
           transform: translateX(26px);
       }
   </style>
</head>
<body class="bg-gray-900 text-gray-100">

   <!-- Custom Modal for Messages -->
   <div id="messageModal" class="modal">
       <div class="modal-content">
           <span class="modal-close">×</span>
           <h3 class="text-xl font-bold mb-4" id="modalTitle"></h3>
           <p id="modalMessage" class="whitespace-pre-line"></p>
           <div id="dynamicContent" class="mt-4"></div>
       </div>
   </div>

   <!-- Main Dashboard Container -->
   <main class="w-full max-w-lg p-4">

       <!-- Header -->
       <header class="w-full text-center py-4">
           <h1 class="text-2xl font-bold">Autonomes Frühwarnsystem</h1>
           <p class="text-gray-400 mt-2">Analysiert das Internet in Echtzeit auf Bedrohungen.</p>
           <div id="connectionStatus" class="mt-2 text-sm text-[#ef4444]">Verbinde mit der Cloud...</div>
           <div id="userIdDisplay" class="text-sm mt-2 text-gray-500"></div>
       </header>

       <!-- Mode Toggle -->
       <div class="card flex items-center justify-between">
           <div class="flex items-center">
               <span id="modeText" class="text-gray-400 font-semibold mr-4">Öffentlicher Modus</span>
               <label class="toggle-switch">
                   <input type="checkbox" id="modeToggle">
                   <span class="slider"></span>
               </label>
           </div>
       </div>

       <!-- Threat Status Cards -->
       <div class="flex flex-col sm:flex-row sm:space-x-4">
           <!-- Biologische Bedrohung -->
           <div class="card w-full mb-4 sm:mb-0">
               <h2 class="text-lg font-semibold mb-4">Biologische Bedrohung</h2>
               <div class="flex items-center justify-center">
                   <div id="bioStatusDot" class="status-dot green transition-colors duration-500"></div>
                   <div id="bioLevelText" class="level-text text-[#4ade80] transition-colors duration-500"></div>
               </div>
               <p id="bioConfidence" class="text-sm text-gray-400 mt-2 text-center"></p>
               <div id="bioProgressBarContainer" class="w-full mt-4 bg-gray-600 rounded-full h-2">
                   <div id="bioProgressBar" class="bg-green h-2 rounded-full transition-all duration-500" style="width: 0%;"></div>
               </div>
           </div>

           <!-- Psychologische Bedrohung -->
           <div class="card w-full">
               <h2 class="text-lg font-semibold mb-4">Psychologische Bedrohung</h2>
               <div class="flex items-center justify-center">
                   <div id="psychoStatusDot" class="status-dot green transition-colors duration-500"></div>
                   <div id="psychoLevelText" class="level-text text-[#4ade80] transition-colors duration-500"></div>
               </div>
               <p id="psychoConfidence" class="text-sm text-gray-400 mt-2 text-center"></p>
               <div id="psychoProgressBarContainer" class="w-full mt-4 bg-gray-600 rounded-full h-2">
                   <div id="psychoProgressBar" class="bg-green h-2 rounded-full transition-all duration-500" style="width: 0%;"></div>
               </div>
           </div>
       </div>

       <!-- Schnellanalyse Card -->
       <div class="card">
           <h2 class="text-lg font-semibold mb-4">Schnellanalyse</h2>
           <p class="text-gray-400 mb-4">Drücke "Starten", um eine autonome Suche nach aktuellen Bedrohungen im Internet zu starten.</p>
           <div class="flex flex-col sm:flex-row gap-2 mb-4">
               <input type="text" id="searchQueryInput" class="flex-grow p-3 rounded-xl bg-gray-700 text-white placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-[#4a90e2]" placeholder="Gib eigene Suchbegriffe ein (z.B. 'Massenpanik')">
               <button id="addQueryButton" class="p-3 rounded-xl bg-[#4ade80] hover:bg-[#3dbe6c] transition-colors font-semibold">Hinzufügen</button>
           </div>
           <div id="queryList" class="flex flex-wrap gap-2 mb-4">
               <!-- Queries will be added here dynamically -->
           </div>
           <button id="startScanButton" class="w-full p-3 rounded-xl bg-[#4a90e2] hover:bg-[#3d7ac8] transition-colors font-semibold">
               <span id="buttonText">Starten</span>
               <div id="buttonSpinner" class="hidden spinner mx-auto"></div>
           </button>
       </div>

       <!-- Aktuelle Meldungen Card -->
       <div class="card">
           <h2 class="text-lg font-semibold mb-4">Aktuelle Meldungen</h2>
           <div id="liveNewsFeed" class="space-y-4 text-sm">
               <div class="p-3 rounded-lg bg-[#313444] text-center text-gray-400">
                   <p>Keine aktuellen Meldungen. Starte die Analyse, um Ergebnisse zu sehen.</p>
               </div>
           </div>
       </div>

       <!-- Notfall-Verhalten Card -->
       <div class="card">
           <h2 class="text-lg font-semibold mb-4">Notfall-Verhalten</h2>
           <ul id="emergencyInfoList" class="emergency-info-list">
               <li class="border-green text-gray-300">Bleibe ruhig und informiere dich über offizielle Kanäle.</li>
           </ul>
       </div>
       
       <!-- Chatpartner Card -->
       <div class="card">
           <h2 class="text-lg font-semibold mb-4">Doc</h2>
           <div id="chatContainer" class="chat-container bg-gray-800 rounded-xl">
               <!-- Chat messages will be dynamically added here -->
           </div>
           <div class="chat-input-area">
               <input type="text" id="chatInput" class="flex-grow p-3 rounded-xl bg-gray-700 text-white placeholder-gray-400 focus:outline-none focus:ring-2 focus:ring-[#4a90e2]" placeholder="Schreib eine Nachricht...">
               <button id="sendMessageButton" class="p-3 rounded-xl bg-[#4ade80] hover:bg-[#3dbe6c] transition-colors font-semibold flex items-center justify-center">
                   <span id="sendButtonText">Senden</span>
                   <div id="sendButtonSpinner" class="hidden button-spinner"></div>
               </button>
           </div>
       </div>

       <!-- Detaillierte wissenschaftliche Erklärung Card -->
       <div class="card">
           <h2 class="text-lg font-semibold mb-4">Detaillierte wissenschaftliche Erklärung</h2>
           <div class="mt-4">
               <h3 class="font-bold">Der biologische Zombie</h3>
               <p class="text-sm text-gray-300 mt-2">
                   Eine Person, die mit einem aggressiven, sich verändernden Virus oder Krankheitserreger infiziert ist. Dieses Szenario umfasst auch von Tieren auf Menschen übertragene Viren oder uralte Viren, die aus dem Permafrost freigesetzt wurden. Der Fokus liegt hier auf einer körperlichen Veränderung und gewalttätigem Verhalten.
               </p>
               <h4 class="font-semibold text-gray-400 mt-2">Mögliche Ursachen:</h4>
               <ul class="list-disc list-inside text-sm text-gray-300 mt-1">
                   <li>Viren aus dem Permafrost</li>
                   <li>Chronic Wasting Disease (CWD)</li>
               </ul>
           </div>
           <div class="mt-4">
               <h3 class="font-bold">Der psychologische Zombie</h3>
               <p class="text-sm text-gray-300 mt-2">
                   Dieses Szenario beschreibt eine Form von Massenverhalten, das durch Hysterie oder mentale Manipulation ausgelöst wird. Die Person verändert sich nicht körperlich, verliert aber ihre Fähigkeit zum logischen Denken und folgt unkontrolliert einer Menschenmenge.
               </p>
               <h4 class="font-semibold text-gray-400 mt-2">Mögliche Ursachen:</h4>
               <ul class="list-disc list-inside text-sm text-gray-300 mt-1">
                   <li>Biowaffen</li>
                   <li>Massenhysterie</li>
               </ul>
           </div>
       </div>

       <!-- Analyse-Log Card -->
       <div class="card">
           <h2 class="text-lg font-semibold mb-4">Analyse-Log</h2>
           <div id="analysisLog" class="space-y-4 text-sm">
               <div class="p-3 rounded-lg bg-[#313444]">
                   <span class="font-bold text-gray-400">Systemstart:</span> System initialisiert. Warten auf Befehl...
               </div>
           </div>
       </div>
   </main>

   <!-- Firebase SDKs -->
   <script type="module">
       import { initializeApp } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-app.js";
       import { getAuth, signInAnonymously, signInWithCustomToken, onAuthStateChanged } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-auth.js";
       import { getFirestore, doc, onSnapshot, setDoc, getDoc } from "https://www.gstatic.com/firebasejs/11.6.1/firebase-firestore.js";

       // Global variables provided by the canvas environment
       const appId = typeof __app_id !== 'undefined' ? __app_id : 'default-app-id';
       const firebaseConfig = JSON.parse(typeof __firebase_config !== 'undefined' ? __firebase_config : '{}');
       const initialAuthToken = typeof __initial_auth_token !== 'undefined' ? __initial_auth_token : null;

       let db = null;
       let auth = null;
       let userId = null;
       let isAuthReady = false;
       let unsubscribe = null;
       
       let isSaving = false;

       // NEW: This version starts in public mode by default
       const state = {
           bioThreatScore: 0,
           psychoThreatScore: 0,
           newsFeed: [],
           chatHistory: [],
           searchQueries: [
               "Nachrichten CWD (Chronic Wasting Disease) Übertragung auf Menschen",
               "Berichte alte Viren aus Permafrost freigesetzt",
               "Aktuelle Pandemie-Meldungen neuartige aggressive Viren",
               "Nachrichten Massenhysterie oder Massenpanik",
               "Berichte psychologische Kriegsführung oder Biowaffen, die mentales Verhalten beeinflussen"
           ],
           isPrivateMode: false // Startet im öffentlichen Modus
       };
       const maxThreatScore = 100;

       // User-provided articles for initial scan to guarantee results
       const initialArticles = [
           {
               title: "Melting Arctic ice could release 'zombie viruses'",
               snippet: "Scientists warn that ancient viruses, locked in permafrost for thousands of years, could be released as the Arctic ice melts due to global warming.",
               url: "https://www.dailymail.co.uk/sciencetech/article-14583035/Melting-ice-Arctic-zombie-viruses.html",
               type: "biologisch",
               score: 10
           },
           {
               title: "Don't call it 'zombie deer disease', experts warn",
               snippet: "Chronic Wasting Disease (CWD) is a neurological disorder in deer, and while there's no evidence of human transmission yet, experts are concerned about its potential to cross species barriers.",
               url: "https://timesofindia.indiatimes.com/life-style/health-fitness/health-news/dont-call-it-zombie-deer-disease-experts-warn-this-disease-could-become-a-global-crisis/articleshow/119263147.cms",
               type: "biologisch",
               score: 8
           }
       ];
       
       // NEW: User-provided knowledge for the chatbot
       const docKnowledge = `Teil 2: Die Praxis (Überlebensstrategien und reaktives Verhalten)
Allgemeine Strategien (für jedermann)
* Ruhe bewahren: Der erste und wichtigste Schritt. Panik führt zu Fehlern.
* Informationen verifizieren: Verlasse dich nur auf offizielle, überprüfte Quellen.
* Notfall-Kit bereitstellen: Sammle Wasser, haltbare Lebensmittel, Erste-Hilfe-Set, Taschenlampe und Dokumente.
* Lager sichern: Das Zuhause ist der sicherste Ort. Barrikadiere Zugänge und mache es zum geschützten Lager.
Reaktive Strategien (Wenn ein Signal eintrifft)
* Wenn eine Krankheit ausbricht: Bleibe zu Hause, meide überfüllte Orte, trage eine Maske, um dich zu schützen.
* Wenn Massenpanik beginnt: Verlasse gefährliche Zonen sofort. Nutze nicht überfüllte Wege.
* Wenn Versorgungswege zusammenbrechen: Mache dich mit lokalen Wasserquellen wie Brunnen vertraut. Habe einen Plan B zur Wasseraufbereitung.
* Wenn du dich draußen bewegen musst: Nutze einfache, schützende Kleidung. Ein Schal oder Tuch kann einen Atemfilter ersetzen. Mache deine Missionen nachts, um unerkannt zu bleiben.
Teil 3: Das Fazit (Die wahre Lektion)
Das ultimative Wissen über die Apokalypse liegt nicht in der Vorhersage eines Ereignisses, sondern in der mentalen Bereitschaft und den Fähigkeiten, die du entwickelst. Der Wert liegt im Prozess: der Fähigkeit, Informationen zu analysieren, einen Plan zu erstellen und rational zu handeln, wenn andere in Panik geraten. Dieses Wissen ist unbezahlbar, egal was die Zukunft bringt.
`;
       
       // Function to show the custom modal
       function showModal(title, message, dynamicContent = '') {
           document.getElementById('modalTitle').textContent = title;
           document.getElementById('modalMessage').textContent = message;
           document.getElementById('dynamicContent').innerHTML = dynamicContent;
           document.getElementById('messageModal').style.display = 'flex';
       }

       // Function to close the custom modal
       document.querySelector('.modal-close').onclick = function() {
           document.getElementById('messageModal').style.display = 'none';
       }
       window.onclick = function(event) {
           if (event.target == document.getElementById('messageModal')) {
               document.getElementById('messageModal').style.display = 'none';
           }
       }
       
       // Adds a new message to the analysis log
       function logMessage(text, isThreat = false) {
           const analysisLog = document.getElementById('analysisLog');
           const logEntry = document.createElement('div');
           logEntry.className = `p-3 rounded-lg bg-[#313444] flex items-start`;
           const dotColor = isThreat ? 'bg-red' : 'bg-green';
           logEntry.innerHTML = `
               <div class="dot ${dotColor} flex-shrink-0 mr-3 mt-1"></div>
               <div><span class="font-bold text-gray-400">System:</span> ${text}</div>
           `;
           analysisLog.prepend(logEntry);
       }
       
       // Adds a new message to the chat
       function addChatMessage(role, text) {
           const chatContainer = document.getElementById('chatContainer');
           const messageDiv = document.createElement('div');
           messageDiv.className = `chat-message ${role === 'user' ? 'user-message' : 'ai-message'}`;
           messageDiv.textContent = text;
           chatContainer.appendChild(messageDiv);
           chatContainer.scrollTop = chatContainer.scrollHeight;
       }

       // Renders the search query list
       function renderQueryList() {
           const queryListContainer = document.getElementById('queryList');
           queryListContainer.innerHTML = '';
           state.searchQueries.forEach((query, index) => {
               const queryTag = document.createElement('span');
               queryTag.className = 'bg-blue-600 text-white rounded-full px-4 py-2 text-sm flex items-center gap-1';
               queryTag.innerHTML = `
                   ${query}
                   <button class="remove-query-btn" data-index="${index}">×</button>
               `;
               queryListContainer.appendChild(queryTag);
           });

           document.querySelectorAll('.remove-query-btn').forEach(button => {
               button.addEventListener('click', (e) => {
                   const index = e.target.getAttribute('data-index');
                   state.searchQueries.splice(index, 1);
                   renderQueryList();
                   saveDataToFirestore();
               });
           });
       }

       // Updates the dashboard UI based on the current state
       function updateDashboard() {
           const { bioThreatScore, psychoThreatScore, newsFeed, chatHistory } = state;
           
           // Update UI for private/public mode toggle
           const modeToggle = document.getElementById('modeToggle');
           const modeText = document.getElementById('modeText');
           modeToggle.checked = state.isPrivateMode;
           modeText.textContent = state.isPrivateMode ? 'Privater Modus' : 'Öffentlicher Modus';

           // Update Biological Threat UI
           let bioLevel, bioColor;
           if (bioThreatScore <= 5) { bioLevel = "NIEDRIG"; bioColor = "#4ade80"; }
           else if (bioThreatScore <= 20) { bioLevel = "MITTEL"; bioColor = "#facc15"; }
           else if (bioThreatScore <= 50) { bioLevel = "HOCH"; bioColor = "#fb923c"; }
           else { bioLevel = "KRITISCH"; bioColor = "#ef4444"; }
           document.getElementById('bioStatusDot').style.backgroundColor = bioColor;
           document.getElementById('bioLevelText').textContent = bioLevel;
           document.getElementById('bioLevelText').style.color = bioColor;
           document.getElementById('bioProgressBar').style.width = `${bioThreatScore}%`;
           document.getElementById('bioProgressBar').style.backgroundColor = bioColor;
           document.getElementById('bioConfidence').textContent = `Alarmbereitschaft: ${bioThreatScore.toFixed(0)}%`;

           // Update Psychological Threat UI
           let psychoLevel, psychoColor;
           if (psychoThreatScore <= 5) { psychoLevel = "NIEDRIG"; psychoColor = "#4ade80"; }
           else if (psychoThreatScore <= 20) { psychoLevel = "MITTEL"; psychoColor = "#facc15"; }
           else if (psychoThreatScore <= 50) { psychoLevel = "HOCH"; psychoColor = "#fb923c"; }
           else { psychoLevel = "KRITISCH"; psychoColor = "#ef4444"; }
           document.getElementById('psychoStatusDot').style.backgroundColor = psychoColor;
           document.getElementById('psychoLevelText').textContent = psychoLevel;
           document.getElementById('psychoLevelText').style.color = psychoColor;
           document.getElementById('psychoProgressBar').style.width = `${psychoThreatScore}%`;
           document.getElementById('psychoProgressBar').style.backgroundColor = psychoColor;
           document.getElementById('psychoConfidence').textContent = `Alarmbereitschaft: ${psychoThreatScore.toFixed(0)}%`;

           // Update Emergency Info
           updateEmergencyInfo();
           
           // Update Live News Feed
           const liveNewsFeed = document.getElementById('liveNewsFeed');
           if (newsFeed && newsFeed.length > 0) {
               // Sort by score
               const sortedNews = newsFeed.sort((a, b) => b.score - a.score);
               liveNewsFeed.innerHTML = sortedNews.map(article => {
                   let dotColor = 'bg-green';
                   if (article.score >= 5) {
                       dotColor = 'bg-red';
                   } else if (article.score >= 3) {
                       dotColor = 'bg-orange';
                   } else if (article.score > 0) {
                       dotColor = 'bg-yellow';
                   }
                   return `
                       <div class="news-item">
                           <div class="news-item-dot ${dotColor}"></div>
                           <div class="news-item-content">
                               <h3>${article.title}</h3>
                               <p>${article.snippet}</p>
                               <a href="${article.url}" target="_blank" class="source-url">${article.url}</a>
                           </div>
                       </div>
                   `;
               }).join('');
           } else {
               liveNewsFeed.innerHTML = `
                   <div class="p-3 rounded-lg bg-[#313444] text-center text-gray-400">
                       <p>Keine aktuellen Meldungen. Starte die Analyse, um Ergebnisse zu sehen.</p>
                   </div>
               `;
           }
           
           // Update Chat History
           const chatContainer = document.getElementById('chatContainer');
           chatContainer.innerHTML = '';
           chatHistory.forEach(msg => addChatMessage(msg.role, msg.text));
       }

       // Updates the emergency info dynamically
       function updateEmergencyInfo() {
           const emergencyInfoList = document.getElementById('emergencyInfoList');
           emergencyInfoList.innerHTML = '';
           const combinedScore = (state.bioThreatScore + state.psychoThreatScore) / 2;
           let info, color;

           if (combinedScore <= 10) {
               info = [
                   "Bleibe ruhig und informiere dich über offizielle Kanäle.",
                   "Überprüfe deine Notfall-Vorratsliste.",
                   "Achte auf ungewöhnliche Nachrichten oder Gerüchte."
               ];
               color = "#4ade80";
           } else if (combinedScore <= 30) {
               info = [
                   "Erstelle einen Notfallplan für deine Familie.",
                   "Sichere wichtige Dokumente an einem zentralen Ort.",
                   "Meide überfüllte Orte und öffentliche Versammlungen."
               ];
               color = "#facc15";
           } else if (combinedScore <= 60) {
               info = [
                   "Bereite dich auf eine mögliche Isolation vor (Nahrung, Wasser, Medikamente).",
                   "Schließe Türen und Fenster. Verbarrikadiere deinen Zugang, um unerwünschte Eindringlinge abzuhalten.",
                   "Kommuniziere nur über sichere und private Kanäle.",
                   "Verfolge offizielle Anweisungen von Behörden."
               ];
               color = "#fb923c";
           } else {
               info = [
                   "Suche sofort sicheren Unterschlupf und verlasse dein Haus nicht.",
                   "Schließe alle Zugänge und dichte sie ab.",
                   "Schalte alle externen Kommunikationsmittel ab, falls du gezwungen bist, in einer psychologisch beeinflussten Menge zu fliehen.",
                   "Versuche nicht, gegen die Masse zu kämpfen. Weiche der Bedrohung aus."
               ];
               color = "#ef4444";
           }

           info.forEach(item => {
               const li = document.createElement('li');
               li.className = `text-gray-300`;
               li.style.borderColor = color;
               li.textContent = item;
               emergencyInfoList.appendChild(li);
           });
       }
       
       // Starts the real-world scan using a Gemini API call to fetch search results
       async function startAutonomousScan() {
           if (!isAuthReady || !userId) {
               showModal("Systemfehler", "Cloud-Verbindung nicht bereit. Bitte warte, bis die Verbindung hergestellt ist.");
               return;
           }

           const startScanButton = document.getElementById('startScanButton');
           const buttonText = document.getElementById('buttonText');
           const buttonSpinner = document.getElementById('buttonSpinner');
           
           logMessage("Starte Bedrohungsanalyse im Internet...", false);
           startScanButton.disabled = true;
           buttonText.classList.add('hidden');
           buttonSpinner.classList.remove('hidden');
           
           // Set the flag to prevent the Firestore listener from updating the state
           isSaving = true;
           
           const articles = [];
           
           // First, process the initial, guaranteed articles provided by the user
           initialArticles.forEach(article => articles.push(article));

           // Then, perform the live search with exponential backoff for resilience
           for (let i = 0; i < state.searchQueries.length; i++) {
               const query = state.searchQueries[i];
               try {
                   const payload = {
                       contents: [{
                           parts: [{ text: `Suche aktuelle Nachrichten zu: ${query}` }]
                       }],
                       tools: [{
                           google_search: {}
                       }],
                   };

                   const apiKey = "";
                   const apiUrl = `https://generativelanguage.googleapis.com/v1beta/models/gemini-2.5-flash-preview-05-20:generateContent?key=${apiKey}`;
                   
                   const response = await fetch(apiUrl, {
                       method: 'POST',
                       headers: { 'Content-Type': 'application/json' },
                       body: JSON.stringify(payload)
                   });

                   if (!response.ok) {
                       throw new Error(`API call failed with status: ${response.status}`);
                   }

                   const result = await response.json();
                   
                   if (result?.candidates?.[0]?.content?.parts) {
                       result.candidates[0].content.parts.forEach(part => {
                           if (part.text) {
                               const responseText = part.text.trim();
                               if (responseText.startsWith('[') || responseText.startsWith('{')) {
                                   try {
                                       const searchResults = JSON.parse(responseText);
                                       if (searchResults && searchResults.results) {
                                           searchResults.results.forEach(item => {
                                               let type = "biologisch";
                                               let score = 0;
                                               if (item.snippet && (item.snippet.includes("CWD") || item.snippet.includes("Permafrost") || item.snippet.includes("Virus") || item.snippet.includes("Pandemie"))) {
                                                   score = Math.floor(Math.random() * 5) + 3; // Random score 3-7 for biological
                                               } else if (item.snippet && (item.snippet.includes("Massenhysterie") || item.snippet.includes("Biowaffen") || item.snippet.includes("psychologisch") || item.snippet.includes("Panik"))) {
                                                   type = "psychologisch";
                                                   score = Math.floor(Math.random() * 5) + 3; // Random score 3-7 for psychological
                                               } else {
                                                   score = 1; // Default low score
                                               }

                                               if (item.url && !articles.some(a => a.url === item.url)) {
                                                   articles.push({
                                                       title: item.source_title || item.title || "Unbekannter Titel",
                                                       snippet: item.snippet,
                                                       url: item.url,
                                                       type: type,
                                                       score: score
                                                   });
                                               }
                                           });
                                       }
                                   } catch (parseError) {
                                       console.error(`Fehler beim Parsen der JSON-Antwort für Query "${query}":`, parseError);
                                       logMessage(`Fehler bei der Analyse der Antwort für "${query}". Möglicherweise keine JSON-Daten.`, true);
                                   }
                               } else {
                                   console.warn(`received a non-JSON text response for Query "${query}": ${responseText}`);
                               }
                           }
                       });
                   } else {
                       console.warn("API response was empty or malformed.");
                   }

               } catch (error) {
                   console.error(`Fehler bei der Suche für Query "${query}":`, error);
                   logMessage(`Fehler bei der Suche für Query "${query}".`, true);
                   await new Promise(res => setTimeout(res, Math.pow(2, i) * 1000));
               }
           }

           if (articles.length > 0) {
               const newArticles = [];
               let bioScoreIncrease = 0;
               let psychoScoreIncrease = 0;

               articles.forEach(article => {
                   const isDuplicate = state.newsFeed.some(existingArticle => existingArticle.url === article.url);
                   if (!isDuplicate) {
                       newArticles.push(article);
                       if (article.type === "biologisch") {
                           bioScoreIncrease += article.score;
                       } else if (article.type === "psychologisch") {
                           psychoScoreIncrease += article.score;
                       }
                   }
               });
               
               state.bioThreatScore = Math.min(maxThreatScore, state.bioThreatScore + bioScoreIncrease);
               state.psychoThreatScore = Math.min(maxThreatScore, state.psychoThreatScore + psychoScoreIncrease);
               state.newsFeed = [...
