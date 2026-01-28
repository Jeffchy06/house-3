<!DOCTYPE html>
<html lang="zh-HK">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0, maximum-scale=1.0, user-scalable=no">
    <title>搵樓 CP 值計算機</title>
    <!-- Tailwind CSS -->
    <script src="https://cdn.tailwindcss.com"></script>
    <!-- Vue.js 3 -->
    <script src="https://unpkg.com/vue@3/dist/vue.global.js"></script>
    <!-- Google Fonts (Noto Sans TC) -->
    <link href="https://fonts.googleapis.com/css2?family=Noto+Sans+TC:wght@400;500;700&display=swap" rel="stylesheet">
    <!-- FontAwesome for Icons -->
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">

    <style>
        body {
            font-family: 'Noto Sans TC', sans-serif;
            background-color: #f3f4f6; /* Light gray background */
            -webkit-tap-highlight-color: transparent;
        }
        /* Hide scrollbar for clean look */
        .no-scrollbar::-webkit-scrollbar {
            display: none;
        }
        .no-scrollbar {
            -ms-overflow-style: none;
            scrollbar-width: none;
        }
        .slide-enter-active, .slide-leave-active {
            transition: all 0.3s ease;
        }
        .slide-enter-from, .slide-leave-to {
            opacity: 0;
            transform: translateY(20px);
        }
    </style>
</head>
<body class="text-gray-800">

