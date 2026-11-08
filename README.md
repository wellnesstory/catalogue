<!DOCTYPE html>
<html lang="zh-HK">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Wellnesstory | 香水目錄</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Noto+Serif+TC:wght@300;400;600&family=Outfit:wght@300;400;600&display=swap" rel="stylesheet">
    <script>
        tailwind.config = {
            theme: {
                extend: {
                    colors: {
                        brand: {
                            bg: '#fef9f5',
                            text: '#4a4440',
                            accent: '#e2d3c8'
                        }
                    },
                    fontFamily: {
                        serif: ['"Noto Serif TC"', 'serif'],
                        sans: ['"Outfit"', '"Noto Serif TC"', 'sans-serif'],
                    }
                }
            }
        }
    </script>
    <style>
        body {
            background-color: #fef9f5;
            color: #4a4440;
            -webkit-font-smoothing: antialiased;
        }
        /* 隱藏捲軸但保持可以捲動 */
        ::-webkit-scrollbar {
            width: 0px;
            background: transparent;
        }
    </style>
</head>
<body class="font-sans antialiased min-h-screen flex flex-col">

    <!-- 頂部提示橫幅 (固定於上方) -->
    <div class="sticky top-0 z-50 w-full bg-[#f4e8e1] shadow-sm border-b border-[#e2d3c8]">
        <div class="max-w-md mx-auto px-4 py-2.5 text-center font-serif text-[#5c524c]">
            <p class="text-[11px] md:text-xs leading-relaxed mb-2 font-medium tracking-wide">
                <span class="font-bold text-[#8b6f5c]">📍 TOP寄賣店限定</span>｜現場僅提供 5ml & 10ml 裝<br>
                購買 30ml 或以上容量：
            </p>
            <div class="flex gap-2 justify-center items-center">
                <a href="https://www.instagram.com/wellnesstory.hk/" target="_blank" class="flex-1 max-w-[145px] flex items-center justify-center gap-1.5 px-2 py-1.5 rounded-lg bg-white border border-[#8b6f5c] text-[#8b6f5c] text-xs font-bold hover:bg-[#fef9f5] transition-colors shadow-sm">
                    <svg xmlns="http://www.w3.org/2000/svg" width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-instagram"><rect width="20" height="20" x="2" y="2" rx="5" ry="5"/><path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"/><line x1="17.5" x2="17.51" y1="6.5" y2="6.5"/></svg>
                    IG DM 聯絡
                </a>
                <a href="https://wellnesstory.github.io/time-for-self-care/" target="_blank" class="flex-1 max-w-[145px] flex items-center justify-center gap-1.5 px-2 py-1.5 rounded-lg bg-[#8b6f5c] text-white text-xs font-bold hover:bg-[#7a6150] transition-colors shadow-sm">
                    <svg xmlns="http://www.w3.org/2000/svg" width="14" height="14" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-globe"><circle cx="12" cy="12" r="10"/><path d="M12 2a14.5 14.5 0 0 0 0 20 14.5 14.5 0 0 0 0-20"/><path d="M2 12h20"/></svg>
                    官方網頁購買
                </a>
            </div>
        </div>
    </div>

    <!-- 品牌標頭 -->
    <header class="pt-8 pb-6 px-4 text-center">
        <h1 class="text-4xl font-semibold tracking-widest font-serif mb-3">Wellnesstory</h1>
        <p class="text-sm text-gray-500 font-serif tracking-widest">「快樂是為自己而噴的香水」</p>
    </header>

    <!-- 搜尋與過濾區塊 -->
    <section class="max-w-lg mx-auto px-4 mb-8">
        <div class="relative mb-4">
            <input type="text" id="searchInput" placeholder="搜尋香水名稱..." class="w-full px-5 py-3 pl-11 rounded-full border border-[#e2d3c8] bg-white focus:outline-none focus:ring-2 focus:ring-[#c7a47a] text-sm font-sans transition-all shadow-sm">
            <svg class="absolute left-4 top-3.5 h-5 w-5 text-gray-400" xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round"><circle cx="11" cy="11" r="8"></circle><line x1="21" y1="21" x2="16.65" y2="16.65"></line></svg>
        </div>
        <div class="flex gap-2 justify-center font-serif text-xs md:text-sm">
            <button class="filter-btn active px-3 md:px-4 py-2 rounded-full bg-[#8b6f5c] text-white transition-all shadow-sm" data-category="all">全部</button>
            <button class="filter-btn px-3 md:px-4 py-2 rounded-full bg-white text-[#8b6f5c] border border-[#e2d3c8] hover:bg-[#f4e8e1] hover:border-[#8b6f5c] transition-all shadow-sm" data-category="emotion">情緒香水</button>
            <button class="filter-btn px-3 md:px-4 py-2 rounded-full bg-white text-[#8b6f5c] border border-[#e2d3c8] hover:bg-[#f4e8e1] hover:border-[#8b6f5c] transition-all shadow-sm" data-category="month">生日月份</button>
        </div>
    </section>

    <!-- 香水目錄內容區塊 -->
    <main class="flex-grow max-w-lg mx-auto px-3 w-full pb-12">
        <div id="catalog-container" class="grid grid-cols-2 gap-3 sm:gap-4">
            <!-- JavaScript 將會在這裡插入香水卡片 -->
        </div>
    </main>

    <!-- 頁腳 -->
    <footer class="mt-auto py-8 bg-white/50 border-t border-[#f4e8e1] text-center">
        <p class="text-xs text-gray-500 mb-2 font-serif">Follow us for more updates</p>
        <a href="https://instagram.com/wellnesstory.hk" target="_blank" class="inline-flex items-center justify-center gap-2 text-[#8b6f5c] hover:text-[#5c524c] transition-colors font-medium">
            <svg xmlns="http://www.w3.org/2000/svg" width="18" height="18" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="lucide lucide-instagram"><rect width="20" height="20" x="2" y="2" rx="5" ry="5"/><path d="M16 11.37A4 4 0 1 1 12.63 8 4 4 0 0 1 16 11.37z"/><line x1="17.5" x2="17.51" y1="6.5" y2="6.5"/></svg>
            @wellnesstory.hk
        </a>
    </footer>

    <!-- 生成香水卡片的腳本 -->
    <script>
        document.addEventListener('DOMContentLoaded', () => {
            const perfumes = [
                // 情緒香水
                { 
                    category: 'emotion',
                    name: 'UNIQUE 獨特', 
                    quote: '「勇敢走過所有情緒，成就這獨特的平靜。」', 
                    top: '粉紅胡椒、伯爵茶、山葡萄', 
                    mid: '煙草、白麝香、金銀花、山艾草', 
                    base: '琥珀、韓國雪松',
                    theme: 'from-[#e6d0b3] to-[#c7a47a]',
                    shadow: 'shadow-[#e6d0b3]/40'
                },
                { 
                    category: 'emotion',
                    name: 'FREEDOM 自由', 
                    quote: '「自由不是用力壓抑，而是學會與它共存。」', 
                    top: '佛手柑、天竺葵、茉莉', 
                    mid: '海洋、白木', 
                    base: '檜木、檀木',
                    theme: 'from-[#a8c5e6] to-[#6b91c2]',
                    shadow: 'shadow-[#a8c5e6]/40'
                },
                { 
                    category: 'emotion',
                    name: 'GLOOMY 憂鬱', 
                    quote: '「憂鬱或許不討喜，但請允許自己偶爾不開心。」', 
                    top: '青檸、香草、快樂鼠尾草', 
                    mid: '五月玫瑰、梔子、晚香玉、鈴蘭、苔蘚', 
                    base: '琥珀、麝香、薰衣草',
                    theme: 'from-[#86c7b3] to-[#458f77]',
                    shadow: 'shadow-[#86c7b3]/40'
                },
                { 
                    category: 'emotion',
                    name: 'JOY 快樂', 
                    quote: '「世界或許複雜，而快樂始終是一種選擇。」', 
                    top: '橙、荔枝、蘋果', 
                    mid: '覆盆子、菠蘿、薄荷', 
                    base: '香根草、含羞草、葡萄柚、桃',
                    theme: 'from-[#c2e8cd] to-[#88c29b]',
                    shadow: 'shadow-[#c2e8cd]/40'
                },
                { 
                    category: 'emotion',
                    name: 'ANXIOUS 焦慮', 
                    quote: '「焦慮是靈魂對事物最真切的重視。」', 
                    top: '黑胡椒、茉莉、綠色植物', 
                    mid: '乾草、野胡蘿蔔籽、香脂、海洋', 
                    base: '橡木、零陵香豆、乳香',
                    theme: 'from-[#eeb793] to-[#d47b4a]',
                    shadow: 'shadow-[#eeb793]/40'
                },
                { 
                    category: 'emotion',
                    name: 'MISS 懷念', 
                    quote: '「懷念是為了讓遺失的自己，再次被拾起。」', 
                    top: '白風鈴草、黃葵', 
                    mid: '迷迭香、木蘭、橙花', 
                    base: '苦橙葉、癒創木、白麝香',
                    theme: 'from-[#fbd786] to-[#f7797d]',
                    shadow: 'shadow-[#fbd786]/40'
                },
                { 
                    category: 'emotion',
                    name: 'HAPPINESS 幸福', 
                    quote: '「幸福一直都在，因愛從未離開。」', 
                    top: '草莓、柑橘、雲呢拿', 
                    mid: '桃、大馬士革玫瑰、茉莉、鬱金香', 
                    base: '麝香、白琥珀',
                    theme: 'from-[#f3b5c4] to-[#d67b93]',
                    shadow: 'shadow-[#f3b5c4]/40'
                },
                { 
                    category: 'emotion',
                    name: 'COURAGE 勇氣', 
                    quote: '「勇氣始於面對恐懼的那一刻。」', 
                    top: '佛手柑、薄荷、白麝香', 
                    mid: '硯石、快樂鼠尾草、白葡萄酒', 
                    base: '韓國雪松、白木、琥珀',
                    theme: 'from-[#ccdcd2] to-[#99b5a4]',
                    shadow: 'shadow-[#ccdcd2]/40'
                },
                { 
                    category: 'emotion',
                    name: 'Loving 愛', 
                    quote: '「愛是微醺的花香，甜美得讓人甘願沉醉。」', 
                    top: '橙、白葡萄酒、香料', 
                    mid: '白桂花、橙花、香脂', 
                    base: '檀木、雲呢拿、橡木',
                    theme: 'from-[#facde5] to-[#e49bbd]',
                    shadow: 'shadow-[#facde5]/40',
                    isNew: true
                },
                { 
                    category: 'emotion',
                    name: 'Tired 疲累', 
                    quote: '「疲累，是歷經微苦後，渴望被洗淨的瞬間。」', 
                    top: '寺香、韓國紙香', 
                    mid: '韓國草藥、韓國雪松、醛', 
                    base: '白琥珀、琥珀',
                    theme: 'from-[#d1d5db] to-[#6b7280]',
                    shadow: 'shadow-[#d1d5db]/40',
                    isNew: true
                },

                // 生日月份香水
                { category: 'month', name: 'JAN 一月', quote: '堅定務實，渴望踏實，尋找安穩的依靠', top: '佛手柑', mid: '乳香、伯爵茶', base: '雪松木', theme: 'from-[#d6cfc7] to-[#8b8076]', shadow: 'shadow-[#d6cfc7]/40' },
                { category: 'month', name: 'FEB 二月', quote: '浪漫敏感，渴望自由與被溫柔接納', top: '梨、薰衣草', mid: '雲呢拿', base: '白麝香', theme: 'from-[#c299d6] to-[#83569c]', shadow: 'shadow-[#c299d6]/40' },
                { category: 'month', name: 'MAR 三月', quote: '活力直率，渴望突破框架', top: '苦檸檬', mid: '鬱金香、伯爵茶', base: '白松香', theme: 'from-[#9ade8c] to-[#4c9e3c]', shadow: 'shadow-[#9ade8c]/40' },
                { category: 'month', name: 'APR 四月', quote: '溫和優雅，渴望柔和陪伴', top: '粉紅胡椒、茉莉', mid: '海洋', base: '檀木', theme: 'from-[#fca5a5] to-[#dc2626]', shadow: 'shadow-[#fca5a5]/40' },
                { category: 'month', name: 'MAY 五月', quote: '活躍交際，渴望激發靈感，保持快樂', top: '葡萄柚', mid: '豆蔻、硯石', base: '橙花、檜木', theme: 'from-[#bbf7d0] to-[#22c55e]', shadow: 'shadow-[#bbf7d0]/40' },
                { category: 'month', name: 'JUN 六月', quote: '情感細膩，渴望情感上安全感', top: '桃、洋甘菊', mid: '大馬士革玫瑰', base: '白琥珀', theme: 'from-[#fde047] to-[#ca8a04]', shadow: 'shadow-[#fde047]/40' },
                { category: 'month', name: 'JUL 七月', quote: '自信熱情，渴望放大自我價值', top: '橙、粉紅胡椒', mid: '綠色植物、海洋', base: '琥珀', theme: 'from-[#fbcfe8] to-[#db2777]', shadow: 'shadow-[#fbcfe8]/40' },
                { category: 'month', name: 'AUG 八月', quote: '追求完美，渴望放空，洗滌疲憊思緒', top: '馬鞭草、海洋', mid: '白風鈴草、香草', base: '檜木', theme: 'from-[#fed7aa] to-[#ea580c]', shadow: 'shadow-[#fed7aa]/40' },
                { category: 'month', name: 'SEP 九月', quote: '和諧優雅，渴望和平陪伴', top: '伯爵茶', mid: '白桂花、柑橘', base: '白木', theme: 'from-[#bfdbfe] to-[#2563eb]', shadow: 'shadow-[#bfdbfe]/40' },
                { category: 'month', name: 'OCT 十月', quote: '神秘深刻，渴望自我探索', top: '沒藥、麝貓', mid: '蘭花', base: '皮革', theme: 'from-[#a5f3fc] to-[#0891b2]', shadow: 'shadow-[#a5f3fc]/40' },
                { category: 'month', name: 'NOV 十一月', quote: '愛好自由，渴望擴闊視野', top: '柚子、煙草', mid: '癒創木', base: '肉豆蔻', theme: 'from-[#fecdd3] to-[#e11d48]', shadow: 'shadow-[#fecdd3]/40' },
                { category: 'month', name: 'DEC 十二月', quote: '沉穩負責，渴望溫暖', top: '橙、鹽', mid: '零陵香豆', base: '黑松、寺香', theme: 'from-[#e5e7eb] to-[#4b5563]', shadow: 'shadow-[#e5e7eb]/40' },
            ];

            const container = document.getElementById('catalog-container');
            const searchInput = document.getElementById('searchInput');
            const filterBtns = document.querySelectorAll('.filter-btn');
            
            let currentCategory = 'all';
            let currentSearchTerm = '';

            function renderPerfumes() {
                container.innerHTML = '';
                
                const filtered = perfumes.filter(perfume => {
                    const matchesCategory = currentCategory === 'all' || perfume.category === currentCategory;
                    const searchStr = `${perfume.name} ${perfume.top} ${perfume.mid} ${perfume.base}`.toLowerCase();
                    const matchesSearch = searchStr.includes(currentSearchTerm.toLowerCase());
                    return matchesCategory && matchesSearch;
                });

                if (filtered.length === 0) {
                    container.innerHTML = '<div class="text-center py-10 text-gray-400 font-serif">找不到符合的香水...</div>';
                    return;
                }

                filtered.forEach(perfume => {
                    const nameParts = perfume.name.split(' ');
                    const enName = nameParts[0];
                    const zhName = nameParts.slice(1).join(' ');
                    
                    const newBadge = perfume.isNew ? '<div class="absolute top-2 left-2 bg-red-400 text-white text-[9px] font-bold px-1.5 py-0.5 rounded shadow-sm z-20 tracking-wider">NEW</div>' : '';

                    const cardHTML = `
                        <div class="bg-white rounded-2xl p-4 sm:p-5 shadow-md hover:shadow-lg ${perfume.shadow} relative overflow-hidden border border-white/40 backdrop-blur-sm transition-all duration-300 flex flex-col h-full">
                            ${newBadge}
                            <!-- 裝飾性漸變背景 (模擬水彩/色塊質感) -->
                            <div class="absolute -bottom-10 -right-10 w-32 h-32 rounded-full bg-gradient-to-br ${perfume.theme} opacity-20 blur-xl pointer-events-none"></div>
                            <div class="absolute top-0 right-0 w-1.5 h-full bg-gradient-to-b ${perfume.theme} opacity-70"></div>

                            <div class="relative z-10 flex-grow flex flex-col">
                                <!-- 香水名稱與引言 -->
                                <div class="mb-3 border-b border-gray-100 pb-2 flex-shrink-0">
                                    <h2 class="text-base sm:text-lg font-semibold mb-0.5 flex flex-col flex-wrap leading-tight mt-1">
                                        <span class="font-sans tracking-wide text-gray-800">${enName}</span> 
                                        <span class="font-serif text-[13px] sm:text-sm text-gray-600">${zhName}</span>
                                    </h2>
                                    <p class="text-[10px] sm:text-xs text-gray-500 font-serif italic mt-1.5 leading-relaxed tracking-wide line-clamp-3">
                                        ${perfume.quote}
                                    </p>
                                </div>

                                <!-- 香調表 -->
                                <div class="space-y-2 font-serif text-[10px] sm:text-xs flex-grow">
                                    <div class="flex items-start gap-1.5">
                                        <span class="text-[9px] font-bold text-white bg-[#b5a395] px-1 py-0.5 rounded tracking-wider shrink-0 mt-0.5">前調</span>
                                        <span class="text-gray-700 leading-snug pt-0.5">${perfume.top}</span>
                                    </div>
                                    <div class="flex items-start gap-1.5">
                                        <span class="text-[9px] font-bold text-white bg-[#a38f7f] px-1 py-0.5 rounded tracking-wider shrink-0 mt-0.5">中調</span>
                                        <span class="text-gray-700 leading-snug pt-0.5">${perfume.mid}</span>
                                    </div>
                                    <div class="flex items-start gap-1.5">
                                        <span class="text-[9px] font-bold text-white bg-[#877464] px-1 py-0.5 rounded tracking-wider shrink-0 mt-0.5">後調</span>
                                        <span class="text-gray-700 leading-snug pt-0.5">${perfume.base}</span>
                                    </div>
                                </div>
                            </div>
                        </div>
                    `;
                    container.insertAdjacentHTML('beforeend', cardHTML);
                });
            }

            // 事件監聽器
            searchInput.addEventListener('input', (e) => {
                currentSearchTerm = e.target.value;
                renderPerfumes();
            });

            filterBtns.forEach(btn => {
                btn.addEventListener('click', (e) => {
                    // 更新按鈕樣式
                    filterBtns.forEach(b => {
                        b.classList.remove('bg-[#8b6f5c]', 'text-white');
                        b.classList.add('bg-white', 'text-[#8b6f5c]', 'border', 'border-[#e2d3c8]');
                    });
                    
                    e.target.classList.remove('bg-white', 'text-[#8b6f5c]', 'border', 'border-[#e2d3c8]');
                    e.target.classList.add('bg-[#8b6f5c]', 'text-white');

                    // 更新分類並渲染
                    currentCategory = e.target.dataset.category;
                    renderPerfumes();
                });
            });

            // 初始渲染
            renderPerfumes();
        });
    </script>
</body>
</html>
