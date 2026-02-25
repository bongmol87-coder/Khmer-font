<!DOCTYPE html>
<html lang="km">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Khmer Unicode to Limon Converter | បង ម៉ុល</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Kantumruy+Pro:wght@300;400;700&family=Moul&display=swap" rel="stylesheet">
    <style>
        :root {
            --primary: #3b82f6;
            --accent: #10b981;
        }

        body {
            font-family: 'Kantumruy Pro', sans-serif;
            background: linear-gradient(135deg, #0f172a 0%, #1e293b 100%);
            color: #f8fafc;
            min-height: 100vh;
        }

        /* RGB Animation for Text */
        .rgb-text {
            background: linear-gradient(to right, #ff0000, #00ff00, #0000ff, #ff00ff, #ff0000);
            background-size: 200% auto;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: shine 3s linear infinite;
        }

        @keyframes shine {
            to { background-position: 200% center; }
        }

        /* Glassmorphism Design */
        .glass-card {
            background: rgba(255, 255, 255, 0.03);
            backdrop-filter: blur(12px);
            border: 1px solid rgba(255, 255, 255, 0.1);
            border-radius: 24px;
        }

        .input-area {
            background: rgba(15, 23, 42, 0.6);
            border: 1px solid rgba(255, 255, 255, 0.1);
            transition: all 0.3s ease;
        }

        .input-area:focus {
            border-color: var(--primary);
            box-shadow: 0 0 0 2px rgba(59, 130, 246, 0.3);
        }

        .limon-font {
            /* This assumes the user has Limon font installed on their system */
            font-family: 'Limon S1', 'Limon R1', sans-serif;
        }

        /* Mobile Optimization */
        @media (max-width: 640px) {
            .header-title { font-size: 1.5rem; }
        }
    </style>
</head>
<body class="flex flex-col items-center justify-center p-4 sm:p-8">

    <!-- Web Container -->
    <div class="w-full max-w-4xl glass-card overflow-hidden shadow-2xl">
        
        <!-- Navbar/Header -->
        <header class="p-6 sm:p-10 text-center border-b border-white/10">
            <h1 class="header-title text-3xl sm:text-5xl font-bold mb-4" style="font-family: 'Moul', cursive;">
                កម្មវិធីបំប្លែង <span class="rgb-text">FONT ខ្មែរ</span>
            </h1>
            
            <div class="flex flex-col sm:flex-row items-center justify-center gap-4 text-gray-300">
                <div class="flex items-center gap-2 px-4 py-1.5 rounded-full bg-white/5 border border-white/10">
                    <span class="text-xs uppercase tracking-widest text-blue-400">អ្នកបង្កើត</span>
                    <span class="font-bold text-white rgb-text">បង ម៉ុល</span>
                </div>
                <a href="tel:093816693" class="flex items-center gap-2 px-4 py-1.5 rounded-full bg-white/5 border border-white/10 hover:bg-white/10 transition">
                    <svg xmlns="http://www.w3.org/2000/svg" class="h-4 w-4 text-green-400" fill="none" viewBox="0 0 24 24" stroke="currentColor">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 5a2 2 0 012-2h3.28a1 1 0 01.948.684l1.498 4.493a1 1 0 01-.502 1.21l-2.257 1.13a11.042 11.042 0 005.516 5.516l1.13-2.257a1 1 0 011.21-.502l4.493 1.498a1 1 0 01.684.949V19a2 2 0 01-2 2h-1C9.716 21 3 14.284 3 6V5z" />
                    </svg>
                    <span class="font-bold">093816693</span>
                </a>
            </div>
        </header>

        <main class="p-6 sm:p-10 grid grid-cols-1 lg:grid-cols-2 gap-8">
            
            <!-- Left Side: Input -->
            <div class="flex flex-col gap-4">
                <div class="flex items-center justify-between">
                    <h2 class="text-lg font-semibold flex items-center gap-2">
                        <span class="w-3 h-3 rounded-full bg-blue-500 shadow-[0_0_10px_#3b82f6]"></span>
                        Khmer Unicode
                    </h2>
                    <span class="text-xs text-gray-500 bg-white/5 px-2 py-1 rounded">យូនីកូដ</span>
                </div>
                <textarea 
                    id="unicodeInput" 
                    placeholder="វាយអត្ថបទយូនីកូដនៅទីនេះ..."
                    oninput="autoConvert()"
                    class="input-area w-full h-64 p-5 rounded-2xl outline-none resize-none text-lg leading-relaxed"
                ></textarea>
            </div>

            <!-- Right Side: Output -->
            <div class="flex flex-col gap-4">
                <div class="flex items-center justify-between">
                    <h2 class="text-lg font-semibold flex items-center gap-2">
                        <span class="w-3 h-3 rounded-full bg-emerald-500 shadow-[0_0_10px_#10b981]"></span>
                        Font Limon
                    </h2>
                    <button onclick="copyContent()" class="text-xs font-bold text-emerald-400 hover:text-emerald-300 transition uppercase tracking-wider">
                        ចម្លង (Copy)
                    </button>
                </div>
                <textarea 
                    id="limonOutput" 
                    readonly
                    placeholder="លទ្ធផលបំប្លែងនឹងបង្ហាញទីនេះ..."
                    class="input-area w-full h-64 p-5 rounded-2xl outline-none resize-none text-2xl leading-relaxed limon-font text-blue-300"
                ></textarea>
            </div>
        </main>

        <!-- Footer Info -->
        <footer class="p-6 bg-black/20 text-center border-t border-white/5">
            <p class="text-gray-500 text-sm italic mb-2">
                "បំប្លែងអក្សរដោយមានទំនុកចិត្ត ជាមួយកម្មវិធីរបស់ បង ម៉ុល"
            </p>
            <div class="flex justify-center gap-4">
                <div class="w-2 h-2 rounded-full bg-red-500"></div>
                <div class="w-2 h-2 rounded-full bg-yellow-500"></div>
                <div class="w-2 h-2 rounded-full bg-green-500"></div>
            </div>
        </footer>
    </div>

    <!-- Notification -->
    <div id="toast" class="fixed bottom-8 left-1/2 -translate-x-1/2 px-8 py-3 bg-emerald-600 text-white font-bold rounded-full shadow-2xl opacity-0 transition-all duration-300 pointer-events-none">
        ចម្លងក្នុង Clipboard រួចរាល់!
    </div>

    <script>
        // Mapping Dictionary for Unicode to Limon
        const charMap = {
            'ក': 'k', 'ខ': 'x', 'គ': 'K', 'ឃ': 'X', 'ង': 'g',
            'ច': 'c', 'ឆ': 'q', 'ជ': 'C', 'ឈ': 'Q', 'ញ': 'j',
            'ដ': 'd', 'ឋ': 'f', 'ឌ': 'D', 'ឍ': 'F', 'ណ': 'N',
            'ត': 't', 'ថ': 'f', 'ទ': 'T', 'ធ': 'F', 'ន': 'n',
            'ប': 'b', 'ផ': 'p', 'ព': 'B', 'ភ': 'P', 'ម': 'm',
            'យ': 'y', 'រ': 'r', 'ល': 'l', 'វ': 'v', 'ស': 's',
            'ហ': 'h', 'ឡ': 'L', 'អ': 'G',
            'ា': 'm', 'ិ': 'i', 'ី': 'I', 'ឹ': 'W', 'ឺ': 'w',
            'ុ': 'u', 'ូ': 'U', 'ួ': 'Y', 'ើ': 'eI', 'ឿ': 'eW', 'ៀ': 'eP',
            'េ': 'e', 'ែ': 'E', 'ៃ': 'y', 'ោ': 'ae', 'ៅ': 'aO',
            'ំ': 'M', 'ះ': 'H', 'ៈ': 'a', '៉': 'y', '៊': 'Y',
            '់': 'o', '៌': 'r', '៍': 'f', '៏': 'O', '័': 'A'
        };

        function autoConvert() {
            const input = document.getElementById('unicodeInput').value;
            let result = "";
            
            for (let char of input) {
                result += charMap[char] || char;
            }
            
            document.getElementById('limonOutput').value = result;
        }

        function copyContent() {
            const output = document.getElementById('limonOutput');
            if (!output.value) return;

            output.select();
            document.execCommand('copy');

            const toast = document.getElementById('toast');
            toast.style.opacity = '1';
            toast.style.bottom = '40px';
            
            setTimeout(() => {
                toast.style.opacity = '0';
                toast.style.bottom = '32px';
            }, 2000);
        }

        // Add auto-conversion for space and enter keys
        document.getElementById('unicodeInput').addEventListener('keydown', (e) => {
            if (e.key === 'Enter') autoConvert();
        });
    </script>
</body>
</html>