<div id="app" class="max-w-md mx-auto min-h-screen bg-gray-50 shadow-2xl relative pb-24">
    
    <!-- Header -->
    <header class="bg-indigo-600 text-white p-6 rounded-b-3xl shadow-lg sticky top-0 z-50">
        <div class="flex justify-between items-center">
            <div>
                <h1 class="text-2xl font-bold tracking-wide">搵樓神器</h1>
                <p class="text-indigo-200 text-xs mt-1">計算最高 CP 值樓盤</p>
            </div>
            <div class="bg-white/20 p-2 rounded-full backdrop-blur-sm">
                <i class="fas fa-home text-xl"></i>
            </div>
        </div>
    </header>

    <!-- Content Area -->
    <main class="p-4 space-y-6">

        <!-- Input Form Card -->
        <div class="bg-white p-5 rounded-2xl shadow-sm border border-gray-100">
            <h2 class="text-lg font-bold text-gray-700 mb-4 flex items-center">
                <i class="fas fa-plus-circle text-indigo-500 mr-2"></i> 新增樓盤資料
            </h2>
            
            <form @submit.prevent="addProperty" class="space-y-4">
                <!-- Name -->
                <div>
                    <label class="block text-xs font-medium text-gray-500 mb-1">樓盤名稱 / 座數</label>
                    <input v-model="form.name" required type="text" placeholder="例如：太古城 X座" 
                        class="w-full bg-gray-50 border border-gray-200 text-gray-900 text-sm rounded-xl focus:ring-indigo-500 focus:border-indigo-500 block p-3 outline-none transition-all">
                </div>

                <div class="grid grid-cols-2 gap-3">
                    <!-- Price -->
                    <div>
                        <label class="block text-xs font-medium text-gray-500 mb-1">總價 (萬元)</label>
                        <input v-model.number="form.price" required type="number" step="0.1" placeholder="800" 
                            class="w-full bg-gray-50 border border-gray-200 text-gray-900 text-sm rounded-xl focus:ring-indigo-500 focus:border-indigo-500 block p-3 outline-none">
                    </div>
                    <!-- Sqft Price -->
                    <div>
                        <label class="block text-xs font-medium text-gray-500 mb-1">實用呎價 ($)</label>
                        <input v-model.number="form.sqftPrice" required type="number" placeholder="15000" 
                            class="w-full bg-gray-50 border border-gray-200 text-gray-900 text-sm rounded-xl focus:ring-indigo-500 focus:border-indigo-500 block p-3 outline-none">
                    </div>
                </div>

                <!-- View Rating -->
                <div>
                    <label class="block text-xs font-medium text-gray-500 mb-1">景觀評分 (1-5分)</label>
                    <div class="flex justify-between items-center bg-gray-50 p-2 rounded-xl border border-gray-200">
                        <span class="text-xs text-gray-400 pl-2">樓景</span>
                        <div class="flex gap-2">
                            <button type="button" v-for="n in 5" :key="n" @click="form.viewScore = n"
                                class="w-8 h-8 rounded-full flex items-center justify-center transition-all"
                                :class="form.viewScore >= n ? 'bg-yellow-400 text-white shadow-sm' : 'bg-gray-200 text-gray-400'">
                                <i class="fas fa-star text-xs"></i>
                            </button>
                        </div>
                        <span class="text-xs text-gray-400 pr-2">海景</span>
                    </div>
                </div>

                <!-- Renovation Toggle -->
                <div class="flex items-center justify-between bg-gray-50 p-3 rounded-xl border border-gray-200">
                    <span class="text-sm text-gray-700 font-medium">已有裝修 (即住)</span>
                    <button type="button" @click="form.hasRenovation = !form.hasRenovation"
                        class="relative inline-flex h-6 w-11 items-center rounded-full transition-colors focus:outline-none"
                        :class="form.hasRenovation ? 'bg-green-500' : 'bg-gray-300'">
                        <span class="inline-block h-4 w-4 transform rounded-full bg-white transition-transform"
                            :class="form.hasRenovation ? 'translate-x-6' : 'translate-x-1'"></span>
                    </button>
                </div>

                <!-- Add Button -->
                <button type="submit" 
                    class="w-full text-white bg-indigo-600 hover:bg-indigo-700 focus:ring-4 focus:ring-indigo-300 font-medium rounded-xl text-sm px-5 py-3.5 text-center shadow-lg shadow-indigo-500/30 transition-all active:scale-95">
                    加入比較
                </button>
            </form>
        </div>

        <!-- Result List -->
        <div v-if="properties.length > 0">
            <div class="flex justify-between items-end mb-3">
                <h2 class="text-lg font-bold text-gray-700">排行榜</h2>
                <button @click="clearAll" class="text-xs text-red-500 hover:text-red-700 underline">清除所有</button>
            </div>

            <transition-group name="slide" tag="div" class="space-y-4">
                <div v-for="(prop, index) in sortedProperties" :key="prop.id" 
                    class="relative bg-white p-5 rounded-2xl shadow-md border-l-4 overflow-hidden"
                    :class="index === 0 ? 'border-yellow-400 ring-2 ring-yellow-400/20' : 'border-gray-200'">
                    
                    <!-- Ranking Badge -->
                    <div class="absolute top-0 right-0 px-3 py-1 rounded-bl-xl text-xs font-bold"
                        :class="index === 0 ? 'bg-yellow-400 text-yellow-900' : 'bg-gray-100 text-gray-500'">
                        <span v-if="index === 0"><i class="fas fa-crown mr-1"></i>CP值之王</span>
                        <span v-else>#{{ index + 1 }}</span>
                    </div>

                    <!-- Delete Button -->
                    <button @click="removeProperty(prop.id)" class="absolute bottom-4 right-4 text-gray-300 hover:text-red-500 transition-colors">
                        <i class="fas fa-trash-alt"></i>
                    </button>

                    <div class="flex justify-between items-start pr-12">
                        <div>
                            <h3 class="font-bold text-gray-800 text-lg">{{ prop.name }}</h3>
                            <div class="flex flex-wrap gap-2 mt-2">
                                <span class="bg-indigo-50 text-indigo-700 text-xs px-2 py-1 rounded-md font-medium">
                                    ${{ formatNumber(prop.price) }}萬
                                </span>
                                <span class="bg-gray-100 text-gray-600 text-xs px-2 py-1 rounded-md">
                                    @${{ formatNumber(prop.sqftPrice) }}/呎
                                </span>
                            </div>
                        </div>
                        <div class="text-right">
                            <div class="text-3xl font-black text-indigo-600 leading-none">{{ prop.score }}</div>
                            <div class="text-[10px] text-gray-400 mt-1 uppercase tracking-wider">總分</div>
                        </div>
                    </div>

                    <div class="mt-4 pt-3 border-t border-gray-100 grid grid-cols-2 gap-4 text-xs text-gray-500">
                        <div class="flex items-center">
                            <i class="fas fa-paint-roller mr-2 w-4 text-center" :class="prop.hasRenovation ? 'text-green-500' : 'text-gray-300'"></i>
                            {{ prop.hasRenovation ? '已有裝修' : '需裝修' }}
                        </div>
                        <div class="flex items-center">
                            <i class="fas fa-binoculars mr-2 w-4 text-center text-blue-400"></i>
                            景觀 {{ prop.viewScore }}/5
                        </div>
                    </div>
                </div>
            </transition-group>
        </div>

        <!-- Empty State -->
        <div v-else class="text-center py-10 opacity-50">
            <div class="bg-white/50 inline-flex p-4 rounded-full mb-3">
                <i class="fas fa-clipboard-list text-4xl text-gray-300"></i>
            </div>
            <p class="text-gray-400 text-sm">暫無資料，請輸入樓盤開始比較</p>
        </div>

    </main>

    <!-- Formula Explanation (Small footer) -->
    <footer class="text-center pb-8 pt-4">
        <p class="text-[10px] text-gray-400">
            計分邏輯: 價格(40%) + 呎價(30%) + 景觀(20%) + 裝修(10%)<br>
            *分數乃相對於列表內的比較結果
        </p>
    </footer>

