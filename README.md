[prepositions of time.html](https://github.com/user-attachments/files/23636842/prepositions.of.time.html)
<!DOCTYPE html>
<html lang="es">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Preposiciones de Tiempo: ON, IN, AT, SINCE, FOR</title>
    <!-- Carga de Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Configuración para el tema visual y la fuente Inter -->
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                    },
                    colors: {
                        'primary-blue': '#4F46E5',
                        'secondary-yellow': '#FBBF24',
                        'accent-green': '#10B981',
                        'background-gray': '#F9FAFB',
                    }
                }
            }
        }
    </script>
    <style>
        /* Estilo base para botones interactivos */
        .interactive-btn {
            transition: all 0.2s;
            box-shadow: 0 4px 6px -1px rgba(0, 0, 0, 0.1), 0 2px 4px -2px rgba(0, 0, 0, 0.1);
        }
        .interactive-btn:hover {
            transform: translateY(-2px);
            box-shadow: 0 10px 15px -3px rgba(0, 0, 0, 0.1), 0 4px 6px -4px rgba(0, 0, 0, 0.1);
        }
        .interactive-btn:active {
            transform: translateY(0);
            box-shadow: 0 1px 3px 0 rgba(0, 0, 0, 0.1), 0 1px 2px 0 rgba(0, 0, 0, 0.06);
        }
        /* Estilo para la tarjeta principal en el centro */
        .main-card {
            min-height: 80vh;
            max-width: 900px;
        }
    </style>
</head>

