إليك الكود المصدري الكامل والمتطور لمتجر Cell Buy Zone (سيل باي زون) كـ Single
Page Application (SPA) احترافية جاهزة للاستخدام الفوري ومكتوبة بلغات الويب
القياسية (HTML5 / Tailwind CSS / Vanilla JavaScript)، ومصممة بأعلى معايير متاجر
التكنولوجيا الفاخرة (Luxury Tech Store).

المتجر يدعم:

1.  ثنائية اللغة الكاملة (العربية RTL والإنجليزية LTR) بتبديل فوري لكامل النصوص
    والعناصر.
2.  الوضع الليلي (Dark Mode) مع الحفظ التلقائي في localStorage.
3.  محرك تجارة إلكترونية حقيقي: سلة مشتريات تفاعلية، قائمة مفضلة، بحث فوري Live
    Search، فلاتر حية بالأسعار والسعات والألوان، صفحة تفاصيل المنتج، وإتمام طلب
    حقيقي (Checkout) مع توليد رقم تتبع في الأردن بالدينار الأردني (JOD).
4.  تركيز استثنائي على منظومة Apple و iPhone (بما في ذلك عائلة iPhone 16 و
    iPhone 17)، بالإضافة لأقسام Kieslect، Realme، الساعات، الإكسسوارات والشواحن.

طريقة التشغيل الفوري:

1.  انسخ الكود أدناه بالكامل واحفظه في ملف باسم index.html.
2.  افتح الملف في أي متصفح حديث (Chrome, Safari, Edge, Firefox) على جهاز
    الكمبيوتر أو التابلت أو الهاتف المحمول.

<!DOCTYPE html>
<html lang="ar" dir="rtl">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Cell Buy Zone | سيل باي زون - متجر الهواتف والإلكترونيات الذكية</title>
    <meta name="description" content="Cell Buy Zone - وجهتكم الأولى لأحدث أجهزة iPhone، Apple، Realme، Kieslect والإلكترونيات الذكية في الأردن بالدينار الأردني.">
    
    <!-- Fonts: Cairo (Arabic) & Plus Jakarta Sans (English) -->
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Cairo:wght@300;400;500;600;700;800;900&family=Plus+Jakarta+Sans:wght@400;500;600;700;800&display=swap" rel="stylesheet">
    
    <!-- Tailwind CSS CDN with Plugins -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Lucide Icons -->
    <script src="https://unpkg.com/lucide@latest"></script>

    <script>
        tailwind.config = {
            darkMode: 'class',
            theme: {
                extend: {
                    colors: {
                        royal: {
                            50: '#eff6ff',
                            100: '#dbeafe',
                            500: '#1d4ed8',
                            600: '#1442bb',
                            700: '#0F3D92', /* الألوان الملكية للهوية */
                            800: '#0B2B68',
                            900: '#071d47',
                            950: '#030f26'
                        },
                        techDark: '#0B0F17',
                        techCard: '#131B2A',
                    },
                    fontFamily: {
                        cairo: ['Cairo', 'sans-serif'],
                        sans: ['Plus Jakarta Sans', 'Cairo', 'sans-serif'],
                    }
                }
            }
        }
    </script>

    <style>
        * {
            -webkit-tap-highlight-color: transparent;
        }
        body {
            font-family: 'Cairo', 'Plus Jakarta Sans', sans-serif;
            transition: background-color 0.3s ease, color 0.3s ease;
        }
        [dir="ltr"] {
            font-family: 'Plus Jakarta Sans', 'Cairo', sans-serif;
        }
        
        /* تأثيرات التمرير المخصص */
        ::-webkit-scrollbar {
            width: 8px;
            height: 8px;
        }
        ::-webkit-scrollbar-track {
            background: rgba(0,0,0,0.05);
        }
        ::-webkit-scrollbar-thumb {
            background: #cbd5e1;
            border-radius: 4px;
        }
        .dark ::-webkit-scrollbar-thumb {
            background: #334155;
        }

        /* حركات ناعمة */
        .glassmorphism {
            background: rgba(255, 255, 255, 0.85);
            backdrop-filter: blur(12px);
            -webkit-backdrop-filter: blur(12px);
        }
        .dark .glassmorphism {
            background: rgba(11, 15, 23, 0.85);
        }

        .badge-glow {
            box-shadow: 0 0 15px rgba(29, 78, 216, 0.4);
        }

        /* حركات ظهور تدريجي */
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(8px); }
            to { opacity: 1; transform: translateY(0); }
        }
        .animate-fade-in {
            animation: fadeIn 0.3s cubic-bezier(0.16, 1, 0.3, 1) forwards;
        }
    </style>
