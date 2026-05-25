<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>RangMatch Studio | Industry-Grade Mockup Tool</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://fonts.googleapis.com/css2?family=Playfair+Display:wght@600;800&family=Inter:wght@300;400;600&display=swap" rel="stylesheet">
    <style>
        body { font-family: 'Inter', sans-serif; background-color: #FDFBF7; color: #2D2D2D; }
        .serif { font-family: 'Playfair Display', serif; }
        .glass { background: rgba(255, 255, 255, 0.8); backdrop-filter: blur(20px); border: 1px solid rgba(255, 255, 255, 0.5); box-shadow: 0 20px 50px rgba(0,0,0,0.05); }
        
        /* Professional Fabric Overlay */
        .fabric-texture {
            position: relative;
            background-image: url('https://www.transparenttextures.com/patterns/natural-paper.png');
            background-repeat: repeat;
        }

        /* Mockup Styling */
        .mockup-container {
            filter: drop-shadow(0 20px 30px rgba(0,0,0,0.15));
            transition: all 0.5s ease;
        }

        #customColor { 
            -webkit-appearance: none; width: 60px; height: 60px; border: none; border-radius: 50%; cursor: pointer; background: none; 
        }
        #customColor::-webkit-color-swatch { border: 4px solid white; border-radius: 50%; box-shadow: 0 0 15px rgba(0,0,0,0.2); }

        .option-card { cursor: pointer; transition: all 0.3s ease; border: 2px solid transparent; }
        .option-card:hover { transform: translateX(10px); border-color: #8B7355; }
        .active-option { border: 3px solid #8B7355 !important; background: white !important; box-shadow: 0 10px 20px rgba(0,0,0,0.1); }
        
        .copy-btn { transition: all 0.2s; }
        .copy-btn:active { transform: scale(0.9); background-color: #d1d5db; }
    </style>
</head>
<body>

    <nav class="p-6 flex justify-between items-center max-w-7xl mx-auto">
        <h1 class="serif text-2xl font-bold text-[#8B7355]">RangMatch <span class="text-slate-400 font-light">Studio Pro</span></h1>
        <button class="bg-[#8B7355] text-white px-6 py-2 rounded-full text-xs uppercase tracking-widest font-medium shadow-lg">Save Collection</button>
    </nav>

    <header class="text-center py-10 px-4">
        <h2 class="serif text-4xl md:text-6xl mb-4">Professional Design Studio</h2>
        <p class="text-slate-500 max-w-xl mx-auto mb-10 text-sm">High-fidelity garment mockups with industry-standard color harmony for textile artists.</p>
        
        <div class="flex flex-col items-center justify-center gap-6 mb-16">
            <div class="flex items-center gap-8 glass p-6 rounded-full shadow-2xl">
                <div class="flex flex-col items-center gap-2">
                    <span class="text-[10px] uppercase font-bold text-slate-400">Kurti Base Colour</span>
                    <input type="color" id="customColor" value="#B22222">
                </div>
                <div class="h-10 w-px bg-slate-200"></div>
                <div class="flex flex-col items-center">
                    <span class="text-[10px] uppercase font-bold text-slate-400">HEX Code</span>
                    <span id="hexDisplay" class="font-mono font-bold text-lg text-[#8B7355]">#B22222</span>
                </div>
            </div>
        </div>
    </header>

    <main class="max-w-7xl mx-auto px-6 pb-24">
        <div class="grid grid-cols-1 lg:grid-cols-12 gap-12">
            
            <!-- LEFT: REALISTIC SVG MOCKUP -->
            <div class="lg:col-span-6 flex flex-col items-center justify-center glass p-8 rounded-[50px] min-h-[650px] relative overflow-hidden bg-white/50">
                <h3 class="serif text-xl mb-8 text-slate-400">Realistic Visualization</h3>
                
                <div class="mockup-container relative w-full flex justify-center items-center">
                    <!-- REALISTIC SVG GARMENT -->
                    <svg width="300" height="500" viewBox="0 0 300 500" fill="none" xmlns="http://www.w3.org/2000/svg">
                        <!-- Dupatta Shape (Realistic Drape) -->
                        <path id="svgDupatta" d="M120 50 C 100 50, 80 100, 80 200 L 90 450 C 120 460, 150 460, 180 450 L 190 200 C 190 100, 170 50, 150 50 Z" 
                              fill="#1A1A1A" stroke="#000" stroke-width="0.5" />
                        <path d="M120 50 Q 135 60 150 50" stroke="white" stroke-opacity="0.3" stroke-width="2" />
                        <!-- Dupatta Border -->
                        <path id="svgBorder" d="M90 450 C 120 460, 150 460, 180 450 L 185 465 C 150 475, 120 475, 85 465 Z" fill="#D4AF37" />

                        <!-- Kurti Shape (Realistic silhouette like your image) -->
                        <path id="svgKurti" d="M100 80 L 200 80 C 210 80, 220 90, 220 110 L 230 220 L 210 400 L 90 400 L 70 220 L 80 110 C 80 90, 90 80, 100 80 Z" 
                              fill="#B22222" stroke="#000" stroke-width="0.5" />
                        <!-- Shading/Folds for Realism -->
                        <path d="M100 80 Q 110 150 100 250" stroke="black" stroke-opacity="0.1" stroke-width="3" />
                        <path d="M200 80 Q 190 150 200 250" stroke="black" stroke-opacity="0.1" stroke-width="3" />
                        <path d="M150 80 L 150 120" stroke="white" stroke-opacity="0.3" stroke-width="2" /> <!-- Neckline -->
                    </svg>
                </div>
                
                <div class="text-center mt-8">
                    <div id="selectedComboName" class="serif text-3xl text-[#8B7355] font-bold">Bold Contrast</div>
                    <div class="flex justify-center gap-3 mt-4">
                        <div onclick="copyToClipboard(document.getElementById('kurtiHex').innerText)" class="cursor-pointer px-3 py-1 bg-white border rounded-full text-[10px] font-mono font-bold hover:bg-slate-100">Kurti: <span id="kurtiHex">#B22222</span></div>
                        <div onclick="copyToClipboard(document.getElementById('dupattaHex').innerText)" class="cursor-pointer px-3 py-1 bg-white border rounded-full text-[10px] font-mono font-bold hover:bg-slate-100">Dupatta: <span id="dupattaHex">#1A1A1A</span></div>
                    </div>
                </div>
            </div>

            <!-- RIGHT: TREND GALLERY -->
            <div class="lg:col-span-6">
                <h3 class="serif text-2xl mb-8 border-b pb-2 border-slate-200">Trending Industry Combinations</h3>
                <div class="grid grid-cols-1 gap-4" id="dupattaGallery">
                    <!-- Industry Options injected here -->
                </div>
                
                <div class="mt-12 glass p-6 rounded-3xl border-l-8 border-[#8B7355]">
                    <div class="flex items-center gap-3 mb-2">
                        <div class="w-8 h-8 bg-[#8B7355] rounded-full flex items-center justify-center text-white text-xs font-bold">AI</div>
                        <h4 class="serif font-bold">Textile Expert Tip</h4>
                    </div>
                    <p id="aiSuggestion" class="text-slate-600 italic text-sm leading-relaxed">
                        "Select a match to see the market trend analysis."
                    </p>
                </div>
            </div>
        </div>
    </main>

    <!-- Hidden input for fallback copy mechanism -->
    <textarea id="copyHelper" class="absolute -left-full top-0 opacity-0"></textarea>

    <script>
        // --- INDUSTRY TREND LIBRARY ---
        const TrendLibrary = {
            "Red": {
                combos: [
                    { name: "Festive Black", dupatta: "#1A1A1A", border: "#D4AF37", ai: "Red aur Black Ajrak hamesha premium festive look deta hai." },
                    { name: "Traditional Mustard", dupatta: "#E1AD01", border: "#B22222", ai: "Red and Mustard classic pairing hai, mehendi aur wedding wear mein top trend hai." },
                    { name: "Luxury Ivory", dupatta: "#FDFBF7", border: "#D4AF37", ai: "Ivory balance karta hai red ko, jisse ek sophisticated look aata hai." },
                    { name: "Emerald Royal", dupatta: "#004D40", border: "#D4AF37", ai: "Deep Emerald green ke saath red ka contrast royal boutiques mein trending hai." },
                    { name: "Blush Pastel", dupatta: "#FFC0CB", border: "#B22222", ai: "Tonal dusty pink dupatta modern summer bridal collection ke liye best hai." }
                ]
            },
            "Mustard": {
                combos: [
                    { name: "Indigo Ikat", dupatta: "#00416A", border: "#E1AD01", ai: "Mustard and Indigo export market ka sabse trending combo hai." },
                    { name: "Maroon Rich", dupatta: "#800000", border: "#D4AF37", ai: "Maroon adds depth, traditional ethnic sets ke liye perfect hai." },
                    { name: "Forest Green", dupatta: "#228B22", border: "#E1AD01", ai: "Nature-inspired tones organic cotton collection mein bahut chal rahe hain." },
                    { name: "Pearl White", dupatta: "#FFFFFF", border: "#B8860B", ai: "White contrast Mustard ko fresh aur luxury look deta hai." },
                    { name: "Rustic Earth", dupatta: "#A0522D", border: "#E1AD01", ai: "Earthy tones contemporary linen wear mein trending hain." }
                ]
            },
            "Indigo": {
                combos: [
                    { name: "Mustard Pop", dupatta: "#E1AD01", border: "#00416A", ai: "Indigo ke saath Mustard ka pop effect market mein sabse zyada bikta hai." },
                    { name: "Rust Orange", dupatta: "#B7410E", border: "#00416A", ai: "Rust aur Indigo ka combination traditional hand-block prints ki pehchan hai." },
                    { name: "Cool Silver", dupatta: "#C0C0C0", border: "#00416A", ai: "Silver grey tones Indigo ke saath professional aur modern look dete hain." },
                    { name: "Pure White", dupatta: "#FDFBF7", border: "#00416A", ai: "Timeless summer combination, breathable aur clean look." },
                    { name: "Wine Mood", dupatta: "#722F37", border: "#D4AF37", ai: "Wine and Indigo ek moody, high-end winter look create karte hain." }
                ]
            },
            "Generic": {
                combos: [
                    { name: "Midnight Contrast", dupatta: "#1A1A1A", border: "#D4AF37", ai: "Black contrast almost har strong base color ke saath premium lagta hai." },
                    { name: "Neutral Luxury", dupatta: "#F5F5DC", border: "#D4AF37", ai: "Beige aur Ivory safest aur most luxury matches hain." },
                    { name: "Tonal Pastel", dupatta: "#E6E6FA", border: "#D3D3D3", ai: "Pastel pairing modern summer vibes ke liye best hai." },
                    { name: "Jewel Tone", dupatta: "#004D40", border: "#D4AF37", ai: "Deep jewel colors festive appearance ko rich banate hain." },
                    { name: "Classic White", dupatta: "#FFFFFF", border: "#8B7355", ai: "White hamesha ek clean aur professional balance create karta hai." }
                ]
            }
        };

        function getCategory(hex) {
            if (hex.startsWith("#B") || hex.startsWith("#C") || hex.startsWith("#D")) return "Red";
            if (hex.startsWith("#E") || hex.startsWith("#F") && hex.includes("A")) return "Mustard";
            if (hex.startsWith("#0") || hex.startsWith("#1")) return "Indigo";
            return "Generic";
        }

        // FIXED COPY FUNCTION (WORKS ON ALL MOBILE BROWSERS)
        function copyToClipboard(text) {
            const helper = document.getElementById('copyHelper');
            helper.value = text;
            helper.select();
            helper.setSelectionRange(0, 99999); // For mobile devices
            
            try {
                document.execCommand('copy');
                alert(`Copied ${text} to clipboard! Now paste in Photoshop.`);
            } catch (err) {
                alert('Oops, unable to copy');
            }
        }

        function applyCombination(index, baseHex) {
            const category = getCategory(baseHex);
            const selected = TrendLibrary[category].combos[index];
            
            document.getElementById('svgDupatta').setAttribute('fill', selected.dupatta);
            document.getElementById('svgBorder').setAttribute('fill', selected.border);
            document.getElementById('selectedComboName').innerText = selected.name;
            document.getElementById('dupattaHex').innerText = selected.dupatta.toUpperCase();
            document.getElementById('aiSuggestion').innerText = `"${selected.ai}"`;
            
            document.querySelectorAll('.option-card').forEach((card, idx) => {
                card.classList.toggle('active-option', idx === index);
            });
        }

        function updateStudio(hex) {
            document.getElementById('hexDisplay').innerText = hex.toUpperCase();
            document.getElementById('svgKurti').setAttribute('fill', hex);
            document.getElementById('kurtiHex').innerText = hex.toUpperCase();
            
            const category = getCategory(hex);
            const combos = TrendLibrary[category].combos;
            const gallery = document.getElementById('dupattaGallery');
            gallery.innerHTML = '';

            combos.forEach((d, index) => {
                const card = document.createElement('div');
                card.className = "option-card glass p-4 rounded-2xl flex items-center gap-4";
                card.onclick = () => applyCombination(index, hex);
                
                card.innerHTML = `
                    <div class="w-12 h-12 rounded-lg border shadow-sm relative overflow-hidden" style="background: ${d.dupatta}; border-bottom: 4px solid ${d.border}"></div>
                    <div class="flex-1 text-left">
                        <div class="text-xs font-bold uppercase tracking-tighter">${d.name}</div>
                        <div class="text-[10px] font-mono text-slate-400">${d.dupatta.toUpperCase()}</div>
                    </div>
                    <button onclick="event.stopPropagation(); copyToClipboard('${d.dupatta}')" class="copy-btn p-2 bg-slate-100 rounded-lg text-[10px] font-bold hover:bg-slate-200">COPY</button>
                `;
                gallery.appendChild(card);
            });

            applyCombination(0, hex);
        }

        document.getElementById('customColor').addEventListener('input', (e) => updateStudio(e.target.value));
        updateStudio("#B22222");
    </script>
</body>
</html>