</div>

<script>
    const { createApp, ref, computed } = Vue;

    createApp({
        setup() {
            // State
            const properties = ref([]);
            const form = ref({
                name: '',
                price: null,
                sqftPrice: null,
                viewScore: 3,
                hasRenovation: false
            });

            // Logic: Load from LocalStorage on mount
            const loadData = () => {
                const saved = localStorage.getItem('hkPropData');
                if (saved) {
                    properties.value = JSON.parse(saved);
                }
            };
            loadData();

            // Logic: Save to LocalStorage
            const saveData = () => {
                localStorage.setItem('hkPropData', JSON.stringify(properties.value));
            };

            // Helper: Number formatter
            const formatNumber = (num) => {
                return new Intl.NumberFormat('en-US').format(num);
            };

            // Logic: Calculate Scores dynamically
            // Algorithm: Normalized relative to the best values in the current list
            const sortedProperties = computed(() => {
                if (properties.value.length === 0) return [];

                // 1. Find min/max values in the dataset for normalization
                const minPrice = Math.min(...properties.value.map(p => p.price));
                // Avoid division by zero if dataset is weird, though input validation prevents it
                const minSqft = Math.min(...properties.value.map(p => p.sqftPrice)); 

                return properties.value.map(p => {
                    // Weight Distribution (Total 100)
                    // Price: 40pts (Lower is better)
                    // Sqft: 30pts (Lower is better)
                    // View: 20pts (Higher is better)
                    // Reno: 10pts (Yes is better)

                    // Calculate Price Score (Relative)
                    // If my price is minPrice, I get 1 * 40 = 40. If double minPrice, I get 0.5 * 40 = 20.
                    let priceScore = (minPrice / p.price) * 40;

                    // Calculate Sqft Score (Relative)
                    let sqftScore = (minSqft / p.sqftPrice) * 30;

                    // View Score (Linear: 1=4pts, 5=20pts)
                    let viewScore = (p.viewScore / 5) * 20;

                    // Reno Score (Fixed)
                    let renoScore = p.hasRenovation ? 10 : 0;

                    let total = priceScore + sqftScore + viewScore + renoScore;

                    return {
                        ...p,
                        rawScore: total,
                        score: total.toFixed(1)
                    };
                }).sort((a, b) => b.rawScore - a.rawScore); // Sort descending
            });

            // Action: Add Property
            const addProperty = () => {
                if (!form.value.name || !form.value.price || !form.value.sqftPrice) return;

                properties.value.push({
                    id: Date.now(),
                    ...form.value
                });
                
                // Reset Form (keep sensible defaults)
                form.value = {
                    name: '',
                    price: null,
                    sqftPrice: null,
                    viewScore: 3,
                    hasRenovation: false
                };
                
                saveData();
            };

            // Action: Remove Property
            const removeProperty = (id) => {
                if(confirm('確定刪除此紀錄？')) {
                    properties.value = properties.value.filter(p => p.id !== id);
                    saveData();
                }
            };

            // Action: Clear All
            const clearAll = () => {
                if(confirm('確定清除所有紀錄？')) {
                    properties.value = [];
                    saveData();
                }
            }

            return {
                form,
                properties,
                sortedProperties,
                addProperty,
                removeProperty,
                formatNumber,
                clearAll
            };
        }
    }).mount('#app');
</script>

</body>
</html>