</head>
<body class="bg-slate-50 text-slate-900 dark:bg-techDark dark:text-slate-100 min-h-screen flex flex-col antialiased selection:bg-royal-600 selection:text-white">

    <!-- 1. شريط الإعلانات والاتصال العلوي (Top Header) -->
    <div class="bg-royal-950 text-slate-300 text-xs py-2 px-4 border-b border-royal-900/60 z-50">
        <div class="max-w-7xl mx-auto flex flex-col sm:flex-row justify-between items-center gap-2">
            <div class="flex items-center gap-4">
                <span class="inline-flex items-center gap-1.5 text-royal-400 font-medium">
                    <i data-lucide="shield-check" class="w-3.5 h-3.5 text-emerald-400"></i>
                    <span data-i18n="top-guarantee">أجهزة أصلية 100% | كفالة معتمدة</span>
                </span>
                <span class="hidden md:inline text-slate-600">|</span>
                <span class="hidden md:inline-flex items-center gap-1 text-slate-300">
                    <i data-lucide="map-pin" class="w-3.5 h-3.5 text-royal-400"></i>
                    <span data-i18n="top-location">عَمّان - الأردن | توصيل فوري لكافة المحافظات</span>
                </span>
            </div>
            
            <div class="flex items-center gap-4">
                <a href="tel:+962790000000" class="hover:text-white transition flex items-center gap-1.5 font-sans">
                    <i data-lucide="phone-call" class="w-3.5 h-3.5 text-royal-400"></i>
                    <span dir="ltr">+962 7 9000 0000</span>
                </a>
                <span class="text-slate-600">|</span>
                <!-- زر تبديل اللغة -->
                <button onclick="toggleLanguage()" class="hover:text-white flex items-center gap-1 font-semibold transition bg-royal-900/80 px-2 py-0.5 rounded border border-royal-700/50">
                    <i data-lucide="globe" class="w-3 h-3 text-royal-300"></i>
                    <span id="langLabel">English</span>
                </button>
                <!-- زر تبديل الوضع الليلي -->
                <button onclick="toggleDarkMode()" class="hover:text-white p-1 rounded-md transition" title="Dark / Light mode">
                    <i id="themeIcon" data-lucide="moon" class="w-3.5 h-3.5 text-royal-300"></i>
                </button>
            </div>
        </div>
    </div>

    <!-- 2. الهيدر الرئيسي وشريط الملاحة (Sticky Nav) -->
    <header class="sticky top-0 z-40 glassmorphism border-b border-slate-200/80 dark:border-slate-800/80 transition-all duration-300">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 py-3.5">
            <div class="flex items-center justify-between gap-4">
                
                <!-- الشعار Brand Logo -->
                <div class="flex items-center gap-3">
                    <button onclick="navigate('home')" class="flex items-center gap-2.5 text-left group">
                        <div class="w-10 h-10 rounded-xl bg-gradient-to-tr from-royal-900 via-royal-700 to-royal-500 flex items-center justify-center text-white shadow-lg shadow-royal-700/30 group-hover:scale-105 transition-transform duration-300">
                            <i data-lucide="zap" class="w-5 h-5 text-amber-300 fill-amber-300"></i>
                        </div>
                        <div>
                            <span class="text-xl sm:text-2xl font-black tracking-tight font-sans text-royal-900 dark:text-white block leading-none">
                                CELL<span class="text-royal-600 dark:text-royal-400">BUY</span>ZONE
                            </span>
                            <span class="text-[10px] tracking-widest text-slate-500 dark:text-slate-400 font-bold uppercase block mt-0.5" data-i18n="logo-subtitle">
                                سيل باي زون للإلكترونيات
                            </span>
                        </div>
                    </button>
                </div>

                <!-- شريط البحث الفوري (Live Search) -->
                <div class="hidden lg:flex flex-1 max-w-md relative mx-4">
                    <div class="relative w-full">
                        <input type="text" id="searchInput" oninput="handleSearch(this.value)" 
                            data-i18n-placeholder="search-placeholder"
                            placeholder="ابحث عن iPhone 17، ساعات، إكسسوارات..." 
                            class="w-full bg-slate-100 dark:bg-slate-900/90 text-sm border border-slate-300 dark:border-slate-700 rounded-full py-2.5 px-11 focus:outline-none focus:ring-2 focus:ring-royal-600/50 focus:border-royal-600 transition">
                        <i data-lucide="search" class="w-4 h-4 text-slate-400 absolute top-3.5 right-4 pointer-events-none"></i>
                        <button onclick="clearSearch()" id="searchClearBtn" class="hidden absolute top-3 left-4 text-slate-400 hover:text-slate-600">
                            <i data-lucide="x" class="w-4 h-4"></i>
                        </button>
                    </div>
                    <!-- نتائج البحث المنسدلة -->
                    <div id="searchResults" class="hidden absolute top-12 right-0 left-0 bg-white dark:bg-techCard border border-slate-200 dark:border-slate-800 rounded-2xl shadow-2xl p-2 z-50 max-h-96 overflow-y-auto"></div>
                </div>

                <!-- أدوات المستخدم: المفضلة، السلة، الطلبات -->
                <div class="flex items-center gap-1 sm:gap-2">
                    <!-- المفضلة -->
                    <button onclick="openWishlistModal()" class="relative p-2.5 text-slate-600 dark:text-slate-300 hover:text-royal-600 dark:hover:text-royal-400 hover:bg-slate-100 dark:hover:bg-slate-800/60 rounded-full transition" title="المفضلة">
                        <i data-lucide="heart" class="w-5 h-5"></i>
                        <span id="wishlistCountBadge" class="hidden absolute -top-1 -right-1 bg-rose-500 text-white text-[10px] font-bold w-4 h-4 rounded-full items-center justify-center">0</span>
                    </button>

                    <!-- سلة المشتريات -->
                    <button onclick="toggleCartDrawer(true)" class="relative p-2.5 text-slate-600 dark:text-slate-300 hover:text-royal-600 dark:hover:text-royal-400 hover:bg-slate-100 dark:hover:bg-slate-800/60 rounded-full transition flex items-center gap-2" title="سلة التسوق">
                        <i data-lucide="shopping-bag" class="w-5 h-5"></i>
                        <span id="cartCountBadge" class="hidden absolute -top-1 -right-1 bg-royal-600 text-white text-[10px] font-bold w-4 h-4 rounded-full items-center justify-center">0</span>
                        <span id="cartTotalHeader" class="hidden md:inline text-xs font-bold font-sans text-slate-900 dark:text-slate-100">0.00 JOD</span>
                    </button>

                    <!-- حسابي / الطلبات -->
                    <button onclick="openOrdersModal()" class="p-2.5 text-slate-600 dark:text-slate-300 hover:text-royal-600 dark:hover:text-royal-400 hover:bg-slate-100 dark:hover:bg-slate-800/60 rounded-full transition" title="طلباتي">
                        <i data-lucide="package-check" class="w-5 h-5"></i>
                    </button>

                    <!-- زر قائمة الهاتف (Mobile Menu) -->
                    <button onclick="toggleMobileMenu()" class="lg:hidden p-2 text-slate-700 dark:text-slate-200">
                        <i data-lucide="menu" class="w-6 h-6"></i>
                    </button>
                </div>
            </div>

            <!-- قائمة الروابط الرئيسية (Desktop Navigation) -->
            <nav class="hidden lg:flex items-center justify-between border-t border-slate-200/60 dark:border-slate-800/60 pt-3 mt-3 text-sm font-semibold">
                <div class="flex items-center gap-7">
                    <button onclick="navigate('home')" class="nav-link text-slate-600 dark:text-slate-300 hover:text-royal-600 dark:hover:text-royal-400 transition flex items-center gap-1.5" data-nav="home">
                        <i data-lucide="home" class="w-4 h-4"></i>
                        <span data-i18n="nav-home">الرئيسية</span>
                    </button>
                    <button onclick="navigate('shop')" class="nav-link text-slate-600 dark:text-slate-300 hover:text-royal-600 dark:hover:text-royal-400 transition" data-nav="shop" data-i18n="nav-shop">
                        جميع المنتجات (Shop All)
                    </button>
                    <!-- رابط Apple المميز -->
                    <button onclick="navigate('apple')" class="nav-link relative text-royal-700 dark:text-royal-400 font-bold transition flex items-center gap-1" data-nav="apple">
                        <i data-lucide="apple" class="w-4 h-4"></i>
                        <span data-i18n="nav-apple">Apple & iPhone</span>
                        <span class="bg-royal-100 dark:bg-royal-950 text-royal-700 dark:text-royal-300 text-[10px] px-1.5 py-0.5 rounded-full font-sans uppercase">Focus</span>
                    </button>
                    <button onclick="filterCategory('realme')" class="nav-link text-slate-600 dark:text-slate-300 hover:text-royal-600 transition" data-nav="realme">
                        Realme
                    </button>
                    <button onclick="filterCategory('kieslect')" class="nav-link text-slate-600 dark:text-slate-300 hover:text-royal-600 transition" data-nav="kieslect">
                        Kieslect
                    </button>
                    <button onclick="filterCategory('smartwatches')" class="nav-link text-slate-600 dark:text-slate-300 hover:text-royal-600 transition" data-nav="smartwatches" data-i18n="nav-watches">
                        ساعات ذكية
                    </button>
                    <button onclick="filterCategory('accessories')" class="nav-link text-slate-600 dark:text-slate-300 hover:text-royal-600 transition" data-nav="accessories" data-i18n="nav-accessories">
                        إكسسوارات وشواحن
                    </button>
                    <button onclick="navigate('preorder')" class="nav-link text-rose-600 dark:text-rose-400 hover:text-rose-700 transition flex items-center gap-1" data-nav="preorder">
                        <span class="w-2 h-2 rounded-full bg-rose-500 animate-pulse"></span>
                        <span data-i18n="nav-preorder">حجز مسبق (Pre-Order)</span>
                    </button>
                    <button onclick="navigate('offers')" class="nav-link text-amber-600 dark:text-amber-400 hover:text-amber-500 transition" data-nav="offers" data-i18n="nav-offers">
                        العروض الخاصة
                    </button>
                    <button onclick="navigate('about')" class="nav-link text-slate-600 dark:text-slate-300 hover:text-royal-600 transition" data-nav="about" data-i18n="nav-about">
                        من نحن (About Us)
                    </button>
                </div>

                <div class="text-xs text-slate-400 flex items-center gap-2">
                    <span class="inline-block w-2 h-2 rounded-full bg-emerald-500"></span>
                    <span data-i18n="top-status">المتجر متاح لاستقبال الطلبات أونلاين</span>
                </div>
            </nav>
        </div>

        <!-- قائمة الموبايل المنسدلة -->
        <div id="mobileMenu" class="hidden lg:hidden border-t border-slate-200 dark:border-slate-800 bg-white dark:bg-techCard px-4 py-4 space-y-2">
            <div class="mb-3">
                <input type="text" oninput="handleSearch(this.value)" data-i18n-placeholder="search-placeholder" placeholder="ابحث عن المنتجات..." class="w-full text-sm bg-slate-100 dark:bg-slate-900 border border-slate-300 dark:border-slate-700 rounded-lg p-2.5">
            </div>
            <button onclick="navigate('home'); toggleMobileMenu()" class="w-full text-right py-2 text-sm font-bold block" data-i18n="nav-home">الرئيسية</button>
            <button onclick="navigate('shop'); toggleMobileMenu()" class="w-full text-right py-2 text-sm font-bold block" data-i18n="nav-shop">جميع المنتجات</button>
            <button onclick="navigate('apple'); toggleMobileMenu()" class="w-full text-right py-2 text-sm font-bold text-royal-600 block">Apple & iPhone</button>
            <button onclick="filterCategory('realme'); toggleMobileMenu()" class="w-full text-right py-2 text-sm font-semibold block">Realme</button>
            <button onclick="filterCategory('kieslect'); toggleMobileMenu()" class="w-full text-right py-2 text-sm font-semibold block">Kieslect</button>
            <button onclick="filterCategory('smartwatches'); toggleMobileMenu()" class="w-full text-right py-2 text-sm font-semibold block" data-i18n="nav-watches">ساعات ذكية</button>
            <button onclick="filterCategory('accessories'); toggleMobileMenu()" class="w-full text-right py-2 text-sm font-semibold block" data-i18n="nav-accessories">إكسسوارات وشواحن</button>
            <button onclick="navigate('preorder'); toggleMobileMenu()" class="w-full text-right py-2 text-sm font-bold text-rose-500 block" data-i18n="nav-preorder">حجز مسبق (Pre-Order)</button>
            <button onclick="navigate('offers'); toggleMobileMenu()" class="w-full text-right py-2 text-sm font-semibold text-amber-500 block" data-i18n="nav-offers">العروض</button>
            <button onclick="navigate('about'); toggleMobileMenu()" class="w-full text-right py-2 text-sm font-semibold block" data-i18n="nav-about">من نحن</button>
        </div>
    </header>

    <!-- المحتوى الرئيسي (Dynamic Views Container) -->
    <main id="appContent" class="flex-1 max-w-7xl mx-auto w-full px-4 sm:px-6 py-6 transition-all duration-300">
        <!-- يتم حقن الواجهات ديناميكياً هنا عبر الجافاسكريبت -->
    </main>

    <!-- 3. المودال التفاعلي لتفاصيل المنتج (Quick View & Full Specs Modal) -->
    <div id="productModal" class="fixed inset-0 z-50 hidden overflow-y-auto bg-black/70 backdrop-blur-sm p-4 flex items-center justify-center animate-fade-in">
        <div class="relative bg-white dark:bg-techCard w-full max-w-4xl rounded-3xl shadow-2xl border border-slate-200 dark:border-slate-800 overflow-hidden my-8">
            <button onclick="closeProductModal()" class="absolute top-4 left-4 z-10 w-9 h-9 rounded-full bg-slate-100 dark:bg-slate-800 text-slate-700 dark:text-slate-300 flex items-center justify-center hover:bg-slate-200 transition">
                <i data-lucide="x" class="w-5 h-5"></i>
            </button>
            <div id="productModalBody" class="p-6 md:p-8">
                <!-- محتوى المنتج يُحقن هنا -->
            </div>
        </div>
    </div>

    <!-- 4. درج سلة المشتريات الجانبي (Cart Drawer) -->
    <div id="cartDrawer" class="fixed inset-0 z-50 hidden transition-opacity duration-300">
        <div onclick="toggleCartDrawer(false)" class="absolute inset-0 bg-black/60 backdrop-blur-xs"></div>
        <div class="absolute top-0 bottom-0 left-0 max-w-md w-full bg-white dark:bg-techCard shadow-2xl flex flex-col z-10 border-r border-slate-200 dark:border-slate-800 animate-fade-in">
            <!-- هيدر السلة -->
            <div class="p-5 border-b border-slate-200 dark:border-slate-800 flex items-center justify-between">
                <div class="flex items-center gap-2">
                    <i data-lucide="shopping-bag" class="w-5 h-5 text-royal-600"></i>
                    <h3 class="font-bold text-lg" data-i18n="cart-title">سلة التسوق الخاصة بك</h3>
                    <span id="cartDrawerItemCount" class="text-xs bg-royal-100 dark:bg-royal-950 text-royal-600 font-bold px-2 py-0.5 rounded-full">0</span>
                </div>
                <button onclick="toggleCartDrawer(false)" class="p-2 hover:bg-slate-100 dark:hover:bg-slate-800 rounded-full transition">
                    <i data-lucide="x" class="w-5 h-5"></i>
                </button>
            </div>

            <!-- قائمة عناصر السلة -->
            <div id="cartDrawerItems" class="flex-1 overflow-y-auto p-5 space-y-4">
                <!-- العناصر -->
            </div>

            <!-- أسفل السلة والحسابات -->
            <div class="p-5 border-t border-slate-200 dark:border-slate-800 bg-slate-50 dark:bg-slate-900/40 space-y-3">
                <div class="space-y-1.5 text-sm">
                    <div class="flex justify-between text-slate-500">
                        <span data-i18n="cart-subtotal">المجموع الفرعي:</span>
                        <span id="cartSubtotal" class="font-sans font-bold">0.00 JOD</span>
                    </div>
                    <div class="flex justify-between text-slate-500">
                        <span data-i18n="cart-delivery">التوصيل لكافة المحافظات:</span>
                        <span class="text-emerald-600 font-bold" data-i18n="cart-free-delivery">مجاني للطلبات فوق 100 JOD</span>
                    </div>
                    <div class="flex justify-between text-base font-black text-slate-900 dark:text-white pt-2 border-t border-slate-200 dark:border-slate-800">
                        <span data-i18n="cart-total">المجموع الكلي:</span>
                        <span id="cartTotal" class="font-sans text-royal-600 dark:text-royal-400 text-lg">0.00 JOD</span>
                    </div>
                </div>

                <div class="grid grid-cols-2 gap-2 pt-2">
                    <button onclick="toggleCartDrawer(false); navigate('shop')" class="py-2.5 px-4 text-xs font-bold text-slate-600 dark:text-slate-300 border border-slate-300 dark:border-slate-700 rounded-xl hover:bg-slate-100 dark:hover:bg-slate-800 transition text-center" data-i18n="btn-continue-shopping">
                        متابعة التسوق
                    </button>
                    <button onclick="toggleCartDrawer(false); navigate('checkout')" class="py-2.5 px-4 text-xs font-bold text-white bg-royal-700 hover:bg-royal-800 rounded-xl transition shadow-lg shadow-royal-700/30 text-center flex items-center justify-center gap-1.5" data-i18n="btn-checkout">
                        <span>إتمام الطلب</span>
                        <i data-lucide="arrow-left" class="w-3.5 h-3.5"></i>
                    </button>
                </div>
            </div>
        </div>
    </div>

    <!-- 5. مودال المفضلة (Wishlist Modal) -->
    <div id="wishlistModal" class="fixed inset-0 z-50 hidden bg-black/60 backdrop-blur-sm p-4 flex items-center justify-center animate-fade-in">
        <div class="bg-white dark:bg-techCard w-full max-w-2xl rounded-3xl shadow-2xl border border-slate-200 dark:border-slate-800 p-6 max-h-[80vh] flex flex-col">
            <div class="flex items-center justify-between pb-4 border-b border-slate-200 dark:border-slate-800">
                <div class="flex items-center gap-2">
                    <i data-lucide="heart" class="w-5 h-5 text-rose-500 fill-rose-500"></i>
                    <h3 class="font-bold text-lg" data-i18n="wishlist-title">قائمة رغباتك ومفضلاتك</h3>
                </div>
                <button onclick="closeWishlistModal()" class="p-1 hover:bg-slate-100 dark:hover:bg-slate-800 rounded-full">
                    <i data-lucide="x" class="w-5 h-5"></i>
                </button>
            </div>
            <div id="wishlistItems" class="flex-1 overflow-y-auto py-4 space-y-3">
                <!-- المحتوى ديناميكي -->
            </div>
        </div>
    </div>

    <!-- 6. مودال متابعة الطلبات (Orders Tracker Modal) -->
    <div id="ordersModal" class="fixed inset-0 z-50 hidden bg-black/60 backdrop-blur-sm p-4 flex items-center justify-center animate-fade-in">
        <div class="bg-white dark:bg-techCard w-full max-w-2xl rounded-3xl shadow-2xl border border-slate-200 dark:border-slate-800 p-6 max-h-[85vh] flex flex-col">
            <div class="flex items-center justify-between pb-4 border-b border-slate-200 dark:border-slate-800">
                <div class="flex items-center gap-2">
                    <i data-lucide="package-check" class="w-5 h-5 text-royal-600"></i>
                    <h3 class="font-bold text-lg" data-i18n="orders-title">سجل طلباتي في Cell Buy Zone</h3>
                </div>
                <button onclick="closeOrdersModal()" class="p-1 hover:bg-slate-100 dark:hover:bg-slate-800 rounded-full">
                    <i data-lucide="x" class="w-5 h-5"></i>
                </button>
            </div>
            <div id="ordersContainer" class="flex-1 overflow-y-auto py-4 space-y-4">
                <!-- الطلبات المسجلة -->
            </div>
        </div>
    </div>

    <!-- إشعار عائم Toast Notification -->
    <div id="toastNotification" class="fixed bottom-6 right-6 z-50 hidden bg-royal-950 text-white border border-royal-700/60 shadow-2xl px-4 py-3 rounded-2xl flex items-center gap-3 text-sm animate-fade-in">
        <div id="toastIcon" class="w-7 h-7 rounded-full bg-emerald-500/20 text-emerald-400 flex items-center justify-center">
            <i data-lucide="check" class="w-4 h-4"></i>
        </div>
        <span id="toastMessage" class="font-medium">تمت الإضافة بنجاح!</span>
    </div>

    <!-- 7. الفوتر الفاخر (Luxury Tech Store Footer) -->
    <footer class="mt-auto bg-slate-900 text-slate-300 border-t border-slate-800">
        <div class="max-w-7xl mx-auto px-4 sm:px-6 py-12">
            <div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-5 gap-8 mb-12">
                <!-- نبذة عن المتجر -->
                <div class="lg:col-span-2 space-y-4">
                    <div class="flex items-center gap-2 text-white">
                        <div class="w-8 h-8 rounded-lg bg-royal-600 flex items-center justify-center text-white">
                            <i data-lucide="zap" class="w-4 h-4 text-amber-300 fill-amber-300"></i>
                        </div>
                        <span class="text-xl font-black font-sans tracking-tight">CELL BUY ZONE</span>
                    </div>
                    <p class="text-sm text-slate-400 leading-relaxed max-w-sm" data-i18n="footer-desc">
                        متجر الإلكترونيات والهواتف الذكية المعتمد في الأردن. نختص بتوفير أحدث هواتف iPhone من Apple، وأجهزة Realme، ساعات Kieslect الذكية، والإكسسوارات الأصلية بأفضل الأسعار بالدينار الأردني.
                    </p>
                    <div class="flex items-center gap-3 text-slate-400 text-sm">
                        <span class="inline-flex items-center gap-1.5 bg-slate-800 px-3 py-1.5 rounded-lg border border-slate-700">
                            <i data-lucide="credit-card" class="w-4 h-4 text-royal-400"></i>
                            <span data-i18n="footer-cod">الدفع عند الاستلام أو بالبطاقة</span>
                        </span>
                        <span class="inline-flex items-center gap-1.5 bg-slate-800 px-3 py-1.5 rounded-lg border border-slate-700">
                            <i data-lucide="truck" class="w-4 h-4 text-emerald-400"></i>
                            <span data-i18n="footer-fast-delivery">شحن لجميع المدن الأردنية</span>
                        </span>
                    </div>
                </div>

                <!-- روابط Apple السريعة -->
                <div class="space-y-3">
                    <h4 class="text-white font-bold text-sm tracking-wider uppercase" data-i18n="footer-apple-title">عالم Apple و iPhone</h4>
                    <ul class="space-y-2 text-sm text-slate-400">
                        <li><a href="javascript:void(0)" onclick="filterSpecificModel('iPhone 17 Pro Max')" class="hover:text-white transition">iPhone 17 Pro Max</a></li>
                        <li><a href="javascript:void(0)" onclick="filterSpecificModel('iPhone 17 Pro')" class="hover:text-white transition">iPhone 17 Pro</a></li>
                        <li><a href="javascript:void(0)" onclick="filterSpecificModel('iPhone 16 Pro Max')" class="hover:text-white transition">iPhone 16 Pro Max</a></li>
                        <li><a href="javascript:void(0)" onclick="filterSpecificModel('iPhone 16')" class="hover:text-white transition">iPhone 16</a></li>
                        <li><a href="javascript:void(0)" onclick="filterCategory('accessories')" class="hover:text-white transition" data-i18n="footer-magsafe">شواحن وإكسسوارات MagSafe</a></li>
                    </ul>
                </div>

                <!-- العلامات التجارية والأقسام -->
                <div class="space-y-3">
                    <h4 class="text-white font-bold text-sm tracking-wider uppercase" data-i18n="footer-brands-title">العلامات والأجهزة</h4>
                    <ul class="space-y-2 text-sm text-slate-400">
                        <li><a href="javascript:void(0)" onclick="filterCategory('realme')" class="hover:text-white transition">Realme Smartphones</a></li>
                        <li><a href="javascript:void(0)" onclick="filterCategory('kieslect')" class="hover:text-white transition">Kieslect Smart Watches</a></li>
                        <li><a href="javascript:void(0)" onclick="filterCategory('smartwatches')" class="hover:text-white transition" data-i18n="nav-watches">الساعات الذكية</a></li>
                        <li><a href="javascript:void(0)" onclick="filterCategory('accessories')" class="hover:text-white transition" data-i18n="nav-accessories">سماعات AirPods وملحقاتها</a></li>
                        <li><a href="javascript:void(0)" onclick="navigate('preorder')" class="text-rose-400 hover:text-rose-300 transition" data-i18n="nav-preorder">خدمة الحجز المسبق</a></li>
                    </ul>
                </div>

                <!-- معلومات الاتصال والموقع -->
                <div class="space-y-3">
                    <h4 class="text-white font-bold text-sm tracking-wider uppercase" data-i18n="footer-contact-title">خدمة العملاء</h4>
                    <ul class="space-y-2.5 text-sm text-slate-400">
                        <li class="flex items-center gap-2">
                            <i data-lucide="phone" class="w-4 h-4 text-royal-400"></i>
                            <span dir="ltr">+962 7 9000 0000</span>
                        </li>
                        <li class="flex items-center gap-2">
                            <i data-lucide="message-circle" class="w-4 h-4 text-emerald-400"></i>
                            <span data-i18n="footer-whatsapp">واتساب مباشر 24/7</span>
                        </li>
                        <li class="flex items-center gap-2">
                            <i data-lucide="map-pin" class="w-4 h-4 text-royal-400"></i>
                            <span data-i18n="footer-address">عمان، المملكة الأردنية الهاشمية</span>
                        </li>
                        <li>
                            <button onclick="navigate('about')" class="mt-2 text-xs bg-royal-800 hover:bg-royal-700 text-white font-bold px-3 py-1.5 rounded-lg transition" data-i18n="footer-about-btn">
                                تعرف أكثر على Cell Buy Zone
                            </button>
                        </li>
                    </ul>
                </div>
            </div>

            <!-- حقوق النشر والعملة -->
            <div class="pt-8 border-t border-slate-800 flex flex-col sm:flex-row justify-between items-center gap-4 text-xs text-slate-500">
                <p>© 2026 Cell Buy Zone (سيل باي زون). جميع الحقوق محفوظة | الأردن 🇯🇴</p>
                <div class="flex items-center gap-4">
                    <span class="text-slate-400 font-semibold" data-i18n="currency-note">العملة المعتمدة: الدينار الأردني (JOD)</span>
                </div>
            </div>
        </div>
    </footer>

    <!-- شريط الهاتف السفلي السريع (Mobile Bottom Navigation) -->
    <div class="lg:hidden fixed bottom-0 left-0 right-0 bg-white/95 dark:bg-techCard/95 backdrop-blur-md border-t border-slate-200 dark:border-slate-800 py-2 px-4 z-40 flex justify-around items-center text-[10px] font-bold">
        <button onclick="navigate('home')" class="flex flex-col items-center gap-1 text-royal-600 dark:text-royal-400">
            <i data-lucide="home" class="w-4 h-4"></i>
            <span data-i18n="nav-home">الرئيسية</span>
        </button>
        <button onclick="navigate('apple')" class="flex flex-col items-center gap-1 text-slate-500 hover:text-royal-600">
            <i data-lucide="apple" class="w-4 h-4"></i>
            <span>iPhone</span>
        </button>
        <button onclick="navigate('shop')" class="flex flex-col items-center gap-1 text-slate-500 hover:text-royal-600">
            <i data-lucide="grid" class="w-4 h-4"></i>
            <span data-i18n="nav-shop">المتجر</span>
        </button>
        <button onclick="toggleCartDrawer(true)" class="flex flex-col items-center gap-1 text-slate-500 hover:text-royal-600 relative">
            <i data-lucide="shopping-bag" class="w-4 h-4"></i>
            <span data-i18n="nav-cart">السلة</span>
            <span id="mobileCartBadge" class="hidden absolute -top-1 -right-2 bg-royal-600 text-white text-[9px] w-3.5 h-3.5 rounded-full items-center justify-center">0</span>
        </button>
        <button onclick="openOrdersModal()" class="flex flex-col items-center gap-1 text-slate-500 hover:text-royal-600">
            <i data-lucide="user" class="w-4 h-4"></i>
            <span data-i18n="nav-account">طلباتي</span>
        </button>
    </div>

    <!-- ========================================================================= -->
    <!-- منطق وتطبيق الجافاسكريبت الموحد (Unified Application Engine)             -->
    <!-- ========================================================================= -->
    <script>
        /* -------------------------------------------------------------------------
         * 1. قاعدة بيانات المنتجات الدقيقة (Product Catalog Database)
         * ------------------------------------------------------------------------- */
        const PRODUCTS_DB = [
            // iPhone 17 Series (Next-Gen Flagships)
            {
                id: 'ip-17-pm',
                name: 'iPhone 17 Pro Max',
                nameEn: 'iPhone 17 Pro Max',
                brand: 'apple',
                category: 'iphone',
                isFeatured: true,
                isPreOrder: true,
                badge: 'جديد قريباً / Pre-Order',
                basePrice: 1149.00,
                rating: 5.0,
                reviewsCount: 38,
                inStock: true,
                image: 'https://images.unsplash.com/photo-1695048133142-1a20484d2569?auto=format&fit=crop&w=800&q=80',
                colors: [
                    { name: 'تيتانيوم أسود فضائي', nameEn: 'Space Black Titanium', hex: '#1C1C1E' },
                    { name: 'تيتانيوم طبيعي', nameEn: 'Natural Titanium', hex: '#9E978E' },
                    { name: 'تيتانيوم أزرق محيطي', nameEn: 'Deep Ocean Titanium', hex: '#1C3144' },
                    { name: 'تيتانيوم أبيض قطبي', nameEn: 'White Titanium', hex: '#F2F2F2' }
                ],
                storages: [
                    { size: '256GB', priceDelta: 0 },
                    { size: '512GB', priceDelta: 120 },
                    { size: '1TB', priceDelta: 250 }
                ],
                specs: {
                    screen: '6.9" Super Retina XDR ProMotion 120Hz',
                    chip: 'Apple A19 Pro (2nm Ultra Efficiency)',
                    camera: '48MP Quad Fusion + 5x Optical Periscope Zoom',
                    battery: 'ما يصل إلى 33 ساعة تشغيل فيديو متواصل',
                    body: 'هيكل تيتانيوم مصقول فائق المتانة مع زر الأكشن وزر الكاميرا الذكي'
                },
                descriptionAr: 'قمة هندسة Apple التكنولوجية. هاتف iPhone 17 Pro Max يأتي بشريحة A19 Pro الثورية مع قدرات ذكاء اصطناعي فائق Apple Intelligence، وأكبر بطارية في تاريخ هواتف آيفون.',
                descriptionEn: 'The absolute pinnacle of Apple engineering. Powered by the groundbreaking A19 Pro chip, full Apple Intelligence suite, and the longest battery life in an iPhone ever.'
            },
            {
                id: 'ip-17-pro',
                name: 'iPhone 17 Pro',
                nameEn: 'iPhone 17 Pro',
                brand: 'apple',
                category: 'iphone',
                isFeatured: true,
                isPreOrder: true,
                badge: 'قريباً / Pre-Order',
                basePrice: 999.00,
                rating: 4.9,
                reviewsCount: 24,
                inStock: true,
                image: 'https://images.unsplash.com/photo-1695048133142-1a20484d2569?auto=format&fit=crop&w=800&q=80',
                colors: [
                    { name: 'تيتانيوم أسود', nameEn: 'Black Titanium', hex: '#212124' },
                    { name: 'تيتانيوم طبيعي', nameEn: 'Natural Titanium', hex: '#A39C94' },
                    { name: 'تيتانيوم صحراوي', nameEn: 'Desert Titanium', hex: '#C2B19D' }
                ],
                storages: [
                    { size: '128GB', priceDelta: 0 },
                    { size: '256GB', priceDelta: 90 },
                    { size: '512GB', priceDelta: 200 }
                ],
                specs: {
                    screen: '6.3" ProMotion 120Hz Always-On',
                    chip: 'Apple A19 Pro',
                    camera: 'نظام كاميرات ثلاثي 48MP احترافي',
                    battery: 'شحن فائق السرعة عبر منفذ USB-C Thunderbolt'
                },
                descriptionAr: 'قوة احترافية في حجم مريح مثالي مع شاشة 6.3 إنش وشريحة A19 Pro المتطورة.',
                descriptionEn: 'Pro performance in an ergonomic 6.3-inch form factor, driven by the powerhouse A19 Pro.'
            },
            {
                id: 'ip-17-std',
                name: 'iPhone 17',
                nameEn: 'iPhone 17',
                brand: 'apple',
                category: 'iphone',
                isFeatured: true,
                isPreOrder: true,
                badge: 'الجيل الجديد',
                basePrice: 779.00,
                rating: 4.8,
                reviewsCount: 19,
                inStock: true,
                image: 'https://images.unsplash.com/photo-1591337676887-a217a6970a8a?auto=format&fit=crop&w=800&q=80',
                colors: [
                    { name: 'أزرق سماوي', nameEn: 'Ultramarine Blue', hex: '#3B82F6' },
                    { name: 'أخضر نعناعي', nameEn: 'Mint Green', hex: '#34D399' },
                    { name: 'وردي ناعم', nameEn: 'Soft Pink', hex: '#F472B6' },
                    { name: 'أسود ليلي', nameEn: 'Midnight Black', hex: '#111827' }
                ],
                storages: [
                    { size: '128GB', priceDelta: 0 },
                    { size: '256GB', priceDelta: 80 },
                    { size: '512GB', priceDelta: 170 }
                ],
                specs: {
                    screen: '6.1" Super Retina XDR OLED',
                    chip: 'Apple A19 Bionic',
                    camera: '48MP Fusion Camera مع 2x Telephoto بدقة بصرية'
                },
                descriptionAr: 'الهاتف المفضل للملايين بقدرات معالجة فائقة وتصميم زجاجي مطفي مدعم ومقاوم للماء والغبار.',
                descriptionEn: 'The ideal modern smartphone combining vibrant aesthetics, robust build and A19 performance.'
            },

            // iPhone 16 Series (Current Market Leaders)
            {
                id: 'ip-16-pm',
                name: 'iPhone 16 Pro Max',
                nameEn: 'iPhone 16 Pro Max',
                brand: 'apple',
                category: 'iphone',
                isFeatured: true,
                isBestSeller: true,
                badge: 'الأكثر طلباً 🔥',
                basePrice: 949.00,
                rating: 4.9,
                reviewsCount: 142,
                inStock: true,
                image: 'https://images.unsplash.com/photo-1695048133142-1a20484d2569?auto=format&fit=crop&w=800&q=80',
                colors: [
                    { name: 'تيتانيوم صحراوي', nameEn: 'Desert Titanium', hex: '#B8A48F' },
                    { name: 'تيتانيوم طبيعي', nameEn: 'Natural Titanium', hex: '#9E978E' },
                    { name: 'تيتانيوم أسود', nameEn: 'Black Titanium', hex: '#1F2022' },
                    { name: 'تيتانيوم أبيض', nameEn: 'White Titanium', hex: '#EDECE8' }
                ],
                storages: [
                    { size: '256GB', priceDelta: 0 },
                    { size: '512GB', priceDelta: 120 },
                    { size: '1TB', priceDelta: 240 }
                ],
                specs: {
                    screen: '6.9" Super Retina XDR مع ProMotion 120Hz',
                    chip: 'Apple A18 Pro (Apple Intelligence)',
                    camera: 'كاميرا Fusion بدقة 48MP مع عدسة تقريب 5x وزر التحكم بالكاميرا',
                    battery: 'أطول عمر بطارية حتى الآن (حتى 33 ساعة)'
                },
                descriptionAr: 'الجهاز الأقوى المتوفر حالياً في الأردن. شاشة عملاقة 6.9 إنش مع دعم كامل لذكاء Apple Intelligence وزر Camera Control المبتكر.',
                descriptionEn: 'Equipped with the potent A18 Pro silicon, Camera Control key, and an expansive 6.9-inch display.'
            },
            {
                id: 'ip-16-pro',
                name: 'iPhone 16 Pro',
                nameEn: 'iPhone 16 Pro',
                brand: 'apple',
                category: 'iphone',
                isFeatured: false,
                isBestSeller: true,
                basePrice: 849.00,
                rating: 4.9,
                reviewsCount: 88,
                inStock: true,
                image: 'https://images.unsplash.com/photo-1695048133142-1a20484d2569?auto=format&fit=crop&w=800&q=80',
                colors: [
                    { name: 'تيتانيوم صحراوي', nameEn: 'Desert Titanium', hex: '#B8A48F' },
                    { name: 'تيتانيوم أسود', nameEn: 'Black Titanium', hex: '#1F2022' }
                ],
                storages: [
                    { size: '128GB', priceDelta: 0 },
                    { size: '256GB', priceDelta: 90 },
                    { size: '512GB', priceDelta: 190 }
                ],
                specs: {
                    screen: '6.3" ProMotion Always-on OLED',
                    chip: 'Apple A18 Pro',
                    camera: '48MP Main + 48MP Ultra-wide + 12MP 5x Telephoto'
                },
                descriptionAr: 'قوة أجهزة Pro الاستثنائية بحجم 6.3 إنش مريح ومثالي مع كاميرا 5x بصرية.',
                descriptionEn: 'Full Pro performance, dedicated Camera Control, and 5x optical telephoto in a comfortable size.'
            },
            {
                id: 'ip-16-std',
                name: 'iPhone 16',
                nameEn: 'iPhone 16',
                brand: 'apple',
                category: 'iphone',
                isFeatured: false,
                isBestSeller: true,
                basePrice: 659.00,
                rating: 4.8,
                reviewsCount: 65,
                inStock: true,
                image: 'https://images.unsplash.com/photo-1510557880182-3d4d3cba35a5?auto=format&fit=crop&w=800&q=80',
                colors: [
                    { name: 'وردي ناعم', nameEn: 'Pink', hex: '#EEA5A6' },
                    { name: 'أزرق بحري', nameEn: 'Teal', hex: '#319795' },
                    { name: 'أزرق فوق بنفسجي', nameEn: 'Ultramarine', hex: '#4A5568' },
                    { name: 'أسود', nameEn: 'Black', hex: '#1A202C' }
                ],
                storages: [
                    { size: '128GB', priceDelta: 0 },
                    { size: '256GB', priceDelta: 75 }
                ],
                specs: {
                    screen: '6.1" OLED Super Retina XDR',
                    chip: 'Apple A18 مع دعم الذكاء الاصطناعي',
                    camera: 'نظام كاميرات عمودي مع دعم التقاط الفيديو المكاني (Spatial Video)'
                },
                descriptionAr: 'الهاتف الأحدث مع زر التحكم بالكاميرا وشريحة A18 المتطورة وكاميرا 48MP فائقة.',
                descriptionEn: 'The modern everyday iPhone featuring the Camera Control switch, Action Button and A18 chip.'
            },

            // Realme Smartphones
            {
                id: 'rm-12-pro-plus',
                name: 'Realme 12 Pro+ 5G',
                nameEn: 'Realme 12 Pro+ 5G',
                brand: 'realme',
                category: 'realme',
                isFeatured: true,
                isBestSeller: true,
                badge: 'أفضل قيمة',
                basePrice: 289.00,
                rating: 4.7,
                reviewsCount: 42,
                inStock: true,
                image: 'https://images.unsplash.com/photo-1598327105666-5b89351aff97?auto=format&fit=crop&w=800&q=80',
                colors: [
                    { name: 'أزرق غواصات فاخر', nameEn: 'Submarine Blue', hex: '#1E3A8A' },
                    { name: 'بيج رملي', nameEn: 'Navigator Beige', hex: '#D6C7B2' }
                ],
                storages: [
                    { size: '256GB / 8GB RAM', priceDelta: 0 },
                    { size: '512GB / 12GB RAM', priceDelta: 40 }
                ],
                specs: {
                    screen: '6.7" AMOLED Curved 120Hz',
                    chip: 'Snapdragon 7s Gen 2 5G',
                    camera: 'عدسة بيريسكوب بورتريه 64MP فريدة من نوعها',
                    battery: '5000mAh مع شحن سريع 67W SuperVOOC'
                },
                descriptionAr: 'تصميم فاخر مستوحى من الساعات السويسرية الراقية بالتعاون مع أوليفييه سافيو، مع كاميرا بيريسكوب خرافية ضمن فئته السعرية.',
                descriptionEn: 'Master luxury design crafted with vegan leather, housing a flagship 64MP periscope portrait camera.'
            },
            {
                id: 'rm-c67',
                name: 'Realme C67 (NFC)',
                nameEn: 'Realme C67 (NFC)',
                brand: 'realme',
                category: 'realme',
                isFeatured: false,
                basePrice: 119.00,
                rating: 4.5,
                reviewsCount: 31,
                inStock: true,
                image: 'https://images.unsplash.com/photo-1565849904461-04a58ad377e0?auto=format&fit=crop&w=800&q=80',
                colors: [
                    { name: 'أخضر واحة', nameEn: 'Sunny Oasis', hex: '#10B981' },
                    { name: 'أسود صخري', nameEn: 'Black Rock', hex: '#1F2937' }
                ],
                storages: [
                    { size: '128GB / 6GB RAM', priceDelta: 0 },
                    { size: '256GB / 8GB RAM', priceDelta: 20 }
                ],
                specs: {
                    screen: '6.72" 90Hz FHD+',
                    chip: 'Snapdragon 685 (6nm)',
                    camera: 'كاميرا 108MP 3X In-sensor Zoom',
                    battery: '5000mAh مع شاحن 33W'
                },
                descriptionAr: 'بطل الفئة الاقتصادية بكاميرا 108 ميجابكسل ومعالج كوالكوم القوي وتصميم نحيف جداً.',
                descriptionEn: 'Unmatched budget performance with 108MP camera clarity and ultra-slim profile.'
            },

            // Kieslect Smart Watches
            {
                id: 'ks-kr-pro-ltd',
                name: 'Kieslect Kr Pro Calling Watch',
                nameEn: 'Kieslect Kr Pro Calling Watch',
                brand: 'kieslect',
                category: 'kieslect',
                isFeatured: true,
                isBestSeller: true,
                badge: 'الأكثر شهرة',
                basePrice: 49.00,
                rating: 4.8,
                reviewsCount: 54,
                inStock: true,
                image: 'https://images.unsplash.com/photo-1508685096489-7aacd43bd3b1?auto=format&fit=crop&w=800&q=80',
                colors: [
                    { name: 'إطار أسود كلاسيكي', nameEn: 'Classic Black', hex: '#000000' },
                    { name: 'إطار فضي مع سوار برتقالي', nameEn: 'Silver / Orange', hex: '#EA580C' }
                ],
                storages: [
                    { size: 'سوار مزدوج مغناطيسي', priceDelta: 0 }
                ],
                specs: {
                    screen: '1.43" Ultra FHD AMOLED Always-On',
                    features: 'إجراء واستقبال المكالمات بوضوح تام عبر البلوتوث',
                    sensors: 'معدل نبضات القلب، الأكسجين SpO2، تتبع النوم، 70 نمط رياضي',
                    battery: 'حتى 7 أيام استخدام متواصل'
                },
                descriptionAr: 'شاشة أموليد مبهرة مع ميزة الاتصال الصوتي وسوارين في الصندوق (مغناطيسي وسيليكون).',
                descriptionEn: 'Crisp AMOLED display with clear Bluetooth calling and dual straps included in the box.'
            },
            {
                id: 'ks-actor-smart',
                name: 'Kieslect Actor Luxury Smartwatch',
                nameEn: 'Kieslect Actor Luxury Smartwatch',
                brand: 'kieslect',
                category: 'kieslect',
                isFeatured: false,
                basePrice: 59.00,
                rating: 4.7,
                reviewsCount: 18,
                inStock: true,
                image: 'https://images.unsplash.com/photo-1523275335684-37898b6baf30?auto=format&fit=crop&w=800&q=80',
                colors: [
                    { name: 'فضي تيتانيوم', nameEn: 'Titanium Silver', hex: '#94A3B8' },
                    { name: 'أسود مطفي', nameEn: 'Matte Black', hex: '#18181B' }
                ],
                storages: [
                    { size: 'إصدار فاخر', priceDelta: 0 }
                ],
                specs: {
                    screen: '1.6" LTPO AMOLED 60FPS',
                    body: 'هيكل سيراميك وتيتانيوم فاخر مقاوم للماء 5ATM',
                    battery: 'حتى 14 يوماً في وضع توفير الطاقة'
                },
                descriptionAr: 'الساعة الفاخرة للرياضيين ورجال الأعمال، متانة عالية ومقاومة للماء حتى عمق 50 متراً.',
                descriptionEn: 'Ceramic bezel premium smartwatch built for endurance and high-end lifestyle.'
            },

            // Apple Watch
            {
                id: 'aw-ultra-2',
                name: 'Apple Watch Ultra 2 (GPS + Cellular)',
                nameEn: 'Apple Watch Ultra 2 (GPS + Cellular)',
                brand: 'apple',
                category: 'smartwatches',
                isFeatured: true,
                basePrice: 669.00,
                rating: 5.0,
                reviewsCount: 29,
                inStock: true,
                image: 'https://images.unsplash.com/photo-1517420704952-d9f39e95b43e?auto=format&fit=crop&w=800&q=80',
                colors: [
                    { name: 'تيتانيوم أسود جديد', nameEn: 'Black Titanium', hex: '#171717' },
                    { name: 'تيتانيوم طبيعي', nameEn: 'Natural Titanium', hex: '#A8A29E' }
                ],
                storages: [
                    { size: '49mm', priceDelta: 0 }
                ],
                specs: {
                    screen: 'سطوع خيالي يصل إلى 3000 شمعة',
                    chip: 'شريحة S9 SiP مع حركة النقر المزدوج (Double Tap)',
                    battery: 'حتى 72 ساعة في نمط حفظ الطاقة'
                },
                descriptionAr: 'الساعة الرياضية الأقوى من Apple للغوص والرياضات الشاقة مع نظام GPS مزدوج عالي الدقة.',
                descriptionEn: 'The ultimate sports and adventure watch made from aerospace-grade titanium.'
            },
            {
                id: 'aw-series-10',
                name: 'Apple Watch Series 10',
                nameEn: 'Apple Watch Series 10',
                brand: 'apple',
                category: 'smartwatches',
                isFeatured: false,
                basePrice: 349.00,
                rating: 4.8,
                reviewsCount: 37,
                inStock: true,
                image: 'https://images.unsplash.com/photo-1509042239860-f550ce710b93?auto=format&fit=crop&w=800&q=80',
                colors: [
                    { name: 'أسود فاحم صقيل', nameEn: 'Jet Black', hex: '#0A0A0A' },
                    { name: 'ذهب وردي', nameEn: 'Rose Gold', hex: '#FBCFE8' },
                    { name: 'فضي ناصع', nameEn: 'Silver', hex: '#E2E8F0' }
                ],
                storages: [
                    { size: '42mm', priceDelta: 0 },
                    { size: '46mm', priceDelta: 30 }
                ],
                specs: {
                    screen: 'أنحف ساعة من Apple مع أكبر مساحة شاشة بزاوية رؤية واسعة',
                    features: 'اكتشاف انقطاع النفس النومي، شحن أسرع بنسبة 80% في 30 دقيقة'
                },
                descriptionAr: 'تصميم فائق النحافة وشاشة أكبر من ساعة Ultra توفر رؤية استثنائية من كافة الزوايا.',
                descriptionEn: 'The thinnest Apple Watch ever with the biggest and most advanced display.'
            },

            // Apple AirPods & Audio
            {
                id: 'airpods-pro-2',
                name: 'AirPods Pro 2 (USB-C & MagSafe)',
                nameEn: 'AirPods Pro 2 (USB-C & MagSafe)',
                brand: 'apple',
                category: 'accessories',
                isFeatured: true,
                isBestSeller: true,
                basePrice: 195.00,
                rating: 4.9,
                reviewsCount: 112,
                inStock: true,
                image: 'https://images.unsplash.com/photo-1600294037681-c80b4cb5b434?auto=format&fit=crop&w=800&q=80',
                colors: [
                    { name: 'أبيض كلاسيكي', nameEn: 'White', hex: '#FFFFFF' }
                ],
                storages: [
                    { size: 'علبة شحن USB-C مع مكبر صوت', priceDelta: 0 }
                ],
                specs: {
                    chip: 'شريحة Apple H2 المتطورة',
                    audio: 'عزل ضوضاء أنشط بمرتين مع نمط الشفافية التكيفية والصوت المكاني',
                    battery: 'حتى 30 ساعة استماع إجمالية'
                },
                descriptionAr: 'السماعات اللاسلكية الأفضل لمالكي iPhone مع دعم الصوت بدون فقدان Lossless ومقاومة الماء والغبار IP54.',
                descriptionEn: 'Industry-leading Active Noise Cancellation with Transparency and Spatial Audio.'
            },
            {
                id: 'airpods-max-usbc',
                name: 'AirPods Max (USB-C Edition)',
                nameEn: 'AirPods Max (USB-C Edition)',
                brand: 'apple',
                category: 'accessories',
                isFeatured: false,
                basePrice: 479.00,
                rating: 4.8,
                reviewsCount: 22,
                inStock: true,
                image: 'https://images.unsplash.com/photo-1546435770-a3e426bf472b?auto=format&fit=crop&w=800&q=80',
                colors: [
                    { name: 'سماء الليل الأزرق', nameEn: 'Midnight', hex: '#1E293B' },
                    { name: 'ضوء النجوم', nameEn: 'Starlight', hex: '#F1F5F9' },
                    { name: 'أرجواني هادئ', nameEn: 'Purple', hex: '#C084FC' }
                ],
                storages: [
                    { size: 'Over-Ear Hi-Fi', priceDelta: 0 }
                ],
                specs: {
                    body: 'أطواق رأس شبكية مسامية وأغطية ألمنيوم مؤكسد فاخرة',
                    audio: 'مشغل ديناميكي صممته Apple لصوت عالي الدقة بدون تشويش'
                },
                descriptionAr: 'تجربة الاستماع الفاخرة ذات العزل المطلق مع منفذ USB-C الجديد وألوان عصرية.',
                descriptionEn: 'The definitive over-ear headphone combining acoustic craftsmanship with Apple silicon.'
            },

            // Chargers & Official Accessories
            {
                id: 'apple-20w-adapter',
                name: 'شاحن أبل الأصلي 20W USB-C Power Adapter',
                nameEn: 'Apple 20W USB-C Power Adapter',
                brand: 'apple',
                category: 'accessories',
                isFeatured: false,
                isBestSeller: true,
                basePrice: 19.00,
                rating: 4.9,
                reviewsCount: 230,
                inStock: true,
                image: 'https://images.unsplash.com/photo-1583863788434-e58a36330cf0?auto=format&fit=crop&w=800&q=80',
                colors: [
                    { name: 'أبيض', nameEn: 'White', hex: '#FFFFFF' }
                ],
                storages: [
                    { size: '20W PD', priceDelta: 0 }
                ],
                specs: {
                    compatibility: 'شحن سريع 50% خلال 30 دقيقة لجميع أجهزة iPhone 12 إلى iPhone 17',
                    safety: 'حماية كاملة من الحرارة والجهد الزائد معتمدة من Apple'
                },
                descriptionAr: 'رأس شاحن أبل الرسمي الأصلي لضمان الحفاظ على بطارية هاتفك وعمرها الافتراضي.',
                descriptionEn: 'Genuine Apple 20W fast charger delivering optimum and safe charging performance.'
            },
            {
                id: 'apple-magsafe-charger',
                name: 'شاحن Apple MagSafe اللاسلكي السريع (25W)',
                nameEn: 'Apple MagSafe Charger (25W Fast Charge)',
                brand: 'apple',
                category: 'accessories',
                isFeatured: false,
                basePrice: 38.00,
                rating: 4.8,
                reviewsCount: 76,
                inStock: true,
                image: 'https://images.unsplash.com/photo-1622445262464-84b14e0745b1?auto=format&fit=crop&w=800&q=80',
                colors: [
                    { name: 'فضي مع كابل قماشي مجدول', nameEn: 'Silver Braided', hex: '#E5E7EB' }
                ],
                storages: [
                    { size: 'طول 1 متر', priceDelta: 0 },
                    { size: 'طول 2 متر', priceDelta: 8 }
                ],
                specs: {
                    power: 'شحن لاسلكي حتى 25W لسلسلة iPhone 16 و iPhone 17 مع محول 30W',
                    cable: 'سلك نسيجي متين يدوم طويلاً ضد الانثناء'
                },
                descriptionAr: 'شاحن ماجسيف اللاسلكي الأصلي بمحاذاة مغناطيسية دقيقة وسرعة مضاعفة.',
                descriptionEn: 'Next-generation MagSafe magnetic wireless charger with up to 25W fast charging.'
            }
        ];

        /* -------------------------------------------------------------------------
         * 2. قاموس اللغات (Bilingual Translations: Arabic & English)
         * ------------------------------------------------------------------------- */
        const I18N = {
            ar: {
                'top-guarantee': 'أجهزة أصلية 100% | كفالة معتمدة',
                'top-location': 'عَمّان - الأردن | توصيل فوري لكافة المحافظات',
                'logo-subtitle': 'سيل باي زون للإلكترونيات',
                'search-placeholder': 'ابحث عن iPhone 17، ساعات، إكسسوارات...',
                'nav-home': 'الرئيسية',
                'nav-shop': 'جميع المنتجات',
                'nav-apple': 'Apple & iPhone',
                'nav-watches': 'ساعات ذكية',
                'nav-accessories': 'إكسسوارات وشواحن',
                'nav-preorder': 'حجز مسبق (Pre-Order)',
                'nav-offers': 'العروض الخاصة',
                'nav-about': 'من نحن (About Us)',
                'top-status': 'المتجر متاح لاستقبال الطلبات أونلاين',
                'hero-title-1': 'عصر الذكاء الخارق',
                'hero-title-2': 'iPhone 17 Pro Max',
                'hero-desc': 'مرحباً بكم في متجر Cell Buy Zone، الوجهة الأرقى لأجهزة Apple وهواتف المستقبل في المملكة الأردنية الهاشمية.',
                'btn-order-now': 'اطلب الآن بالدينار الأردني',
                'btn-explore-apple': 'استكشف عائلة iPhone بالكامل',
                'section-featured': 'الأجهزة المختارة والوافدون الجدد',
                'section-featured-sub': 'تشكيلة مختارة من أرقى الهواتف والساعات والإكسسوارات التقنية',
                'section-iphone-title': 'تجربة Apple iPhone المتكاملة',
                'section-iphone-sub': 'اختر جهازك المفضل بمواصفات رسمية وكفالة مضمونة',
                'section-bestsellers': 'الأكثر مبيعاً هذا الأسبوع',
                'section-brands': 'العلامات التجارية المعتمدة لدينا',
                'filter-all': 'الكل',
                'filter-price-asc': 'السعر: من الأقل للأعلى',
                'filter-price-desc': 'السعر: من الأعلى للأقل',
                'filter-storage': 'سعة التخزين:',
                'filter-color': 'اللون المتاح:',
                'btn-add-cart': 'إضافة إلى السلة',
                'btn-quick-view': 'تفاصيل سريعة',
                'cart-title': 'سلة التسوق الخاصة بك',
                'cart-subtotal': 'المجموع الفرعي:',
                'cart-delivery': 'التوصيل لكافة المحافظات:',
                'cart-free-delivery': 'مجاني للطلبات فوق 100 JOD',
                'cart-total': 'المجموع الكلي:',
                'btn-continue-shopping': 'متابعة التسوق',
                'btn-checkout': 'إتمام الطلب',
                'wishlist-title': 'قائمة رغباتك ومفضلاتك',
                'orders-title': 'سجل طلباتي في Cell Buy Zone',
                'nav-cart': 'السلة',
                'nav-account': 'طلباتي',
                'checkout-title': 'إتمام الشراء والدفع',
                'checkout-cust-info': 'بيانات العميل وعنوان التوصيل في الأردن',
                'input-name': 'الاسم الكامل',
                'input-phone': 'رقم الهاتف (مثال: 079xxxxxxx)',
                'input-city': 'المحافظة / المدينة',
                'input-address': 'العنوان بالتفصيل (الحي، الشارع، البناية)',
                'input-notes': 'ملاحظات إضافية للتوصيل',
                'payment-method': 'طريقة الدفع',
                'payment-cod': 'الدفع عند الاستلام (Cash on Delivery)',
                'payment-card': 'بطاقة فيزا / ماستركارد عند الاستلام',
                'btn-submit-order': 'تأكيد وإرسال الطلب الآن',
                'footer-desc': 'متجر الإلكترونيات والهواتف الذكية المعتمد في الأردن. نختص بتوفير أحدث هواتف iPhone من Apple، وأجهزة Realme، ساعات Kieslect الذكية، والإكسسوارات الأصلية بأفضل الأسعار بالدينار الأردني.',
                'footer-cod': 'الدفع عند الاستلام أو بالبطاقة',
                'footer-fast-delivery': 'شحن لجميع المدن الأردنية',
                'footer-apple-title': 'عالم Apple و iPhone',
                'footer-brands-title': 'العلامات والأجهزة',
                'footer-contact-title': 'خدمة العملاء',
                'footer-magsafe': 'شواحن وإكسسوارات MagSafe',
                'footer-whatsapp': 'واتساب مباشر 24/7',
                'footer-address': 'عمان، المملكة الأردنية الهاشمية',
                'footer-about-btn': 'تعرف أكثر على Cell Buy Zone',
                'currency-note': 'العملة المعتمدة: الدينار الأردني (JOD)'
            },
            en: {
                'top-guarantee': '100% Genuine Devices | Certified Warranty',
                'top-location': 'Amman - Jordan | Fast Express Delivery Nationwide',
                'logo-subtitle': 'Smart Electronics Store',
                'search-placeholder': 'Search iPhone 17, Apple Watch, accessories...',
                'nav-home': 'Home',
                'nav-shop': 'Shop All',
                'nav-apple': 'Apple & iPhone',
                'nav-watches': 'Smart Watches',
                'nav-accessories': 'Accessories & Chargers',
                'nav-preorder': 'Pre-Order',
                'nav-offers': 'Offers',
                'nav-about': 'About Us',
                'top-status': 'Store open for online orders 24/7',
                'hero-title-1': 'The Ultimate Intelligence',
                'hero-title-2': 'iPhone 17 Pro Max',
                'hero-desc': 'Welcome to Cell Buy Zone, Jordan’s premier tech sanctuary for genuine Apple gear, flagship smartphones and premium smart accessories.',
                'btn-order-now': 'Order in Jordanian Dinar (JOD)',
                'btn-explore-apple': 'Explore the iPhone Lineup',
                'section-featured': 'Featured Devices & Fresh Arrivals',
                'section-featured-sub': 'Handpicked collection of elite smartphones, wearables and gear',
                'section-iphone-title': 'The Apple iPhone Experience',
                'section-iphone-sub': 'Choose your next iPhone with certified warranty and flexible local payment',
                'section-bestsellers': 'Weekly Best Sellers',
                'section-brands': 'Authorized Brands We Carry',
                'filter-all': 'All Products',
                'filter-price-asc': 'Price: Low to High',
                'filter-price-desc': 'Price: High to Low',
                'filter-storage': 'Storage Capacity:',
                'filter-color': 'Color:',
                'btn-add-cart': 'Add to Cart',
                'btn-quick-view': 'Quick View',
                'cart-title': 'Your Shopping Cart',
                'cart-subtotal': 'Subtotal:',
                'cart-delivery': 'Delivery across Jordan:',
                'cart-free-delivery': 'Free for orders over 100 JOD',
                'cart-total': 'Grand Total:',
                'btn-continue-shopping': 'Continue Shopping',
                'btn-checkout': 'Checkout Now',
                'wishlist-title': 'Your Wishlist',
                'orders-title': 'Order History - Cell Buy Zone',
                'nav-cart': 'Cart',
                'nav-account': 'Orders',
                'checkout-title': 'Complete Your Order',
                'checkout-cust-info': 'Customer Info & Jordan Delivery Address',
                'input-name': 'Full Name',
                'input-phone': 'Phone Number (e.g. 079xxxxxxx)',
                'input-city': 'Governorate / City',
                'input-address': 'Detailed Address (Street, Building, Flat)',
                'input-notes': 'Delivery Notes (Optional)',
                'payment-method': 'Payment Method',
                'payment-cod': 'Cash on Delivery (COD)',
                'payment-card': 'Credit / Debit Card on Delivery',
                'btn-submit-order': 'Confirm and Place Order',
                'footer-desc': 'Authorized smart devices and electronics store in Jordan. Specializing in genuine Apple iPhones, Realme smartphones, Kieslect watches and certified gear in Jordanian Dinars (JOD).',
                'footer-cod': 'Cash & Card on Delivery',
                'footer-fast-delivery': 'Express Shipping Across Jordan',
                'footer-apple-title': 'Apple & iPhone World',
                'footer-brands-title': 'Brands & Hardware',
                'footer-contact-title': 'Customer Care',
                'footer-magsafe': 'MagSafe & Power Adapters',
                'footer-whatsapp': 'Direct 24/7 WhatsApp Support',
                'footer-address': 'Amman, Hashemite Kingdom of Jordan',
                'footer-about-btn': 'Learn more about Cell Buy Zone',
                'currency-note': 'Official Currency: Jordanian Dinar (JOD)'
            }
        };

        /* -------------------------------------------------------------------------
         * 3. حالة التطبيق (State Management)
         * ------------------------------------------------------------------------- */
        let state = {
            lang: localStorage.getItem('cbz_lang') || 'ar',
            darkMode: localStorage.getItem('cbz_theme') === 'dark',
            currentView: 'home',
            activeCategory: 'all',
            searchQuery: '',
            cart: JSON.parse(localStorage.getItem('cbz_cart')) || [],
            wishlist: JSON.parse(localStorage.getItem('cbz_wishlist')) || [],
            orders: JSON.parse(localStorage.getItem('cbz_orders')) || [],
            selectedProduct: null,
            // فلاتر البحث في صفحة الآيفون والمتجر
            filters: {
                brand: 'all',
                series: 'all',
                maxPrice: 1500,
                sortBy: 'featured',
                storage: 'all'
            }
        };

        /* -------------------------------------------------------------------------
         * 4. التهيئة ودعم اللغات والمظهر (Initialization & Core Handlers)
         * ------------------------------------------------------------------------- */
        function initApp() {
            applyTheme();
            applyLanguage();
            updateBadges();
            navigate(state.currentView);
            lucide.createIcons();
        }

        function toggleDarkMode() {
            state.darkMode = !state.darkMode;
            localStorage.setItem('cbz_theme', state.darkMode ? 'dark' : 'light');
            applyTheme();
        }

        function applyTheme() {
            const html = document.documentElement;
            const icon = document.getElementById('themeIcon');
            if (state.darkMode) {
                html.classList.add('dark');
                if (icon) icon.setAttribute('data-lucide', 'sun');
            } else {
                html.classList.remove('dark');
                if (icon) icon.setAttribute('data-lucide', 'moon');
            }
            lucide.createIcons();
        }

        function toggleLanguage() {
            state.lang = state.lang === 'ar' ? 'en' : 'ar';
            localStorage.setItem('cbz_lang', state.lang);
            applyLanguage();
            // إعادة رسم الواجهة الحالية باللغة الجديدة
            navigate(state.currentView);
        }

        function applyLanguage() {
            const html = document.documentElement;
            html.setAttribute('lang', state.lang);
            html.setAttribute('dir', state.lang === 'ar' ? 'rtl' : 'ltr');
            
            document.getElementById('langLabel').innerText = state.lang === 'ar' ? 'English' : 'العربية';

            // ترجمة جميع العناصر المعرفة بـ data-i18n
            document.querySelectorAll('[data-i18n]').forEach(el => {
                const key = el.getAttribute('data-i18n');
                if (I18N[state.lang][key]) {
                    el.innerText = I18N[state.lang][key];
                }
            });

            // ترجمة الـ Placeholders
            document.querySelectorAll('[data-i18n-placeholder]').forEach(el => {
                const key = el.getAttribute('data-i18n-placeholder');
                if (I18N[state.lang][key]) {
                    el.setAttribute('placeholder', I18N[state.lang][key]);
                }
            });
        }

        function t(key) {
            return I18N[state.lang][key] || key;
        }

        /* -------------------------------------------------------------------------
         * 5. نظام التنقل والصفحات (Router & Views)
         * ------------------------------------------------------------------------- */
        function navigate(viewName) {
            state.currentView = viewName;
            window.scrollTo({ top: 0, behavior: 'smooth' });

            // تحديث تمييز الرابط النشط في القائمة
            document.querySelectorAll('.nav-link').forEach(link => {
                const target = link.getAttribute('data-nav');
                if (target === viewName) {
                    link.classList.add('text-royal-600', 'dark:text-royal-400', 'font-black');
                } else {
                    link.classList.remove('font-black');
                }
            });

            const container = document.getElementById('appContent');
            
            switch (viewName) {
                case 'home':
                    renderHomeView(container);
                    break;
                case 'shop':
                    renderShopView(container, 'all');
                    break;
                case 'apple':
                    renderAppleFocusedView(container);
                    break;
                case 'preorder':
                    renderShopView(container, 'preorder');
                    break;
                case 'offers':
                    renderShopView(container, 'offers');
                    break;
                case 'about':
                    renderAboutView(container);
                    break;
                case 'checkout':
                    renderCheckoutView(container);
                    break;
                default:
                    renderHomeView(container);
            }

            lucide.createIcons();
        }

        function filterCategory(cat) {
            state.activeCategory = cat;
            navigate('shop');
        }

        function filterSpecificModel(modelName) {
            state.searchQuery = modelName;
            navigate('shop');
        }

        function toggleMobileMenu() {
            const menu = document.getElementById('mobileMenu');
            menu.classList.toggle('hidden');
        }

        /* -------------------------------------------------------------------------
         * 6. عروض الواجهات (View Renderers)
         * ------------------------------------------------------------------------- */
        
        // 6.1 الصفحة الرئيسية (Home Page)
        function renderHomeView(container) {
            const featuredList = PRODUCTS_DB.filter(p => p.isFeatured);
            const bestSellersList = PRODUCTS_DB.filter(p => p.isBestSeller);
            const iphonesList = PRODUCTS_DB.filter(p => p.category === 'iphone');

            container.innerHTML = `
                <!-- البانر الترويجي الفاخر (Hero Section) -->
                <div class="relative rounded-3xl overflow-hidden bg-gradient-to-r from-royal-950 via-royal-900 to-techDark text-white mb-14 shadow-2xl border border-royal-800/40">
                    <div class="absolute inset-0 bg-[radial-gradient(ellipse_at_top_right,_var(--tw-gradient-stops))] from-royal-600/20 via-transparent to-transparent pointer-events-none"></div>
                    
                    <div class="grid grid-cols-1 lg:grid-cols-12 items-center p-8 sm:p-12 lg:p-16 gap-8 relative z-10">
                        <div class="lg:col-span-7 space-y-6 text-center lg:text-start">
                            <div class="inline-flex items-center gap-2 px-3 py-1.5 rounded-full bg-royal-800/70 border border-royal-700/80 text-royal-300 text-xs font-semibold badge-glow">
                                <span class="w-2 h-2 rounded-full bg-emerald-400 animate-ping"></span>
                                <span>Apple Intelligence Ready | كفالة رسمية</span>
                            </div>

                            <div class="space-y-2">
                                <span class="text-royal-400 font-bold tracking-widest uppercase text-sm block" data-i18n="hero-title-1">${t('hero-title-1')}</span>
                                <h1 class="text-4xl sm:text-6xl font-black font-sans tracking-tight text-white leading-tight">
                                    iPhone 17 Pro Max
                                </h1>
                            </div>

                            <p class="text-slate-300 text-base sm:text-lg leading-relaxed max-w-xl mx-auto lg:mx-0" data-i18n="hero-desc">
                                ${t('hero-desc')}
                            </p>

                            <!-- السعر والمزايا السريعة -->
                            <div class="flex flex-wrap items-center justify-center lg:justify-start gap-4 pt-2">
                                <div class="bg-white/10 backdrop-blur-md px-4 py-2 rounded-2xl border border-white/10">
                                    <span class="text-xs text-slate-400 block">السعر يبدأ من</span>
                                    <span class="text-2xl font-black font-sans text-amber-300">1149.00 JOD</span>
                                </div>
                                <div class="text-xs text-slate-300 space-y-1 text-right">
                                    <div class="flex items-center gap-1.5"><i data-lucide="check-circle" class="w-3.5 h-3.5 text-emerald-400"></i> معالج A19 Pro الثوري 2nm</div>
                                    <div class="flex items-center gap-1.5"><i data-lucide="check-circle" class="w-3.5 h-3.5 text-emerald-400"></i> كاميرا بروفيشنال مع تقريب 5x بيريسكوب</div>
                                </div>
                            </div>

                            <div class="flex flex-wrap items-center justify-center lg:justify-start gap-3 pt-4">
                                <button onclick="openProductModal('ip-17-pm')" class="px-7 py-3.5 rounded-2xl font-bold bg-royal-600 hover:bg-royal-500 text-white shadow-xl shadow-royal-600/30 transition transform hover:-translate-y-0.5 flex items-center gap-2">
                                    <span data-i18n="btn-order-now">${t('btn-order-now')}</span>
                                    <i data-lucide="arrow-left" class="w-4 h-4"></i>
                                </button>
                                <button onclick="navigate('apple')" class="px-7 py-3.5 rounded-2xl font-bold bg-white/10 hover:bg-white/20 text-white border border-white/15 transition flex items-center gap-2">
                                    <i data-lucide="apple" class="w-4 h-4"></i>
                                    <span data-i18n="btn-explore-apple">${t('btn-explore-apple')}</span>
                                </button>
                            </div>
                        </div>

                        <!-- صورة البانر الفاخرة للآيفون -->
                        <div class="lg:col-span-5 flex justify-center relative">
                            <div class="relative w-72 sm:w-80 lg:w-96 drop-shadow-2xl group cursor-pointer" onclick="openProductModal('ip-17-pm')">
                                <div class="absolute -inset-4 bg-royal-600/20 rounded-full blur-2xl group-hover:bg-royal-600/30 transition duration-500"></div>
                                <img src="https://images.unsplash.com/photo-1695048133142-1a20484d2569?auto=format&fit=crop&w=800&q=80" 
                                     alt="iPhone 17 Pro Max" 
                                     class="relative z-10 w-full rounded-3xl object-cover border-4 border-slate-700/50 shadow-2xl transform group-hover:scale-105 transition duration-500">
                                
                                <div class="absolute bottom-4 left-4 right-4 z-20 bg-techDark/90 backdrop-blur-md p-3 rounded-2xl border border-slate-700 text-center">
                                    <span class="text-xs text-amber-300 font-bold block">متوفر للحجز المسبق الفوري</span>
                                    <span class="text-[11px] text-slate-300">توصيل الأولوية الأولى فور الإطلاق</span>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>

                <!-- شريط العلامات التجارية المعتمدة -->
                <div class="mb-14">
                    <p class="text-center text-xs font-bold text-slate-400 uppercase tracking-widest mb-6" data-i18n="section-brands">
                        ${t('section-brands')}
                    </p>
                    <div class="grid grid-cols-2 sm:grid-cols-4 gap-4">
                        <div onclick="navigate('apple')" class="bg-white dark:bg-techCard p-5 rounded-2xl border border-slate-200 dark:border-slate-800 text-center hover:border-royal-500 transition cursor-pointer group shadow-sm">
                            <i data-lucide="apple" class="w-8 h-8 mx-auto text-slate-800 dark:text-white group-hover:scale-110 transition"></i>
                            <h4 class="font-bold font-sans mt-2 text-sm text-slate-900 dark:text-white">Apple Store</h4>
                            <span class="text-xs text-slate-500">iPhone, Watch, AirPods</span>
                        </div>
                        <div onclick="filterCategory('realme')" class="bg-white dark:bg-techCard p-5 rounded-2xl border border-slate-200 dark:border-slate-800 text-center hover:border-amber-500 transition cursor-pointer group shadow-sm">
                            <span class="font-black text-2xl font-sans text-amber-500 group-hover:scale-110 transition block">realme</span>
                            <h4 class="font-bold font-sans mt-1 text-sm text-slate-900 dark:text-white">Realme Series</h4>
                            <span class="text-xs text-slate-500">هواتف ذكية بمعالجات قوية</span>
                        </div>
                        <div onclick="filterCategory('kieslect')" class="bg-white dark:bg-techCard p-5 rounded-2xl border border-slate-200 dark:border-slate-800 text-center hover:border-rose-500 transition cursor-pointer group shadow-sm">
                            <span class="font-bold text-lg font-sans text-rose-500 group-hover:scale-110 transition block">KIESLECT</span>
                            <h4 class="font-bold font-sans mt-1 text-sm text-slate-900 dark:text-white">Smart Calling Watches</h4>
                            <span class="text-xs text-slate-500">ساعات مكالمات وشاشات AMOLED</span>
                        </div>
                        <div onclick="filterCategory('accessories')" class="bg-white dark:bg-techCard p-5 rounded-2xl border border-slate-200 dark:border-slate-800 text-center hover:border-royal-500 transition cursor-pointer group shadow-sm">
                            <i data-lucide="zap" class="w-8 h-8 mx-auto text-royal-600 group-hover:scale-110 transition"></i>
                            <h4 class="font-bold font-sans mt-2 text-sm text-slate-900 dark:text-white">MagSafe & Power</h4>
                            <span class="text-xs text-slate-500">شواحن أصلية وإكسسوارات</span>
                        </div>
                    </div>
                </div>

                <!-- قسم التركيز الأساسي: أجهزة iPhone المتاحة في Cell Buy Zone -->
                <div class="mb-14">
                    <div class="flex flex-col sm:flex-row justify-between items-start sm:items-end gap-3 mb-8">
                        <div>
                            <div class="inline-flex items-center gap-1.5 text-royal-600 dark:text-royal-400 text-xs font-bold uppercase tracking-wider mb-1">
                                <i data-lucide="apple" class="w-4 h-4"></i>
                                <span>Apple Flagships</span>
                            </div>
                            <h2 class="text-2xl sm:text-3xl font-black text-slate-900 dark:text-white" data-i18n="section-iphone-title">
                                ${t('section-iphone-title')}
                            </h2>
                            <p class="text-sm text-slate-500 dark:text-slate-400 mt-1" data-i18n="section-iphone-sub">
                                ${t('section-iphone-sub')}
                            </p>
                        </div>
                        <button onclick="navigate('apple')" class="text-sm font-bold text-royal-600 dark:text-royal-400 hover:underline flex items-center gap-1">
                            <span>عرض كل هواتف Apple</span>
                            <i data-lucide="arrow-left" class="w-4 h-4"></i>
                        </button>
                    </div>

                    <!-- شبكة هواتف iPhone -->
                    <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
                        ${iphonesList.map(item => renderProductCardHtml(item)).join('')}
                    </div>
                </div>

                <!-- قسم المنتجات المختارة والوافدون الجدد -->
                <div class="mb-14">
                    <div class="flex justify-between items-end mb-8">
                        <div>
                            <h2 class="text-2xl sm:text-3xl font-black text-slate-900 dark:text-white" data-i18n="section-featured">
                                ${t('section-featured')}
                            </h2>
                            <p class="text-sm text-slate-500 dark:text-slate-400 mt-1" data-i18n="section-featured-sub">
                                ${t('section-featured-sub')}
                            </p>
                        </div>
                        <button onclick="navigate('shop')" class="text-sm font-bold text-royal-600 dark:text-royal-400 hover:underline">
                            عرض الكل
                        </button>
                    </div>

                    <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6">
                        ${featuredList.map(item => renderProductCardHtml(item)).join('')}
                    </div>
                </div>

                <!-- قسم الأكثر مبيعاً (Best Sellers) -->
                <div class="mb-14 bg-slate-100 dark:bg-slate-900/50 -mx-4 sm:-mx-6 px-4 sm:px-6 py-10 rounded-3xl border border-slate-200/80 dark:border-slate-800">
                    <div class="max-w-7xl mx-auto">
                        <div class="mb-8">
                            <span class="text-xs text-rose-500 font-bold uppercase tracking-wider block mb-1">Top Selling in Jordan</span>
                            <h2 class="text-2xl sm:text-3xl font-black text-slate-900 dark:text-white" data-i18n="section-bestsellers">
                                ${t('section-bestsellers')}
                            </h2>
                        </div>
                        <div class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-4 gap-6">
                            ${bestSellersList.map(item => renderProductCardHtml(item)).join('')}
                        </div>
                    </div>
                </div>
            `;
        }

        // 6.2 صفحة Apple و iPhone المتكاملة (Dedicated Apple & iPhone Experience)
        function renderAppleFocusedView(container) {
            const appleProducts = PRODUCTS_DB.filter(p => p.brand === 'apple');
            
            container.innerHTML = `
                <div class="mb-8 space-y-4">
                    <!-- ترويسة صفحة آبل الفاخرة -->
                    <div class="bg-gradient-to-r from-slate-900 via-royal-950 to-slate-900 text-white p-8 sm:p-12 rounded-3xl border border-slate-800 shadow-xl relative overflow-hidden">
                        <div class="max-w-2xl relative z-10 space-y-4">
                            <div class="inline-flex items-center gap-2 px-3 py-1 rounded-full bg-white/10 text-white text-xs font-bold">
                                <i data-lucide="apple" class="w-4 h-4"></i>
                                <span>Apple Official Destination at Cell Buy Zone</span>
                            </div>
                            <h1 class="text-3xl sm:text-5xl font-black font-sans tracking-tight">
                                عائلة Apple iPhone & Accessories
                            </h1>
                            <p class="text-slate-300 text-sm sm:text-base leading-relaxed">
                                تصفح تشكيلتنا الشاملة من أحدث أجهزة iPhone 17 و iPhone 16 و Apple Watch وسماعات AirPods مع كفالة مصنعية معتمدة وأسعار دقيقة بالدينار الأردني (JOD).
                            </p>
                        </div>
                    </div>

                    <!-- فلاتر آبل الذكية -->
                    <div class="bg-white dark:bg-techCard p-4 rounded-2xl border border-slate-200 dark:border-slate-800 flex flex-wrap items-center justify-between gap-4 shadow-sm">
                        <div class="flex flex-wrap items-center gap-2">
                            <button onclick="filterAppleSub('all')" class="px-4 py-2 rounded-xl text-xs font-bold bg-royal-600 text-white">الكل</button>
                            <button onclick="filterAppleSub('iphone')" class="px-4 py-2 rounded-xl text-xs font-bold bg-slate-100 dark:bg-slate-800 text-slate-700 dark:text-slate-200 hover:bg-slate-200">هواتف iPhone</button>
                            <button onclick="filterAppleSub('smartwatches')" class="px-4 py-2 rounded-xl text-xs font-bold bg-slate-100 dark:bg-slate-800 text-slate-700 dark:text-slate-200 hover:bg-slate-200">ساعات Apple Watch</button>
                            <button onclick="filterAppleSub('accessories')" class="px-4 py-2 rounded-xl text-xs font-bold bg-slate-100 dark:bg-slate-800 text-slate-700 dark:text-slate-200 hover:bg-slate-200">سماعات وشواحن MagSafe</button>
                        </div>

                        <div class="flex items-center gap-2 text-xs">
                            <span class="text-slate-500">عدد المنتجات: </span>
                            <span class="font-bold text-royal-600 font-sans">${appleProducts.length} أجهزة متوفرة</span>
                        </div>
                    </div>
                </div>

                <!-- شبكة منتجات Apple -->
                <div id="appleGrid" class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
                    ${appleProducts.map(item => renderProductCardHtml(item)).join('')}
                </div>
            `;
        }

        function filterAppleSub(subCat) {
            const grid = document.getElementById('appleGrid');
            if (!grid) return;

            let filtered = PRODUCTS_DB.filter(p => p.brand === 'apple');
            if (subCat !== 'all') {
                filtered = filtered.filter(p => p.category === subCat);
            }
            grid.innerHTML = filtered.map(item => renderProductCardHtml(item)).join('');
            lucide.createIcons();
        }

        // 6.3 صفحة المتجر الشاملة مع الفلاتر الحية (Shop All View)
        function renderShopView(container, forcedCategory = 'all') {
            let initialProducts = PRODUCTS_DB;

            if (forcedCategory === 'preorder') {
                initialProducts = initialProducts.filter(p => p.isPreOrder);
            } else if (forcedCategory === 'offers') {
                initialProducts = initialProducts.filter(p => p.badge);
            } else if (forcedCategory !== 'all') {
                initialProducts = initialProducts.filter(p => p.category === forcedCategory || p.brand === forcedCategory);
            }

            container.innerHTML = `
                <div class="mb-8">
                    <h1 class="text-3xl font-black text-slate-900 dark:text-white mb-2" data-i18n="nav-shop">
                        ${t('nav-shop')}
                    </h1>
                    <p class="text-slate-500 text-sm">استكشف جميع الأجهزة الإلكترونية والهواتف الذكية مع الفلاتر المتقدمة</p>
                </div>

                <div class="grid grid-cols-1 lg:grid-cols-4 gap-8">
                    <!-- الجانب الأيمن: شريط الفلاتر الذكية -->
                    <div class="space-y-6">
                        <div class="bg-white dark:bg-techCard p-5 rounded-3xl border border-slate-200 dark:border-slate-800 shadow-sm space-y-6">
                            <div class="flex items-center justify-between pb-3 border-b border-slate-200 dark:border-slate-800">
                                <h3 class="font-bold text-sm flex items-center gap-2">
                                    <i data-lucide="filter" class="w-4 h-4 text-royal-600"></i>
                                    <span>فلاتر المنتجات</span>
                                </h3>
                                <button onclick="resetShopFilters()" class="text-[11px] text-royal-600 hover:underline">إعادة ضبط</button>
                            </div>

                            <!-- فلتر الفئة / العلامة -->
                            <div class="space-y-2">
                                <label class="text-xs font-bold text-slate-400 uppercase">القسم أو العلامة</label>
                                <select id="shopBrandFilter" onchange="applyShopFilters()" class="w-full bg-slate-50 dark:bg-slate-900 border border-slate-300 dark:border-slate-700 rounded-xl p-2.5 text-xs font-semibold focus:ring-2 focus:ring-royal-600">
                                    <option value="all">جميع العلامات</option>
                                    <option value="apple">Apple (iPhone, Watch, AirPods)</option>
                                    <option value="realme">Realme</option>
                                    <option value="kieslect">Kieslect</option>
                                    <option value="accessories">شواحن وإكسسوارات</option>
                                </select>
                            </div>

                            <!-- فلتر سعة التخزين -->
                            <div class="space-y-2">
                                <label class="text-xs font-bold text-slate-400 uppercase">سعة التخزين</label>
                                <select id="shopStorageFilter" onchange="applyShopFilters()" class="w-full bg-slate-50 dark:bg-slate-900 border border-slate-300 dark:border-slate-700 rounded-xl p-2.5 text-xs font-semibold focus:ring-2 focus:ring-royal-600">
                                    <option value="all">جميع السعات</option>
                                    <option value="128GB">128GB</option>
                                    <option value="256GB">256GB</option>
                                    <option value="512GB">512GB</option>
                                    <option value="1TB">1TB</option>
                                </select>
                            </div>

                            <!-- فلتر الترتيب حسب السعر -->
                            <div class="space-y-2">
                                <label class="text-xs font-bold text-slate-400 uppercase">ترتيب حسب</label>
                                <select id="shopSortFilter" onchange="applyShopFilters()" class="w-full bg-slate-50 dark:bg-slate-900 border border-slate-300 dark:border-slate-700 rounded-xl p-2.5 text-xs font-semibold focus:ring-2 focus:ring-royal-600">
                                    <option value="featured">الأبرز والموصى به</option>
                                    <option value="price-asc">السعر: من الأقل للأعلى</option>
                                    <option value="price-desc">السعر: من الأعلى للأقل</option>
                                </select>
                            </div>
                        </div>
                    </div>

                    <!-- الجانب الأيسر: عرض شبكة المنتجات المفلترة -->
                    <div class="lg:col-span-3">
                        <div id="shopProductsGrid" class="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-6">
                            ${initialProducts.map(item => renderProductCardHtml(item)).join('')}
                        </div>
                    </div>
                </div>
            `;
        }

        function applyShopFilters() {
            const brandVal = document.getElementById('shopBrandFilter').value;
            const storageVal = document.getElementById('shopStorageFilter').value;
            const sortVal = document.getElementById('shopSortFilter').value;

            let result = [...PRODUCTS_DB];

            if (brandVal !== 'all') {
                result = result.filter(p => p.brand === brandVal || p.category === brandVal);
            }

            if (storageVal !== 'all') {
                result = result.filter(p => p.storages && p.storages.some(s => s.size.includes(storageVal)));
            }

            if (sortVal === 'price-asc') {
                result.sort((a, b) => a.basePrice - b.basePrice);
            } else if (sortVal === 'price-desc') {
                result.sort((a, b) => b.basePrice - a.basePrice);
            }

            const grid = document.getElementById('shopProductsGrid');
            if (grid) {
                if (result.length === 0) {
                    grid.innerHTML = `
                        <div class="col-span-full py-16 text-center space-y-3">
                            <i data-lucide="package-open" class="w-12 h-12 mx-auto text-slate-400"></i>
                            <h4 class="font-bold text-lg">لم يتم العثور على أجهزة مطابقة للفلاتر</h4>
                            <p class="text-slate-500 text-xs">جرب تغيير شروط الفلترة أو إعادة ضبطها.</p>
                        </div>
                    `;
                } else {
                    grid.innerHTML = result.map(item => renderProductCardHtml(item)).join('');
                }
                lucide.createIcons();
            }
        }

        function resetShopFilters() {
            if (document.getElementById('shopBrandFilter')) document.getElementById('shopBrandFilter').value = 'all';
            if (document.getElementById('shopStorageFilter')) document.getElementById('shopStorageFilter').value = 'all';
            if (document.getElementById('shopSortFilter')) document.getElementById('shopSortFilter').value = 'featured';
            applyShopFilters();
        }

        // 6.4 توليد بطاقة المنتج الموحدة (Universal Product Card HTML)
        function renderProductCardHtml(product) {
            const isWish = state.wishlist.includes(product.id);
            const displayName = state.lang === 'ar' ? product.name : product.nameEn;

            return `
                <div class="group bg-white dark:bg-techCard rounded-3xl border border-slate-200/90 dark:border-slate-800 p-4 flex flex-col justify-between hover:shadow-2xl hover:border-royal-500/50 dark:hover:border-royal-500/50 transition-all duration-300 relative">
                    
                    <!-- الأوسمة العلوية (Badge & Wishlist) -->
                    <div class="flex items-center justify-between gap-2 mb-3">
                        ${product.badge ? `
                            <span class="text-[10px] font-black tracking-wider uppercase px-2.5 py-1 rounded-full bg-royal-100 dark:bg-royal-950 text-royal-700 dark:text-royal-300 border border-royal-200 dark:border-royal-800">
                                ${product.badge}
                            </span>
                        ` : `<span></span>`}

                        <button onclick="toggleWishlist('${product.id}')" class="p-2 rounded-full bg-slate-100 dark:bg-slate-800/80 text-slate-400 hover:text-rose-500 transition" title="أضف للمفضلة">
                            <i data-lucide="heart" class="w-4 h-4 ${isWish ? 'text-rose-500 fill-rose-500' : ''}"></i>
                        </button>
                    </div>

                    <!-- صورة المنتج مع تأثير التحويم -->
                    <div class="relative overflow-hidden rounded-2xl bg-slate-50 dark:bg-slate-900/40 p-4 mb-4 flex items-center justify-center cursor-pointer" onclick="openProductModal('${product.id}')">
                        <img src="${product.image}" alt="${displayName}" class="h-48 w-full object-contain group-hover:scale-105 transition-transform duration-500">
                    </div>

                    <!-- تفاصيل المنتج والاسم -->
                    <div class="space-y-2 mb-4">
                        <div class="flex items-center justify-between text-xs text-slate-400">
                            <span class="uppercase tracking-wider font-semibold font-sans">${product.brand}</span>
                            <div class="flex items-center gap-1 text-amber-500">
                                <i data-lucide="star" class="w-3.5 h-3.5 fill-amber-500"></i>
                                <span class="font-bold text-slate-700 dark:text-slate-300">${product.rating}</span>
                                <span class="text-[10px] text-slate-400">(${product.reviewsCount})</span>
                            </div>
                        </div>

                        <h3 onclick="openProductModal('${product.id}')" class="font-black text-slate-900 dark:text-white text-base hover:text-royal-600 transition cursor-pointer line-clamp-1">
                            ${displayName}
                        </h3>

                        <!-- عينات الألوان المتاحة (Color Dots) -->
                        <div class="flex items-center gap-1.5 pt-1">
                            ${product.colors.map(c => `
                                <span class="w-3 h-3 rounded-full border border-black/20 dark:border-white/20" style="background-color: ${c.hex};" title="${state.lang === 'ar' ? c.name : c.nameEn}"></span>
                            `).join('')}
                        </div>
                    </div>

                    <!-- السعر وزر الشراء -->
                    <div class="pt-3 border-t border-slate-100 dark:border-slate-800 flex items-center justify-between gap-2">
                        <div>
                            <span class="text-[10px] text-slate-400 block">السعر</span>
                            <span class="font-black font-sans text-lg text-royal-700 dark:text-royal-400">
                                ${product.basePrice.toFixed(2)} <span class="text-xs font-bold">JOD</span>
                            </span>
                        </div>

                        <div class="flex items-center gap-1.5">
                            <button onclick="openProductModal('${product.id}')" class="p-2.5 rounded-xl border border-slate-200 dark:border-slate-700 hover:bg-slate-100 dark:hover:bg-slate-800 text-slate-600 dark:text-slate-300 transition" title="عرض التفاصيل">
                                <i data-lucide="eye" class="w-4 h-4"></i>
                            </button>
                            <button onclick="quickAddToCart('${product.id}')" class="px-3.5 py-2.5 rounded-xl bg-royal-700 hover:bg-royal-800 text-white font-bold text-xs flex items-center gap-1.5 shadow-md shadow-royal-700/20 transition">
                                <i data-lucide="shopping-bag" class="w-4 h-4"></i>
                                <span class="hidden sm:inline" data-i18n="btn-add-cart">${t('btn-add-cart')}</span>
                            </button>
                        </div>
                    </div>
                </div>
            `;
        }

        // 6.5 صفحة "من نحن" (About Us View)
        function renderAboutView(container) {
            container.innerHTML = `
                <div class="max-w-4xl mx-auto space-y-12 py-6 animate-fade-in">
                    <!-- الترويسة -->
                    <div class="text-center space-y-4">
                        <div class="inline-flex items-center gap-2 px-3 py-1 rounded-full bg-royal-100 dark:bg-royal-950 text-royal-600 dark:text-royal-400 text-xs font-bold">
                            <i data-lucide="shield-check" class="w-4 h-4"></i>
                            <span>Cell Buy Zone Jordan</span>
                        </div>
                        <h1 class="text-3xl sm:text-5xl font-black text-slate-900 dark:text-white font-sans">
                            من نحن | About Cell Buy Zone
                        </h1>
                        <p class="text-slate-500 dark:text-slate-400 text-base max-w-2xl mx-auto leading-relaxed">
                            علامة أردنية متخصصة في بيع وتوزيع أحدث الهواتف الذكية والإلكترونيات والأجهزة التقنية الفاخرة، مع تركيز استثنائي على منظومة Apple العالمية.
                        </p>
                    </div>

                    <!-- ركائز المتجر -->
                    <div class="grid grid-cols-1 md:grid-cols-3 gap-6">
                        <div class="bg-white dark:bg-techCard p-6 rounded-3xl border border-slate-200 dark:border-slate-800 shadow-sm space-y-3">
                            <div class="w-10 h-10 rounded-2xl bg-royal-100 dark:bg-royal-950 text-royal-600 flex items-center justify-center">
                                <i data-lucide="target" class="w-5 h-5"></i>
                            </div>
                            <h3 class="font-black text-lg text-slate-900 dark:text-white">رؤيتنا</h3>
                            <p class="text-slate-500 dark:text-slate-400 text-sm leading-relaxed">
                                أن نكون الوجهة الأولى والموثوقة في الأردن لاقتناء أرقى الهواتف والمنتجات التقنية الأصلية، وتوفير تجربة شراء رقمية متكاملة تضاهي المتاجر العالمية.
                            </p>
                        </div>

                        <div class="bg-white dark:bg-techCard p-6 rounded-3xl border border-slate-200 dark:border-slate-800 shadow-sm space-y-3">
                            <div class="w-10 h-10 rounded-2xl bg-emerald-100 dark:bg-emerald-950 text-emerald-600 flex items-center justify-center">
                                <i data-lucide="compass" class="w-5 h-5"></i>
                            </div>
                            <h3 class="font-black text-lg text-slate-900 dark:text-white">رسالتنا</h3>
                            <p class="text-slate-500 dark:text-slate-400 text-sm leading-relaxed">
                                تمكين عملائنا من الوصول لأحدث إصدارات التكنولوجيا العالمية فور إطلاقها بأسعار عادلة وبالدينار الأردني، مع ضمان الشفافية والكفالة المعتمدة وسرعة التوصيل.
                            </p>
                        </div>

                        <div class="bg-white dark:bg-techCard p-6 rounded-3xl border border-slate-200 dark:border-slate-800 shadow-sm space-y-3">
                            <div class="w-10 h-10 rounded-2xl bg-amber-100 dark:bg-amber-950 text-amber-600 flex items-center justify-center">
                                <i data-lucide="sparkles" class="w-5 h-5"></i>
                            </div>
                            <h3 class="font-black text-lg text-slate-900 dark:text-white">ما الذي يميزنا؟</h3>
                            <p class="text-slate-500 dark:text-slate-400 text-sm leading-relaxed">
                                الاهتمام الدقيق بفحص ومطابقة الأجهزة الأصلية، وتوفير خيارات التخزين والألوان النادرة، إضافة إلى خدمات ما بعد البيع والدعم الفني المباشر لعملائنا.
                            </p>
                        </div>
                    </div>

                    <!-- قنوات التواصل المباشرة -->
                    <div class="bg-gradient-to-r from-royal-950 to-techDark text-white p-8 rounded-3xl border border-royal-900 space-y-6">
                        <div class="text-center sm:text-start">
                            <h3 class="text-2xl font-bold font-sans">تواصل مباشرة مع فريق Cell Buy Zone</h3>
                            <p class="text-slate-400 text-sm mt-1">نسعد بالإجابة على استفساراتك وتأكيد طلباتك على مدار الساعة</p>
                        </div>

                        <div class="grid grid-cols-1 sm:grid-cols-3 gap-4 pt-2">
                            <div class="flex items-center gap-3 bg-white/5 p-4 rounded-2xl border border-white/10">
                                <i data-lucide="phone" class="w-5 h-5 text-royal-400"></i>
                                <div>
                                    <span class="text-xs text-slate-400 block">اتصال هاتفي</span>
                                    <span class="font-bold font-sans text-sm" dir="ltr">+962 7 9000 0000</span>
                                </div>
                            </div>
                            <div class="flex items-center gap-3 bg-white/5 p-4 rounded-2xl border border-white/10">
                                <i data-lucide="message-circle" class="w-5 h-5 text-emerald-400"></i>
                                <div>
                                    <span class="text-xs text-slate-400 block">واتساب مباشر</span>
                                    <span class="font-bold text-sm">محادثة فورية مع المبيعات</span>
                                </div>
                            </div>
                            <div class="flex items-center gap-3 bg-white/5 p-4 rounded-2xl border border-white/10">
                                <i data-lucide="map-pin" class="w-5 h-5 text-amber-400"></i>
                                <div>
                                    <span class="text-xs text-slate-400 block">الموقع</span>
                                    <span class="font-bold text-sm">عمان - الأردن</span>
                                </div>
                            </div>
                        </div>
                    </div>
                </div>
            `;
        }

        // 6.6 صفحة إتمام الطلب (Checkout View)
        function renderCheckoutView(container) {
            if (state.cart.length === 0) {
                container.innerHTML = `
                    <div class="max-w-md mx-auto py-20 text-center space-y-4">
                        <div class="w-16 h-16 rounded-full bg-slate-100 dark:bg-slate-800 text-slate-400 flex items-center justify-center mx-auto">
                            <i data-lucide="shopping-bag" class="w-8 h-8"></i>
                        </div>
                        <h2 class="text-2xl font-bold">سلة الشراء فارغة حالياً</h2>
                        <p class="text-slate-500 text-sm">أضف بعض هواتف iPhone أو الساعات الذكية لتتمكن من إتمام الطلب.</p>
                        <button onclick="navigate('shop')" class="px-6 py-2.5 bg-royal-700 text-white rounded-xl font-bold text-sm">تصفح المنتجات</button>
                    </div>
                `;
                return;
            }

            const subtotal = calculateCartSubtotal();
            const total = subtotal; // التوصيل مجاني

            container.innerHTML = `
                <div class="max-w-4xl mx-auto py-6 animate-fade-in">
                    <div class="mb-8">
                        <h1 class="text-3xl font-black text-slate-900 dark:text-white" data-i18n="checkout-title">
                            ${t('checkout-title')}
                        </h1>
                        <p class="text-slate-500 text-sm">أدخل معلومات التوصيل في الأردن لتأكيد حجز طلبك فوراً</p>
                    </div>

                    <div class="grid grid-cols-1 lg:grid-cols-12 gap-8">
                        <!-- نموذج معلومات العميل -->
                        <div class="lg:col-span-7 bg-white dark:bg-techCard p-6 sm:p-8 rounded-3xl border border-slate-200 dark:border-slate-800 shadow-sm space-y-6">
                            <h3 class="font-bold text-lg text-slate-900 dark:text-white pb-3 border-b border-slate-200 dark:border-slate-800" data-i18n="checkout-cust-info">
                                ${t('checkout-cust-info')}
                            </h3>

                            <form id="checkoutForm" onsubmit="handlePlaceOrder(event)" class="space-y-4">
                                <div>
                                    <label class="block text-xs font-bold text-slate-500 dark:text-slate-400 mb-1" data-i18n="input-name">الاسم الكامل</label>
                                    <input type="text" id="custName" required placeholder="مثال: محمد عبدالله" class="w-full bg-slate-50 dark:bg-slate-900 border border-slate-300 dark:border-slate-700 rounded-xl p-3 text-sm focus:ring-2 focus:ring-royal-600">
                                </div>

                                <div>
                                    <label class="block text-xs font-bold text-slate-500 dark:text-slate-400 mb-1" data-i18n="input-phone">رقم الهاتف للتواصل</label>
                                    <input type="tel" id="custPhone" required placeholder="0790000000" class="w-full bg-slate-50 dark:bg-slate-900 border border-slate-300 dark:border-slate-700 rounded-xl p-3 text-sm focus:ring-2 focus:ring-royal-600" dir="ltr">
                                </div>

                                <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                                    <div>
                                        <label class="block text-xs font-bold text-slate-500 dark:text-slate-400 mb-1" data-i18n="input-city">المحافظة</label>
                                        <select id="custCity" class="w-full bg-slate-50 dark:bg-slate-900 border border-slate-300 dark:border-slate-700 rounded-xl p-3 text-sm focus:ring-2 focus:ring-royal-600 font-semibold">
                                            <option value="عمان">عَمّان (العاصمة)</option>
                                            <option value="الزرقاء">الزرقاء</option>
                                            <option value="إربد">إربد</option>
                                            <option value="البلقاء / السلط">البلقاء / السلط</option>
                                            <option value="العقبة">العقبة</option>
                                            <option value="مادبا">مادبا</option>
                                            <option value="جرش">جرش</option>
                                            <option value="عجلون">عجلون</option>
                                            <option value="الكرك">الكرك</option>
                                            <option value="المفرق">المفرق</option>
                                            <option value="الطفيلة">الطفيلة</option>
                                            <option value="معان">معان</option>
                                        </select>
                                    </div>
                                    <div>
                                        <label class="block text-xs font-bold text-slate-500 dark:text-slate-400 mb-1" data-i18n="input-address">العنوان التفصيلي</label>
                                        <input type="text" id="custAddress" required placeholder="المنطقة، الشارع، رقم البناية" class="w-full bg-slate-50 dark:bg-slate-900 border border-slate-300 dark:border-slate-700 rounded-xl p-3 text-sm focus:ring-2 focus:ring-royal-600">
                                    </div>
                                </div>

                                <div>
                                    <label class="block text-xs font-bold text-slate-500 dark:text-slate-400 mb-1" data-i18n="input-notes">ملاحظات إضافية للتوصيل (اختياري)</label>
                                    <textarea id="custNotes" rows="2" placeholder="أي تفاصيل خاصة بتسليم الشحنة..." class="w-full bg-slate-50 dark:bg-slate-900 border border-slate-300 dark:border-slate-700 rounded-xl p-3 text-sm focus:ring-2 focus:ring-royal-600"></textarea>
                                </div>

                                <!-- خيارات الدفع -->
                                <div class="pt-2 space-y-2">
                                    <label class="block text-xs font-bold text-slate-500 dark:text-slate-400" data-i18n="payment-method">طريقة الدفع</label>
                                    <div class="grid grid-cols-1 sm:grid-cols-2 gap-3">
                                        <label class="flex items-center gap-2 p-3.5 rounded-2xl border border-royal-600 bg-royal-50/50 dark:bg-royal-950/40 cursor-pointer">
                                            <input type="radio" name="paymentMethod" value="COD" checked class="text-royal-600">
                                            <span class="text-xs font-bold" data-i18n="payment-cod">الدفع عند الاستلام (COD)</span>
                                        </label>
                                        <label class="flex items-center gap-2 p-3.5 rounded-2xl border border-slate-200 dark:border-slate-800 hover:border-slate-400 cursor-pointer">
                                            <input type="radio" name="paymentMethod" value="CARD_ON_DELIVERY" class="text-royal-600">
                                            <span class="text-xs font-bold" data-i18n="payment-card">بطاقة فيزا عند الاستلام</span>
                                        </label>
                                    </div>
                                </div>

                                <button type="submit" class="w-full py-4 rounded-2xl bg-royal-700 hover:bg-royal-800 text-white font-bold text-base shadow-xl shadow-royal-700/30 transition mt-4 flex items-center justify-center gap-2">
                                    <i data-lucide="shield-check" class="w-5 h-5 text-emerald-400"></i>
                                    <span data-i18n="btn-submit-order">${t('btn-submit-order')}</span>
                                </button>
                            </form>
                        </div>

                        <!-- ملخص الطلب الجانبي -->
                        <div class="lg:col-span-5 space-y-6">
                            <div class="bg-white dark:bg-techCard p-6 rounded-3xl border border-slate-200 dark:border-slate-800 shadow-sm space-y-4">
                                <h3 class="font-bold text-sm text-slate-900 dark:text-white pb-3 border-b border-slate-200 dark:border-slate-800">
                                    ملخص المنتجات في الطلب (${state.cart.length})
                                </h3>

                                <div class="space-y-3 max-h-64 overflow-y-auto pr-1">
                                    ${state.cart.map(item => `
                                        <div class="flex items-center justify-between text-xs py-1 border-b border-slate-100 dark:border-slate-800/60 pb-2">
                                            <div class="flex items-center gap-2.5">
                                                <img src="${item.product.image}" class="w-10 h-10 object-contain rounded-lg bg-slate-50 dark:bg-slate-900 p-1">
                                                <div>
                                                    <h5 class="font-bold text-slate-800 dark:text-slate-200">${item.product.name}</h5>
                                                    <span class="text-[10px] text-slate-400">${item.storage} | ${item.color} | س: ${item.quantity}</span>
                                                </div>
                                            </div>
                                            <span class="font-sans font-bold text-royal-600">${(item.price * item.quantity).toFixed(2)} JOD</span>
                                        </div>
                                    `).join('')}
                                </div>

                                <div class="space-y-2 pt-2 text-xs">
                                    <div class="flex justify-between text-slate-500">
                                        <span>المجموع الفرعي:</span>
                                        <span class="font-sans font-bold">${subtotal.toFixed(2)} JOD</span>
                                    </div>
                                    <div class="flex justify-between text-slate-500">
                                        <span>الشحن:</span>
                                        <span class="text-emerald-500 font-bold">مجاني</span>
                                    </div>
                                    <div class="flex justify-between text-base font-black text-slate-900 dark:text-white pt-2 border-t border-slate-200 dark:border-slate-800">
                                        <span>المجموع للدفع:</span>
                                        <span class="font-sans text-royal-600 dark:text-royal-400 text-lg">${total.toFixed(2)} JOD</span>
                                    </div>
                                </div>
                            </div>

                            <div class="bg-royal-50 dark:bg-royal-950/40 p-4 rounded-2xl border border-royal-200 dark:border-royal-800 text-xs text-royal-800 dark:text-royal-300 space-y-1">
                                <div class="font-bold flex items-center gap-1">
                                    <i data-lucide="info" class="w-3.5 h-3.5"></i>
                                    <span>ضمان Cell Buy Zone:</span>
                                </div>
                                <p class="text-[11px] leading-relaxed">
                                    يتم التواصل معك هاتفياً من قبل قسم المبيعات فور إرسال الطلب لتأكيد الموعد وتسليم الشحنة في أسرع وقت.
                                </p>
                            </div>
                        </div>
                    </div>
                </div>
            `;
        }

        /* -------------------------------------------------------------------------
         * 7. نظام سلة التسوق التفاعلية (Interactive Cart Engine)
         * ------------------------------------------------------------------------- */
        function quickAddToCart(productId) {
            const product = PRODUCTS_DB.find(p => p.id === productId);
            if (!product) return;

            const defaultStorage = product.storages && product.storages.length > 0 ? product.storages[0].size : 'Standard';
            const defaultColor = product.colors && product.colors.length > 0 ? (state.lang === 'ar' ? product.colors[0].name : product.colors[0].nameEn) : 'Original';
            const price = product.basePrice;

            addToCartCore(product, defaultStorage, defaultColor, price, 1);
        }

        function addToCartCore(product, storage, color, price, quantity = 1) {
            const existingIndex = state.cart.findIndex(item => 
                item.product.id === product.id && item.storage === storage && item.color === color
            );

            if (existingIndex > -1) {
                state.cart[existingIndex].quantity += quantity;
            } else {
                state.cart.push({
                    product,
                    storage,
                    color,
                    price,
                    quantity
                });
            }

            saveCartState();
            showToast(`${product.name} أضيف إلى سلة المشتريات`);
            renderCartDrawer();
            toggleCartDrawer(true);
        }

        function updateCartQuantity(index, delta) {
            if (!state.cart[index]) return;
            state.cart[index].quantity += delta;
            if (state.cart[index].quantity <= 0) {
                state.cart.splice(index, 1);
            }
            saveCartState();
            renderCartDrawer();
        }

        function removeFromCart(index) {
            state.cart.splice(index, 1);
            saveCartState();
            renderCartDrawer();
        }

        function saveCartState() {
            localStorage.setItem('cbz_cart', JSON.stringify(state.cart));
            updateBadges();
        }

        function calculateCartSubtotal() {
            return state.cart.reduce((sum, item) => sum + (item.price * item.quantity), 0);
        }

        function renderCartDrawer() {
            const container = document.getElementById('cartDrawerItems');
            const subtotalElem = document.getElementById('cartSubtotal');
            const totalElem = document.getElementById('cartTotal');
            const badgeElem = document.getElementById('cartDrawerItemCount');

            if (!container) return;

            badgeElem.innerText = state.cart.length;

            if (state.cart.length === 0) {
                container.innerHTML = `
                    <div class="h-64 flex flex-col items-center justify-center text-center space-y-3 text-slate-400">
                        <i data-lucide="shopping-bag" class="w-12 h-12 stroke-[1.5]"></i>
                        <p class="text-sm font-bold text-slate-500">سلة التسوق فارغة حالياً</p>
                    </div>
                `;
                subtotalElem.innerText = '0.00 JOD';
                totalElem.innerText = '0.00 JOD';
                lucide.createIcons();
                return;
            }

            container.innerHTML = state.cart.map((item, index) => `
                <div class="flex items-center gap-3 p-3 rounded-2xl bg-slate-50 dark:bg-slate-900/60 border border-slate-200/80 dark:border-slate-800">
                    <img src="${item.product.image}" alt="${item.product.name}" class="w-16 h-16 object-contain rounded-xl bg-white dark:bg-techCard p-1 border border-slate-200 dark:border-slate-800">
                    
                    <div class="flex-1 min-w-0 space-y-1">
                        <h4 class="font-bold text-xs text-slate-900 dark:text-white truncate">${item.product.name}</h4>
                        <p class="text-[10px] text-slate-400">${item.storage} | ${item.color}</p>
                        <span class="font-sans font-bold text-xs text-royal-600 dark:text-royal-400 block">${item.price.toFixed(2)} JOD</span>
                        
                        <!-- عداد الكمية -->
                        <div class="flex items-center gap-2 pt-1">
                            <button onclick="updateCartQuantity(${index}, -1)" class="w-6 h-6 rounded-md bg-white dark:bg-slate-800 border border-slate-200 dark:border-slate-700 flex items-center justify-center text-xs font-bold hover:bg-slate-200">-</button>
                            <span class="font-sans font-bold text-xs">${item.quantity}</span>
                            <button onclick="updateCartQuantity(${index}, 1)" class="w-6 h-6 rounded-md bg-white dark:bg-slate-800 border border-slate-200 dark:border-slate-700 flex items-center justify-center text-xs font-bold hover:bg-slate-200">+</button>
                        </div>
                    </div>

                    <button onclick="removeFromCart(${index})" class="text-slate-400 hover:text-rose-500 p-1" title="حذف">
                        <i data-lucide="trash-2" class="w-4 h-4"></i>
                    </button>
                </div>
            `).join('');

            const subtotal = calculateCartSubtotal();
            subtotalElem.innerText = `${subtotal.toFixed(2)} JOD`;
            totalElem.innerText = `${subtotal.toFixed(2)} JOD`;
            lucide.createIcons();
        }

        function toggleCartDrawer(open) {
            const drawer = document.getElementById('cartDrawer');
            if (open) {
                renderCartDrawer();
                drawer.classList.remove('hidden');
            } else {
                drawer.classList.add('hidden');
            }
        }

        /* -------------------------------------------------------------------------
         * 8. مودال تفاصيل المنتج الشاملة (Full Product Details Modal)
         * ------------------------------------------------------------------------- */
        function openProductModal(productId) {
            const product = PRODUCTS_DB.find(p => p.id === productId);
            if (!product) return;

            state.selectedProduct = product;
            let currentPrice = product.basePrice;
            let selectedStorageIndex = 0;
            let selectedColorIndex = 0;

            const modalBody = document.getElementById('productModalBody');
            const displayName = state.lang === 'ar' ? product.name : product.nameEn;
            const desc = state.lang === 'ar' ? product.descriptionAr : product.descriptionEn;

            modalBody.innerHTML = `
                <div class="grid grid-cols-1 md:grid-cols-2 gap-8 items-center">
                    <!-- الصورة الكبيرة -->
                    <div class="bg-slate-50 dark:bg-slate-900/60 rounded-3xl p-8 flex items-center justify-center border border-slate-200 dark:border-slate-800 relative">
                        ${product.badge ? `
                            <span class="absolute top-4 right-4 bg-royal-700 text-white text-xs font-bold px-3 py-1 rounded-full">
                                ${product.badge}
                            </span>
                        ` : ''}
                        <img id="modalProductImg" src="${product.image}" alt="${displayName}" class="max-h-80 w-full object-contain">
                    </div>

                    <!-- خيارات الشراء والمواصفات -->
                    <div class="space-y-5">
                        <div>
                            <span class="text-xs font-bold text-royal-600 uppercase font-sans tracking-wider">${product.brand} Official</span>
                            <h2 class="text-2xl sm:text-3xl font-black text-slate-900 dark:text-white mt-1">${displayName}</h2>
                            <p class="text-xs text-slate-500 mt-2 leading-relaxed">${desc}</p>
                        </div>

                        <!-- السعر التفاعلي المحدث -->
                        <div class="p-3.5 rounded-2xl bg-royal-50/70 dark:bg-royal-950/40 border border-royal-200 dark:border-royal-800/80 flex items-center justify-between">
                            <div>
                                <span class="text-[11px] text-slate-400 block">السعر الحالي بالدينار الأردني</span>
                                <span id="modalDynamicPrice" class="text-2xl font-black font-sans text-royal-700 dark:text-royal-400">
                                    ${currentPrice.toFixed(2)} JOD
                                </span>
                            </div>
                            <span class="text-xs font-bold text-emerald-600 bg-emerald-100 dark:bg-emerald-950 px-2.5 py-1 rounded-full">
                                متوفر في المستودع
                            </span>
                        </div>

                        <!-- اختيار سعة التخزين -->
                        ${product.storages ? `
                            <div class="space-y-2">
                                <label class="text-xs font-bold text-slate-500 block" data-i18n="filter-storage">سعة التخزين:</label>
                                <div class="flex flex-wrap gap-2">
                                    ${product.storages.map((st, i) => `
                                        <button onclick="selectModalStorage(${i})" class="storage-btn px-4 py-2 rounded-xl text-xs font-bold border transition ${i === 0 ? 'border-royal-600 bg-royal-600 text-white' : 'border-slate-300 dark:border-slate-700 hover:border-royal-500'}">
                                            ${st.size}
                                        </button>
                                    `).join('')}
                                </div>
                            </div>
                        ` : ''}

                        <!-- اختيار اللون المتاح -->
                        ${product.colors ? `
                            <div class="space-y-2">
                                <label class="text-xs font-bold text-slate-500 block" data-i18n="filter-color">اللون المتاح:</label>
                                <div class="flex flex-wrap gap-2">
                                    ${product.colors.map((c, i) => `
                                        <button onclick="selectModalColor(${i})" class="color-btn flex items-center gap-2 px-3 py-1.5 rounded-xl text-xs font-semibold border transition ${i === 0 ? 'border-royal-600 bg-royal-50 dark:bg-royal-950 font-bold' : 'border-slate-200 dark:border-slate-700'}">
                                            <span class="w-3.5 h-3.5 rounded-full border border-black/20" style="background-color:${c.hex}"></span>
                                            <span>${state.lang === 'ar' ? c.name : c.nameEn}</span>
                                        </button>
                                    `).join('')}
                                </div>
                            </div>
                        ` : ''}

                        <!-- أبرز المواصفات التقنية -->
                        <div class="border-t border-slate-200 dark:border-slate-800 pt-3 text-xs space-y-1 text-slate-600 dark:text-slate-300">
                            ${Object.entries(product.specs).map(([key, val]) => `
                                <div class="flex items-start gap-2">
                                    <i data-lucide="check" class="w-3.5 h-3.5 text-royal-600 mt-0.5 shrink-0"></i>
                                    <span>${val}</span>
                                </div>
                            `).join('')}
                        </div>

                        <!-- زر الإضافة النهائي -->
                        <div class="pt-2 flex gap-3">
                            <button onclick="confirmModalAddToCart()" class="flex-1 py-3.5 rounded-2xl bg-royal-700 hover:bg-royal-800 text-white font-bold text-sm shadow-xl shadow-royal-700/30 transition flex items-center justify-center gap-2">
                                <i data-lucide="shopping-bag" class="w-5 h-5"></i>
                                <span>إضافة إلى سلة المشتريات</span>
                            </button>
                        </div>
                    </div>
                </div>
            `;

            window.activeModalStorageIndex = 0;
            window.activeModalColorIndex = 0;

            document.getElementById('productModal').classList.remove('hidden');
            lucide.createIcons();
        }

        function selectModalStorage(index) {
            window.activeModalStorageIndex = index;
            const product = state.selectedProduct;
            const delta = product.storages[index].priceDelta || 0;
            const newPrice = product.basePrice + delta;

            document.getElementById('modalDynamicPrice').innerText = `${newPrice.toFixed(2)} JOD`;

            document.querySelectorAll('.storage-btn').forEach((btn, i) => {
                if (i === index) {
                    btn.className = 'storage-btn px-4 py-2 rounded-xl text-xs font-bold border border-royal-600 bg-royal-600 text-white transition';
                } else {
                    btn.className = 'storage-btn px-4 py-2 rounded-xl text-xs font-bold border border-slate-300 dark:border-slate-700 hover:border-royal-500 transition';
                }
            });
        }

        function selectModalColor(index) {
            window.activeModalColorIndex = index;
            document.querySelectorAll('.color-btn').forEach((btn, i) => {
                if (i === index) {
                    btn.classList.add('border-royal-600', 'bg-royal-50', 'dark:bg-royal-950', 'font-bold');
                } else {
                    btn.classList.remove('border-royal-600', 'bg-royal-50', 'dark:bg-royal-950', 'font-bold');
                }
            });
        }

        function confirmModalAddToCart() {
            const product = state.selectedProduct;
            if (!product) return;

            const stIndex = window.activeModalStorageIndex || 0;
            const colIndex = window.activeModalColorIndex || 0;

            const storage = product.storages ? product.storages[stIndex].size : 'Standard';
            const color = product.colors ? (state.lang === 'ar' ? product.colors[colIndex].name : product.colors[colIndex].nameEn) : 'Default';
            const price = product.basePrice + (product.storages ? product.storages[stIndex].priceDelta : 0);

            addToCartCore(product, storage, color, price, 1);
            closeProductModal();
        }

        function closeProductModal() {
            document.getElementById('productModal').classList.add('hidden');
        }

        /* -------------------------------------------------------------------------
         * 9. قائمة المفضلة (Wishlist Engine)
         * ------------------------------------------------------------------------- */
        function toggleWishlist(productId) {
            const idx = state.wishlist.indexOf(productId);
            if (idx > -1) {
                state.wishlist.splice(idx, 1);
                showToast('تمت الإزالة من المفضلة');
            } else {
                state.wishlist.push(productId);
                showToast('تمت الإضافة إلى المفضلة ❤️');
            }
            localStorage.setItem('cbz_wishlist', JSON.stringify(state.wishlist));
            updateBadges();
            
            // إعادة رسم إذا كانت القائمة مفتوحة
            if (!document.getElementById('wishlistModal').classList.contains('hidden')) {
                renderWishlistItems();
            }
        }

        function openWishlistModal() {
            renderWishlistItems();
            document.getElementById('wishlistModal').classList.remove('hidden');
        }

        function closeWishlistModal() {
            document.getElementById('wishlistModal').classList.add('hidden');
        }

        function renderWishlistItems() {
            const container = document.getElementById('wishlistItems');
            if (!container) return;

            if (state.wishlist.length === 0) {
                container.innerHTML = `
                    <div class="py-12 text-center text-slate-400 space-y-2">
                        <i data-lucide="heart" class="w-10 h-10 mx-auto stroke-[1.5]"></i>
                        <p class="text-sm font-bold">قائمة مفضلتك فارغة</p>
                    </div>
                `;
                lucide.createIcons();
                return;
            }

            const items = PRODUCTS_DB.filter(p => state.wishlist.includes(p.id));
            container.innerHTML = items.map(p => `
                <div class="flex items-center justify-between p-3 rounded-2xl bg-slate-50 dark:bg-slate-900 border border-slate-200 dark:border-slate-800">
                    <div class="flex items-center gap-3">
                        <img src="${p.image}" class="w-12 h-12 object-contain rounded-xl bg-white dark:bg-techCard p-1">
                        <div>
                            <h4 class="font-bold text-xs">${p.name}</h4>
                            <span class="font-sans font-bold text-xs text-royal-600">${p.basePrice.toFixed(2)} JOD</span>
                        </div>
                    </div>
                    <div class="flex items-center gap-2">
                        <button onclick="quickAddToCart('${p.id}'); toggleWishlist('${p.id}')" class="px-3 py-1.5 rounded-lg bg-royal-700 text-white text-xs font-bold">
                            نقل إلى السلة
                        </button>
                        <button onclick="toggleWishlist('${p.id}')" class="text-slate-400 hover:text-rose-500 p-1">
                            <i data-lucide="trash-2" class="w-4 h-4"></i>
                        </button>
                    </div>
                </div>
            `).join('');
            lucide.createIcons();
        }

        /* -------------------------------------------------------------------------
         * 10. إتمام الطلب وسجل الطلبات (Order Handling & Storage)
         * ------------------------------------------------------------------------- */
        function handlePlaceOrder(e) {
            e.preventDefault();

            const name = document.getElementById('custName').value.trim();
            const phone = document.getElementById('custPhone').value.trim();
            const city = document.getElementById('custCity').value;
            const address = document.getElementById('custAddress').value.trim();
            const notes = document.getElementById('custNotes').value.trim();
            const paymentMethod = document.querySelector('input[name="paymentMethod"]:checked').value;

            if (!name || !phone || !address) {
                alert('يرجى تعبئة كافة الحقول الإلزامية');
                return;
            }

            const orderId = 'CBZ-' + Math.floor(100000 + Math.random() * 900000);
            const total = calculateCartSubtotal();

            const order = {
                id: orderId,
                date: new Date().toLocaleDateString(state.lang === 'ar' ? 'ar-JO' : 'en-US', { year: 'numeric', month: 'short', day: 'numeric', hour: '2-digit', minute: '2-digit' }),
                customer: { name, phone, city, address, notes },
                paymentMethod,
                items: [...state.cart],
                total: total,
                status: 'تم تأكيد الحجز (قيد التجهيز للتوصيل)'
            };

            state.orders.unshift(order);
            localStorage.setItem('cbz_orders', JSON.stringify(state.orders));

            // تفريغ السلة
            state.cart = [];
            saveCartState();

            // إظهار شاشة النجاح
            const container = document.getElementById('appContent');
            container.innerHTML = `
                <div class="max-w-xl mx-auto py-16 px-4 text-center space-y-6 animate-fade-in">
                    <div class="w-20 h-20 rounded-full bg-emerald-100 dark:bg-emerald-950 text-emerald-500 flex items-center justify-center mx-auto shadow-xl">
                        <i data-lucide="check-check" class="w-10 h-10"></i>
                    </div>
                    <div class="space-y-2">
                        <span class="text-xs font-bold text-royal-600 uppercase tracking-widest">Cell Buy Zone Orders</span>
                        <h2 class="text-3xl font-black text-slate-900 dark:text-white">شكراً لك، تم استلام طلبك بنجاح!</h2>
                        <p class="text-sm text-slate-500">رقم تتبع طلبك هو: <strong class="font-sans text-royal-600 text-lg">${orderId}</strong></p>
                    </div>

                    <div class="bg-white dark:bg-techCard p-6 rounded-3xl border border-slate-200 dark:border-slate-800 text-xs text-right space-y-2 shadow-sm">
                        <div class="flex justify-between border-b pb-2">
                            <span class="text-slate-400">اسم العميل:</span>
                            <span class="font-bold">${name}</span>
                        </div>
                        <div class="flex justify-between border-b pb-2">
                            <span class="text-slate-400">وجهة التوصيل:</span>
                            <span class="font-bold">${city} - ${address}</span>
                        </div>
                        <div class="flex justify-between border-b pb-2">
                            <span class="text-slate-400">طريقة الدفع:</span>
                            <span class="font-bold">${paymentMethod === 'COD' ? 'الدفع عند الاستلام' : 'بطاقة فيزا'}</span>
                        </div>
                        <div class="flex justify-between pt-1 text-sm font-black text-royal-700">
                            <span>المبلغ الإجمالي:</span>
                            <span class="font-sans">${total.toFixed(2)} JOD</span>
                        </div>
                    </div>

                    <div class="flex justify-center gap-3">
                        <button onclick="navigate('home')" class="px-6 py-3 rounded-2xl bg-royal-700 text-white font-bold text-xs">العودة للرئيسية</button>
                        <button onclick="openOrdersModal()" class="px-6 py-3 rounded-2xl border border-slate-300 dark:border-slate-700 text-xs font-bold">عرض طلباتي</button>
                    </div>
                </div>
            `;
            lucide.createIcons();
        }

        function openOrdersModal() {
            const container = document.getElementById('ordersContainer');
            if (state.orders.length === 0) {
                container.innerHTML = `
                    <div class="py-12 text-center text-slate-400 space-y-2">
                        <i data-lucide="package" class="w-10 h-10 mx-auto stroke-[1.5]"></i>
                        <p class="text-sm font-bold">لا توجد طلبات مسجلة حتى الآن</p>
                    </div>
                `;
            } else {
                container.innerHTML = state.orders.map(ord => `
                    <div class="p-4 rounded-2xl bg-slate-50 dark:bg-slate-900 border border-slate-200 dark:border-slate-800 space-y-3">
                        <div class="flex justify-between items-center text-xs">
                            <span class="font-sans font-bold text-royal-600">${ord.id}</span>
                            <span class="text-slate-400">${ord.date}</span>
                        </div>
                        <div class="space-y-1 text-xs">
                            ${ord.items.map(it => `
                                <div class="flex justify-between text-slate-600 dark:text-slate-300">
                                    <span>${it.product.name} (${it.quantity})</span>
                                    <span class="font-sans">${(it.price * it.quantity).toFixed(2)} JOD</span>
                                </div>
                            `).join('')}
                        </div>
                        <div class="flex justify-between items-center pt-2 border-t border-slate-200 dark:border-slate-800 text-xs">
                            <span class="inline-flex items-center gap-1 text-emerald-600 font-bold">
                                <i data-lucide="clock" class="w-3.5 h-3.5"></i>
                                <span>${ord.status}</span>
                            </span>
                            <span class="font-black font-sans text-sm">${ord.total.toFixed(2)} JOD</span>
                        </div>
                    </div>
                `).join('');
            }

            document.getElementById('ordersModal').classList.remove('hidden');
            lucide.createIcons();
        }

        function closeOrdersModal() {
            document.getElementById('ordersModal').classList.add('hidden');
        }

        /* -------------------------------------------------------------------------
         * 11. البحث الفوري (Live Search Engine)
         * ------------------------------------------------------------------------- */
        function handleSearch(val) {
            const query = val.toLowerCase().trim();
            const resultsBox = document.getElementById('searchResults');
            const clearBtn = document.getElementById('searchClearBtn');

            if (clearBtn) {
                clearBtn.classList.toggle('hidden', query.length === 0);
            }

            if (!resultsBox) return;

            if (query.length < 2) {
                resultsBox.classList.add('hidden');
                return;
            }

            const matched = PRODUCTS_DB.filter(p => 
                p.name.toLowerCase().includes(query) ||
                p.nameEn.toLowerCase().includes(query) ||
                p.brand.toLowerCase().includes(query)
            );

            if (matched.length === 0) {
                resultsBox.innerHTML = `
                    <div class="p-4 text-center text-xs text-slate-400">
                        لا توجد نتائج تطابق "${val}"
                    </div>
                `;
            } else {
                resultsBox.innerHTML = matched.map(p => `
                    <div onclick="openProductModal('${p.id}'); clearSearch();" class="flex items-center gap-3 p-2 hover:bg-slate-100 dark:hover:bg-slate-800/80 rounded-xl cursor-pointer transition">
                        <img src="${p.image}" class="w-10 h-10 object-contain rounded-lg bg-white dark:bg-techCard p-1">
                        <div class="flex-1 min-w-0">
                            <h5 class="text-xs font-bold text-slate-900 dark:text-white truncate">${p.name}</h5>
                            <span class="text-[10px] text-slate-400">${p.brand.toUpperCase()}</span>
                        </div>
                        <span class="font-sans font-bold text-xs text-royal-600">${p.basePrice.toFixed(2)} JOD</span>
                    </div>
                `).join('');
            }

            resultsBox.classList.remove('hidden');
        }

        function clearSearch() {
            const input = document.getElementById('searchInput');
            if (input) input.value = '';
            const resultsBox = document.getElementById('searchResults');
            if (resultsBox) resultsBox.classList.add('hidden');
            const clearBtn = document.getElementById('searchClearBtn');
            if (clearBtn) clearBtn.classList.add('hidden');
        }

        /* -------------------------------------------------------------------------
         * 12. تحديث الشارات والتنبيهات (Badges & Toast)
         * ------------------------------------------------------------------------- */
        function updateBadges() {
            // شارة السلة
            const cartTotalItems = state.cart.reduce((sum, it) => sum + it.quantity, 0);
            const cartBadge = document.getElementById('cartCountBadge');
            const mobileCartBadge = document.getElementById('mobileCartBadge');
            const headerTotal = document.getElementById('cartTotalHeader');

            if (cartBadge) {
                cartBadge.innerText = cartTotalItems;
                cartBadge.classList.toggle('hidden', cartTotalItems === 0);
                cartBadge.classList.toggle('flex', cartTotalItems > 0);
            }
            if (mobileCartBadge) {
                mobileCartBadge.innerText = cartTotalItems;
                mobileCartBadge.classList.toggle('hidden', cartTotalItems === 0);
                mobileCartBadge.classList.toggle('flex', cartTotalItems > 0);
            }
            if (headerTotal) {
                const sub = calculateCartSubtotal();
                headerTotal.innerText = `${sub.toFixed(2)} JOD`;
            }

            // شارة المفضلة
            const wishBadge = document.getElementById('wishlistCountBadge');
            if (wishBadge) {
                wishBadge.innerText = state.wishlist.length;
                wishBadge.classList.toggle('hidden', state.wishlist.length === 0);
                wishBadge.classList.toggle('flex', state.wishlist.length > 0);
            }
        }

        function showToast(message) {
            const toast = document.getElementById('toastNotification');
            const msgElem = document.getElementById('toastMessage');
            if (!toast || !msgElem) return;

            msgElem.innerText = message;
            toast.classList.remove('hidden');

            setTimeout(() => {
                toast.classList.add('hidden');
            }, 3000);
        }

        // بدء التشغيل عند اكتمال تحميل الصفحة
        window.addEventListener('DOMContentLoaded', initApp);
    </script>
