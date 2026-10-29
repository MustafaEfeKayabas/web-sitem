<!DOCTYPE html>
<html lang="tr" class="h-full">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Stüdyo Moda - Özel Tasarım Kıyafet Atölyesi</title>
    <!-- Tailwind CSS CDN -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- FontAwesome Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <!-- Google Fonts -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Cinzel:wght@600;700&family=Inter:wght@300;400;500;600;700&family=Montserrat:wght@800&family=Pacifico&family=Space+Grotesk:wght@600&display=swap" rel="stylesheet">
    
    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    colors: {
                        brand: {
                            50: '#fbf7f5',
                            100: '#f6ede8',
                            500: '#e56b40',
                            600: '#d15328',
                            900: '#1e1915',
                            dark: '#121212',
                            card: '#1e1e1e'
                        }
                    },
                    fontFamily: {
                        sans: ['Inter', 'sans-serif'],
                        heading: ['Cinzel', 'serif'],
                        boldFont: ['Montserrat', 'sans-serif'],
                        cursive: ['Pacifico', 'cursive'],
                        tech: ['Space Grotesk', 'sans-serif']
                    }
                }
            }
        }
    </script>
    <style>
        /* Custom Styles for Canvas and Controls */
        .workspace-bg {
            background-color: #1a1a1a;
            background-image: radial-gradient(#333 1px, transparent 1px);
            background-size: 20px 20px;
        }
        
        .tab-btn.active {
            border-bottom-color: #e56b40;
            color: #e56b40;
        }

        .custom-scrollbar::-webkit-scrollbar {
            width: 6px;
            height: 6px;
        }
        .custom-scrollbar::-webkit-scrollbar-track {
            background: #262626;
        }
        .custom-scrollbar::-webkit-scrollbar-thumb {
            background: #404040;
            border-radius: 3px;
        }
        .custom-scrollbar::-webkit-scrollbar-thumb:hover {
            background: #525252;
        }
        
        /* Interactive overlay item styling */
        .design-element {
            cursor: move;
            user-select: none;
            touch-action: none;
        }
        .design-element.selected {
            outline: 2px dashed #e56b40;
            outline-offset: 4px;
        }
    </style>
</head>
<body class="bg-zinc-950 text-zinc-100 font-sans h-full flex flex-col antialiased selection:bg-brand-500 selection:text-white">

    <!-- Header / Navbar -->
    <header class="border-b border-zinc-800 bg-zinc-900/80 backdrop-blur-md sticky top-0 z-40">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 lg:px-8 h-16 flex items-center justify-between">
            <!-- Brand Logo -->
            <div class="flex items-center space-x-3">
                <div class="w-10 h-10 rounded-xl bg-gradient-to-tr from-brand-600 to-amber-500 flex items-center justify-center text-white shadow-lg shadow-brand-500/20">
                    <i class="fa-solid font-bold fa-shirt text-xl"></i>
                </div>
                <div>
                    <span class="font-heading text-xl font-bold tracking-wider text-white">ATÖLYE<span class="text-brand-500">MODA</span></span>
                    <span class="hidden sm:inline-block text-xs bg-zinc-800 text-zinc-400 px-2 py-0.5 rounded ml-2 border border-zinc-700">3D Studio v2.0</span>
                </div>
            </div>

            <!-- Action Controls -->
            <div class="flex items-center space-x-3">
                <button id="btn-size-chart" class="px-3 py-2 text-xs sm:text-sm font-medium text-zinc-300 hover:text-white bg-zinc-800/80 hover:bg-zinc-800 border border-zinc-700/60 rounded-lg transition-all flex items-center gap-2">
                    <i class="fa-solid fa-ruler-horizontal text-brand-500"></i>
                    <span class="hidden sm:inline">Beden Rehberi</span>
                </button>
                <button id="btn-reset-design" class="px-3 py-2 text-xs sm:text-sm font-medium text-zinc-300 hover:text-rose-400 bg-zinc-800/80 hover:bg-zinc-800 border border-zinc-700/60 rounded-lg transition-all flex items-center gap-2">
                    <i class="fa-solid fa-rotate-left"></i>
                    <span class="hidden sm:inline">Sıfırla</span>
                </button>
                <button id="btn-save-design" class="px-3 py-2 text-xs sm:text-sm font-medium text-zinc-200 hover:text-white bg-zinc-800 hover:bg-zinc-700 border border-zinc-700 rounded-lg transition-all flex items-center gap-2">
                    <i class="fa-solid fa-download text-emerald-400"></i>
                    <span>Tasarımı Indir</span>
                </button>
            </div>
        </div>
    </header>

    <!-- Main Studio Layout -->
    <main class="flex-1 flex flex-col lg:flex-row overflow-hidden relative">

        <!-- LEFT PANEL: CUSTOMIZATION CONTROLS -->
        <aside class="w-full lg:w-96 bg-zinc-900 border-r border-zinc-800 flex flex-col z-10 shrink-0 h-[45vh] lg:h-auto border-b lg:border-b-0">
            <!-- Navigation Tabs -->
            <div class="flex border-b border-zinc-800 bg-zinc-900/50 text-xs sm:text-sm font-medium overflow-x-auto custom-scrollbar">
                <button class="tab-btn flex-1 min-w-[75px] py-3.5 px-3 border-b-2 border-transparent text-zinc-400 hover:text-zinc-200 transition-all flex flex-col items-center gap-1 active" data-tab="garment">
                    <i class="fa-solid fa-vest text-base"></i>
                    <span>Ürün</span>
                </button>
                <button class="tab-btn flex-1 min-w-[75px] py-3.5 px-3 border-b-2 border-transparent text-zinc-400 hover:text-zinc-200 transition-all flex flex-col items-center gap-1" data-tab="color">
                    <i class="fa-solid fa-palette text-base"></i>
                    <span>Renk</span>
                </button>
                <button class="tab-btn flex-1 min-w-[75px] py-3.5 px-3 border-b-2 border-transparent text-zinc-400 hover:text-zinc-200 transition-all flex flex-col items-center gap-1" data-tab="text">
                    <i class="fa-solid fa-font text-base"></i>
                    <span>Yazı</span>
                </button>
                <button class="tab-btn flex-1 min-w-[75px] py-3.5 px-3 border-b-2 border-transparent text-zinc-400 hover:text-zinc-200 transition-all flex flex-col items-center gap-1" data-tab="graphics">
                    <i class="fa-solid fa-icons text-base"></i>
                    <span>Grafik</span>
                </button>
                <button class="tab-btn flex-1 min-w-[75px] py-3.5 px-3 border-b-2 border-transparent text-zinc-400 hover:text-zinc-200 transition-all flex flex-col items-center gap-1" data-tab="pattern">
                    <i class="fa-solid fa-chess-board text-base"></i>
                    <span>Desen</span>
                </button>
            </div>

            <!-- Tab Contents Container -->
            <div class="flex-1 overflow-y-auto p-4 sm:p-5 custom-scrollbar space-y-6">
                
                <!-- TAB 1: GARMENT SELECTOR -->
                <div id="tab-garment" class="tab-content space-y-4">
                    <h3 class="text-xs uppercase font-bold tracking-wider text-zinc-400">Kıyafet Tipi Seçin</h3>
                    <div class="grid grid-cols-2 gap-3" id="garment-options">
                        <!-- Items rendered via JS -->
                    </div>
                </div>

                <!-- TAB 2: FABRIC COLOR -->
                <div id="tab-color" class="tab-content hidden space-y-5">
                    <h3 class="text-xs uppercase font-bold tracking-wider text-zinc-400">Kumaş Rengi</h3>
                    
                    <div>
                        <span class="text-xs text-zinc-400 mb-2 block">Hazır Renk Paleti</span>
                        <div class="grid grid-cols-6 gap-2" id="preset-colors">
                            <!-- Preset colors generated by JS -->
                        </div>
                    </div>

                    <div class="pt-3 border-t border-zinc-800">
                        <label for="custom-color-picker" class="text-xs text-zinc-400 mb-2 block">Özel Renk Seçici</label>
                        <div class="flex items-center space-x-3">
                            <input type="color" id="custom-color-picker" value="#222222" class="w-10 h-10 rounded-lg border border-zinc-700 bg-transparent cursor-pointer p-0.5">
                            <span id="custom-color-hex" class="text-sm font-mono text-zinc-300">#222222</span>
                        </div>
                    </div>

                    <div class="pt-3 border-t border-zinc-800">
                        <label class="text-xs text-zinc-400 mb-2 block">Baskı / Dikiş Tipi</label>
                        <div class="grid grid-cols-2 gap-2">
                            <button class="technique-btn active p-2.5 rounded-lg border border-brand-500 bg-brand-500/10 text-xs text-left font-medium" data-tech="print" data-price="0">
                                <div class="font-bold text-white">Dijital Baskı</div>
                                <div class="text-zinc-400 text-[10px]">Standart Canlı Renkler</div>
                            </button>
                            <button class="technique-btn p-2.5 rounded-lg border border-zinc-700 bg-zinc-800/50 text-xs text-left font-medium hover:border-zinc-600" data-tech="embroidery" data-price="45">
                                <div class="font-bold text-white">Nakış İşleme</div>
                                <div class="text-amber-400 text-[10px]">Premium Kabartma (+45 ₺)</div>
                            </button>
                        </div>
                    </div>
                </div>

                <!-- TAB 3: TEXT CREATOR -->
                <div id="tab-text" class="tab-content hidden space-y-4">
                    <h3 class="text-xs uppercase font-bold tracking-wider text-zinc-400">Özel Yazı Ekle</h3>
                    
                    <div class="space-y-3">
                        <div>
                            <label class="text-xs text-zinc-400 block mb-1">Metin</label>
                            <input type="text" id="text-input" placeholder="Yazınızı yazın..." class="w-full bg-zinc-800 border border-zinc-700 rounded-lg px-3 py-2 text-sm text-white focus:outline-none focus:border-brand-500">
                        </div>

                        <div class="grid grid-cols-2 gap-2">
                            <div>
                                <label class="text-xs text-zinc-400 block mb-1">Font Stili</label>
                                <select id="text-font" class="w-full bg-zinc-800 border border-zinc-700 rounded-lg px-2.5 py-2 text-xs text-white focus:outline-none focus:border-brand-500">
                                    <option value="Inter">Modern (Sans-Serif)</option>
                                    <option value="Montserrat">Kalın & Bold</option>
                                    <option value="Cinzel">Klasik & Lüks</option>
                                    <option value="Pacifico">El Yazısı</option>
                                    <option value="Space Grotesk">Sokak Stili / Tech</option>
                                </select>
                            </div>

                            <div>
                                <label class="text-xs text-zinc-400 block mb-1">Yazı Rengi</label>
                                <input type="color" id="text-color" value="#ffffff" class="w-full h-9 rounded-lg border border-zinc-700 bg-transparent cursor-pointer p-0.5">
                            </div>
                        </div>

                        <div>
                            <div class="flex justify-between text-xs text-zinc-400 mb-1">
                                <span>Boyut</span>
                                <span id="text-size-val">24px</span>
                            </div>
                            <input type="range" id="text-size" min="12" max="60" value="24" class="w-full accent-brand-500 bg-zinc-800">
                        </div>

                        <button id="btn-add-text" class="w-full py-2.5 bg-brand-500 hover:bg-brand-600 text-white font-medium rounded-lg text-sm transition-all flex items-center justify-center gap-2">
                            <i class="fa-solid fa-plus"></i> Metni Tasarıma Ekle
                        </button>
                    </div>
                </div>

                <!-- TAB 4: GRAPHICS & STICKERS -->
                <div id="tab-graphics" class="tab-content hidden space-y-4">
                    <h3 class="text-xs uppercase font-bold tracking-wider text-zinc-400">Görsel & Stiker Kütüphanesi</h3>
                    
                    <!-- Preset Sticker Collection -->
                    <div class="grid grid-cols-4 gap-2" id="sticker-grid">
                        <!-- Rendered by JS -->
                    </div>

                    <div class="pt-3 border-t border-zinc-800">
                        <label class="text-xs text-zinc-400 block mb-2">Kendi Logonu / Görselini Yükle</label>
                        <label class="flex flex-col items-center justify-center border-2 border-dashed border-zinc-700 hover:border-brand-500 rounded-xl p-4 cursor-pointer bg-zinc-800/30 hover:bg-zinc-800/60 transition-all text-center">
                            <i class="fa-solid fa-cloud-arrow-up text-2xl text-brand-500 mb-2"></i>
                            <span class="text-xs text-zinc-300 font-medium">Görsel Yüklemek İçin Tıklayın</span>
                            <span class="text-[10px] text-zinc-500 mt-1">PNG, JPG veya SVG (Max 5MB)</span>
                            <input type="file" id="custom-image-upload" accept="image/*" class="hidden">
                        </label>
                    </div>
                </div>

                <!-- TAB 5: PATTERNS -->
                <div id="tab-pattern" class="tab-content hidden space-y-4">
                    <h3 class="text-xs uppercase font-bold tracking-wider text-zinc-400">Kumaş Dokusu & Desen</h3>
                    <div class="grid grid-cols-2 gap-3" id="pattern-options">
                        <button class="pattern-card active p-3 border border-brand-500 bg-zinc-800/80 rounded-xl text-left" data-pattern="none">
                            <div class="w-full h-12 bg-zinc-700/50 rounded mb-2 flex items-center justify-center text-zinc-400">
                                <i class="fa-solid fa-ban"></i>
                            </div>
                            <span class="text-xs font-medium text-white block">Düz Kumaş</span>
                        </button>
                        <button class="pattern-card p-3 border border-zinc-700 hover:border-zinc-600 bg-zinc-800/80 rounded-xl text-left" data-pattern="camo">
                            <div class="w-full h-12 bg-zinc-700/50 rounded mb-2 flex items-center justify-center opacity-60 text-xs font-mono text-zinc-300">
                                CAMO
                            </div>
                            <span class="text-xs font-medium text-white block">Karakalem / Camo</span>
                        </button>
                        <button class="pattern-card p-3 border border-zinc-700 hover:border-zinc-600 bg-zinc-800/80 rounded-xl text-left" data-pattern="dots">
                            <div class="w-full h-12 bg-zinc-700/50 rounded mb-2 flex items-center justify-center opacity-60 text-xs font-mono text-zinc-300">
                                DOTS
                            </div>
                            <span class="text-xs font-medium text-white block">Puantiyeli</span>
                        </button>
                        <button class="pattern-card p-3 border border-zinc-700 hover:border-zinc-600 bg-zinc-800/80 rounded-xl text-left" data-pattern="stripes">
                            <div class="w-full h-12 bg-zinc-700/50 rounded mb-2 flex items-center justify-center opacity-60 text-xs font-mono text-zinc-300">
                                STRIPES
                            </div>
                            <span class="text-xs font-medium text-white block">Çizgili Moda</span>
                        </button>
                    </div>
                </div>

            </div>
        </aside>

        <!-- CENTER PANEL: INTERACTIVE CANVAS WORKSPACE -->
        <section class="flex-1 workspace-bg flex flex-col items-center justify-center p-4 sm:p-8 relative min-h-[350px] overflow-hidden">
            
            <!-- View Controls (Front/Back Toggle) -->
            <div class="absolute top-4 left-4 z-20 bg-zinc-900/90 border border-zinc-800 p-1.5 rounded-xl shadow-2xl flex items-center space-x-1 backdrop-blur-md">
                <button id="view-front" class="px-3 py-1.5 text-xs font-semibold rounded-lg bg-brand-500 text-white transition-all shadow">
                    Ön Yüz
                </button>
                <button id="view-back" class="px-3 py-1.5 text-xs font-semibold rounded-lg text-zinc-400 hover:text-white transition-all">
                    Arka Yüz
                </button>
            </div>

            <!-- Canvas Clear / Element Quick Controls -->
            <div id="element-controls" class="absolute top-4 right-4 z-20 hidden bg-zinc-900/90 border border-zinc-800 p-2 rounded-xl shadow-xl flex items-center space-x-2 text-xs">
                <span class="text-zinc-400 px-1">Seçili Öğeyi:</span>
                <button id="btn-delete-element" class="p-1.5 bg-rose-500/20 text-rose-400 hover:bg-rose-500 hover:text-white rounded-lg transition-all" title="Sil">
                    <i class="fa-solid fa-trash-can"></i>
                </button>
            </div>

            <!-- Garment Vector Mockup Container -->
            <div class="relative w-full max-w-[420px] aspect-square flex items-center justify-center select-none">
                
                <!-- SVG Dynamic Mockup Base -->
                <svg id="garment-svg" class="w-full h-full drop-shadow-2xl transition-all duration-300" viewBox="0 0 500 500" fill="none" xmlns="http://www.w3.org/2000/svg">
                    <!-- SVG content dynamically updated by JS -->
                </svg>

                <!-- Interactive Printable Area Overlay -->
                <div id="print-area" class="absolute w-[42%] h-[52%] top-[24%] left-[29%] border border-dashed border-brand-500/30 rounded-lg overflow-hidden flex items-center justify-center pointer-events-auto">
                    <!-- Text and Graphics Elements will be appended here -->
                    <div id="canvas-front-layer" class="w-full h-full relative"></div>
                    <div id="canvas-back-layer" class="w-full h-full relative hidden"></div>
                </div>
            </div>

            <!-- Hint overlay -->
            <div class="absolute bottom-4 text-center text-xs text-zinc-500 pointer-events-none flex items-center gap-2 bg-zinc-900/70 px-3 py-1.5 rounded-full border border-zinc-800/80">
                <i class="fa-solid fa-hand-pointer text-brand-500"></i>
                <span>Öğeleri sürükleyip boyutlandırabilirsiniz</span>
            </div>
        </section>

        <!-- RIGHT PANEL: SIZE, SUMMARY & CHECKOUT -->
        <aside class="w-full lg:w-80 bg-zinc-900 border-l border-zinc-800 p-5 flex flex-col justify-between z-10 shrink-0">
            <div class="space-y-6">
                
                <!-- Size Selector -->
                <div>
                    <div class="flex justify-between items-center mb-2.5">
                        <label class="text-xs uppercase font-bold tracking-wider text-zinc-400">Beden Seçimi</label>
                        <span id="stock-status" class="text-[10px] text-emerald-400 font-medium bg-emerald-950/60 border border-emerald-800/50 px-2 py-0.5 rounded-full">Stokta Var</span>
                    </div>
                    <div class="grid grid-cols-5 gap-1.5" id="size-selector">
                        <button class="size-btn py-2 text-xs font-bold rounded-lg border border-zinc-700 bg-zinc-800 text-zinc-300 hover:border-zinc-500 transition-all" data-size="S">S</button>
                        <button class="size-btn active py-2 text-xs font-bold rounded-lg border border-brand-500 bg-brand-500 text-white transition-all" data-size="M">M</button>
                        <button class="size-btn py-2 text-xs font-bold rounded-lg border border-zinc-700 bg-zinc-800 text-zinc-300 hover:border-zinc-500 transition-all" data-size="L">L</button>
                        <button class="size-btn py-2 text-xs font-bold rounded-lg border border-zinc-700 bg-zinc-800 text-zinc-300 hover:border-zinc-500 transition-all" data-size="XL">XL</button>
                        <button class="size-btn py-2 text-xs font-bold rounded-lg border border-zinc-700 bg-zinc-800 text-zinc-300 hover:border-zinc-500 transition-all" data-size="XXL">XXL</button>
                    </div>
                </div>

                <!-- Customization Features Checklist -->
                <div class="border-t border-zinc-800 pt-4 space-y-2">
                    <h4 class="text-xs uppercase font-bold tracking-wider text-zinc-400 mb-3">Tasarım Özeti</h4>
                    
                    <div class="flex justify-between text-xs text-zinc-300">
                        <span class="text-zinc-500">Seçilen Ürün:</span>
                        <span id="summary-garment-name" class="font-medium">Oversized Tişört</span>
                    </div>
                    <div class="flex justify-between text-xs text-zinc-300">
                        <span class="text-zinc-500">Teknik:</span>
                        <span id="summary-technique" class="font-medium">Dijital Baskı</span>
                    </div>
                    <div class="flex justify-between text-xs text-zinc-300">
                        <span class="text-zinc-500">Ekstra Detaylar:</span>
                        <span id="summary-extras" class="font-medium text-zinc-400">Yok</span>
                    </div>
                </div>

                <!-- Price Breakdown Calculation -->
                <div class="border-t border-zinc-800 pt-4 space-y-2.5 bg-zinc-950/40 p-3.5 rounded-xl border">
                    <div class="flex justify-between text-xs text-zinc-400">
                        <span>Taban Ürün Fiyatı:</span>
                        <span id="price-base">350 ₺</span>
                    </div>
                    <div class="flex justify-between text-xs text-zinc-400">
                        <span>Baskı / Özelleştirme:</span>
                        <span id="price-custom">0 ₺</span>
                    </div>
                    <div class="border-t border-zinc-800 pt-2 flex justify-between items-baseline">
                        <span class="text-sm font-bold text-white">Toplam Tutar:</span>
                        <div class="text-right">
                            <span id="price-total" class="text-xl font-extrabold text-brand-500">350 ₺</span>
                            <span class="block text-[10px] text-zinc-500">KDV Dahil / Ücretsiz Kargo</span>
                        </div>
                    </div>
                </div>

            </div>

            <!-- Order / Checkout Action CTA -->
            <div class="pt-4 border-t border-zinc-800 space-y-2">
                <button id="btn-order-now" class="w-full py-3.5 bg-gradient-to-r from-brand-500 to-amber-600 hover:from-brand-600 hover:to-amber-700 text-white font-bold rounded-xl text-sm shadow-xl shadow-brand-500/20 transition-all transform active:scale-[0.98] flex items-center justify-center gap-2">
                    <i class="fa-solid fa-bag-shopping"></i>
                    <span>Siparişi Tamamla</span>
                </button>
            </div>
        </aside>

    </main>

    <!-- MODAL 1: CHECKOUT / ORDER SUMMARY OVERLAY -->
    <div id="modal-checkout" class="fixed inset-0 bg-black/80 backdrop-blur-sm z-50 flex items-center justify-center p-4 hidden">
        <div class="bg-zinc-900 border border-zinc-800 rounded-2xl max-w-lg w-full p-6 space-y-5 relative shadow-2xl animate-fade-in">
            <button class="modal-close absolute top-4 right-4 text-zinc-400 hover:text-white text-lg">
                <i class="fa-solid fa-xmark"></i>
            </button>

            <div class="flex items-center space-x-3">
                <div class="w-10 h-10 rounded-full bg-brand-500/20 text-brand-500 flex items-center justify-center text-xl">
                    <i class="fa-solid fa-circle-check"></i>
                </div>
                <div>
                    <h3 class="text-lg font-bold text-white">Tasarımınız Hazır!</h3>
                    <p class="text-xs text-zinc-400">Sipariş bilgilerinizi tamamlayarak üretime gönderin.</p>
                </div>
            </div>

            <div class="bg-zinc-950 p-4 rounded-xl border border-zinc-800 space-y-2 text-xs">
                <div class="flex justify-between text-zinc-300">
                    <span>Ürün Türü:</span>
                    <span id="modal-summary-garment" class="font-bold text-white">-</span>
                </div>
                <div class="flex justify-between text-zinc-300">
                    <span>Beden:</span>
                    <span id="modal-summary-size" class="font-bold text-white">M</span>
                </div>
                <div class="flex justify-between text-zinc-300">
                    <span>Renk:</span>
                    <span id="modal-summary-color" class="font-bold text-white">-</span>
                </div>
                <div class="flex justify-between text-zinc-300 border-t border-zinc-800 pt-2">
                    <span class="text-sm font-bold text-white">Toplam Ödenecek:</span>
                    <span id="modal-summary-total" class="text-base font-bold text-brand-500">0 ₺</span>
                </div>
            </div>

            <form id="order-form" class="space-y-3">
                <div>
                    <label class="text-xs text-zinc-400 block mb-1">Ad Soyad</label>
                    <input type="text" required placeholder="Ahmet Yılmaz" class="w-full bg-zinc-800 border border-zinc-700 rounded-lg px-3 py-2 text-xs text-white focus:outline-none focus:border-brand-500">
                </div>
                <div class="grid grid-cols-2 gap-2">
                    <div>
                        <label class="text-xs text-zinc-400 block mb-1">E-Posta</label>
                        <input type="email" required placeholder="ahmet@example.com" class="w-full bg-zinc-800 border border-zinc-700 rounded-lg px-3 py-2 text-xs text-white focus:outline-none focus:border-brand-500">
                    </div>
                    <div>
                        <label class="text-xs text-zinc-400 block mb-1">Telefon</label>
                        <input type="tel" required placeholder="0555 000 00 00" class="w-full bg-zinc-800 border border-zinc-700 rounded-lg px-3 py-2 text-xs text-white focus:outline-none focus:border-brand-500">
                    </div>
                </div>
                <div>
                    <label class="text-xs text-zinc-400 block mb-1">Teslimat Adresi</label>
                    <textarea rows="2" required placeholder="Adresiniz..." class="w-full bg-zinc-800 border border-zinc-700 rounded-lg px-3 py-2 text-xs text-white focus:outline-none focus:border-brand-500"></textarea>
                </div>

                <button type="submit" class="w-full py-3 bg-brand-500 hover:bg-brand-600 text-white font-bold rounded-xl text-sm transition-all mt-2">
                    Ödemeye Geç & Üretime Gönder
                </button>
            </form>
        </div>
    </div>

    <!-- MODAL 2: SIZE CHART MODAL -->
    <div id="modal-size-chart" class="fixed inset-0 bg-black/80 backdrop-blur-sm z-50 flex items-center justify-center p-4 hidden">
        <div class="bg-zinc-900 border border-zinc-800 rounded-2xl max-w-md w-full p-6 space-y-4 relative shadow-2xl">
            <button class="modal-close absolute top-4 right-4 text-zinc-400 hover:text-white text-lg">
                <i class="fa-solid fa-xmark"></i>
            </button>

            <h3 class="text-base font-bold text-white flex items-center gap-2">
                <i class="fa-solid fa-ruler-combined text-brand-500"></i>
                <span>Beden Ölçü Tablosu (cm)</span>
            </h3>

            <div class="overflow-x-auto">
                <table class="w-full text-xs text-left text-zinc-300 border-collapse">
                    <thead class="bg-zinc-800 text-zinc-400 uppercase text-[10px]">
                        <tr>
                            <th class="p-2.5 border border-zinc-700">Beden</th>
                            <th class="p-2.5 border border-zinc-700">En (Göğüs)</th>
                            <th class="p-2.5 border border-zinc-700">Boy</th>
                            <th class="p-2.5 border border-zinc-700">Omuz</th>
                        </tr>
                    </thead>
                    <tbody>
                        <tr>
                            <td class="p-2.5 border border-zinc-800 font-bold text-white">S</td>
                            <td class="p-2.5 border border-zinc-800">50 cm</td>
                            <td class="p-2.5 border border-zinc-800">70 cm</td>
                            <td class="p-2.5 border border-zinc-800">46 cm</td>
                        </tr>
                        <tr class="bg-zinc-800/30">
                            <td class="p-2.5 border border-zinc-800 font-bold text-white">M</td>
                            <td class="p-2.5 border border-zinc-800">53 cm</td>
                            <td class="p-2.5 border border-zinc-800">72 cm</td>
                            <td class="p-2.5 border border-zinc-800">48 cm</td>
                        </tr>
                        <tr>
                            <td class="p-2.5 border border-zinc-800 font-bold text-white">L</td>
                            <td class="p-2.5 border border-zinc-800">56 cm</td>
                            <td class="p-2.5 border border-zinc-800">74 cm</td>
                            <td class="p-2.5 border border-zinc-800">50 cm</td>
                        </tr>
                        <tr class="bg-zinc-800/30">
                            <td class="p-2.5 border border-zinc-800 font-bold text-white">XL</td>
                            <td class="p-2.5 border border-zinc-800">60 cm</td>
                            <td class="p-2.5 border border-zinc-800">76 cm</td>
                            <td class="p-2.5 border border-zinc-800">53 cm</td>
                        </tr>
                        <tr>
                            <td class="p-2.5 border border-zinc-800 font-bold text-white">XXL</td>
                            <td class="p-2.5 border border-zinc-800">64 cm</td>
                            <td class="p-2.5 border border-zinc-800">78 cm</td>
                            <td class="p-2.5 border border-zinc-800">56 cm</td>
                        </tr>
                    </tbody>
                </table>
            </div>

            <p class="text-[11px] text-zinc-500 italic">
                * Ölçümler unisex rahat kesim (oversize) kalıplarımıza göredir.
            </p>
        </div>
    </div>

    <!-- Notification Toast -->
    <div id="toast" class="fixed bottom-5 right-5 bg-zinc-800 border border-zinc-700 text-white px-4 py-3 rounded-xl shadow-2xl flex items-center space-x-3 transition-all transform translate-y-20 opacity-0 z-50">
        <i id="toast-icon" class="fa-solid fa-circle-info text-brand-500"></i>
        <span id="toast-message" class="text-xs font-medium">İşlem başarılı</span>
    </div>

    <!-- APPLICATION LOGIC JS -->
    <script>
        // --- Garment Catalog Data ---
        const GARMENTS = {
            tshirt: {
                name: 'Oversized Tişört',
                basePrice: 350,
                icon: 'fa-shirt',
                svgFront: `<path d="M150,110 L200,90 L250,110 L300,90 L350,110 L390,180 L340,200 L340,430 L160,430 L160,200 L110,180 Z" fill="CURRENT_COLOR" stroke="#333" stroke-width="4"/>
                           <path d="M200,90 Q250,130 300,90" fill="none" stroke="#222" stroke-width="5"/>`,
                svgBack: `<path d="M150,110 L200,90 L250,110 L300,90 L350,110 L390,180 L340,200 L340,430 L160,430 L160,200 L110,180 Z" fill="CURRENT_COLOR" stroke="#333" stroke-width="4"/>
                          <path d="M200,90 Q250,105 300,90" fill="none" stroke="#222" stroke-width="4"/>`
            },
            hoodie: {
                name: 'Kapüşonlu Sweatshirt',
                basePrice: 650,
                icon: 'fa-user-ninja',
                svgFront: `<path d="M140,130 L190,80 Q250,60 310,80 L360,130 L410,210 L350,230 L350,440 L150,440 L150,230 L90,210 Z" fill="CURRENT_COLOR" stroke="#333" stroke-width="4"/>
                           <!-- Hoodie strings & Pocket -->
                           <path d="M220,130 L220,200 M280,130 L280,200" stroke="#888" stroke-width="3" stroke-linecap="round"/>
                           <path d="M180,330 L320,330 L340,410 L160,410 Z" fill="none" stroke="#333" stroke-width="3"/>`,
                svgBack: `<path d="M140,130 L190,80 Q250,60 310,80 L360,130 L410,210 L350,230 L350,440 L150,440 L150,230 L90,210 Z" fill="CURRENT_COLOR" stroke="#333" stroke-width="4"/>
                          <!-- Hood Fold Back -->
                          <path d="M190,80 Q250,160 310,80" fill="none" stroke="#222" stroke-width="4"/>`
            },
            sweatshirt: {
                name: 'Bisiklet Yaka Sweat',
                basePrice: 550,
                icon: 'fa-vest-patches',
                svgFront: `<path d="M145,115 L200,95 L250,110 L300,95 L355,115 L400,200 L345,220 L345,435 L155,435 L155,220 L100,200 Z" fill="CURRENT_COLOR" stroke="#333" stroke-width="4"/>
                           <path d="M200,95 Q250,125 300,95" fill="none" stroke="#222" stroke-width="6"/>`,
                svgBack: `<path d="M145,115 L200,95 L250,110 L300,95 L355,115 L400,200 L345,220 L345,435 L155,435 L155,220 L100,200 Z" fill="CURRENT_COLOR" stroke="#333" stroke-width="4"/>
                          <path d="M200,95 Q250,105 300,95" fill="none" stroke="#222" stroke-width="4"/>`
            },
            jacket: {
                name: 'Kruvaze Kolej Ceket',
                basePrice: 890,
                icon: 'fa-mitten',
                svgFront: `<path d="M140,120 L200,90 L250,110 L300,90 L360,120 L405,210 L350,230 L350,430 L150,430 L150,230 L95,210 Z" fill="CURRENT_COLOR" stroke="#333" stroke-width="4"/>
                           <!-- Zip / Buttons Line -->
                           <line x1="250" y1="110" x2="250" y2="430" stroke="#111" stroke-width="4"/>
                           <circle cx="260" cy="180" r="4" fill="#aaa"/>
                           <circle cx="260" cy="240" r="4" fill="#aaa"/>
                           <circle cx="260" cy="300" r="4" fill="#aaa"/>`,
                svgBack: `<path d="M140,120 L200,90 L250,110 L300,90 L360,120 L405,210 L350,230 L350,430 L150,430 L150,230 L95,210 Z" fill="CURRENT_COLOR" stroke="#333" stroke-width="4"/>`
            }
        };

        const COLOR_PRESETS = [
            '#222222', '#f5f5f5', '#1a2e40', '#4a1525', 
            '#2d4a3e', '#7c522b', '#d15328', '#e2b13c'
        ];

        const STICKER_ICONS = [
            'fa-fire', 'fa-bolt', 'fa-heart', 'fa-crown',
            'fa-skull', 'fa-dragon', 'fa-star', 'fa-gem',
            'fa-cat', 'fa-compass', 'fa-feather', 'fa-face-smile'
        ];

        // --- Application State ---
        let state = {
            selectedGarment: 'tshirt',
            selectedColor: '#222222',
            selectedSize: 'M',
            currentView: 'front', // 'front' | 'back'
            techniquePrice: 0,
            techniqueName: 'Dijital Baskı',
            selectedElement: null,
            elementsCount: 0
        };

        // --- DOM Elements ---
        const garmentSvg = document.getElementById('garment-svg');
        const canvasFront = document.getElementById('canvas-front-layer');
        const canvasBack = document.getElementById('canvas-back-layer');
        const priceBaseEl = document.getElementById('price-base');
        const priceCustomEl = document.getElementById('price-custom');
        const priceTotalEl = document.getElementById('price-total');
        const elementControls = document.getElementById('element-controls');

        // --- Initialize Studio ---
        window.addEventListener('DOMContentLoaded', () => {
            renderGarmentCatalog();
            renderColorPresets();
            renderStickerGrid();
            updateGarmentSvg();
            setupEventListeners();
            updatePricing();
        });

        // --- Render Functions ---
        function renderGarmentCatalog() {
            const container = document.getElementById('garment-options');
            container.innerHTML = '';

            Object.keys(GARMENTS).forEach(key => {
                const item = GARMENTS[key];
                const activeClass = key === state.selectedGarment ? 'border-brand-500 bg-brand-500/10' : 'border-zinc-800 bg-zinc-800/40 hover:border-zinc-700';
                
                const btn = document.createElement('button');
                btn.className = `p-3 rounded-xl border ${activeClass} transition-all text-left flex flex-col justify-between h-24 group`;
                btn.onclick = () => selectGarment(key);
                
                btn.innerHTML = `
                    <div class="flex justify-between items-start">
                        <i class="fa-solid ${item.icon} text-xl text-brand-500"></i>
                        <span class="text-[11px] font-bold text-zinc-400">${item.basePrice} ₺</span>
                    </div>
                    <span class="text-xs font-semibold text-white group-hover:text-brand-500 transition-colors">${item.name}</span>
                `;
                container.appendChild(btn);
            });
        }

        function renderColorPresets() {
            const container = document.getElementById('preset-colors');
            container.innerHTML = '';

            COLOR_PRESETS.forEach(color => {
                const btn = document.createElement('button');
                btn.className = `w-8 h-8 rounded-full border-2 border-zinc-700 hover:scale-110 transition-transform flex items-center justify-center`;
                btn.style.backgroundColor = color;
                btn.onclick = () => setGarmentColor(color);
                
                if (color === state.selectedColor) {
                    btn.innerHTML = `<i class="fa-solid fa-check text-xs ${color === '#f5f5f5' ? 'text-black' : 'text-white'}"></i>`;
                }
                container.appendChild(btn);
            });
        }

        function renderStickerGrid() {
            const container = document.getElementById('sticker-grid');
            container.innerHTML = '';

            STICKER_ICONS.forEach(iconClass => {
                const btn = document.createElement('button');
                btn.className = `h-12 rounded-lg bg-zinc-800 border border-zinc-700 hover:border-brand-500 flex items-center justify-center text-xl text-zinc-300 hover:text-brand-500 transition-all`;
                btn.innerHTML = `<i class="fa-solid ${iconClass}"></i>`;
                btn.onclick = () => addIconToCanvas(iconClass);
                container.appendChild(btn);
            });
        }

        // --- Core Interactions ---
        function selectGarment(key) {
            state.selectedGarment = key;
            renderGarmentCatalog();
            updateGarmentSvg();
            document.getElementById('summary-garment-name').textContent = GARMENTS[key].name;
            updatePricing();
        }

        function setGarmentColor(colorHex) {
            state.selectedColor = colorHex;
            document.getElementById('custom-color-picker').value = colorHex;
            document.getElementById('custom-color-hex').textContent = colorHex.toUpperCase();
            renderColorPresets();
            updateGarmentSvg();
        }

        function updateGarmentSvg() {
            const garment = GARMENTS[state.selectedGarment];
            const rawSvg = state.currentView === 'front' ? garment.svgFront : garment.svgBack;
            garmentSvg.innerHTML = rawSvg.replace(/CURRENT_COLOR/g, state.selectedColor);
        }

        function updatePricing() {
            const basePrice = GARMENTS[state.selectedGarment].basePrice;
            const customPrice = state.elementsCount * 25 + state.techniquePrice; // 25 TL per design element
            const totalPrice = basePrice + customPrice;

            priceBaseEl.textContent = `${basePrice} ₺`;
            priceCustomEl.textContent = `${customPrice} ₺`;
            priceTotalEl.textContent = `${totalPrice} ₺`;
        }

        // --- Canvas Element Manipulations ---
        function getCurrentCanvasLayer() {
            return state.currentView === 'front' ? canvasFront : canvasBack;
        }

        function addTextToCanvas(text, font, color, size) {
            if (!text.trim()) return;

            const el = document.createElement('div');
            el.className = 'design-element absolute p-1';
            el.style.left = '30%';
            el.style.top = '40%';
            el.style.color = color;
            el.style.fontSize = `${size}px`;
            el.style.fontFamily = font;
            el.textContent = text;

            makeElementInteractive(el);
            getCurrentCanvasLayer().appendChild(el);
            state.elementsCount++;
            updatePricing();
            showToast('Yazı eklendi');
        }

        function addIconToCanvas(iconClass) {
            const el = document.createElement('div');
            el.className = 'design-element absolute p-1 text-brand-500';
            el.style.left = '40%';
            el.style.top = '40%';
            el.style.fontSize = '40px';
            el.innerHTML = `<i class="fa-solid ${iconClass}"></i>`;

            makeElementInteractive(el);
            getCurrentCanvasLayer().appendChild(el);
            state.elementsCount++;
            updatePricing();
            showToast('Grafik eklendi');
        }

        function makeElementInteractive(el) {
            let isDragging = false;
            let currentX, currentY, initialX, initialY;

            el.addEventListener('pointerdown', (e) => {
                e.stopPropagation();
                selectElement(el);

                isDragging = true;
                initialX = e.clientX - el.offsetLeft;
                initialY = e.clientY - el.offsetTop;
            });

            window.addEventListener('pointermove', (e) => {
                if (!isDragging || state.selectedElement !== el) return;
                
                currentX = e.clientX - initialX;
                currentY = e.clientY - initialY;

                el.style.left = `${currentX}px`;
                el.style.top = `${currentY}px`;
            });

            window.addEventListener('pointerup', () => {
                isDragging = false;
            });
        }

        function selectElement(el) {
            document.querySelectorAll('.design-element').forEach(item => item.classList.remove('selected'));
            if (el) {
                el.classList.add('selected');
                state.selectedElement = el;
                elementControls.classList.remove('hidden');
            } else {
                state.selectedElement = null;
                elementControls.classList.add('hidden');
            }
        }

        // --- Event Listeners Setup ---
        function setupEventListeners() {
            // Tab Switcher
            document.querySelectorAll('.tab-btn').forEach(btn => {
                btn.addEventListener('click', () => {
                    document.querySelectorAll('.tab-btn').forEach(b => b.classList.remove('active'));
                    document.querySelectorAll('.tab-content').forEach(c => c.classList.add('hidden'));

                    btn.classList.add('active');
                    const tabId = btn.getAttribute('data-tab');
                    document.getElementById(`tab-${tabId}`).classList.remove('hidden');
                });
            });

            // Front/Back View Toggle
            document.getElementById('view-front').addEventListener('click', () => {
                state.currentView = 'front';
                document.getElementById('view-front').className = 'px-3 py-1.5 text-xs font-semibold rounded-lg bg-brand-500 text-white transition-all shadow';
                document.getElementById('view-back').className = 'px-3 py-1.5 text-xs font-semibold rounded-lg text-zinc-400 hover:text-white transition-all';
                canvasFront.classList.remove('hidden');
                canvasBack.classList.add('hidden');
                updateGarmentSvg();
            });

            document.getElementById('view-back').addEventListener('click', () => {
                state.currentView = 'back';
                document.getElementById('view-back').className = 'px-3 py-1.5 text-xs font-semibold rounded-lg bg-brand-500 text-white transition-all shadow';
                document.getElementById('view-front').className = 'px-3 py-1.5 text-xs font-semibold rounded-lg text-zinc-400 hover:text-white transition-all';
                canvasBack.classList.remove('hidden');
                canvasFront.classList.add('hidden');
                updateGarmentSvg();
            });

            // Color picker
            document.getElementById('custom-color-picker').addEventListener('input', (e) => {
                setGarmentColor(e.target.value);
            });

            // Add Text
            document.getElementById('btn-add-text').addEventListener('click', () => {
                const text = document.getElementById('text-input').value;
                const font = document.getElementById('text-font').value;
                const color = document.getElementById('text-color').value;
                const size = document.getElementById('text-size').value;
                addTextToCanvas(text, font, color, size);
            });

            document.getElementById('text-size').addEventListener('input', (e) => {
                document.getElementById('text-size-val').textContent = `${e.target.value}px`;
            });

            // Custom Image Upload
            document.getElementById('custom-image-upload').addEventListener('change', (e) => {
                const file = e.target.files[0];
                if (file) {
                    const reader = new FileReader();
                    reader.onload = function(event) {
                        const img = document.createElement('img');
                        img.src = event.target.result;
                        img.className = 'design-element absolute w-20 h-20 object-contain';
                        img.style.left = '35%';
                        img.style.top = '35%';
                        
                        makeElementInteractive(img);
                        getCurrentCanvasLayer().appendChild(img);
                        state.elementsCount++;
                        updatePricing();
                        showToast('Görsel yüklendi');
                    };
                    reader.readAsDataURL(file);
                }
            });

            // Technique selection
            document.querySelectorAll('.technique-btn').forEach(btn => {
                btn.addEventListener('click', () => {
                    document.querySelectorAll('.technique-btn').forEach(b => {
                        b.className = 'technique-btn p-2.5 rounded-lg border border-zinc-700 bg-zinc-800/50 text-xs text-left font-medium hover:border-zinc-600';
                    });
                    btn.className = 'technique-btn active p-2.5 rounded-lg border border-brand-500 bg-brand-500/10 text-xs text-left font-medium';
                    
                    state.techniquePrice = parseInt(btn.getAttribute('data-price'));
                    state.techniqueName = btn.querySelector('.font-bold').textContent;
                    document.getElementById('summary-technique').textContent = state.techniqueName;
                    updatePricing();
                });
            });

            // Delete Element
            document.getElementById('btn-delete-element').addEventListener('click', () => {
                if (state.selectedElement) {
                    state.selectedElement.remove();
                    selectElement(null);
                    state.elementsCount = Math.max(0, state.elementsCount - 1);
                    updatePricing();
                    showToast('Öğe silindi');
                }
            });

            // Deselect on workspace click
            document.getElementById('print-area').addEventListener('click', (e) => {
                if (e.target === document.getElementById('print-area')) {
                    selectElement(null);
                }
            });

            // Size Selector Buttons
            document.querySelectorAll('.size-btn').forEach(btn => {
                btn.addEventListener('click', () => {
                    document.querySelectorAll('.size-btn').forEach(b => {
                        b.className = 'size-btn py-2 text-xs font-bold rounded-lg border border-zinc-700 bg-zinc-800 text-zinc-300 hover:border-zinc-500 transition-all';
                    });
                    btn.className = 'size-btn active py-2 text-xs font-bold rounded-lg border border-brand-500 bg-brand-500 text-white transition-all';
                    state.selectedSize = btn.getAttribute('data-size');
                });
            });

            // Reset Design Button
            document.getElementById('btn-reset-design').addEventListener('click', () => {
                canvasFront.innerHTML = '';
                canvasBack.innerHTML = '';
                state.elementsCount = 0;
                selectElement(null);
                updatePricing();
                showToast('Tasarım sıfırlandı');
            });

            // Modals Logic
            document.getElementById('btn-size-chart').addEventListener('click', () => {
                document.getElementById('modal-size-chart').classList.remove('hidden');
            });

            document.getElementById('btn-order-now').addEventListener('click', () => {
                document.getElementById('modal-summary-garment').textContent = GARMENTS[state.selectedGarment].name;
                document.getElementById('modal-summary-size').textContent = state.selectedSize;
                document.getElementById('modal-summary-color').textContent = state.selectedColor.toUpperCase();
                document.getElementById('modal-summary-total').textContent = priceTotalEl.textContent;

                document.getElementById('modal-checkout').classList.remove('hidden');
            });

            document.querySelectorAll('.modal-close').forEach(btn => {
                btn.addEventListener('click', () => {
                    document.querySelectorAll('.fixed').forEach(m => {
                        if (!m.id.includes('toast')) m.classList.add('hidden');
                    });
                });
            });

            // Submit order
            document.getElementById('order-form').addEventListener('submit', (e) => {
                e.preventDefault();
                document.getElementById('modal-checkout').classList.add('hidden');
                showToast('Siparişiniz başarıyla alındı!');
            });

            // Save Design Download
            document.getElementById('btn-save-design').addEventListener('click', () => {
                showToast('Tasarım görüntüsü indiriliyor...');
            });
        }

        // --- Notification System ---
        function showToast(msg) {
            const toast = document.getElementById('toast');
            document.getElementById('toast-message').textContent = msg;
            toast.classList.remove('translate-y-20', 'opacity-0');
            
            setTimeout(() => {
                toast.classList.add('translate-y-20', 'opacity-0');
            }, 3000);
        }
    </script>
</body>
</html>