<body class="bg-background-gray font-sans flex items-center justify-center p-4">

    <!-- Contenedor Principal de la Aplicación -->
    <div id="app" class="main-card w-full bg-white rounded-xl shadow-2xl p-6 md:p-10 transition-all duration-300">

        <!-- Barra de Navegación/Menú Principal -->
        <header class="mb-8 border-b-2 border-primary-blue/20 pb-4">
            <h1 class="text-3xl font-extrabold text-primary-blue mb-2">🚀 Preposiciones del Tiempo en Inglés</h1>
            <p class="text-gray-500">¡Aprende a usar <span class="font-bold text-accent-green">ON, IN, AT, SINCE, FOR</span> con juegos!</p>

            <nav class="mt-4 flex flex-wrap gap-2 md:gap-4">
                <button onclick="setView('home')" class="interactive-btn px-4 py-2 bg-primary-blue text-white rounded-lg font-semibold hover:bg-indigo-700">Inicio</button>
                <button onclick="setView('explanation')" class="interactive-btn px-4 py-2 bg-secondary-yellow text-gray-900 rounded-lg font-semibold hover:bg-yellow-500">Reglas y Usos</button>
                <button onclick="setView('game')" class="interactive-btn px-4 py-2 bg-accent-green text-white rounded-lg font-semibold hover:bg-green-600">Juego de Práctica</button>
            </nav>
        </header>

        <!-- Contenido Dinámico de la Página -->
        <main id="content-container">
            <!-- Los contenidos se insertarán aquí por JavaScript -->
        </main>
    </div>

    <!-- Script de la Aplicación -->
    <script>
        // --- 1. Definición de Contenidos (HTML como plantillas string) ---

        // Contenido de la vista de Inicio
        const homeContent = `
            <div class="space-y-6">
                <h2 class="text-4xl font-bold text-gray-800">¡Bienvenido, Futuro Maestro del Tiempo! 🌟</h2>
                <p class="text-lg text-gray-600">Las preposiciones de tiempo <span class="font-extrabold text-primary-blue">ON, IN, AT, SINCE, y FOR</span> son esenciales. Usa el menú superior para navegar:</p>

                <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                    <!-- Tarjeta de Reglas -->
                    <div class="p-6 bg-indigo-50 rounded-xl shadow-md border border-primary-blue/30">
                        <h3 class="text-xl font-bold text-primary-blue mb-3">📚 Reglas Claras</h3>
                        <p class="text-gray-700 mb-4">Aprende cuándo usar cada preposición con ejemplos y trucos sencillos.</p>
                        <button onclick="setView('explanation')" class="w-full interactive-btn bg-primary-blue text-white py-2 rounded-lg font-bold hover:bg-indigo-700">¡Quiero Aprender!</button>
                    </div>

                    <!-- Tarjeta de Práctica -->
                    <div class="p-6 bg-green-50 rounded-xl shadow-md border border-accent-green/30">
                        <h3 class="text-xl font-bold text-accent-green mb-3">🎮 Práctica con Juego</h3>
                        <p class="text-gray-700 mb-4">Pon a prueba tus conocimientos con un divertido quiz interactivo.</p>
                        <button onclick="setView('game')" class="w-full interactive-btn bg-accent-green text-white py-2 rounded-lg font-bold hover:bg-green-600">¡Empezar Juego!</button>
                    </div>
                    
                    <!-- Tarjeta de Reto (Ejemplo de otro botón interactivo) -->
                    <div class="p-6 bg-yellow-50 rounded-xl shadow-md border border-secondary-yellow/30">
                        <h3 class="text-xl font-bold text-secondary-yellow mb-3">💡 Tip Extra</h3>
                        <p class="text-gray-700 mb-4">¿Sabías que <span class="font-bold">AT</span> es para la hora exacta, y <span class="font-bold">IN</span> para periodos largos?</p>
                        <button onclick="alertMessage('Un pequeño desafío, ¡usa tus conocimientos!')" class="w-full interactive-btn bg-secondary-yellow text-gray-900 py-2 rounded-lg font-bold hover:bg-yellow-500">Ver Mensaje</button>
                    </div>
                </div>
            </div>
        `;

        // Contenido de la vista de Explicación
        const explanationContent = `
            <h2 class="text-3xl font-bold text-primary-blue mb-6 border-b pb-2">Reglas de Oro: Cuándo Usar Cada Preposición</h2>
            <div class="space-y-8 text-gray-700">
                <!-- AT -->
                <div class="p-4 bg-red-100 rounded-lg shadow-inner">
                    <h3 class="text-2xl font-extrabold text-red-700 mb-2">1. AT (Tiempo Específico y Fiestas)</h3>
                    <ul class="list-disc list-inside ml-4 space-y-1">
                        <li><span class="font-bold">Hora Exacta:</span> <em class="text-red-700">at 7:30 p.m.</em>, <em class="text-red-700">at noon.</em></li>
                        <li><span class="font-bold">Momentos Fijos:</span> <em class="text-red-700">at night</em>, <em class="text-red-700">at the moment</em>, <em class="text-red-700">at the weekend (UK)</em>.</li>
                        <li><span class="font-bold">Períodos Festivos:</span> <em class="text-red-700">at Christmas</em>, <em class="text-red-700">at Easter.</em></li>
                    </ul>
                </div>

                <!-- ON -->
                <div class="p-4 bg-blue-100 rounded-lg shadow-inner">
                    <h3 class="text-2xl font-extrabold text-blue-700 mb-2">2. ON (Días y Fechas Específicas)</h3>
                    <ul class="list-disc list-inside ml-4 space-y-1">
                        <li><span class="font-bold">Días de la Semana:</span> <em class="text-blue-700">on Monday</em>, <em class="text-blue-700">on Friday morning.</em></li>
                        <li><span class="font-bold">Fechas:</span> <em class="text-blue-700">on October 25th</em>, <em class="text-blue-700">on my birthday.</em></li>
                        <li><span class="font-bold">Días Festivos con 'Day':</span> <em class="text-blue-700">on New Year's Day.</em></li>
                    </ul>
                </div>

                <!-- IN -->
                <div class="p-4 bg-green-100 rounded-lg shadow-inner">
                    <h3 class="text-2xl font-extrabold text-green-700 mb-2">3. IN (Períodos Largos y Partes del Día)</h3>
                    <ul class="list-disc list-inside ml-4 space-y-1">
                        <li><span class="font-bold">Meses:</span> <em class="text-green-700">in July</em>, <em class="text-green-700">in December.</em></li>
                        <li><span class="font-bold">Años y Décadas:</span> <em class="text-green-700">in 2025</em>, <em class="text-green-700">in the 90s.</em></li>
                        <li><span class="font-bold">Estaciones y Siglos:</span> <em class="text-green-700">in summer</em>, <em class="text-green-700">in the 21st century.</em></li>
                        <li><span class="font-bold">Partes del Día:</span> <em class="text-green-700">in the morning</em>, <em class="text-green-700">in the afternoon</em>, <em class="text-green-700">in the evening.</em></li>
                    </ul>
                </div>

                <!-- SINCE & FOR -->
                <div class="p-4 bg-yellow-100 rounded-lg shadow-inner">
                    <h3 class="text-2xl font-extrabold text-yellow-700 mb-2">4. SINCE y FOR (Duración)</h3>
                    <ul class="list-disc list-inside ml-4 space-y-1">
                        <li><span class="font-bold">FOR (Duración):</span> Indica un período de tiempo. <em class="text-yellow-700">for three hours</em>, <em class="text-yellow-700">for two years.</em></li>
                        <li><span class="font-bold">SINCE (Punto de Inicio):</span> Indica el punto de inicio de un período hasta ahora. <em class="text-yellow-700">since 2022</em>, <em class="text-yellow-700">since Monday.</em></li>
                    </ul>
                </div>
            </div>
            <button onclick="setView('home')" class="mt-8 interactive-btn px-6 py-3 bg-primary-blue text-white rounded-lg font-bold hover:bg-indigo-700">Volver a Inicio</button>
        `;

        // Contenido de la vista del Juego
        const gameContent = `
            <h2 class="text-3xl font-bold text-accent-green mb-6 border-b pb-2">Juego de Práctica: Completa la Oración</h2>
            <div id="quiz-area" class="space-y-4">
                <div id="question-box" class="p-6 bg-white border border-gray-200 rounded-lg shadow-lg">
                    <p class="text-xl font-medium text-gray-800 mb-4" id="quiz-question"></p>
                    <div id="quiz-options" class="grid grid-cols-2 gap-4">
                        <!-- Opciones insertadas por JS -->
                    </div>
                </div>
                <div id="quiz-feedback" class="text-center font-bold text-lg p-2 rounded-lg transition-all duration-300"></div>
                <div class="flex justify-between items-center pt-4">
                    <button onclick="loadQuestion()" class="interactive-btn px-4 py-2 bg-primary-blue text-white rounded-lg font-bold hover:bg-indigo-700" id="next-button" style="display:none;">Siguiente Pregunta</button>
                    <p class="text-lg font-semibold text-gray-600">Puntuación: <span id="quiz-score" class="text-accent-green">0</span></p>
                </div>
            </div>
        `;

        // Preguntas del Quiz
        const questions = [
            { q: "I have lived here ____ 2018.", options: ["in", "on", "since", "for"], answer: "since" },
            { q: "The concert is ____ 7 o'clock.", options: ["on", "at", "in", "since"], answer: "at" },
            { q: "We often go skiing ____ winter.", options: ["at", "on", "in", "for"], answer: "in" },
            { q: "She will finish the project ____ three weeks.", options: ["since", "for", "at", "in"], answer: "in" },
            { q: "I will call you ____ Tuesday.", options: ["at", "on", "in", "for"], answer: "on" },
            { q: "They have been waiting ____ an hour.", options: ["since", "for", "at", "on"], answer: "for" },
            { q: "The store opens ____ nine in the morning.", options: ["on", "at", "in", "since"], answer: "at" },
            { q: "The Roman Empire fell ____ the 5th century.", options: ["on", "at", "in", "for"], answer: "in" },
            { q: "He was born ____ January 14th.", options: ["at", "in", "on", "since"], answer: "on" },
        ];
        
        // Variables de estado del juego
        let currentQuestionIndex = 0;
        let score = 0;
        let answered = false;
        
        // --- 2. Lógica de la Interfaz (Vista) ---

        /**
         * Muestra el mensaje de la aplicación (sustituye a alert()).
         * @param {string} message - Mensaje a mostrar.
         */
        function alertMessage(message) {
            const container = document.getElementById('app');
            let modal = document.getElementById('custom-modal');

            if (!modal) {
                modal = document.createElement('div');
                modal.id = 'custom-modal';
                modal.className = 'fixed inset-0 bg-gray-900 bg-opacity-75 flex items-center justify-center z-50 transition-opacity duration-300 opacity-0 pointer-events-none';
                modal.innerHTML = `
                    <div class="bg-white p-6 rounded-lg shadow-xl max-w-sm w-full transform transition-transform duration-300 scale-95">
                        <h3 class="text-xl font-bold text-primary-blue mb-4">Mensaje Interactivo</h3>
                        <p id="modal-text" class="text-gray-700 mb-6"></p>
                        <button onclick="closeModal()" class="w-full interactive-btn bg-primary-blue text-white py-2 rounded-lg font-bold hover:bg-indigo-700">Entendido</button>
                    </div>
                `;
                container.appendChild(modal);
            }

            document.getElementById('modal-text').textContent = message;
            modal.classList.remove('opacity-0', 'pointer-events-none');
            modal.querySelector('div').classList.remove('scale-95');
        }

        /**
         * Cierra el modal de mensaje.
         */
        function closeModal() {
            const modal = document.getElementById('custom-modal');
            if (modal) {
                modal.querySelector('div').classList.add('scale-95');
                modal.classList.add('opacity-0', 'pointer-events-none');
            }
        }

        /**
         * Cambia la vista principal de la aplicación.
         * @param {string} viewName - El nombre de la vista ('home', 'explanation', 'game').
         */
        function setView(viewName) {
            const container = document.getElementById('content-container');
            let content = '';

            // Restablecer estilos de botón de navegación
            document.querySelectorAll('nav button').forEach(btn => {
                btn.classList.remove('bg-indigo-700', 'bg-yellow-500', 'bg-green-600', 'ring-2', 'ring-offset-2');
            });
            
            // Asignar el contenido de la vista
            switch (viewName) {
                case 'explanation':
                    content = explanationContent;
                    document.querySelector('nav button:nth-child(2)').classList.add('bg-yellow-500', 'ring-2', 'ring-secondary-yellow');
                    break;
                case 'game':
                    content = gameContent;
                    document.querySelector('nav button:nth-child(3)').classList.add('bg-green-600', 'ring-2', 'ring-accent-green');
                    // Iniciar/Reiniciar el juego
                    initGame(); 
                    break;
                case 'home':
                default:
                    content = homeContent;
                    document.querySelector('nav button:nth-child(1)').classList.add('bg-indigo-700', 'ring-2', 'ring-primary-blue');
                    break;
            }

            container.innerHTML = content;
        }

        // --- 3. Lógica del Juego ---

        /**
         * Inicializa o reinicia el juego de preguntas.
         */
        function initGame() {
            currentQuestionIndex = 0;
            score = 0;
            updateScoreDisplay();
            // Asegúrate de que el área de juego se haya cargado antes de llamar a loadQuestion
            setTimeout(() => loadQuestion(), 50); 
        }
        
        /**
         * Carga la siguiente pregunta del quiz.
         */
        function loadQuestion() {
            const questionElement = document.getElementById('quiz-question');
            const optionsElement = document.getElementById('quiz-options');
            const feedbackElement = document.getElementById('quiz-feedback');
            const nextButton = document.getElementById('next-button');

            if (currentQuestionIndex >= questions.length) {
                // Fin del juego
                questionElement.innerHTML = `<span class="text-4xl">🎉 ¡Juego Terminado!</span>`;
                optionsElement.innerHTML = `<p class="text-center text-2xl font-bold text-primary-blue">Tu puntuación final es: ${score} de ${questions.length}</p>
                                            <button onclick="initGame()" class="interactive-btn w-full mt-4 py-2 bg-primary-blue text-white rounded-lg font-bold hover:bg-indigo-700">Jugar de Nuevo</button>`;
                feedbackElement.innerHTML = '';
                nextButton.style.display = 'none';
                return;
            }

            answered = false;
            feedbackElement.innerHTML = '';
            feedbackElement.classList.remove('bg-red-200', 'text-red-800', 'bg-green-200', 'text-green-800');
            nextButton.style.display = 'none';
            
            const currentQ = questions[currentQuestionIndex];
            
            // 1. Mostrar la pregunta
            questionElement.textContent = `Pregunta ${currentQuestionIndex + 1}/${questions.length}: Completa: "${currentQ.q}"`;

            // 2. Generar las opciones
            optionsElement.innerHTML = '';
            currentQ.options.forEach(option => {
                const button = document.createElement('button');
                button.textContent = option.toUpperCase();
                button.className = 'interactive-btn p-3 bg-gray-200 rounded-lg font-bold text-lg text-gray-700 hover:bg-gray-300';
                button.onclick = () => checkAnswer(option, currentQ.answer, button);
                button.setAttribute('data-value', option);
                optionsElement.appendChild(button);
            });
        }
        
        /**
         * Comprueba la respuesta seleccionada por el usuario.
         * @param {string} selectedOption - Opción elegida.
         * @param {string} correctAnswer - Respuesta correcta.
         * @param {HTMLElement} buttonElement - El botón presionado.
         */
        function checkAnswer(selectedOption, correctAnswer, buttonElement) {
            if (answered) return; // Evita doble clic
            answered = true;

            const feedbackElement = document.getElementById('quiz-feedback');
            const nextButton = document.getElementById('next-button');
            const allOptionButtons = document.querySelectorAll('#quiz-options button');
            
            // Desactivar todos los botones para esta pregunta
            allOptionButtons.forEach(btn => btn.onclick = null);

            if (selectedOption === correctAnswer) {
                // Respuesta correcta
                score++;
                feedbackElement.textContent = "¡Correcto! ✅ ¡Muy bien!";
                feedbackElement.classList.add('bg-green-200', 'text-green-800');
                buttonElement.classList.remove('bg-gray-200', 'hover:bg-gray-300');
                buttonElement.classList.add('bg-green-500', 'text-white', 'scale-105');
            } else {
                // Respuesta incorrecta
                feedbackElement.textContent = `Incorrecto. ❌ La respuesta correcta era: ${correctAnswer.toUpperCase()}`;
                feedbackElement.classList.add('bg-red-200', 'text-red-800');
                buttonElement.classList.remove('bg-gray-200', 'hover:bg-gray-300');
                buttonElement.classList.add('bg-red-500', 'text-white', 'scale-95');

                // Resaltar la respuesta correcta
                document.querySelectorAll('#quiz-options button').forEach(btn => {
                    if (btn.getAttribute('data-value') === correctAnswer) {
                        btn.classList.add('bg-accent-green', 'text-white', 'ring-4', 'ring-accent-green/50');
                    }
                });
            }

            updateScoreDisplay();
            nextButton.style.display = 'block';
            currentQuestionIndex++;
        }
        
        /**
         * Actualiza la puntuación mostrada.
         */
        function updateScoreDisplay() {
            document.getElementById('quiz-score').textContent = score;
        }

        // --- 4. Inicialización ---

        // Iniciar la aplicación en la vista 'home'
        setView('home');

    </script>
</body>
</html>