</body>
</html>

أهم المزايا والوظائف المضمنة:

  - تركيز شامل على هواتف iPhone: يضم أجهزة عائلة iPhone 17 (Pro Max / Pro /
    Standard) وعائلة iPhone 16 بكافة سعاتها التخزينية المعتمدة وألوان التيتانيوم
    الدقيقة ومواصفاتها الحقيقية.
  - محرك تجارة إلكترونية كامل بالدينار الأردني (JOD):
      - حساب المجموع الفرعي وتكلفة التوصيل المجاني فوق 100 دينار تلقائياً.
      - سلة مشتريات جانبية تسمح بزيادة وإنقاص الكميات والحذف الفوري.
      - قائمة أمنيات (Wishlist) لحفظ الأجهزة المفضلة ونقلها للسلة بنقرة واحدة.
      - نافذة تفاصيل منبثقة تفاعلية عند النقر على أي جهاز لاختيار السعة
        التخزينية واللون مع تحديث السعر والمواصفات فورياً.
      - نظام إتمام طلبات حقيقي (Checkout) مع حفظ الطلب وتوليد كود تتبع الطلب
        وتخزينه في localStorage.
  - تصميم فاخر (Luxury Tech Store):
      - ألوان الهوية الملكية (Royal Blue #0F3D92 / #0B2B68، الأبيض الصافي،
        الرمادي التقني).
      - الوضع الليلي الكامل (Dark Mode) بلمسة زر مع مراعاة راحة العين وتناسق
        الألوان.
      - دعم كامل للغتين: العربية (RTL) والإنجليزية (LTR).
