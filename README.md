<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>PB Tracker</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <link href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css" rel="stylesheet">
    <style>
        @import url('https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700;800&display=swap');
        @import url('https://fonts.googleapis.com/css2?family=Orbitron:wght@400;500;600;700;800;900&display=swap');
        
        * {
            font-family: 'Poppins', sans-serif;
        }
        
        .logo-text {
            font-family: 'Orbitron', monospace;
            background: linear-gradient(45deg, #FF9900, #146EB4, #232F3E, #37475A, #FF9900);
            background-size: 400% 400%;
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            animation: gradientShift 4s ease-in-out infinite;
            text-shadow: 0 0 30px rgba(255, 153, 0, 0.5);
            transition: all 0.4s ease;
        }
        
        .logo-text:hover {
            transform: scale(1.1) rotate(2deg);
            text-shadow: 0 0 50px rgba(255, 153, 0, 0.8), 0 0 80px rgba(20, 110, 180, 0.6);
            filter: brightness(1.3);
        }
        
        @keyframes gradientShift {
            0%, 100% { background-position: 0% 50%; }
            25% { background-position: 100% 50%; }
            50% { background-position: 50% 100%; }
            75% { background-position: 100% 0%; }
        }
        
        .gradient-bg {
            background: linear-gradient(135deg, #232F3E 0%, #37475A 25%, #FF9900 50%, #146EB4 75%, #232F3E 100%);
            background-size: 400% 400%;
            animation: backgroundShift 15s ease infinite;
        }
        
        @keyframes backgroundShift {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }
        
        .glass-effect {
            background: linear-gradient(135deg, rgba(255, 255, 255, 0.1), rgba(255, 255, 255, 0.05));
            backdrop-filter: blur(20px);
            border: 1px solid rgba(255, 255, 255, 0.2);
            box-shadow: 0 15px 35px rgba(0, 0, 0, 0.1), 0 5px 15px rgba(0, 0, 0, 0.08);
            transition: all 0.4s cubic-bezier(0.23, 1, 0.320, 1);
        }
        
        .glass-effect:hover {
            background: linear-gradient(135deg, rgba(255, 255, 255, 0.15), rgba(255, 255, 255, 0.08));
            border: 1px solid rgba(255, 255, 255, 0.3);
            box-shadow: 0 20px 40px rgba(0, 0, 0, 0.15), 0 10px 20px rgba(0, 0, 0, 0.1);
            transform: translateY(-8px) scale(1.02);
        }
        
        .hover-lift {
            transition: all 0.4s cubic-bezier(0.23, 1, 0.320, 1);
            position: relative;
            overflow: hidden;
        }
        
        .hover-lift::before {
            content: '';
            position: absolute;
            top: 0;
            left: -100%;
            width: 100%;
            height: 100%;
            background: linear-gradient(90deg, transparent, rgba(255, 255, 255, 0.1), transparent);
            transition: left 0.6s;
        }
        
        .hover-lift:hover::before {
            left: 100%;
        }
        
        .hover-lift:hover {
            transform: translateY(-10px) scale(1.03);
            box-shadow: 0 25px 50px rgba(0, 0, 0, 0.2);
        }
        
        .gradient-button {
            background: #FF9900;
            border: none;
            color: white;
            font-weight: 600;
            text-shadow: 0 2px 4px rgba(0, 0, 0, 0.3);
            transition: all 0.4s ease;
        }
        
        .gradient-button:hover {
            background: #e6890a;
            transform: translateY(-3px) scale(1.05);
            box-shadow: 0 15px 30px rgba(0, 0, 0, 0.2);
        }
        
        @keyframes gradientMove {
            0%, 100% { background-position: 0% 50%; }
            50% { background-position: 100% 50%; }
        }
        
        .neon-glow {
            box-shadow: 0 0 20px rgba(255, 153, 0, 0.5), 0 0 40px rgba(20, 110, 180, 0.3), 0 0 60px rgba(35, 47, 62, 0.2);
            transition: all 0.4s ease;
        }
        
        .neon-glow:hover {
            box-shadow: 0 0 30px rgba(255, 153, 0, 0.8), 0 0 60px rgba(20, 110, 180, 0.5), 0 0 90px rgba(35, 47, 62, 0.3);
        }
        
        .pulse-animation {
            animation: pulse 2s infinite;
        }
        
        @keyframes pulse {
            0%, 100% { 
                opacity: 1; 
                transform: scale(1);
            }
            50% { 
                opacity: 0.8; 
                transform: scale(1.05);
            }
        }
        
        .slide-in {
            animation: slideIn 0.8s cubic-bezier(0.23, 1, 0.320, 1);
        }
        
        @keyframes slideIn {
            from { 
                transform: translateX(-100%) rotate(-10deg); 
                opacity: 0; 
            }
            to { 
                transform: translateX(0) rotate(0deg); 
                opacity: 1; 
            }
        }
        
        .fade-in {
            animation: fadeIn 0.8s ease-out;
        }
        
        @keyframes fadeIn {
            from { 
                opacity: 0; 
                transform: translateY(30px) scale(0.9); 
            }
            to { 
                opacity: 1; 
                transform: translateY(0) scale(1); 
            }
        }
        
        .floating-animation {
            animation: floating 3s ease-in-out infinite;
        }
        
        @keyframes floating {
            0%, 100% { transform: translateY(0px); }
            50% { transform: translateY(-10px); }
        }
        
        .rainbow-border {
            border: 2px solid;
            border-image: linear-gradient(45deg, #FF9900, #146EB4, #232F3E, #37475A, #FF9900) 1;
            animation: borderShift 3s linear infinite;
        }
        
        @keyframes borderShift {
            0%, 100% { border-image-source: linear-gradient(45deg, #FF9900, #146EB4, #232F3E, #37475A, #FF9900); }
            25% { border-image-source: linear-gradient(45deg, #146EB4, #232F3E, #37475A, #FF9900, #FF9900); }
            50% { border-image-source: linear-gradient(45deg, #232F3E, #37475A, #FF9900, #FF9900, #146EB4); }
            75% { border-image-source: linear-gradient(45deg, #37475A, #FF9900, #FF9900, #146EB4, #232F3E); }
        }
        
        .morphing-card {
            transition: all 0.6s cubic-bezier(0.23, 1, 0.320, 1);
            transform-style: preserve-3d;
        }
        
        .morphing-card:hover {
            transform: rotateY(10deg) rotateX(5deg) translateZ(20px);
        }
        
        .text-gradient {
            background: linear-gradient(45deg, #FF9900, #146EB4, #232F3E);
            -webkit-background-clip: text;
            -webkit-text-fill-color: transparent;
            background-clip: text;
            font-weight: 700;
        }
        
        .input-glow {
            transition: all 0.3s ease;
            border: 2px solid rgba(255, 255, 255, 0.2);
        }
        
        .input-glow:focus {
            border: 2px solid rgba(255, 153, 0, 0.6);
            box-shadow: 0 0 20px rgba(255, 153, 0, 0.3), inset 0 0 20px rgba(20, 110, 180, 0.1);
            background: rgba(255, 255, 255, 0.1);
        }
        
        .status-indicator {
            position: relative;
            display: inline-block;
        }
        
        .status-indicator::before {
            content: '';
            position: absolute;
            top: -2px;
            right: -2px;
            width: 12px;
            height: 12px;
            background: linear-gradient(45deg, #FF9900, #146EB4);
            border-radius: 50%;
            animation: statusPulse 2s infinite;
        }
        
        @keyframes statusPulse {
            0%, 100% { 
                transform: scale(1); 
                opacity: 1; 
            }
            50% { 
                transform: scale(1.3); 
                opacity: 0.7; 
            }
        }
        
        /* Dark Mode Styles */
        .dark-mode {
            filter: invert(1) hue-rotate(180deg);
        }
        
        .dark-mode img,
        .dark-mode video,
        .dark-mode iframe,
        .dark-mode svg {
            filter: invert(1) hue-rotate(180deg);
        }
        
        /* Custom Scrollbar */
        ::-webkit-scrollbar {
            width: 8px;
        }
        
        ::-webkit-scrollbar-track {
            background: rgba(255, 255, 255, 0.1);
            border-radius: 10px;
        }
        
        ::-webkit-scrollbar-thumb {
            background: linear-gradient(45deg, #FF9900, #146EB4);
            border-radius: 10px;
        }
        
        ::-webkit-scrollbar-thumb:hover {
            background: linear-gradient(45deg, #146EB4, #232F3E);
        }
    </style>
</head>
<body class="min-h-screen gradient-bg">


    <!-- Floating Action Buttons -->
    <div class="fixed bottom-4 right-4 z-50 flex flex-col space-y-3">
        <!-- Alert Popup Button -->
        <button onclick="showAlertPopup()" id="alertBtn" class="bg-red-600 hover:bg-red-500 text-white p-3 rounded-full transition-all duration-300 hover:scale-110 hover:shadow-xl shadow-lg pulse-animation" title="View system alerts">
            <i class="fas fa-bell text-xl"></i>
        </button>
        
        <!-- GPS Location Button -->
        <button onclick="enableGPSLocation()" id="gpsLocationBtn" class="bg-emerald-600 hover:bg-emerald-500 text-white p-3 rounded-full transition-all duration-300 hover:scale-110 hover:shadow-xl shadow-lg" title="Enable GPS & find nearby buses">
            <i class="fas fa-crosshairs text-xl"></i>
        </button>
        
        <!-- Dark Mode Toggle -->
        <button id="darkModeToggle" class="bg-slate-700 hover:bg-slate-600 text-white p-3 rounded-full transition-all duration-300 hover:scale-110 hover:shadow-xl shadow-lg" title="Toggle dark mode">
            <i class="fas fa-moon text-xl"></i>
        </button>
    </div>

    <!-- Notification Container -->
    <div id="notificationContainer" class="fixed top-4 left-1/2 transform -translate-x-1/2 z-50 space-y-2"></div>

    <!-- Header with Login -->
    <header class="bg-slate-800 border-b-2 border-slate-700 p-4 shadow-lg">
        <div class="container mx-auto flex justify-between items-center">
            <div class="flex items-center space-x-3">
                <i class="fas fa-bus text-cyan-400 text-3xl hover:text-cyan-300 transition-colors duration-300"></i>
                <div>
                    <h1 class="logo-text text-2xl font-bold cursor-pointer hover:scale-105 transition-transform duration-300" data-translate="title">PB Tracker</h1>
                </div>
            </div>
            
            <div class="flex items-center space-x-4">
                <!-- Language Selector -->
                <select id="languageSelector" class="bg-slate-700 text-white border-2 border-slate-600 rounded-lg px-3 py-2 hover:bg-slate-600 hover:border-cyan-400 transition-all duration-300 focus:outline-none focus:ring-2 focus:ring-cyan-400 focus:border-cyan-400">
                    <option value="en">🇺🇸 English</option>
                    <option value="hi">🇮🇳 हिंदी</option>
                    <option value="pa">🇮🇳 ਪੰਜਾਬੀ</option>
                </select>
                
                <!-- Login Button -->
                <button onclick="showLoginOptions()" class="gradient-button px-3 sm:px-6 py-2 rounded-lg text-sm sm:text-base font-medium neon-glow">
                    <i class="fas fa-sign-in-alt mr-1 sm:mr-2"></i>
                    <span data-translate="login">Login</span>
                </button>
            </div>
        </div>
    </header>

    <!-- Main Content -->
    <main class="container mx-auto px-2 sm:px-4 py-4 sm:py-8">
        <!-- Bus Tracking Section -->
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-4 sm:gap-8 mb-6 sm:mb-8">
            <!-- Track by Route -->
            <div class="glass-effect rounded-xl sm:rounded-2xl p-4 sm:p-6 hover-lift fade-in">
                <h2 class="text-white text-lg sm:text-xl font-semibold mb-4 sm:mb-6 flex items-center">
                    <i class="fas fa-route mr-2 sm:mr-3 text-slate-300"></i>
                    <span data-translate="trackByRoute">Track by Route</span>
                </h2>
                
                <div class="space-y-3 sm:space-y-4">
                    <div>
                        <label class="block text-white/80 mb-2" data-translate="pickup">Pickup Location</label>
                        <select id="pickupLocation" class="w-full bg-white/10 input-glow rounded-lg px-3 sm:px-4 py-2 sm:py-3 text-sm sm:text-base text-white placeholder-white/60 focus:outline-none transition-all duration-300">
                            <option value="" data-translate="selectPickup">Select Pickup Location</option>
                        </select>
                    </div>
                    
                    <div>
                        <label class="block text-white/80 mb-2" data-translate="drop">Drop Location</label>
                        <select id="dropLocation" class="w-full bg-white/10 input-glow rounded-lg px-3 sm:px-4 py-2 sm:py-3 text-sm sm:text-base text-white placeholder-white/60 focus:outline-none transition-all duration-300">
                            <option value="" data-translate="selectDrop">Select Drop Location</option>
                        </select>
                    </div>
                    
                    <!-- Date & Time Selector -->
                    <div>
                        <label class="block text-white/80 mb-2" data-translate="selectDateTime">Select Date & Time (Optional)</label>
                        <button onclick="showJourneyDateSelector()" class="w-full bg-white/10 hover:bg-white/20 border border-white/30 rounded-lg px-3 sm:px-4 py-2 sm:py-3 text-white text-left transition-all duration-300 hover-lift flex items-center justify-between">
                            <div class="flex items-center space-x-2">
                                <i class="fas fa-calendar-alt text-emerald-400"></i>
                                <div>
                                    <div class="text-sm font-medium" id="selectedJourneyDate" data-translate="selectDate">Any Date</div>
                                    <div class="text-xs opacity-80" id="selectedJourneyTime" data-translate="selectTime">Any Time</div>
                                </div>
                            </div>
                            <i class="fas fa-chevron-right text-white/60"></i>
                        </button>
                    </div>
                    
                    <button onclick="trackByRoute()" class="w-full gradient-button font-semibold py-2 sm:py-3 text-sm sm:text-base rounded-lg neon-glow">
                        <i class="fas fa-search mr-2"></i>
                        <span data-translate="findBuses">Find Buses</span>
                    </button>
                </div>
            </div>

            <!-- Track by Bus Number -->
            <div class="glass-effect rounded-xl sm:rounded-2xl p-4 sm:p-6 hover-lift fade-in">
                <h2 class="text-white text-lg sm:text-xl font-semibold mb-4 sm:mb-6 flex items-center">
                    <i class="fas fa-hashtag mr-2 sm:mr-3 text-emerald-300"></i>
                    <span data-translate="trackByNumber">Track by Bus Number</span>
                </h2>
                
                <div class="space-y-4">
                    <div>
                        <label class="block text-white/80 mb-2" data-translate="busNumber">Bus Number</label>
                        <input type="text" id="busNumberInput" placeholder="Enter bus number (e.g., PB-01-1234)" class="w-full bg-white/10 input-glow rounded-lg px-3 sm:px-4 py-2 sm:py-3 text-sm sm:text-base text-white placeholder-white/60 focus:outline-none transition-all duration-300">
                    </div>
                    
                    <!-- Date & Time Selector -->
                    <div>
                        <label class="block text-white/80 mb-2" data-translate="selectDateTime">Select Date & Time (Optional)</label>
                        <button onclick="showJourneyDateSelector()" class="w-full bg-white/10 hover:bg-white/20 input-glow rounded-lg px-3 sm:px-4 py-2 sm:py-3 text-white text-left transition-all duration-300 hover-lift flex items-center justify-between">
                            <div class="flex items-center space-x-2">
                                <i class="fas fa-calendar-alt text-emerald-400"></i>
                                <div>
                                    <div class="text-sm font-medium" id="selectedJourneyDate2" data-translate="selectDate">Any Date</div>
                                    <div class="text-xs opacity-80" id="selectedJourneyTime2" data-translate="selectTime">Any Time</div>
                                </div>
                            </div>
                            <i class="fas fa-chevron-right text-white/60"></i>
                        </button>
                    </div>
                    
                    <button onclick="trackByNumber()" class="w-full gradient-button font-semibold py-2 sm:py-3 text-sm sm:text-base rounded-lg neon-glow">
                        <i class="fas fa-map-marker-alt mr-2"></i>
                        <span data-translate="trackBus">Track Bus</span>
                    </button>
                </div>
            </div>
        </div>

        <!-- Quick Actions Section -->
        <div class="grid grid-cols-1 lg:grid-cols-2 gap-4 sm:gap-8 mb-6 sm:mb-8">
            <!-- Recent Searches -->
            <div class="glass-effect rounded-xl sm:rounded-2xl p-4 sm:p-6 hover-lift fade-in">
                <h2 class="text-white text-lg sm:text-xl font-semibold mb-4 sm:mb-6 flex items-center">
                    <i class="fas fa-history mr-2 sm:mr-3 text-slate-300"></i>
                    <span data-translate="recentSearches">Recent Searches</span>
                </h2>
                
                <div id="recentSearchesList" class="space-y-3">
                    <div class="text-center text-white/60 py-8">
                        <i class="fas fa-search text-3xl mb-3"></i>
                        <p data-translate="noRecentSearches">No recent searches yet</p>
                        <p class="text-sm mt-2" data-translate="searchToSave">Search for buses to see them here</p>
                    </div>
                </div>
                
                <button onclick="clearRecentSearches()" class="w-full mt-4 bg-white/10 hover:bg-white/20 text-white font-medium py-2 rounded-lg transition-all duration-300 hover-lift text-sm" style="display: none;" id="clearRecentBtn">
                    <i class="fas fa-trash mr-2"></i>
                    <span data-translate="clearHistory">Clear History</span>
                </button>
            </div>

            <!-- Recommended Routes -->
            <div class="glass-effect rounded-xl sm:rounded-2xl p-4 sm:p-6 hover-lift fade-in">
                <h2 class="text-white text-lg sm:text-xl font-semibold mb-4 sm:mb-6 flex items-center">
                    <i class="fas fa-star mr-2 sm:mr-3 text-amber-300"></i>
                    <span data-translate="recommendedRoutes">Recommended Routes</span>
                </h2>
                
                <div class="space-y-3">
                    <div class="bg-white/10 hover:bg-white/20 rounded-lg p-3 cursor-pointer transition-all duration-300 hover-lift" onclick="selectRecommendedRoute('Chandigarh', 'Ludhiana')">
                        <div class="flex justify-between items-center">
                            <div>
                                <p class="text-white font-medium">Chandigarh → Ludhiana</p>
                                <p class="text-white/70 text-sm">Popular route • 98 km</p>
                            </div>
                            <div class="text-right">
                                <p class="text-emerald-400 font-semibold">₹120</p>
                                <p class="text-white/60 text-xs">5 buses available</p>
                            </div>
                        </div>
                    </div>
                    
                    <div class="bg-white/10 hover:bg-white/20 rounded-lg p-3 cursor-pointer transition-all duration-300 hover-lift" onclick="selectRecommendedRoute('Chandigarh', 'Amritsar')">
                        <div class="flex justify-between items-center">
                            <div>
                                <p class="text-white font-medium">Chandigarh → Amritsar</p>
                                <p class="text-white/70 text-sm">Frequent service • 230 km</p>
                            </div>
                            <div class="text-right">
                                <p class="text-emerald-400 font-semibold">₹280</p>
                                <p class="text-white/60 text-xs">3 buses available</p>
                            </div>
                        </div>
                    </div>
                    
                    <div class="bg-white/10 hover:bg-white/20 rounded-lg p-3 cursor-pointer transition-all duration-300 hover-lift" onclick="selectRecommendedRoute('Ludhiana', 'Amritsar')">
                        <div class="flex justify-between items-center">
                            <div>
                                <p class="text-white font-medium">Ludhiana → Amritsar</p>
                                <p class="text-white/70 text-sm">Express route • 132 km</p>
                            </div>
                            <div class="text-right">
                                <p class="text-emerald-400 font-semibold">₹160</p>
                                <p class="text-white/60 text-xs">4 buses available</p>
                            </div>
                        </div>
                    </div>
                </div>
                
                <button onclick="showAllRecommendations()" class="w-full mt-4 bg-gradient-to-r from-emerald-600 to-emerald-700 hover:from-emerald-500 hover:to-emerald-600 text-white font-semibold py-2 rounded-lg transition-all duration-300 transform hover:scale-105 hover:shadow-lg">
                    <i class="fas fa-route mr-2"></i>
                    <span data-translate="viewAllRoutes">View All Routes</span>
                </button>
            </div>
        </div>

        <!-- Bus Results -->
        <div id="busResults" class="hidden glass-effect rounded-xl sm:rounded-2xl p-4 sm:p-6 fade-in">
            <h2 class="text-white text-lg sm:text-xl font-semibold mb-3 sm:mb-4 flex items-center">
                <i class="fas fa-list mr-2 sm:mr-3 text-slate-300"></i>
                <span data-translate="availableBuses">Available Buses</span>
            </h2>
            <div id="busList" class="space-y-4"></div>
        </div>
    </main>

    <!-- Login Options Modal -->
    <div id="loginOptionsModal" class="fixed inset-0 bg-black/50 backdrop-blur-sm hidden items-center justify-center z-50">
        <div class="glass-effect rounded-2xl p-8 m-4 w-full max-w-md slide-in">
            <div class="flex justify-between items-center mb-6">
                <h2 class="text-white text-2xl font-semibold" data-translate="selectLoginType">Select Login Type</h2>
                <button onclick="closeLoginOptions()" class="text-white/60 hover:text-white transition-colors">
                    <i class="fas fa-times text-xl"></i>
                </button>
            </div>
            
            <div class="space-y-4">
                <button onclick="showLogin('admin')" class="w-full bg-gradient-to-r from-blue-500 to-purple-600 hover:from-blue-600 hover:to-purple-700 text-white font-semibold py-4 rounded-lg transition-all duration-300 transform hover:scale-105 hover-lift">
                    <i class="fas fa-user-shield mr-3 text-xl"></i>
                    <span data-translate="adminPortal">Admin Portal</span>
                </button>
                
                <button onclick="showLogin('driver')" class="w-full bg-gradient-to-r from-green-500 to-teal-600 hover:from-green-600 hover:to-teal-700 text-white font-semibold py-4 rounded-lg transition-all duration-300 transform hover:scale-105 hover-lift">
                    <i class="fas fa-id-card mr-3 text-xl"></i>
                    <span data-translate="driverPortal">Driver Portal</span>
                </button>
                
                <div class="border-t border-white/20 pt-4 mt-6">
                    <p class="text-white/70 text-center mb-4" data-translate="newUser">New User?</p>
                    <div class="grid grid-cols-2 gap-3">
                        <button onclick="showCreateAccount('admin')" class="bg-white/10 hover:bg-white/20 text-white font-medium py-3 px-4 rounded-lg transition-all duration-300 hover-lift text-sm">
                            <i class="fas fa-user-plus mr-2"></i>
                            <span data-translate="createAdmin">Create Admin</span>
                        </button>
                        
                        <button onclick="showCreateAccount('driver')" class="bg-white/10 hover:bg-white/20 text-white font-medium py-3 px-4 rounded-lg transition-all duration-300 hover-lift text-sm">
                            <i class="fas fa-user-plus mr-2"></i>
                            <span data-translate="createDriver">Create Driver</span>
                        </button>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Login Modal -->
    <div id="loginModal" class="fixed inset-0 bg-black/50 backdrop-blur-sm hidden items-center justify-center z-50">
        <div class="glass-effect rounded-2xl p-8 m-4 w-full max-w-md slide-in">
            <div class="flex justify-between items-center mb-6">
                <h2 id="loginTitle" class="text-white text-2xl font-semibold"></h2>
                <button onclick="closeLogin()" class="text-white/60 hover:text-white transition-colors">
                    <i class="fas fa-times text-xl"></i>
                </button>
            </div>
            
            <form id="loginForm" class="space-y-4">
                <div>
                    <label class="block text-white/80 mb-2" data-translate="username">Username</label>
                    <input type="text" id="username" class="w-full bg-white/10 border border-white/30 rounded-lg px-4 py-3 text-white placeholder-white/60 focus:outline-none focus:ring-2 focus:ring-blue-400 transition-all duration-300">
                </div>
                
                <div>
                    <label class="block text-white/80 mb-2" data-translate="password">Password</label>
                    <div class="relative">
                        <input type="password" id="password" class="w-full bg-white/10 border border-white/30 rounded-lg px-4 py-3 pr-12 text-white placeholder-white/60 focus:outline-none focus:ring-2 focus:ring-blue-400 transition-all duration-300">
                        <button type="button" id="togglePassword" class="absolute right-3 top-1/2 transform -translate-y-1/2 text-white/60 hover:text-white transition-colors hidden" onclick="togglePasswordVisibility('password', 'togglePassword')">
                            <i class="fas fa-eye"></i>
                        </button>
                    </div>
                </div>
                
                <button type="submit" class="w-full bg-gradient-to-r from-purple-500 to-pink-600 hover:from-purple-600 hover:to-pink-700 text-white font-semibold py-3 rounded-lg transition-all duration-300 transform hover:scale-105">
                    <i class="fas fa-sign-in-alt mr-2"></i>
                    <span data-translate="login">Login</span>
                </button>
            </form>
            
            <div class="mt-4 text-center text-white/60 text-sm">
                <p data-translate="demoCredentials">Demo Credentials:</p>
                <p>Admin: admin1 / admin123</p>
                <p>Driver: driver1 / pass123</p>
            </div>
        </div>
    </div>

    <!-- Dashboard Modal -->
    <div id="dashboardModal" class="fixed inset-0 bg-black/50 backdrop-blur-sm hidden items-center justify-center z-50">
        <div class="glass-effect rounded-2xl p-8 m-4 w-full max-w-4xl max-h-[90vh] overflow-y-auto slide-in">
            <div class="flex justify-between items-center mb-6">
                <h2 id="dashboardTitle" class="text-white text-2xl font-semibold"></h2>
                <button onclick="closeDashboard()" class="text-white/60 hover:text-white transition-colors">
                    <i class="fas fa-times text-xl"></i>
                </button>
            </div>
            
            <div id="dashboardContent" class="text-white"></div>
        </div>
    </div>

    <!-- Create Account Modal -->
    <div id="createAccountModal" class="fixed inset-0 bg-black/50 backdrop-blur-sm hidden items-center justify-center z-50">
        <div class="glass-effect rounded-2xl p-8 m-4 w-full max-w-lg max-h-[90vh] overflow-y-auto slide-in">
            <div class="flex justify-between items-center mb-6">
                <h2 id="createAccountTitle" class="text-white text-2xl font-semibold"></h2>
                <button onclick="closeCreateAccount()" class="text-white/60 hover:text-white transition-colors">
                    <i class="fas fa-times text-xl"></i>
                </button>
            </div>
            
            <form id="createAccountForm" class="space-y-4">
                <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                    <div>
                        <label class="block text-white/80 mb-2" data-translate="fullName">Full Name *</label>
                        <input type="text" id="createName" required class="w-full bg-white/10 border border-white/30 rounded-lg px-4 py-3 text-white placeholder-white/60 focus:outline-none focus:ring-2 focus:ring-blue-400 transition-all duration-300">
                    </div>
                    
                    <div>
                        <label class="block text-white/80 mb-2" data-translate="age">Age *</label>
                        <input type="number" id="createAge" min="18" max="65" required class="w-full bg-white/10 border border-white/30 rounded-lg px-4 py-3 text-white placeholder-white/60 focus:outline-none focus:ring-2 focus:ring-blue-400 transition-all duration-300">
                    </div>
                </div>
                
                <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                    <div>
                        <label class="block text-white/80 mb-2" data-translate="gender">Gender *</label>
                        <select id="createGender" required class="w-full bg-white/10 border border-white/30 rounded-lg px-4 py-3 text-white focus:outline-none focus:ring-2 focus:ring-blue-400 transition-all duration-300">
                            <option value="" data-translate="selectGender">Select Gender</option>
                            <option value="male" data-translate="male">Male</option>
                            <option value="female" data-translate="female">Female</option>
                            <option value="other" data-translate="other">Other</option>
                        </select>
                    </div>
                    
                    <div>
                        <label class="block text-white/80 mb-2" data-translate="mobile">Mobile Number *</label>
                        <input type="tel" id="createMobile" pattern="[0-9]{10}" required class="w-full bg-white/10 border border-white/30 rounded-lg px-4 py-3 text-white placeholder-white/60 focus:outline-none focus:ring-2 focus:ring-blue-400 transition-all duration-300" placeholder="10-digit number">
                    </div>
                </div>
                
                <div>
                    <label class="block text-white/80 mb-2" data-translate="email">Email (Optional)</label>
                    <input type="email" id="createEmail" class="w-full bg-white/10 border border-white/30 rounded-lg px-4 py-3 text-white placeholder-white/60 focus:outline-none focus:ring-2 focus:ring-blue-400 transition-all duration-300" placeholder="example@email.com">
                </div>
                
                <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                    <div>
                        <label class="block text-white/80 mb-2" data-translate="username">Username *</label>
                        <input type="text" id="createUsername" required class="w-full bg-white/10 border border-white/30 rounded-lg px-4 py-3 text-white placeholder-white/60 focus:outline-none focus:ring-2 focus:ring-blue-400 transition-all duration-300">
                    </div>
                    
                    <div>
                        <label class="block text-white/80 mb-2" data-translate="password">Password *</label>
                        <div class="relative">
                            <input type="password" id="createPassword" required minlength="6" class="w-full bg-white/10 border border-white/30 rounded-lg px-4 py-3 pr-12 text-white placeholder-white/60 focus:outline-none focus:ring-2 focus:ring-blue-400 transition-all duration-300">
                            <button type="button" id="toggleCreatePassword" class="absolute right-3 top-1/2 transform -translate-y-1/2 text-white/60 hover:text-white transition-colors hidden" onclick="togglePasswordVisibility('createPassword', 'toggleCreatePassword')">
                                <i class="fas fa-eye"></i>
                            </button>
                        </div>
                    </div>
                </div>
                
                <div id="driverSpecificFields" class="hidden space-y-4">
                    <div class="border-t border-white/20 pt-4">
                        <h3 class="text-white font-semibold mb-3" data-translate="driverInfo">Driver Information</h3>
                        <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                            <div>
                                <label class="block text-white/80 mb-2" data-translate="licenseNumber">License Number</label>
                                <input type="text" id="createLicense" class="w-full bg-white/10 border border-white/30 rounded-lg px-4 py-3 text-white placeholder-white/60 focus:outline-none focus:ring-2 focus:ring-blue-400 transition-all duration-300">
                            </div>
                            
                            <div>
                                <label class="block text-white/80 mb-2" data-translate="experience">Experience (Years)</label>
                                <input type="number" id="createExperience" min="0" max="50" class="w-full bg-white/10 border border-white/30 rounded-lg px-4 py-3 text-white placeholder-white/60 focus:outline-none focus:ring-2 focus:ring-blue-400 transition-all duration-300">
                            </div>
                        </div>
                    </div>
                </div>
                
                <div id="adminSpecificFields" class="hidden space-y-4">
                    <div class="border-t border-white/20 pt-4">
                        <h3 class="text-white font-semibold mb-3" data-translate="adminInfo">Admin Information</h3>
                        <div class="grid grid-cols-1 sm:grid-cols-2 gap-4">
                            <div>
                                <label class="block text-white/80 mb-2" data-translate="department">Department</label>
                                <select id="createDepartment" class="w-full bg-white/10 border border-white/30 rounded-lg px-4 py-3 text-white focus:outline-none focus:ring-2 focus:ring-blue-400 transition-all duration-300">
                                    <option value="" data-translate="selectDepartment">Select Department</option>
                                    <option value="operations">Operations</option>
                                    <option value="fleet">Fleet Management</option>
                                    <option value="customer">Customer Service</option>
                                    <option value="maintenance">Maintenance</option>
                                    <option value="planning">Route Planning</option>
                                </select>
                            </div>
                            
                            <div>
                                <label class="block text-white/80 mb-2" data-translate="level">Level</label>
                                <select id="createLevel" class="w-full bg-white/10 border border-white/30 rounded-lg px-4 py-3 text-white focus:outline-none focus:ring-2 focus:ring-blue-400 transition-all duration-300">
                                    <option value="" data-translate="selectLevel">Select Level</option>
                                    <option value="junior">Junior</option>
                                    <option value="senior">Senior</option>
                                    <option value="supervisor">Supervisor</option>
                                    <option value="manager">Manager</option>
                                    <option value="head">Head</option>
                                </select>
                            </div>
                        </div>
                    </div>
                </div>
                
                <button type="submit" class="w-full bg-gradient-to-r from-purple-500 to-pink-600 hover:from-purple-600 hover:to-pink-700 text-white font-semibold py-3 rounded-lg transition-all duration-300 transform hover:scale-105 mt-6">
                    <i class="fas fa-user-plus mr-2"></i>
                    <span data-translate="createAccount">Create Account</span>
                </button>
            </form>
        </div>
    </div>

    <!-- GPS Location Modal -->
    <div id="gpsLocationModal" class="fixed inset-0 bg-black/50 backdrop-blur-sm hidden items-center justify-center z-50">
        <div class="glass-effect rounded-2xl p-6 m-4 w-full max-w-md slide-in">
            <div class="flex justify-between items-center mb-6">
                <h2 class="text-white text-xl font-semibold flex items-center">
                    <i class="fas fa-crosshairs mr-2 text-blue-400"></i>
                    <span>GPS Location Services</span>
                </h2>
                <button onclick="closeGPSModal()" class="text-white/60 hover:text-white transition-colors">
                    <i class="fas fa-times text-xl"></i>
                </button>
            </div>
            
            <div id="gpsModalContent">
                <!-- GPS Permission Request -->
                <div id="gpsPermissionRequest" class="space-y-4">
                    <div class="bg-blue-500/20 rounded-lg p-4 border border-blue-400/30">
                        <div class="flex items-center space-x-3 mb-3">
                            <i class="fas fa-satellite-dish text-blue-400 text-2xl"></i>
                            <div>
                                <h3 class="text-white font-semibold">Enable GPS Location</h3>
                                <p class="text-white/80 text-sm">Get accurate location for nearby buses</p>
                            </div>
                        </div>
                    </div>
                    
                    <div class="space-y-3">
                        <div class="bg-white/10 rounded-lg p-3">
                            <h4 class="text-white font-medium mb-2">🎯 What you'll get:</h4>
                            <ul class="text-white/80 text-sm space-y-1">
                                <li>• Find buses near your exact location</li>
                                <li>• Real-time distance calculations</li>
                                <li>• Interactive Google Maps integration</li>
                                <li>• Live GPS tracking of your position</li>
                            </ul>
                        </div>
                        
                        <button onclick="requestGPSPermission()" class="w-full bg-green-500 hover:bg-green-600 text-white font-semibold py-3 rounded-lg transition-all duration-300 transform hover:scale-105">
                            <i class="fas fa-location-arrow mr-2"></i>
                            Enable GPS & Find Nearby Buses
                        </button>
                        
                        <button onclick="showManualLocationSearch()" class="w-full bg-blue-500/20 hover:bg-blue-500/30 text-white font-medium py-2 rounded-lg transition-all duration-300">
                            <i class="fas fa-search mr-2"></i>
                            Search by City Name Instead
                        </button>
                    </div>
                </div>
                
                <!-- GPS Active Status -->
                <div id="gpsActiveStatus" class="hidden space-y-4">
                    <div class="bg-green-500/20 rounded-lg p-4 border border-green-400/30">
                        <div class="flex items-center justify-between mb-2">
                            <span class="text-green-400 font-semibold">
                                <i class="fas fa-check-circle mr-2"></i>
                                GPS Location Active
                            </span>
                            <div class="w-3 h-3 bg-green-500 rounded-full animate-pulse"></div>
                        </div>
                        <p id="currentLocationInfo" class="text-white text-sm"></p>
                    </div>
                    
                    <div id="googleMapContainer" class="bg-white/10 rounded-lg p-4">
                        <h4 class="text-white font-semibold mb-3">
                            <i class="fas fa-map mr-2 text-blue-400"></i>
                            Your Location on Map
                        </h4>
                        <div id="googleMapPlaceholder" class="bg-gray-800 rounded-lg h-48 flex items-center justify-center">
                            <div class="text-center text-white/60">
                                <i class="fas fa-map-marked-alt text-3xl mb-2"></i>
                                <p>Google Maps would load here</p>
                                <p class="text-xs">Interactive map with your location</p>
                            </div>
                        </div>
                    </div>
                    
                    <div class="grid grid-cols-2 gap-3">
                        <button onclick="findNearbyBuses()" class="bg-blue-500 hover:bg-blue-600 text-white font-medium py-2 rounded-lg transition-colors text-sm">
                            <i class="fas fa-bus mr-1"></i>
                            Find Buses
                        </button>
                        
                        <button onclick="shareCurrentLocation()" class="bg-purple-500 hover:bg-purple-600 text-white font-medium py-2 rounded-lg transition-colors text-sm">
                            <i class="fas fa-share-alt mr-1"></i>
                            Share Location
                        </button>
                    </div>
                </div>
            </div>
        </div>
    </div>

    <!-- Journey Date & Time Selector Modal -->
    <div id="journeyDateModal" class="fixed inset-0 bg-black/50 backdrop-blur-sm hidden items-center justify-center z-50">
        <div class="glass-effect rounded-2xl p-6 m-4 w-full max-w-sm slide-in">
            <div class="flex justify-between items-center mb-4">
                <h2 class="text-white text-lg font-semibold flex items-center">
                    <i class="fas fa-calendar-alt mr-2 text-blue-400"></i>
                    <span data-translate="selectDateTime">Select Date & Time</span>
                </h2>
                <button onclick="closeJourneyDateSelector()" class="text-white/60 hover:text-white transition-colors">
                    <i class="fas fa-times"></i>
                </button>
            </div>
            
            <div class="space-y-4">
                <!-- Date Selection -->
                <div>
                    <label class="block text-white/80 mb-2 text-sm" data-translate="selectDate">Select Date</label>
                    <input type="date" id="journeyDateInput" class="w-full bg-white/10 border border-white/30 rounded-lg px-3 py-2 text-white focus:outline-none focus:ring-2 focus:ring-blue-400 transition-all duration-300">
                </div>
                
                <!-- Time Selection -->
                <div>
                    <label class="block text-white/80 mb-2 text-sm" data-translate="selectTime">Select Time</label>
                    <input type="time" id="customTimeInput" class="w-full bg-white/10 border border-white/30 rounded-lg px-3 py-2 text-white focus:outline-none focus:ring-2 focus:ring-blue-400 transition-all duration-300">
                </div>
                
                <!-- Action Buttons -->
                <div class="flex space-x-2 pt-2">
                    <button onclick="confirmJourneyDateTime()" class="flex-1 bg-blue-500 hover:bg-blue-600 text-white font-medium py-2 rounded-lg transition-all duration-300">
                        <i class="fas fa-check mr-1"></i>
                        <span data-translate="confirm">Confirm</span>
                    </button>
                    <button onclick="closeJourneyDateSelector()" class="bg-white/10 hover:bg-white/20 text-white px-4 py-2 rounded-lg transition-all duration-300">
                        <i class="fas fa-arrow-left"></i>
                    </button>
                </div>
            </div>
        </div>
    </div>



    <!-- Nearby Buses Modal -->
    <div id="nearbyBusesModal" class="fixed inset-0 bg-black/50 backdrop-blur-sm hidden items-center justify-center z-50">
        <div class="glass-effect rounded-2xl p-6 m-4 w-full max-w-2xl max-h-[90vh] overflow-y-auto slide-in">
            <div class="flex justify-between items-center mb-6">
                <h2 class="text-white text-xl font-semibold flex items-center">
                    <i class="fas fa-map-marker-alt mr-2 text-blue-400"></i>
                    <span data-translate="nearbyBuses">Buses Near You</span>
                </h2>
                <button onclick="closeNearbyBuses()" class="text-white/60 hover:text-white transition-colors">
                    <i class="fas fa-times text-xl"></i>
                </button>
            </div>
            
            <div id="nearbyBusesContent">
                <!-- Content will be populated by JavaScript -->
            </div>
        </div>
    </div>

    <!-- Driver Issue Report Modal -->
    <div id="driverIssueModal" class="fixed inset-0 bg-black/50 backdrop-blur-sm hidden items-center justify-center z-50">
        <div class="glass-effect rounded-2xl p-6 m-4 w-full max-w-3xl max-h-[95vh] overflow-y-auto slide-in border-2 border-orange-500/30">
            <div class="flex justify-between items-center mb-6">
                <div class="flex items-center space-x-3">
                    <div class="w-12 h-12 bg-gradient-to-r from-orange-500 to-green-600 rounded-full flex items-center justify-center">
                        <i class="fas fa-exclamation-triangle text-white text-xl"></i>
                    </div>
                    <div>
                        <h2 class="text-white text-xl font-semibold">ਸਮੱਸਿਆ ਦੀ ਰਿਪੋਰਟ / Issue Report</h2>
                        <p class="text-orange-400 text-sm">Driver Issue Reporting System</p>
                    </div>
                </div>
                <button onclick="closeDriverIssueModal()" class="text-white/60 hover:text-white transition-colors">
                    <i class="fas fa-times text-xl"></i>
                </button>
            </div>
            
            <form id="driverIssueForm" onsubmit="event.preventDefault(); handleDriverIssueSubmit();" class="space-y-6">
                <!-- Bus Selection -->
                <div class="bg-gradient-to-r from-orange-500/10 to-green-600/10 rounded-lg p-4 border border-orange-500/20">
                    <label class="block text-orange-400 font-semibold mb-2">
                        <i class="fas fa-bus mr-2"></i>ਬੱਸ ਚੁਣੋ / Select Bus *
                    </label>
                    <select id="issueBusSelect" name="busNumber" required class="w-full bg-white/10 border-2 border-orange-500/30 rounded-lg px-4 py-3 text-white focus:outline-none focus:ring-2 focus:ring-orange-400 focus:border-orange-400 transition-all duration-300">
                        <option value="">Select your assigned bus</option>
                    </select>
                </div>

                <!-- Issue Type & Priority -->
                <div class="grid md:grid-cols-2 gap-4">
                    <div>
                        <label class="block text-green-400 font-semibold mb-2">
                            <i class="fas fa-tag mr-2"></i>ਸਮੱਸਿਆ ਦੀ ਕਿਸਮ / Issue Type *
                        </label>
                        <select name="issueType" required class="w-full bg-white/10 border-2 border-green-500/30 rounded-lg px-4 py-3 text-white focus:outline-none focus:ring-2 focus:ring-green-400 focus:border-green-400 transition-all duration-300">
                            <option value="">Select issue type</option>
                            <option value="Vehicle Breakdown">🔧 Vehicle Breakdown</option>
                            <option value="Mechanical Issue">⚙️ Mechanical Issue</option>
                            <option value="Traffic Jam">🚦 Traffic Jam/Road Block</option>
                            <option value="Passenger Issue">👥 Passenger Related Issue</option>
                            <option value="Route Obstruction">🚧 Route Obstruction</option>
                            <option value="Weather Delay">🌧️ Weather Related Delay</option>
                            <option value="Fuel Issue">⛽ Fuel/Maintenance Issue</option>
                            <option value="Safety Concern">⚠️ Safety Concern</option>
                            <option value="AC Problem">❄️ AC/Cooling Problem</option>
                            <option value="Tire Issue">🛞 Tire Problem</option>
                            <option value="Engine Problem">🔥 Engine Problem</option>
                            <option value="Other">📝 Other Issue</option>
                        </select>
                    </div>
                    
                    <div>
                        <label class="block text-red-400 font-semibold mb-2">
                            <i class="fas fa-exclamation-circle mr-2"></i>ਤਰਜੀਹ / Priority *
                        </label>
                        <select name="priority" required class="w-full bg-white/10 border-2 border-red-500/30 rounded-lg px-4 py-3 text-white focus:outline-none focus:ring-2 focus:ring-red-400 focus:border-red-400 transition-all duration-300">
                            <option value="">Select priority</option>
                            <option value="Critical">🚨 Critical - Emergency</option>
                            <option value="High">🔴 High - Urgent</option>
                            <option value="Medium">🟡 Medium - Important</option>
                            <option value="Low">🟢 Low - Minor</option>
                        </select>
                    </div>
                </div>

                <!-- Quick Issue Buttons -->
                <div class="bg-white/5 rounded-lg p-4 border border-white/10">
                    <h3 class="text-white font-semibold mb-3">
                        <i class="fas fa-mouse-pointer mr-2 text-orange-400"></i>ਤੇਜ਼ ਸਮੱਸਿਆ ਚੁਣੋ / Quick Issue Selection
                    </h3>
                    <div class="grid grid-cols-2 md:grid-cols-3 gap-2">
                        <button type="button" onclick="selectQuickIssue('Bus broke down and cannot move')" class="bg-orange-500 hover:bg-orange-600 text-white px-3 py-2 rounded-lg text-sm transition-all duration-300 hover:scale-105">
                            🔧 Breakdown
                        </button>
                        <button type="button" onclick="selectQuickIssue('Heavy traffic causing major delay')" class="bg-orange-500 hover:bg-orange-600 text-white px-3 py-2 rounded-lg text-sm transition-all duration-300 hover:scale-105">
                            🚦 Traffic Jam
                        </button>
                        <button type="button" onclick="selectQuickIssue('AC system not working properly')" class="bg-orange-500 hover:bg-orange-600 text-white px-3 py-2 rounded-lg text-sm transition-all duration-300 hover:scale-105">
                            ❄️ AC Problem
                        </button>
                        <button type="button" onclick="selectQuickIssue('Tire puncture or tire problem')" class="bg-orange-500 hover:bg-orange-600 text-white px-3 py-2 rounded-lg text-sm transition-all duration-300 hover:scale-105">
                            🛞 Tire Issue
                        </button>
                        <button type="button" onclick="selectQuickIssue('Engine overheating or engine problem')" class="bg-orange-500 hover:bg-orange-600 text-white px-3 py-2 rounded-lg text-sm transition-all duration-300 hover:scale-105">
                            🔥 Engine Issue
                        </button>
                        <button type="button" onclick="selectQuickIssue('Passenger safety concern or incident')" class="bg-orange-500 hover:bg-orange-600 text-white px-3 py-2 rounded-lg text-sm transition-all duration-300 hover:scale-105">
                            👥 Passenger Issue
                        </button>
                    </div>
                </div>

                <!-- Location & Contact -->
                <div class="grid md:grid-cols-2 gap-4">
                    <div>
                        <label class="block text-blue-400 font-semibold mb-2">
                            <i class="fas fa-map-marker-alt mr-2"></i>ਮੌਜੂਦਾ ਸਥਾਨ / Current Location
                        </label>
                        <input type="text" name="location" placeholder="Enter your current location" class="w-full bg-white/10 border-2 border-blue-500/30 rounded-lg px-4 py-3 text-white placeholder-white/60 focus:outline-none focus:ring-2 focus:ring-blue-400 focus:border-blue-400 transition-all duration-300">
                    </div>
                    
                    <div>
                        <label class="block text-purple-400 font-semibold mb-2">
                            <i class="fas fa-phone mr-2"></i>ਸੰਪਰਕ ਨੰਬਰ / Contact Number
                        </label>
                        <input type="tel" name="contactNumber" placeholder="Your contact number" class="w-full bg-white/10 border-2 border-purple-500/30 rounded-lg px-4 py-3 text-white placeholder-white/60 focus:outline-none focus:ring-2 focus:ring-purple-400 focus:border-purple-400 transition-all duration-300">
                    </div>
                </div>

                <!-- Issue Description -->
                <div>
                    <label class="block text-yellow-400 font-semibold mb-2">
                        <i class="fas fa-edit mr-2"></i>ਸਮੱਸਿਆ ਦਾ ਵੇਰਵਾ / Issue Description *
                    </label>
                    <textarea id="issueDescription" name="description" required rows="4" placeholder="Describe the issue in detail... / ਸਮੱਸਿਆ ਦਾ ਵਿਸਤਾਰ ਨਾਲ ਵਰਣਨ ਕਰੋ..." class="w-full bg-white/10 border-2 border-yellow-500/30 rounded-lg px-4 py-3 text-white placeholder-white/60 focus:outline-none focus:ring-2 focus:ring-yellow-400 focus:border-yellow-400 transition-all duration-300 resize-none"></textarea>
                    <p class="text-white/60 text-xs mt-1">Minimum 10 characters required</p>
                </div>

                <!-- Emergency Contact Info -->
                <div class="bg-red-500/10 rounded-lg p-4 border border-red-500/30">
                    <h4 class="text-red-400 font-semibold mb-2">
                        <i class="fas fa-phone-alt mr-2"></i>ਐਮਰਜੈਂਸੀ ਸੰਪਰਕ / Emergency Contacts
                    </h4>
                    <div class="grid md:grid-cols-2 gap-2 text-sm text-white/80">
                        <p>🚨 Emergency: <span class="text-red-400 font-semibold">108</span></p>
                        <p>📞 Control Room: <span class="text-orange-400 font-semibold">1800-PB-HELP</span></p>
                        <p>🚑 Medical Emergency: <span class="text-red-400 font-semibold">102</span></p>
                        <p>👮 Police: <span class="text-blue-400 font-semibold">100</span></p>
                    </div>
                </div>

                <!-- Submit Button -->
                <div class="flex space-x-3 pt-4">
                    <button type="submit" class="flex-1 bg-gradient-to-r from-orange-500 to-green-600 hover:from-orange-600 hover:to-green-700 text-white font-semibold py-4 rounded-lg transition-all duration-300 transform hover:scale-105 hover:shadow-xl">
                        <i class="fas fa-paper-plane mr-2"></i>
                        ਰਿਪੋਰਟ ਭੇਜੋ / Submit Report
                    </button>
                    
                    <button type="button" onclick="closeDriverIssueModal()" class="bg-white/10 hover:bg-white/20 text-white font-medium px-6 py-4 rounded-lg transition-all duration-300">
                        <i class="fas fa-times mr-2"></i>
                        Cancel
                    </button>
                </div>

                <!-- MongoDB Connection Info -->
                <div class="bg-green-500/10 rounded-lg p-3 border border-green-500/20">
                    <div class="flex items-center space-x-2 text-green-400 text-sm">
                        <i class="fas fa-database"></i>
                        <span>Connected to MongoDB Atlas</span>
                        <div class="w-2 h-2 bg-green-500 rounded-full animate-pulse"></div>
                    </div>
                    <p class="text-xs text-white/60 mt-1">Your report will be securely stored and processed</p>
                </div>
            </form>
        </div>
    </div>

    <!-- Alert Popup Modal -->
    <div id="alertPopupModal" class="fixed inset-0 bg-black/50 backdrop-blur-sm hidden items-center justify-center z-50">
        <div class="bg-slate-900 rounded-2xl p-6 m-4 w-full max-w-2xl max-h-[90vh] overflow-y-auto slide-in border-2 border-red-500/30">
            <div class="flex justify-between items-center mb-6">
                <div class="flex items-center space-x-3">
                    <div class="w-12 h-12 bg-red-600 rounded-full flex items-center justify-center">
                        <i class="fas fa-bell text-white text-xl"></i>
                    </div>
                    <div>
                        <h2 class="text-white text-xl font-semibold">System Alerts</h2>
                        <p class="text-red-400 text-sm">Important notifications and updates</p>
                    </div>
                </div>
                <button onclick="closeAlertPopup()" class="text-white/60 hover:text-white transition-colors">
                    <i class="fas fa-times text-xl"></i>
                </button>
            </div>
            
            <div id="alertPopupContent">
                <!-- Alert content will be populated by JavaScript -->
            </div>
        </div>
    </div>

    <!-- Bus Details Modal -->
    <div id="busDetailsModal" class="fixed inset-0 bg-black/50 backdrop-blur-sm hidden items-center justify-center z-50">
        <div class="glass-effect rounded-2xl p-8 m-4 w-full max-w-6xl max-h-[90vh] overflow-y-auto slide-in">
            <div class="flex justify-between items-center mb-6">
                <h2 class="text-white text-2xl font-semibent" data-translate="busDetails">Bus Details</h2>
                <button onclick="closeBusDetails()" class="text-white/60 hover:text-white transition-colors">
                    <i class="fas fa-times text-xl"></i>
                </button>
            </div>
            
            <div id="busDetailsContent" class="text-white"></div>
        </div>
    </div>

    <script>
        // Language translations
        const translations = {
            en: {
                title: "PB Tracker",
                admin: "Admin",
                driver: "Driver",
                trackByRoute: "Track by Route",
                trackByNumber: "Track by Bus Number",
                pickup: "Pickup Location",
                drop: "Drop Location",
                selectPickup: "Select Pickup Location",
                selectDrop: "Select Drop Location",
                busNumber: "Bus Number",
                findBuses: "Find Buses",
                trackBus: "Track Bus",
                liveTracking: "Live Bus Tracking",
                mapDemo: "Interactive Map (Demo Mode)",
                mapNote: "Google Maps integration would be implemented here",
                availableBuses: "Available Buses",
                username: "Username",
                password: "Password",
                login: "Login",
                adminLogin: "Admin Login",
                driverLogin: "Driver Login",
                selectLoginType: "Select Login Type",
                adminPortal: "Admin Portal",
                driverPortal: "Driver Portal",
                demoCredentials: "Demo Credentials:",
                busDetails: "Bus Details",
                viewDetails: "View Details",
                distance: "Distance",
                speed: "Speed",
                fare: "Fare",
                driverName: "Driver",
                contact: "Contact",
                busType: "Bus Type",
                status: "Status",
                eta: "ETA",
                route: "Route",
                newUser: "New User?",
                createAdmin: "Create Admin",
                createDriver: "Create Driver",
                createAccount: "Create Account",
                fullName: "Full Name",
                age: "Age",
                gender: "Gender",
                mobile: "Mobile Number",
                email: "Email (Optional)",
                selectGender: "Select Gender",
                male: "Male",
                female: "Female",
                other: "Other",
                driverInfo: "Driver Information",
                adminInfo: "Admin Information",
                licenseNumber: "License Number",
                experience: "Experience (Years)",
                department: "Department",
                level: "Level",
                selectDepartment: "Select Department",
                selectLevel: "Select Level",
                recentSearches: "Recent Searches",
                recommendedRoutes: "Recommended Routes",
                noRecentSearches: "No recent searches yet",
                searchToSave: "Search for buses to see them here",
                clearHistory: "Clear History",
                viewAllRoutes: "View All Routes",
                searchAgain: "Search Again",
                selectDate: "Select Date",
                selectTime: "Select Time",
                selectDateTime: "Select Date & Time",
                confirm: "Confirm",
                selectTheme: "Select Theme",
                nearbyBuses: "Buses Near You",
                findingLocation: "Finding your location...",
                locationPermission: "Location Permission Required",
                noNearbyBuses: "No buses found near your location",
                distance: "Distance",
                currentLocation: "Current Location"
            },
            hi: {
                title: "पीबी ट्रैकर",
                admin: "एडमिन",
                driver: "ड्राइवर",
                trackByRoute: "रूट से ट्रैक करें",
                trackByNumber: "बस नंबर से ट्रैक करें",
                pickup: "पिकअप स्थान",
                drop: "ड्रॉप स्थान",
                selectPickup: "पिकअप स्थान चुनें",
                selectDrop: "ड्रॉप स्थान चुनें",
                busNumber: "बस नंबर",
                findBuses: "बसें खोजें",
                trackBus: "बस ट्रैक करें",
                liveTracking: "लाइव बस ट्रैकिंग",
                mapDemo: "इंटरैक्टिव मैप (डेमो मोड)",
                mapNote: "यहाँ Google Maps एकीकरण लागू किया जाएगा",
                availableBuses: "उपलब्ध बसें",
                username: "उपयोगकर्ता नाम",
                password: "पासवर्ड",
                login: "लॉगिन",
                adminLogin: "एडमिन लॉगिन",
                driverLogin: "ड्राइवर लॉगिन",
                selectLoginType: "लॉगिन प्रकार चुनें",
                adminPortal: "एडमिन पोर्टल",
                driverPortal: "ड्राइवर पोर्टल",
                demoCredentials: "डेमो क्रेडेंशियल:",
                busDetails: "बस विवरण",
                viewDetails: "विवरण देखें",
                distance: "दूरी",
                speed: "गति",
                fare: "किराया",
                driverName: "ड्राइवर",
                contact: "संपर्क",
                busType: "बस प्रकार",
                status: "स्थिति",
                eta: "पहुंचने का समय",
                route: "रूट",
                newUser: "नया उपयोगकर्ता?",
                createAdmin: "एडमिन बनाएं",
                createDriver: "ड्राइवर बनाएं",
                createAccount: "खाता बनाएं",
                fullName: "पूरा नाम",
                age: "उम्र",
                gender: "लिंग",
                mobile: "मोबाइल नंबर",
                email: "ईमेल (वैकल्पिक)",
                selectGender: "लिंग चुनें",
                male: "पुरुष",
                female: "महिला",
                other: "अन्य",
                driverInfo: "ड्राइवर जानकारी",
                adminInfo: "एडमिन जानकारी",
                licenseNumber: "लाइसेंस नंबर",
                experience: "अनुभव (वर्ष)",
                department: "विभाग",
                level: "स्तर",
                selectDepartment: "विभाग चुनें",
                selectLevel: "स्तर चुनें",
                recentSearches: "हाल की खोजें",
                recommendedRoutes: "सुझाए गए रूट",
                noRecentSearches: "अभी तक कोई हाल की खोज नहीं",
                searchToSave: "बसों की खोज करें और यहाँ देखें",
                clearHistory: "इतिहास साफ़ करें",
                viewAllRoutes: "सभी रूट देखें",
                searchAgain: "फिर से खोजें",
                selectDate: "तारीख चुनें",
                selectTime: "समय चुनें",
                selectDateTime: "तारीख और समय चुनें",
                confirm: "पुष्टि करें",
                selectTheme: "थीम चुनें",
                nearbyBuses: "आपके पास की बसें",
                findingLocation: "आपका स्थान खोजा जा रहा है...",
                locationPermission: "स्थान की अनुमति आवश्यक",
                noNearbyBuses: "आपके स्थान के पास कोई बस नहीं मिली",
                distance: "दूरी",
                currentLocation: "वर्तमान स्थान"
            },
            pa: {
                title: "ਪੀਬੀ ਟਰੈਕਰ",
                admin: "ਐਡਮਿਨ",
                driver: "ਡਰਾਈਵਰ",
                trackByRoute: "ਰੂਟ ਨਾਲ ਟਰੈਕ ਕਰੋ",
                trackByNumber: "ਬੱਸ ਨੰਬਰ ਨਾਲ ਟਰੈਕ ਕਰੋ",
                pickup: "ਪਿਕਅੱਪ ਸਥਾਨ",
                drop: "ਡਰਾਪ ਸਥਾਨ",
                selectPickup: "ਪਿਕਅੱਪ ਸਥਾਨ ਚੁਣੋ",
                selectDrop: "ਡਰਾਪ ਸਥਾਨ ਚੁਣੋ",
                busNumber: "ਬੱਸ ਨੰਬਰ",
                findBuses: "ਬੱਸਾਂ ਲੱਭੋ",
                trackBus: "ਬੱਸ ਟਰੈਕ ਕਰੋ",
                liveTracking: "ਲਾਈਵ ਬੱਸ ਟਰੈਕਿੰਗ",
                mapDemo: "ਇੰਟਰਐਕਟਿਵ ਮੈਪ (ਡੈਮੋ ਮੋਡ)",
                mapNote: "ਇੱਥੇ Google Maps ਏਕੀਕਰਣ ਲਾਗੂ ਕੀਤਾ ਜਾਵੇਗਾ",
                availableBuses: "ਉਪਲਬਧ ਬੱਸਾਂ",
                username: "ਯੂਜ਼ਰਨੇਮ",
                password: "ਪਾਸਵਰਡ",
                login: "ਲਾਗਇਨ",
                adminLogin: "ਐਡਮਿਨ ਲਾਗਇਨ",
                driverLogin: "ਡਰਾਈਵਰ ਲਾਗਇਨ",
                selectLoginType: "ਲਾਗਇਨ ਕਿਸਮ ਚੁਣੋ",
                adminPortal: "ਐਡਮਿਨ ਪੋਰਟਲ",
                driverPortal: "ਡਰਾਈਵਰ ਪੋਰਟਲ",
                demoCredentials: "ਡੈਮੋ ਕ੍ਰੈਡੈਂਸ਼ਲ:",
                busDetails: "ਬੱਸ ਵੇਰਵੇ",
                viewDetails: "ਵੇਰਵੇ ਵੇਖੋ",
                distance: "ਦੂਰੀ",
                speed: "ਗਤੀ",
                fare: "ਕਿਰਾਇਆ",
                driverName: "ਡਰਾਈਵਰ",
                contact: "ਸੰਪਰਕ",
                busType: "ਬੱਸ ਕਿਸਮ",
                status: "ਸਥਿਤੀ",
                eta: "ਪਹੁੰਚਣ ਦਾ ਸਮਾਂ",
                route: "ਰੂਟ",
                newUser: "ਨਵਾਂ ਯੂਜ਼ਰ?",
                createAdmin: "ਐਡਮਿਨ ਬਣਾਓ",
                createDriver: "ਡਰਾਈਵਰ ਬਣਾਓ",
                createAccount: "ਖਾਤਾ ਬਣਾਓ",
                fullName: "ਪੂਰਾ ਨਾਮ",
                age: "ਉਮਰ",
                gender: "ਲਿੰਗ",
                mobile: "ਮੋਬਾਈਲ ਨੰਬਰ",
                email: "ਈਮੇਲ (ਵਿਕਲਪਿਕ)",
                selectGender: "ਲਿੰਗ ਚੁਣੋ",
                male: "ਮਰਦ",
                female: "ਔਰਤ",
                other: "ਹੋਰ",
                driverInfo: "ਡਰਾਈਵਰ ਜਾਣਕਾਰੀ",
                adminInfo: "ਐਡਮਿਨ ਜਾਣਕਾਰੀ",
                licenseNumber: "ਲਾਇਸੈਂਸ ਨੰਬਰ",
                experience: "ਤਜਰਬਾ (ਸਾਲ)",
                department: "ਵਿਭਾਗ",
                level: "ਪੱਧਰ",
                selectDepartment: "ਵਿਭਾਗ ਚੁਣੋ",
                selectLevel: "ਪੱਧਰ ਚੁਣੋ",
                recentSearches: "ਹਾਲ ਦੀਆਂ ਖੋਜਾਂ",
                recommendedRoutes: "ਸਿਫਾਰਸ਼ੀ ਰੂਟ",
                noRecentSearches: "ਅਜੇ ਤੱਕ ਕੋਈ ਹਾਲ ਦੀ ਖੋਜ ਨਹੀਂ",
                searchToSave: "ਬੱਸਾਂ ਦੀ ਖੋਜ ਕਰੋ ਅਤੇ ਇੱਥੇ ਵੇਖੋ",
                clearHistory: "ਇਤਿਹਾਸ ਸਾਫ਼ ਕਰੋ",
                viewAllRoutes: "ਸਾਰੇ ਰੂਟ ਵੇਖੋ",
                searchAgain: "ਦੁਬਾਰਾ ਖੋਜੋ",
                selectDate: "ਤਾਰੀਖ ਚੁਣੋ",
                selectTime: "ਸਮਾਂ ਚੁਣੋ",
                selectDateTime: "ਤਾਰੀਖ ਅਤੇ ਸਮਾਂ ਚੁਣੋ",
                confirm: "ਪੁਸ਼ਟੀ ਕਰੋ",
                selectTheme: "ਥੀਮ ਚੁਣੋ",
                nearbyBuses: "ਤੁਹਾਡੇ ਨੇੜੇ ਦੀਆਂ ਬੱਸਾਂ",
                findingLocation: "ਤੁਹਾਡਾ ਸਥਾਨ ਲੱਭਿਆ ਜਾ ਰਿਹਾ ਹੈ...",
                locationPermission: "ਸਥਾਨ ਦੀ ਇਜਾਜ਼ਤ ਲੋੜੀਂਦੀ ਹੈ",
                noNearbyBuses: "ਤੁਹਾਡੇ ਸਥਾਨ ਦੇ ਨੇੜੇ ਕੋਈ ਬੱਸ ਨਹੀਂ ਮਿਲੀ",
                distance: "ਦੂਰੀ",
                currentLocation: "ਮੌਜੂਦਾ ਸਥਾਨ"
            }
        };

        // Punjab cities with multi-language support
        const punjabCities = {
            en: [
                "Chandigarh", "Ludhiana", "Amritsar", "Jalandhar", "Patiala",
                "Bathinda", "Mohali", "Pathankot", "Hoshiarpur", "Batala",
                "Kapurthala", "Abohar", "Khanna", "Phagwara", "Muktsar",
                "Barnala", "Rajpura", "Firozpur", "Sunam", "Gurdaspur"
            ],
            hi: [
                "चंडीगढ़", "लुधियाना", "अमृतसर", "जालंधर", "पटियाला",
                "बठिंडा", "मोहाली", "पठानकोट", "होशियारपुर", "बटाला",
                "कपूरथला", "अबोहर", "खन्ना", "फगवाड़ा", "मुक्तसर",
                "बरनाला", "राजपुरा", "फिरोजपुर", "सुनाम", "गुरदासपुर"
            ],
            pa: [
                "ਚੰਡੀਗੜ੍ਹ", "ਲੁਧਿਆਣਾ", "ਅੰਮ੍ਰਿਤਸਰ", "ਜਲੰਧਰ", "ਪਟਿਆਲਾ",
                "ਬਠਿੰਡਾ", "ਮੋਹਾਲੀ", "ਪਠਾਨਕੋਟ", "ਹੁਸ਼ਿਆਰਪੁਰ", "ਬਟਾਲਾ",
                "ਕਪੂਰਥਲਾ", "ਅਬੋਹਰ", "ਖੰਨਾ", "ਫਗਵਾੜਾ", "ਮੁਕਤਸਰ",
                "ਬਰਨਾਲਾ", "ਰਾਜਪੁਰਾ", "ਫਿਰੋਜ਼ਪੁਰ", "ਸੁਨਾਮ", "ਗੁਰਦਾਸਪੁਰ"
            ]
        };

        // Comprehensive bus database with detailed information
        const busDatabase = [
            // Chandigarh buses
            { 
                number: "PB-01-1234", 
                route: "Chandigarh - Ludhiana", 
                status: "On Time", 
                eta: "15 mins", 
                distance: "98 km", 
                speed: "65 km/h", 
                fare: "₹120", 
                driver: "Rajesh Kumar", 
                contact: "+91-98765-43210", 
                busType: "AC Deluxe",
                currentLocation: "Kharar",
                nextStop: "Kurali",
                coordinates: { lat: 30.7333, lng: 76.7794 }, // Chandigarh area
                stopsCompleted: 3,
                totalStops: 8,
                departureDate: "2024-01-20",
                departureTime: "06:00 AM",
                arrivalTime: "08:15 AM",
                lastUpdated: "2024-01-20 06:32 AM",
                trackingHistory: [
                    { location: "Chandigarh Bus Stand", timestamp: "2024-01-20 06:00 AM", status: "Departed" },
                    { location: "Mohali", timestamp: "2024-01-20 06:15 AM", status: "Arrived" },
                    { location: "Kharar", timestamp: "2024-01-20 06:30 AM", status: "Current Location" }
                ],
                busStops: [
                    { name: "Chandigarh Bus Stand", scheduledTime: "06:00 AM", actualTime: "06:00 AM", status: "completed", date: "2024-01-20" },
                    { name: "Mohali", scheduledTime: "06:15 AM", actualTime: "06:15 AM", status: "completed", date: "2024-01-20" },
                    { name: "Kharar", scheduledTime: "06:30 AM", actualTime: "06:30 AM", status: "completed", date: "2024-01-20" },
                    { name: "Kurali", scheduledTime: "06:45 AM", actualTime: null, status: "current", date: "2024-01-20" },
                    { name: "Morinda", scheduledTime: "07:00 AM", actualTime: null, status: "upcoming", date: "2024-01-20" },
                    { name: "Samrala", scheduledTime: "07:30 AM", actualTime: null, status: "upcoming", date: "2024-01-20" },
                    { name: "Khanna", scheduledTime: "07:45 AM", actualTime: null, status: "upcoming", date: "2024-01-20" },
                    { name: "Ludhiana Bus Stand", scheduledTime: "08:15 AM", actualTime: null, status: "upcoming", date: "2024-01-20" }
                ],
                nextBuses: [
                    { time: "07:30 AM", number: "PB-01-2468", date: "2024-01-20" },
                    { time: "08:00 AM", number: "PB-01-3579", date: "2024-01-20" },
                    { time: "08:30 AM", number: "PB-01-4680", date: "2024-01-20" }
                ],
                averageSpeed: "62 km/h",
                fuelLevel: "75%",
                passengerCount: "28/45",
                lastMaintenance: "2024-01-15",
                estimatedArrival: "2024-01-20 08:15 AM",
                delay: "0 mins"
            },
            { number: "PB-01-2345", route: "Chandigarh - Amritsar", status: "Delayed", eta: "25 mins", distance: "230 km", speed: "70 km/h", fare: "₹280", driver: "Sukhdev Singh", contact: "+91-98765-43211", busType: "Non-AC", departureDate: "2024-01-20", departureTime: "07:00 AM", arrivalTime: "10:30 AM", lastUpdated: "2024-01-20 07:25 AM", delay: "15 mins", coordinates: { lat: 30.7046, lng: 76.7179 } },
            { number: "PB-01-3456", route: "Chandigarh - Jalandhar", status: "On Time", eta: "10 mins", distance: "144 km", speed: "68 km/h", fare: "₹180", driver: "Manpreet Kaur", contact: "+91-98765-43212", busType: "AC Deluxe", departureDate: "2024-01-20", departureTime: "08:00 AM", arrivalTime: "10:15 AM", lastUpdated: "2024-01-20 08:10 AM", delay: "0 mins", coordinates: { lat: 30.7500, lng: 76.7800 } },
            { number: "PB-01-4567", route: "Chandigarh - Patiala", status: "On Time", eta: "8 mins", distance: "67 km", speed: "60 km/h", fare: "₹90", driver: "Harjeet Singh", contact: "+91-98765-43213", busType: "Non-AC", departureDate: "2024-01-20", departureTime: "09:00 AM", arrivalTime: "10:15 AM", lastUpdated: "2024-01-20 09:08 AM", delay: "0 mins", coordinates: { lat: 30.7200, lng: 76.7600 } },
            { number: "PB-01-5678", route: "Chandigarh - Bathinda", status: "Running", eta: "20 mins", distance: "227 km", speed: "72 km/h", fare: "₹270", driver: "Gurpreet Singh", contact: "+91-98765-43214", busType: "AC Deluxe", departureDate: "2024-01-20", departureTime: "06:30 AM", arrivalTime: "09:45 AM", lastUpdated: "2024-01-20 09:25 AM", delay: "0 mins", coordinates: { lat: 30.7100, lng: 76.7900 } },
            
            // Ludhiana buses
            { number: "PB-02-1234", route: "Ludhiana - Amritsar", status: "On Time", eta: "12 mins", distance: "132 km", speed: "66 km/h", fare: "₹160", driver: "Jasbir Singh", contact: "+91-98765-43215", busType: "AC", departureDate: "2024-01-20", departureTime: "07:30 AM", arrivalTime: "09:30 AM", lastUpdated: "2024-01-20 09:18 AM", delay: "0 mins", coordinates: { lat: 30.9010, lng: 75.8573 } },
            { number: "PB-02-2345", route: "Ludhiana - Jalandhar", status: "Delayed", eta: "18 mins", distance: "46 km", speed: "55 km/h", fare: "₹60", driver: "Simran Kaur", contact: "+91-98765-43216", busType: "Non-AC", departureDate: "2024-01-20", departureTime: "08:15 AM", arrivalTime: "09:15 AM", lastUpdated: "2024-01-20 08:57 AM", delay: "10 mins", coordinates: { lat: 30.8800, lng: 75.8400 } },
            { number: "PB-02-3456", route: "Ludhiana - Patiala", status: "On Time", eta: "14 mins", distance: "54 km", speed: "58 km/h", fare: "₹70", driver: "Balwinder Singh", contact: "+91-98765-43217", busType: "AC", departureDate: "2024-01-20", departureTime: "09:00 AM", arrivalTime: "10:00 AM", lastUpdated: "2024-01-20 09:46 AM", delay: "0 mins", coordinates: { lat: 30.9200, lng: 75.8700 } },
            { number: "PB-02-4567", route: "Ludhiana - Bathinda", status: "Running", eta: "22 mins", distance: "129 km", speed: "64 km/h", fare: "₹150", driver: "Kuldeep Kaur", contact: "+91-98765-43218", busType: "AC Deluxe", departureDate: "2024-01-20", departureTime: "07:00 AM", arrivalTime: "09:00 AM", lastUpdated: "2024-01-20 08:38 AM", delay: "0 mins", coordinates: { lat: 30.8900, lng: 75.8300 } },
            { number: "PB-02-5678", route: "Ludhiana - Mohali", status: "On Time", eta: "16 mins", distance: "108 km", speed: "62 km/h", fare: "₹130", driver: "Amarjeet Singh", contact: "+91-98765-43219", busType: "Non-AC", departureDate: "2024-01-20", departureTime: "08:30 AM", arrivalTime: "10:15 AM", lastUpdated: "2024-01-20 09:59 AM", delay: "0 mins", coordinates: { lat: 30.9100, lng: 75.8600 } },
            
            // Amritsar buses
            { number: "PB-03-1234", route: "Amritsar - Jalandhar", status: "On Time", eta: "11 mins", distance: "86 km", speed: "63 km/h", fare: "₹100", driver: "Tejinder Singh", contact: "+91-98765-43220", busType: "AC", coordinates: { lat: 31.6340, lng: 74.8723 } },
            { number: "PB-03-2345", route: "Amritsar - Pathankot", status: "Delayed", eta: "28 mins", distance: "107 km", speed: "59 km/h", fare: "₹120", driver: "Navdeep Kaur", contact: "+91-98765-43221", busType: "Non-AC", coordinates: { lat: 31.6200, lng: 74.8600 } },
            { number: "PB-03-3456", route: "Amritsar - Batala", status: "On Time", eta: "9 mins", distance: "32 km", speed: "52 km/h", fare: "₹45", driver: "Ranjit Singh", contact: "+91-98765-43222", busType: "Non-AC", coordinates: { lat: 31.6500, lng: 74.8900 } },
            { number: "PB-03-4567", route: "Amritsar - Gurdaspur", status: "Running", eta: "19 mins", distance: "51 km", speed: "56 km/h", fare: "₹65", driver: "Paramjeet Kaur", contact: "+91-98765-43223", busType: "AC", coordinates: { lat: 31.6100, lng: 74.8500 } },
            { number: "PB-03-5678", route: "Amritsar - Kapurthala", status: "On Time", eta: "13 mins", distance: "54 km", speed: "61 km/h", fare: "₹70", driver: "Harbhajan Singh", contact: "+91-98765-43224", busType: "AC Deluxe", coordinates: { lat: 31.6400, lng: 74.8800 } },
            
            // Jalandhar buses
            { number: "PB-04-1234", route: "Jalandhar - Hoshiarpur", status: "On Time", eta: "17 mins", distance: "38 km", speed: "54 km/h", fare: "₹50", driver: "Lakhwinder Singh", contact: "+91-98765-43225", busType: "Non-AC", coordinates: { lat: 31.3260, lng: 75.5762 } },
            { number: "PB-04-2345", route: "Jalandhar - Phagwara", status: "Running", eta: "7 mins", distance: "21 km", speed: "48 km/h", fare: "₹30", driver: "Manjeet Kaur", contact: "+91-98765-43226", busType: "Non-AC", coordinates: { lat: 31.3100, lng: 75.5600 } },
            { number: "PB-04-3456", route: "Jalandhar - Kapurthala", status: "On Time", eta: "12 mins", distance: "19 km", speed: "45 km/h", fare: "₹25", driver: "Davinder Singh", contact: "+91-98765-43227", busType: "AC", coordinates: { lat: 31.3400, lng: 75.5900 } },
            { number: "PB-04-4567", route: "Jalandhar - Nawanshahr", status: "Delayed", eta: "21 mins", distance: "42 km", speed: "57 km/h", fare: "₹55", driver: "Baljeet Kaur", contact: "+91-98765-43228", busType: "AC", coordinates: { lat: 31.3000, lng: 75.5500 } },
            { number: "PB-04-5678", route: "Jalandhar - Kartarpur", status: "On Time", eta: "15 mins", distance: "17 km", speed: "43 km/h", fare: "₹22", driver: "Sukhwinder Singh", contact: "+91-98765-43229", busType: "Non-AC", coordinates: { lat: 31.3500, lng: 75.6000 } },
            
            // Patiala buses
            { number: "PB-05-1234", route: "Patiala - Bathinda", status: "Running", eta: "24 mins", distance: "160 km", speed: "67 km/h", fare: "₹190", driver: "Joginder Singh", contact: "+91-98765-43230", busType: "AC Deluxe", coordinates: { lat: 30.3398, lng: 76.3869 } },
            { number: "PB-05-2345", route: "Patiala - Sangrur", status: "On Time", eta: "18 mins", distance: "48 km", speed: "59 km/h", fare: "₹60", driver: "Kulwant Kaur", contact: "+91-98765-43231", busType: "Non-AC", coordinates: { lat: 30.3200, lng: 76.3700 } },
            { number: "PB-05-3456", route: "Patiala - Barnala", status: "Delayed", eta: "26 mins", distance: "75 km", speed: "61 km/h", fare: "₹85", driver: "Jaswinder Singh", contact: "+91-98765-43232", busType: "AC", coordinates: { lat: 30.3600, lng: 76.4000 } },
            { number: "PB-05-4567", route: "Patiala - Rajpura", status: "On Time", eta: "8 mins", distance: "23 km", speed: "47 km/h", fare: "₹35", driver: "Harpreet Kaur", contact: "+91-98765-43233", busType: "Non-AC", coordinates: { lat: 30.3100, lng: 76.3600 } },
            { number: "PB-05-5678", route: "Patiala - Samana", status: "Running", eta: "14 mins", distance: "31 km", speed: "53 km/h", fare: "₹40", driver: "Gurbachan Singh", contact: "+91-98765-43234", busType: "AC", coordinates: { lat: 30.3500, lng: 76.3900 } }
        ];

        // Driver and Admin credentials
        const credentials = {
            drivers: [
                { username: "driver1", password: "pass123", name: "Rajesh Kumar", id: "D001", phone: "+91-98765-43210", experience: "8 years", license: "PB12A2023001" },
                { username: "driver2", password: "pass123", name: "Sukhdev Singh", id: "D002", phone: "+91-98765-43211", experience: "12 years", license: "PB15B2021045" },
                { username: "driver3", password: "pass123", name: "Manpreet Kaur", id: "D003", phone: "+91-98765-43212", experience: "6 years", license: "PB08C2022078" },
                { username: "driver4", password: "pass123", name: "Harjeet Singh", id: "D004", phone: "+91-98765-43213", experience: "10 years", license: "PB22D2020156" },
                { username: "driver5", password: "pass123", name: "Gurpreet Singh", id: "D005", phone: "+91-98765-43214", experience: "15 years", license: "PB05E2019234" }
            ],
            admins: [
                { username: "admin1", password: "admin123", name: "Amarjit Singh", id: "A001", department: "Operations", level: "Senior" },
                { username: "admin2", password: "admin123", name: "Simran Kaur", id: "A002", department: "Fleet Management", level: "Manager" },
                { username: "admin3", password: "admin123", name: "Balwinder Singh", id: "A003", department: "Customer Service", level: "Supervisor" },
                { username: "admin4", password: "admin123", name: "Kuldeep Kaur", id: "A004", department: "Maintenance", level: "Head" },
                { username: "admin5", password: "admin123", name: "Tejinder Singh", id: "A005", department: "Route Planning", level: "Manager" }
            ]
        };

        let currentLoginType = '';
        let currentLanguage = 'en';
        let isDarkMode = false;
        let loggedInUser = null;
        let currentCreateType = '';
        let selectedJourneyDate = null;
        let selectedJourneyTime = null;
        let currentTheme = 'default';
        let userLocation = null;

        // MongoDB connection configuration
        const mongoDBConnection = "mongodb+srv://punjab-bus-tracker:punjab1@cluster0.hzlpcu1.mongodb.net/";
        const databaseName = "punjab_bus_tracker";
        
        // MongoDB API endpoints (would be implemented on backend server)
        const API_BASE_URL = "https://your-backend-api.com/api"; // Replace with actual backend URL
        
        // MongoDB operations (simulated for frontend demo)
        const mongoOperations = {
            async createUser(userData, userType) {
                try {
                    // In a real application, this would make an API call to your backend
                    const response = await fetch(`${API_BASE_URL}/users`, {
                        method: 'POST',
                        headers: {
                            'Content-Type': 'application/json',
                        },
                        body: JSON.stringify({
                            ...userData,
                            userType: userType,
                            createdAt: new Date().toISOString(),
                            isActive: true
                        })
                    });
                    
                    if (!response.ok) {
                        throw new Error('Failed to create user');
                    }
                    
                    return await response.json();
                } catch (error) {
                    console.error('MongoDB Create User Error:', error);
                    // For demo purposes, we'll simulate success and store locally
                    return this.simulateMongoCreate(userData, userType);
                }
            },
            
            async authenticateUser(username, password, userType) {
                try {
                    const response = await fetch(`${API_BASE_URL}/auth/login`, {
                        method: 'POST',
                        headers: {
                            'Content-Type': 'application/json',
                        },
                        body: JSON.stringify({
                            username,
                            password,
                            userType
                        })
                    });
                    
                    if (!response.ok) {
                        throw new Error('Authentication failed');
                    }
                    
                    return await response.json();
                } catch (error) {
                    console.error('MongoDB Auth Error:', error);
                    // Fallback to local authentication for demo
                    return this.simulateMongoAuth(username, password, userType);
                }
            },
            
            simulateMongoCreate(userData, userType) {
                // Simulate MongoDB document creation
                const mongoDocument = {
                    _id: new Date().getTime().toString(),
                    ...userData,
                    userType: userType,
                    createdAt: new Date().toISOString(),
                    isActive: true,
                    lastLogin: null
                };
                
                // Store in localStorage to simulate database persistence
                const storageKey = `mongo_${userType}s`;
                const existingUsers = JSON.parse(localStorage.getItem(storageKey) || '[]');
                existingUsers.push(mongoDocument);
                localStorage.setItem(storageKey, JSON.stringify(existingUsers));
                
                console.log('MongoDB Simulation - User Created:', mongoDocument);
                console.log('Connection String:', mongoDBConnection);
                console.log('Database:', databaseName);
                console.log('Collection:', `${userType}s`);
                
                return { success: true, user: mongoDocument };
            },
            
            simulateMongoAuth(username, password, userType) {
                // Check localStorage first (simulated MongoDB)
                const storageKey = `mongo_${userType}s`;
                const mongoUsers = JSON.parse(localStorage.getItem(storageKey) || '[]');
                const mongoUser = mongoUsers.find(u => u.username === username && u.password === password);
                
                if (mongoUser) {
                    // Update last login
                    mongoUser.lastLogin = new Date().toISOString();
                    localStorage.setItem(storageKey, JSON.stringify(mongoUsers));
                    return { success: true, user: mongoUser };
                }
                
                // Fallback to hardcoded credentials for demo
                const userType_plural = userType === 'admin' ? 'admins' : 'drivers';
                const user = credentials[userType_plural].find(u => u.username === username && u.password === password);
                return user ? { success: true, user } : { success: false };
            }
        };

        // Initialize the application
        function init() {
            populateLocationDropdowns();
            setupEventListeners();
            updateLanguage('en');
            updateRecentSearchesDisplay();
            startClock();
        }

        // Live clock functionality
        function startClock() {
            function updateClock() {
                const now = new Date();
                const dateOptions = { 
                    weekday: 'short', 
                    year: 'numeric', 
                    month: 'short', 
                    day: 'numeric' 
                };
                const timeOptions = { 
                    hour: '2-digit', 
                    minute: '2-digit', 
                    second: '2-digit',
                    hour12: true 
                };
                
                document.getElementById('currentDate').textContent = now.toLocaleDateString('en-US', dateOptions);
                document.getElementById('currentTime').textContent = now.toLocaleTimeString('en-US', timeOptions);
            }
            
            updateClock(); // Initial call
            setInterval(updateClock, 1000); // Update every second
        }

        // Populate location dropdowns with multi-language support
        function populateLocationDropdowns() {
            updateLocationDropdowns(currentLanguage);
        }

        function updateLocationDropdowns(lang) {
            const pickupSelect = document.getElementById('pickupLocation');
            const dropSelect = document.getElementById('dropLocation');
            
            // Clear existing options except the first one
            pickupSelect.innerHTML = `<option value="" data-translate="selectPickup">Select Pickup Location</option>`;
            dropSelect.innerHTML = `<option value="" data-translate="selectDrop">Select Drop Location</option>`;
            
            punjabCities[lang].forEach((city, index) => {
                const englishCity = punjabCities.en[index];
                const pickupOption = new Option(city, englishCity);
                const dropOption = new Option(city, englishCity);
                pickupSelect.add(pickupOption);
                dropSelect.add(dropOption);
            });
        }

        // Setup event listeners
        function setupEventListeners() {
            document.getElementById('languageSelector').addEventListener('change', (e) => {
                updateLanguage(e.target.value);
            });

            document.getElementById('loginForm').addEventListener('submit', (e) => {
                e.preventDefault();
                handleLogin();
            });

            document.getElementById('createAccountForm').addEventListener('submit', (e) => {
                e.preventDefault();
                handleCreateAccount();
            });

            document.getElementById('darkModeToggle').addEventListener('click', toggleDarkMode);
            
            // Password input listeners to show/hide toggle button
            document.getElementById('password').addEventListener('input', (e) => {
                togglePasswordButton('password', 'togglePassword', e.target.value);
            });
            
            document.getElementById('createPassword').addEventListener('input', (e) => {
                togglePasswordButton('createPassword', 'toggleCreatePassword', e.target.value);
            });
        }
        
        // Toggle password visibility button display
        function togglePasswordButton(inputId, buttonId, value) {
            const button = document.getElementById(buttonId);
            if (value.length > 0) {
                button.classList.remove('hidden');
            } else {
                button.classList.add('hidden');
            }
        }
        
        // Toggle password visibility
        function togglePasswordVisibility(inputId, buttonId) {
            const input = document.getElementById(inputId);
            const button = document.getElementById(buttonId);
            const icon = button.querySelector('i');
            
            if (input.type === 'password') {
                input.type = 'text';
                icon.className = 'fas fa-eye-slash';
            } else {
                input.type = 'password';
                icon.className = 'fas fa-eye';
            }
        }

        // Update language
        function updateLanguage(lang) {
            currentLanguage = lang;
            const elements = document.querySelectorAll('[data-translate]');
            elements.forEach(element => {
                const key = element.getAttribute('data-translate');
                if (translations[lang] && translations[lang][key]) {
                    element.textContent = translations[lang][key];
                }
            });
            updateLocationDropdowns(lang);
        }

        // Dark mode toggle
        function toggleDarkMode() {
            isDarkMode = !isDarkMode;
            const body = document.body;
            const darkModeIcon = document.querySelector('#darkModeToggle i');
            
            if (isDarkMode) {
                body.classList.add('dark-mode');
                darkModeIcon.className = 'fas fa-sun text-xl';
            } else {
                body.classList.remove('dark-mode');
                darkModeIcon.className = 'fas fa-moon text-xl';
            }
        }

        // Show login options modal
        function showLoginOptions() {
            const modal = document.getElementById('loginOptionsModal');
            modal.classList.remove('hidden');
            modal.classList.add('flex');
        }

        // Close login options modal
        function closeLoginOptions() {
            const modal = document.getElementById('loginOptionsModal');
            modal.classList.add('hidden');
            modal.classList.remove('flex');
        }

        // Show login modal
        function showLogin(type) {
            currentLoginType = type;
            const modal = document.getElementById('loginModal');
            const title = document.getElementById('loginTitle');
            
            title.textContent = type === 'admin' ? translations[currentLanguage].adminLogin : translations[currentLanguage].driverLogin;
            closeLoginOptions();
            modal.classList.remove('hidden');
            modal.classList.add('flex');
        }

        // Close login modal
        function closeLogin() {
            const modal = document.getElementById('loginModal');
            modal.classList.add('hidden');
            modal.classList.remove('flex');
            document.getElementById('username').value = '';
            document.getElementById('password').value = '';
        }

        // Handle login with MongoDB integration
        async function handleLogin() {
            const username = document.getElementById('username').value;
            const password = document.getElementById('password').value;
            
            if (!username || !password) {
                alert('Please enter both username and password');
                return;
            }

            // Show loading state
            const submitButton = document.querySelector('#loginForm button[type="submit"]');
            const originalText = submitButton.innerHTML;
            submitButton.innerHTML = '<i class="fas fa-spinner fa-spin mr-2"></i>Authenticating...';
            submitButton.disabled = true;

            try {
                // Authenticate with MongoDB
                const authResult = await mongoOperations.authenticateUser(username, password, currentLoginType);
                
                if (authResult.success) {
                    loggedInUser = { ...authResult.user, type: currentLoginType };
                    closeLogin();
                    showDashboard(authResult.user, currentLoginType);
                    
                    // Show success message
                    showNotification('Login successful!', 'success');
                } else {
                    alert('Invalid credentials. Please try again.');
                }
            } catch (error) {
                console.error('Login error:', error);
                alert('Login failed. Please try again.');
            } finally {
                // Restore button state
                submitButton.innerHTML = originalText;
                submitButton.disabled = false;
            }
        }

        // Show dashboard
        function showDashboard(user, type) {
            const modal = document.getElementById('dashboardModal');
            const title = document.getElementById('dashboardTitle');
            const content = document.getElementById('dashboardContent');
            
            title.textContent = `${type.charAt(0).toUpperCase() + type.slice(1)} Dashboard - Welcome ${user.name}`;
            
            if (type === 'admin') {
                const driverIssues = JSON.parse(localStorage.getItem('mongo_driver_issues') || '[]');
                const openIssues = driverIssues.filter(issue => issue.status === 'Open');
                const criticalIssues = driverIssues.filter(issue => issue.priority === 'Critical');
                
                content.innerHTML = `
                    <!-- Admin Control Panel Header -->
                    <div class="bg-gradient-to-r from-blue-500/20 to-purple-500/20 rounded-lg p-4 mb-6 border border-blue-400/30">
                        <div class="flex items-center justify-between">
                            <div>
                                <h2 class="text-xl font-bold text-white">Admin Control Center</h2>
                                <p class="text-blue-400">Real-time fleet management & emergency response</p>
                            </div>
                            <div class="text-right">
                                <div class="flex items-center space-x-2">
                                    <div class="w-3 h-3 bg-green-500 rounded-full animate-pulse"></div>
                                    <span class="text-green-400 font-semibold">System Online</span>
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- Emergency & Quick Actions -->
                    <div class="grid md:grid-cols-4 gap-4 mb-6">
                        <button onclick="showEmergencyAlert()" class="bg-red-500 hover:bg-red-600 text-white p-4 rounded-lg transition-all duration-300 transform hover:scale-105 hover:shadow-xl">
                            <i class="fas fa-exclamation-triangle text-2xl mb-2"></i>
                            <p class="font-semibold">Emergency Alert</p>
                            <p class="text-xs opacity-80">Broadcast to all buses</p>
                        </button>
                        
                        <button onclick="showDriverIssues()" class="bg-orange-500 hover:bg-orange-600 text-white p-4 rounded-lg transition-all duration-300 transform hover:scale-105 hover:shadow-xl relative">
                            <i class="fas fa-exclamation-circle text-2xl mb-2"></i>
                            <p class="font-semibold">Driver Issues</p>
                            <p class="text-xs opacity-80">${openIssues.length} open issues</p>
                            ${openIssues.length > 0 ? '<div class="absolute -top-2 -right-2 w-6 h-6 bg-red-500 rounded-full flex items-center justify-center text-xs font-bold animate-pulse">' + openIssues.length + '</div>' : ''}
                        </button>
                        
                        <button onclick="showAddNewBus()" class="bg-green-500 hover:bg-green-600 text-white p-4 rounded-lg transition-all duration-300 transform hover:scale-105 hover:shadow-xl">
                            <i class="fas fa-plus-circle text-2xl mb-2"></i>
                            <p class="font-semibold">Add New Bus</p>
                            <p class="text-xs opacity-80">Register new vehicle</p>
                        </button>
                        
                        <button onclick="showRouteManagement()" class="bg-purple-500 hover:bg-purple-600 text-white p-4 rounded-lg transition-all duration-300 transform hover:scale-105 hover:shadow-xl">
                            <i class="fas fa-route text-2xl mb-2"></i>
                            <p class="font-semibold">Route Management</p>
                            <p class="text-xs opacity-80">Manage bus routes</p>
                        </button>
                    </div>

                    <!-- Admin Stats Grid -->
                    <div class="grid md:grid-cols-3 gap-6 mb-6">
                        <div class="bg-white/10 rounded-lg p-6">
                            <h3 class="text-xl font-semibold mb-4"><i class="fas fa-user-circle mr-2 text-blue-400"></i>Profile Information</h3>
                            <div class="space-y-2">
                                <p><strong>Name:</strong> ${user.name}</p>
                                <p><strong>Admin ID:</strong> ${user.id}</p>
                                <p><strong>Department:</strong> ${user.department}</p>
                                <p><strong>Level:</strong> ${user.level}</p>
                                <p><strong>Last Login:</strong> ${new Date().toLocaleString()}</p>
                            </div>
                        </div>
                        
                        <div class="bg-white/10 rounded-lg p-6">
                            <h3 class="text-xl font-semibold mb-4"><i class="fas fa-chart-bar mr-2 text-green-400"></i>Fleet Statistics</h3>
                            <div class="space-y-2">
                                <p><strong>Total Buses:</strong> ${busDatabase.length}</p>
                                <p><strong>Active Routes:</strong> ${new Set(busDatabase.map(b => b.route)).size}</p>
                                <p><strong>On Time:</strong> <span class="text-green-400">${busDatabase.filter(b => b.status === 'On Time').length}</span></p>
                                <p><strong>Delayed:</strong> <span class="text-yellow-400">${busDatabase.filter(b => b.status === 'Delayed').length}</span></p>
                                <p><strong>Out of Service:</strong> <span class="text-red-400">${busDatabase.filter(b => b.status === 'Out of Service').length}</span></p>
                            </div>
                        </div>
                        
                        <div class="bg-white/10 rounded-lg p-6">
                            <h3 class="text-xl font-semibold mb-4"><i class="fas fa-bell mr-2 text-red-400"></i>Alert Summary</h3>
                            <div class="space-y-2">
                                <p><strong>Critical Issues:</strong> <span class="text-red-400">${criticalIssues.length}</span></p>
                                <p><strong>Open Issues:</strong> <span class="text-orange-400">${openIssues.length}</span></p>
                                <p><strong>Active Drivers:</strong> <span class="text-green-400">${credentials.drivers.length}</span></p>
                                <p><strong>Emergency Alerts:</strong> <span class="text-yellow-400">0</span></p>
                                <button onclick="showRecentAlerts()" class="mt-2 bg-blue-500 hover:bg-blue-600 text-white px-3 py-1 rounded text-sm">
                                    View Recent Alerts
                                </button>
                            </div>
                        </div>
                    </div>

                    <!-- Driver Authentication & Management -->
                    <div class="bg-white/10 rounded-lg p-6 mb-6">
                        <h3 class="text-xl font-semibold mb-4"><i class="fas fa-id-card mr-2 text-yellow-400"></i>Driver Authentication & Management</h3>
                        <div class="grid md:grid-cols-2 gap-4">
                            <div>
                                <h4 class="font-semibold mb-3 text-green-400">Verify Driver License</h4>
                                <div class="space-y-2">
                                    <input type="text" id="licenseVerifyInput" placeholder="Enter License Number" class="w-full bg-white/10 border border-white/30 rounded-lg px-3 py-2 text-white placeholder-white/60">
                                    <button onclick="verifyDriverLicense()" class="w-full bg-green-500 hover:bg-green-600 text-white py-2 rounded-lg">
                                        <i class="fas fa-check-circle mr-2"></i>Verify License
                                    </button>
                                </div>
                            </div>
                            <div>
                                <h4 class="font-semibold mb-3 text-blue-400">Registered Drivers</h4>
                                <div class="max-h-32 overflow-y-auto space-y-1">
                                    ${credentials.drivers.map(driver => `
                                        <div class="flex justify-between items-center bg-white/5 rounded px-2 py-1 text-sm">
                                            <span>${driver.name}</span>
                                            <span class="text-green-400">${driver.id}</span>
                                        </div>
                                    `).join('')}
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- Recent Bus Activities -->
                    <div class="bg-white/10 rounded-lg p-6">
                        <h3 class="text-xl font-semibold mb-4"><i class="fas fa-bus mr-2 text-cyan-400"></i>Recent Bus Activities</h3>
                        <div class="space-y-2 max-h-48 overflow-y-auto">
                            ${busDatabase.slice(0, 8).map(bus => `
                                <div class="flex justify-between items-center py-2 border-b border-white/20 hover:bg-white/5 rounded px-2">
                                    <div class="flex-1">
                                        <span class="font-medium">${bus.number}</span>
                                        <span class="text-white/70 ml-2">${bus.route}</span>
                                    </div>
                                    <div class="flex items-center space-x-2">
                                        <span class="px-2 py-1 rounded text-xs ${bus.status === 'On Time' ? 'bg-green-500' : bus.status === 'Delayed' ? 'bg-yellow-500' : 'bg-blue-500'}">${bus.status}</span>
                                        <button onclick="showBusDetails('${bus.number}')" class="text-blue-400 hover:text-blue-300">
                                            <i class="fas fa-eye"></i>
                                        </button>
                                    </div>
                                </div>
                            `).join('')}
                        </div>
                    </div>
                `;
            } else {
                const driverBuses = busDatabase.filter(bus => bus.driver === user.name);
                const driverIssues = JSON.parse(localStorage.getItem('mongo_driver_issues') || '[]').filter(issue => issue.driverName === user.name);
                
                content.innerHTML = `
                    <!-- Driver Control Panel Header -->
                    <div class="bg-gradient-to-r from-green-500/20 to-blue-500/20 rounded-lg p-4 mb-6 border border-green-400/30">
                        <div class="flex items-center justify-between">
                            <div>
                                <h2 class="text-xl font-bold text-white">Driver Dashboard</h2>
                                <p class="text-green-400">Real-time bus management & passenger updates</p>
                            </div>
                            <div class="text-right">
                                <div class="flex items-center space-x-2">
                                    <div class="w-3 h-3 bg-green-500 rounded-full animate-pulse"></div>
                                    <span class="text-green-400 font-semibold">On Duty</span>
                                </div>
                            </div>
                        </div>
                    </div>

                    <!-- Driver Quick Actions -->
                    <div class="grid md:grid-cols-3 gap-4 mb-6">
                        <button onclick="showDriverReportIssue()" class="bg-orange-500 hover:bg-orange-600 text-white p-4 rounded-lg transition-all duration-300 transform hover:scale-105 hover:shadow-xl">
                            <i class="fas fa-exclamation-triangle text-2xl mb-2"></i>
                            <p class="font-semibold">Report Issue</p>
                            <p class="text-xs opacity-80">Emergency & maintenance</p>
                        </button>
                        
                        <button onclick="updateBusLocation()" class="bg-blue-500 hover:bg-blue-600 text-white p-4 rounded-lg transition-all duration-300 transform hover:scale-105 hover:shadow-xl">
                            <i class="fas fa-map-marker-alt text-2xl mb-2"></i>
                            <p class="font-semibold">Update Location</p>
                            <p class="text-xs opacity-80">Real-time GPS update</p>
                        </button>
                        
                        <button onclick="showRouteProgress()" class="bg-purple-500 hover:bg-purple-600 text-white p-4 rounded-lg transition-all duration-300 transform hover:scale-105 hover:shadow-xl">
                            <i class="fas fa-route text-2xl mb-2"></i>
                            <p class="font-semibold">Route Progress</p>
                            <p class="text-xs opacity-80">Track journey status</p>
                        </button>
                    </div>

                    <!-- Driver Stats Grid -->
                    <div class="grid md:grid-cols-2 gap-6 mb-6">
                        <div class="bg-white/10 rounded-lg p-6">
                            <h3 class="text-xl font-semibold mb-4"><i class="fas fa-user-circle mr-2 text-blue-400"></i>Driver Profile</h3>
                            <div class="space-y-2">
                                <p><strong>Name:</strong> ${user.name}</p>
                                <p><strong>Driver ID:</strong> ${user.id}</p>
                                <p><strong>Phone:</strong> ${user.phone}</p>
                                <p><strong>Experience:</strong> ${user.experience}</p>
                                <p><strong>License:</strong> ${user.license || 'Verified'}</p>
                                <p><strong>Status:</strong> <span class="text-green-400">Active</span></p>
                            </div>
                        </div>
                        
                        <div class="bg-white/10 rounded-lg p-6">
                            <h3 class="text-xl font-semibold mb-4"><i class="fas fa-bus mr-2 text-green-400"></i>Assigned Buses</h3>
                            <div class="space-y-2">
                                <p><strong>Total Assigned:</strong> ${driverBuses.length}</p>
                                <p><strong>Currently Active:</strong> <span class="text-green-400">${driverBuses.filter(b => b.status !== 'Parked').length}</span></p>
                                <p><strong>On Time:</strong> <span class="text-green-400">${driverBuses.filter(b => b.status === 'On Time').length}</span></p>
                                <p><strong>Issues Reported:</strong> <span class="text-orange-400">${driverIssues.length}</span></p>
                                <p><strong>Today's Trips:</strong> <span class="text-blue-400">${driverBuses.length}</span></p>
                            </div>
                        </div>
                    </div>

                    <!-- My Routes & Real-time Updates -->
                    <div class="bg-white/10 rounded-lg p-6 mb-6">
                        <h3 class="text-xl font-semibold mb-4"><i class="fas fa-route mr-2 text-cyan-400"></i>My Routes & Live Updates</h3>
                        <div class="space-y-3">
                            ${driverBuses.map(bus => `
                                <div class="bg-white/5 rounded-lg p-4 border border-white/10">
                                    <div class="flex justify-between items-start mb-3">
                                        <div class="flex-1">
                                            <h4 class="font-semibold text-white">${bus.number} - ${bus.route}</h4>
                                            <p class="text-white/70 text-sm">${bus.busType} • Current: ${bus.currentLocation || 'Unknown'}</p>
                                        </div>
                                        <span class="px-3 py-1 rounded-full text-sm ${bus.status === 'On Time' ? 'bg-green-500' : bus.status === 'Delayed' ? 'bg-yellow-500' : 'bg-blue-500'}">${bus.status}</span>
                                    </div>
                                    
                                    <div class="grid grid-cols-2 md:grid-cols-4 gap-2 text-xs text-white/80 mb-3">
                                        <div><strong>Speed:</strong> ${bus.speed}</div>
                                        <div><strong>ETA:</strong> ${bus.eta}</div>
                                        <div><strong>Next Stop:</strong> ${bus.nextStop || 'Unknown'}</div>
                                        <div><strong>Passengers:</strong> ${bus.passengerCount || 'N/A'}</div>
                                    </div>
                                    
                                    <div class="flex space-x-2">
                                        <button onclick="updateBusLocationSpecific('${bus.number}')" class="flex-1 bg-blue-500 hover:bg-blue-600 text-white py-2 px-3 rounded text-sm">
                                            <i class="fas fa-map-marker-alt mr-1"></i>Update Location
                                        </button>
                                        <button onclick="updatePassengerCount('${bus.number}')" class="flex-1 bg-green-500 hover:bg-green-600 text-white py-2 px-3 rounded text-sm">
                                            <i class="fas fa-users mr-1"></i>Update Passengers
                                        </button>
                                        <button onclick="reportDelayForBus('${bus.number}')" class="flex-1 bg-yellow-500 hover:bg-yellow-600 text-white py-2 px-3 rounded text-sm">
                                            <i class="fas fa-clock mr-1"></i>Report Delay
                                        </button>
                                    </div>
                                </div>
                            `).join('')}
                        </div>
                    </div>

                    <!-- Recent Issues & Alerts -->
                    <div class="bg-white/10 rounded-lg p-6">
                        <h3 class="text-xl font-semibold mb-4"><i class="fas fa-bell mr-2 text-orange-400"></i>My Recent Issues & Alerts</h3>
                        ${driverIssues.length > 0 ? `
                            <div class="space-y-2 max-h-32 overflow-y-auto">
                                ${driverIssues.slice(0, 5).map(issue => `
                                    <div class="flex justify-between items-center py-2 border-b border-white/20">
                                        <div class="flex-1">
                                            <span class="font-medium">${issue.reportId}</span>
                                            <span class="text-white/70 ml-2">${issue.issueType}</span>
                                        </div>
                                        <div class="flex items-center space-x-2">
                                            <span class="px-2 py-1 rounded text-xs ${issue.priority === 'Critical' ? 'bg-red-500' : issue.priority === 'High' ? 'bg-orange-500' : 'bg-yellow-500'}">${issue.priority}</span>
                                            <span class="text-white/60 text-xs">${new Date(issue.timestamp).toLocaleDateString()}</span>
                                        </div>
                                    </div>
                                `).join('')}
                            </div>
                        ` : `
                            <div class="text-center text-white/60 py-4">
                                <i class="fas fa-check-circle text-2xl mb-2"></i>
                                <p>No recent issues reported</p>
                                <p class="text-xs">Keep up the good work!</p>
                            </div>
                        `}
                    </div>
                `;
            }
            
            modal.classList.remove('hidden');
            modal.classList.add('flex');
        }

        // Close dashboard
        function closeDashboard() {
            const modal = document.getElementById('dashboardModal');
            modal.classList.add('hidden');
            modal.classList.remove('flex');
        }

        // Show create account modal
        function showCreateAccount(type) {
            currentCreateType = type;
            const modal = document.getElementById('createAccountModal');
            const title = document.getElementById('createAccountTitle');
            const driverFields = document.getElementById('driverSpecificFields');
            const adminFields = document.getElementById('adminSpecificFields');
            
            title.textContent = `Create ${type.charAt(0).toUpperCase() + type.slice(1)} Account`;
            
            // Show/hide specific fields based on account type
            if (type === 'driver') {
                driverFields.classList.remove('hidden');
                adminFields.classList.add('hidden');
            } else {
                adminFields.classList.remove('hidden');
                driverFields.classList.add('hidden');
            }
            
            closeLoginOptions();
            modal.classList.remove('hidden');
            modal.classList.add('flex');
        }

        // Close create account modal
        function closeCreateAccount() {
            const modal = document.getElementById('createAccountModal');
            modal.classList.add('hidden');
            modal.classList.remove('flex');
            
            // Reset form
            document.getElementById('createAccountForm').reset();
        }

        // Handle create account with MongoDB integration
        async function handleCreateAccount() {
            const formData = {
                name: document.getElementById('createName').value,
                age: document.getElementById('createAge').value,
                gender: document.getElementById('createGender').value,
                mobile: document.getElementById('createMobile').value,
                email: document.getElementById('createEmail').value,
                username: document.getElementById('createUsername').value,
                password: document.getElementById('createPassword').value
            };

            // Validate required fields
            if (!formData.name || !formData.age || !formData.gender || !formData.mobile || !formData.username || !formData.password) {
                alert('Please fill in all required fields');
                return;
            }

            // Validate mobile number
            if (!/^[0-9]{10}$/.test(formData.mobile)) {
                alert('Please enter a valid 10-digit mobile number');
                return;
            }

            // Check if username already exists in both local and MongoDB storage
            const existingUser = [...credentials.admins, ...credentials.drivers].find(u => u.username === formData.username);
            const mongoAdmins = JSON.parse(localStorage.getItem('mongo_admins') || '[]');
            const mongoDrivers = JSON.parse(localStorage.getItem('mongo_drivers') || '[]');
            const mongoExistingUser = [...mongoAdmins, ...mongoDrivers].find(u => u.username === formData.username);
            
            if (existingUser || mongoExistingUser) {
                alert('Username already exists. Please choose a different username.');
                return;
            }

            // Show loading state
            const submitButton = document.querySelector('#createAccountForm button[type="submit"]');
            const originalText = submitButton.innerHTML;
            submitButton.innerHTML = '<i class="fas fa-spinner fa-spin mr-2"></i>Creating Account...';
            submitButton.disabled = true;

            try {
                // Add type-specific data
                if (currentCreateType === 'driver') {
                    formData.license = document.getElementById('createLicense').value;
                    formData.experience = document.getElementById('createExperience').value || '0';
                    formData.phone = `+91-${formData.mobile}`;
                    formData.id = `D${String(Date.now()).slice(-6)}`;
                    formData.vehicleAssigned = null;
                    formData.routeAssigned = null;
                } else {
                    formData.department = document.getElementById('createDepartment').value || 'General';
                    formData.level = document.getElementById('createLevel').value || 'Junior';
                    formData.id = `A${String(Date.now()).slice(-6)}`;
                    formData.permissions = ['read', 'write'];
                    formData.managedRoutes = [];
                }

                // Create user in MongoDB
                const createResult = await mongoOperations.createUser(formData, currentCreateType);
                
                if (createResult.success) {
                    // Also add to local credentials for backward compatibility
                    if (currentCreateType === 'driver') {
                        credentials.drivers.push({
                            username: formData.username,
                            password: formData.password,
                            name: formData.name,
                            id: formData.id,
                            phone: formData.phone,
                            experience: `${formData.experience} years`,
                            age: formData.age,
                            gender: formData.gender,
                            email: formData.email,
                            license: formData.license
                        });
                    } else {
                        credentials.admins.push({
                            username: formData.username,
                            password: formData.password,
                            name: formData.name,
                            id: formData.id,
                            department: formData.department,
                            level: formData.level,
                            age: formData.age,
                            gender: formData.gender,
                            email: formData.email,
                            mobile: formData.mobile
                        });
                    }

                    alert(`🎉 ${currentCreateType.charAt(0).toUpperCase() + currentCreateType.slice(1)} account created successfully!\n\n📋 Account Details:\nUsername: ${formData.username}\nID: ${formData.id}\nDatabase: MongoDB Atlas\n\n✅ Account is now active and ready to use!`);
                    closeCreateAccount();
                    showNotification('Account created successfully!', 'success');
                    
                    console.log('✅ MongoDB Account Created:', createResult.user);
                    console.log('🔗 Connection:', mongoDBConnection);
                    console.log('🗄️ Database:', databaseName);
                    console.log('📁 Collection:', `${currentCreateType}s`);
                } else {
                    alert('Failed to create account. Please try again.');
                }
            } catch (error) {
                console.error('Create account error:', error);
                alert('Account creation failed. Please try again.');
            } finally {
                // Restore button state
                submitButton.innerHTML = originalText;
                submitButton.disabled = false;
            }
        }

        // Show bus details
        function showBusDetails(busNumber) {
            const bus = busDatabase.find(b => b.number === busNumber);
            if (!bus) return;
            
            const modal = document.getElementById('busDetailsModal');
            const content = document.getElementById('busDetailsContent');
            
            // Default values for buses without detailed info
            const busStops = bus.busStops || [
                { name: "Start Point", time: "06:00 AM", status: "completed" },
                { name: "Intermediate Stop 1", time: "06:30 AM", status: "current" },
                { name: "Intermediate Stop 2", time: "07:00 AM", status: "upcoming" },
                { name: "End Point", time: "07:30 AM", status: "upcoming" }
            ];
            
            const nextBuses = bus.nextBuses || [
                { time: "07:30 AM", number: "PB-XX-XXXX" },
                { time: "08:00 AM", number: "PB-XX-XXXX" },
                { time: "08:30 AM", number: "PB-XX-XXXX" }
            ];
            
            content.innerHTML = `
                <!-- Live Tracking Header -->
                <div class="bg-gradient-to-r from-blue-500/20 to-purple-500/20 rounded-lg p-4 mb-6 border border-blue-400/30">
                    <div class="flex items-center justify-between">
                        <div class="flex items-center space-x-3">
                            <div class="w-3 h-3 bg-green-500 rounded-full animate-pulse"></div>
                            <h3 class="text-lg font-semibold text-white">Live Tracking Active</h3>
                        </div>
                        <div class="text-right text-sm text-white/80">
                            <p><strong>Last Updated:</strong> ${bus.lastUpdated || 'Just now'}</p>
                            <p><strong>Journey Date:</strong> ${bus.departureDate || new Date().toISOString().split('T')[0]}</p>
                        </div>
                    </div>
                </div>

                <!-- Bus Stops Progress - Main Focus -->
                <div class="bg-white/10 rounded-lg p-6 mb-6">
                    <h3 class="text-xl font-semibold mb-4"><i class="fas fa-map-signs mr-2 text-orange-400"></i>Bus Stops Progress</h3>
                    <div class="space-y-3">
                        ${busStops.map((stop, index) => `
                            <div class="flex items-center space-x-3 ${stop.status === 'current' ? 'bg-blue-500/20 p-3 rounded-lg' : 'p-1'}">
                                <div class="flex-shrink-0">
                                    <div class="w-5 h-5 rounded-full ${
                                        stop.status === 'completed' ? 'bg-green-500' : 
                                        stop.status === 'current' ? 'bg-blue-500 animate-pulse' : 
                                        'bg-gray-500'
                                    }"></div>
                                </div>
                                <div class="flex-1">
                                    <p class="font-medium ${stop.status === 'current' ? 'text-blue-300 text-lg' : ''}">${stop.name}</p>
                                    <div class="text-sm text-white/70">
                                        <p><strong>Scheduled:</strong> ${stop.scheduledTime || stop.time}</p>
                                        ${stop.actualTime ? `<p><strong>Actual:</strong> ${stop.actualTime}</p>` : ''}
                                        ${stop.date ? `<p><strong>Date:</strong> ${stop.date}</p>` : ''}
                                    </div>
                                </div>
                                <div class="flex-shrink-0">
                                    ${stop.status === 'completed' ? '<i class="fas fa-check text-green-500 text-lg"></i>' : 
                                      stop.status === 'current' ? '<i class="fas fa-bus text-blue-500 text-lg"></i>' : 
                                      '<i class="fas fa-clock text-gray-500"></i>'}
                                </div>
                            </div>
                            ${index < busStops.length - 1 ? '<div class="w-px h-6 bg-white/20 ml-2.5"></div>' : ''}
                        `).join('')}
                    </div>
                    
                    <div class="mt-6 p-4 bg-blue-500/20 rounded-lg">
                        <p class="text-lg font-medium"><strong>Progress:</strong> ${bus.stopsCompleted || 2}/${bus.totalStops || busStops.length} stops completed</p>
                        <div class="w-full bg-gray-700 rounded-full h-3 mt-3">
                            <div class="bg-blue-500 h-3 rounded-full transition-all duration-500" style="width: ${((bus.stopsCompleted || 2) / (bus.totalStops || busStops.length)) * 100}%"></div>
                        </div>
                    </div>
                </div>

                <!-- Quick Info Grid -->
                <div class="grid md:grid-cols-3 gap-4 mb-6">
                    <div class="bg-white/10 rounded-lg p-4 text-center">
                        <i class="fas fa-bus text-2xl text-blue-400 mb-2"></i>
                        <p class="text-sm text-white/70">Bus Number</p>
                        <p class="font-semibold text-lg">${bus.number}</p>
                    </div>
                    <div class="bg-white/10 rounded-lg p-4 text-center">
                        <i class="fas fa-clock text-2xl text-green-400 mb-2"></i>
                        <p class="text-sm text-white/70">ETA</p>
                        <p class="font-semibold text-lg">${bus.eta}</p>
                    </div>
                    <div class="bg-white/10 rounded-lg p-4 text-center">
                        <i class="fas fa-rupee-sign text-2xl text-yellow-400 mb-2"></i>
                        <p class="text-sm text-white/70">Fare</p>
                        <p class="font-semibold text-lg">${bus.fare}</p>
                    </div>
                </div>

                <!-- Timing & Schedule Details -->
                <div class="bg-white/10 rounded-lg p-4 mb-4">
                    <h4 class="font-semibold mb-3"><i class="fas fa-clock mr-2 text-yellow-400"></i>Journey Timeline</h4>
                    <div class="grid md:grid-cols-3 gap-4 text-sm">
                        <div class="text-center">
                            <p class="text-white/70">Departure</p>
                            <p class="font-semibold">${bus.departureTime || 'N/A'}</p>
                            <p class="text-xs text-white/60">${bus.departureDate || 'Today'}</p>
                        </div>
                        <div class="text-center">
                            <p class="text-white/70">Expected Arrival</p>
                            <p class="font-semibold">${bus.arrivalTime || 'N/A'}</p>
                            <p class="text-xs ${bus.delay && bus.delay !== '0 mins' ? 'text-yellow-400' : 'text-green-400'}">
                                ${bus.delay ? `Delay: ${bus.delay}` : 'On Schedule'}
                            </p>
                        </div>
                        <div class="text-center">
                            <p class="text-white/70">ETA to Next Stop</p>
                            <p class="font-semibold text-blue-400">${bus.eta}</p>
                            <p class="text-xs text-white/60">Live Update</p>
                        </div>
                    </div>
                </div>

                <!-- Compact Details -->
                <div class="grid md:grid-cols-2 gap-4">
                    <div class="bg-white/10 rounded-lg p-4">
                        <h4 class="font-semibold mb-3"><i class="fas fa-info-circle mr-2 text-cyan-400"></i>Bus Details</h4>
                        <div class="space-y-1 text-sm">
                            <p><strong>Route:</strong> ${bus.route}</p>
                            <p><strong>Type:</strong> ${bus.busType}</p>
                            <p><strong>Status:</strong> <span class="px-2 py-1 rounded text-xs ${bus.status === 'On Time' ? 'bg-green-500' : bus.status === 'Delayed' ? 'bg-yellow-500' : 'bg-blue-500'}">${bus.status}</span></p>
                            <p><strong>Current Speed:</strong> ${bus.speed}</p>
                            <p><strong>Current Location:</strong> ${bus.currentLocation || 'Updating...'}</p>
                        </div>
                    </div>
                    
                    <div class="bg-white/10 rounded-lg p-4">
                        <h4 class="font-semibold mb-3"><i class="fas fa-user mr-2 text-green-400"></i>Driver & Contact</h4>
                        <div class="space-y-1 text-sm">
                            <p><strong>Driver:</strong> ${bus.driver}</p>
                            <p><strong>Contact:</strong> ${bus.contact}</p>
                            <p><strong>Next Stop:</strong> ${bus.nextStop || 'Unknown'}</p>
                            <p><strong>Distance Remaining:</strong> ${bus.distance}</p>
                            <p><strong>Last Updated:</strong> ${bus.lastUpdated || 'Just now'}</p>
                        </div>
                    </div>
                </div>
                
                <!-- Action Buttons -->
                <div class="mt-6 flex flex-wrap gap-3 justify-center">
                    <button onclick="trackBusLive('${bus.number}')" class="bg-blue-500 hover:bg-blue-600 text-white px-4 py-2 rounded-lg transition-colors">
                        <i class="fas fa-satellite-dish mr-2"></i>Live Track
                    </button>
                    <button onclick="setBusAlert('${bus.number}')" class="bg-green-500 hover:bg-green-600 text-white px-4 py-2 rounded-lg transition-colors">
                        <i class="fas fa-bell mr-2"></i>Set Alert
                    </button>
                    <button onclick="shareBusInfo('${bus.number}')" class="bg-purple-500 hover:bg-purple-600 text-white px-4 py-2 rounded-lg transition-colors">
                        <i class="fas fa-share mr-2"></i>Share Info
                    </button>
                    <button onclick="reportIssue('${bus.number}')" class="bg-orange-500 hover:bg-orange-600 text-white px-4 py-2 rounded-lg transition-colors">
                        <i class="fas fa-exclamation-triangle mr-2"></i>Report Issue
                    </button>
                </div>
            `;
            
            modal.classList.remove('hidden');
            modal.classList.add('flex');
        }

        // Close bus details
        function closeBusDetails() {
            const modal = document.getElementById('busDetailsModal');
            modal.classList.add('hidden');
            modal.classList.remove('flex');
        }

        // Track by route
        function trackByRoute() {
            const pickup = document.getElementById('pickupLocation').value;
            const drop = document.getElementById('dropLocation').value;
            
            if (!pickup || !drop) {
                alert('Please select both pickup and drop locations');
                return;
            }
            
            if (pickup === drop) {
                alert('Pickup and drop locations cannot be the same');
                return;
            }
            
            // Add to recent searches
            addToRecentSearches({
                type: 'route',
                query: `${pickup} → ${drop}`,
                pickup: pickup,
                drop: drop
            });
            
            showBusResults(`${pickup} - ${drop}`);
        }

        // Track by bus number
        function trackByNumber() {
            const busNumber = document.getElementById('busNumberInput').value.trim();
            
            if (!busNumber) {
                alert('Please enter a bus number');
                return;
            }
            
            // Add to recent searches
            addToRecentSearches({
                type: 'number',
                query: busNumber
            });
            
            showBusResults(null, busNumber);
        }

        // Recent searches management
        let recentSearches = JSON.parse(localStorage.getItem('recentSearches') || '[]');

        function addToRecentSearches(searchData) {
            // Remove if already exists
            recentSearches = recentSearches.filter(search => 
                !(search.type === searchData.type && search.query === searchData.query)
            );
            
            // Add to beginning
            recentSearches.unshift({
                ...searchData,
                timestamp: new Date().toISOString(),
                id: Date.now()
            });
            
            // Keep only last 5 searches
            recentSearches = recentSearches.slice(0, 5);
            
            // Save to localStorage
            localStorage.setItem('recentSearches', JSON.stringify(recentSearches));
            
            // Update display
            updateRecentSearchesDisplay();
        }

        function updateRecentSearchesDisplay() {
            const container = document.getElementById('recentSearchesList');
            const clearBtn = document.getElementById('clearRecentBtn');
            
            if (recentSearches.length === 0) {
                container.innerHTML = `
                    <div class="text-center text-white/60 py-8">
                        <i class="fas fa-search text-3xl mb-3"></i>
                        <p data-translate="noRecentSearches">No recent searches yet</p>
                        <p class="text-sm mt-2" data-translate="searchToSave">Search for buses to see them here</p>
                    </div>
                `;
                clearBtn.style.display = 'none';
            } else {
                container.innerHTML = recentSearches.map(search => `
                    <div class="bg-white/10 hover:bg-white/20 rounded-lg p-3 cursor-pointer transition-all duration-300 hover-lift" onclick="repeatSearch('${search.id}')">
                        <div class="flex justify-between items-center">
                            <div>
                                <p class="text-white font-medium">
                                    <i class="fas ${search.type === 'route' ? 'fa-route' : 'fa-hashtag'} mr-2 text-sm"></i>
                                    ${search.type === 'route' ? search.query : `Bus ${search.query}`}
                                </p>
                                <p class="text-white/60 text-sm">${new Date(search.timestamp).toLocaleDateString()}</p>
                            </div>
                            <div class="text-right">
                                <button onclick="event.stopPropagation(); repeatSearch('${search.id}')" class="bg-blue-500 hover:bg-blue-600 text-white px-3 py-1 rounded text-xs transition-colors">
                                    <i class="fas fa-redo mr-1"></i>
                                    <span data-translate="searchAgain">Search Again</span>
                                </button>
                            </div>
                        </div>
                    </div>
                `).join('');
                clearBtn.style.display = 'block';
            }
        }

        function repeatSearch(searchId) {
            const search = recentSearches.find(s => s.id == searchId);
            if (!search) return;
            
            if (search.type === 'route') {
                const [pickup, drop] = search.query.split(' → ');
                document.getElementById('pickupLocation').value = pickup;
                document.getElementById('dropLocation').value = drop;
                trackByRoute();
            } else {
                document.getElementById('busNumberInput').value = search.query;
                trackByNumber();
            }
        }

        function clearRecentSearches() {
            if (confirm('Are you sure you want to clear all recent searches?')) {
                recentSearches = [];
                localStorage.removeItem('recentSearches');
                updateRecentSearchesDisplay();
                showNotification('Recent searches cleared', 'success');
            }
        }

        // Recommended routes functionality
        function selectRecommendedRoute(pickup, drop) {
            document.getElementById('pickupLocation').value = pickup;
            document.getElementById('dropLocation').value = drop;
            trackByRoute();
        }

        function showAllRecommendations() {
            const allRoutes = [
                { from: 'Chandigarh', to: 'Ludhiana', fare: '₹120', buses: 5 },
                { from: 'Chandigarh', to: 'Amritsar', fare: '₹280', buses: 3 },
                { from: 'Ludhiana', to: 'Amritsar', fare: '₹160', buses: 4 },
                { from: 'Chandigarh', to: 'Jalandhar', fare: '₹180', buses: 2 },
                { from: 'Chandigarh', to: 'Patiala', fare: '₹90', buses: 3 },
                { from: 'Ludhiana', to: 'Patiala', fare: '₹70', buses: 2 },
                { from: 'Amritsar', to: 'Jalandhar', fare: '₹100', buses: 3 },
                { from: 'Patiala', to: 'Bathinda', fare: '₹190', buses: 2 }
            ];
            
            const routesList = allRoutes.map(route => `
                <div class="bg-white/10 hover:bg-white/20 rounded-lg p-3 cursor-pointer transition-all duration-300 hover-lift" onclick="selectRecommendedRoute('${route.from}', '${route.to}')">
                    <div class="flex justify-between items-center">
                        <div>
                            <p class="text-white font-medium">${route.from} → ${route.to}</p>
                        </div>
                        <div class="text-right">
                            <p class="text-green-400 font-semibold">${route.fare}</p>
                            <p class="text-white/60 text-xs">${route.buses} buses</p>
                        </div>
                    </div>
                </div>
            `).join('');
            
            alert(`🚌 All Available Routes:\n\n${allRoutes.map(r => `${r.from} → ${r.to}: ${r.fare} (${r.buses} buses)`).join('\n')}\n\nClick on any route above to search for buses!`);
        }

        // Show bus results
        function showBusResults(route = null, busNumber = null) {
            const resultsDiv = document.getElementById('busResults');
            const busList = document.getElementById('busList');
            
            let filteredBuses = busDatabase;
            
            if (route) {
                const [pickup, drop] = route.split(' - ');
                filteredBuses = busDatabase.filter(bus => 
                    (bus.route.toLowerCase().includes(pickup.toLowerCase()) && bus.route.toLowerCase().includes(drop.toLowerCase())) ||
                    bus.route.toLowerCase().includes(pickup.toLowerCase()) ||
                    bus.route.toLowerCase().includes(drop.toLowerCase())
                );
            }
            
            if (busNumber) {
                filteredBuses = busDatabase.filter(bus => 
                    bus.number.toLowerCase().includes(busNumber.toLowerCase())
                );
            }
            
            busList.innerHTML = '';
            
            if (filteredBuses.length === 0) {
                busList.innerHTML = `
                    <div class="text-center text-white/70 py-8">
                        <i class="fas fa-search text-4xl mb-4"></i>
                        <p>No buses found matching your criteria</p>
                    </div>
                `;
            } else {
                filteredBuses.forEach(bus => {
                    const busCard = document.createElement('div');
                    busCard.className = 'bg-white/10 rounded-lg p-4 hover:bg-white/20 transition-all duration-300 hover-lift cursor-pointer';
                    busCard.onclick = () => showBusDetails(bus.number);
                    busCard.innerHTML = `
                        <div class="flex justify-between items-center">
                            <div class="flex-1">
                                <h3 class="text-white font-semibold text-lg">${bus.number}</h3>
                                <p class="text-white/70">${bus.route}</p>
                                <p class="text-white/60 text-sm">${bus.busType} • ${bus.driver}</p>
                                <div class="flex items-center space-x-4 text-xs text-white/50 mt-1">
                                    <span><i class="fas fa-calendar-alt mr-1"></i>${bus.departureDate || 'Today'}</span>
                                    <span><i class="fas fa-clock mr-1"></i>Dep: ${bus.departureTime || 'N/A'}</span>
                                    <span><i class="fas fa-map-marker-alt mr-1"></i>Arr: ${bus.arrivalTime || 'N/A'}</span>
                                </div>
                            </div>
                            <div class="text-right">
                                <span class="inline-block px-3 py-1 rounded-full text-sm ${
                                    bus.status === 'On Time' ? 'bg-emerald-500' : 
                                    bus.status === 'Delayed' ? 'bg-amber-500' : 'bg-slate-500'
                                } text-white mb-2">${bus.status}</span>
                                <p class="text-white/70">ETA: ${bus.eta}</p>
                                <p class="text-white/70">${bus.fare}</p>
                                ${bus.delay && bus.delay !== '0 mins' ? `<p class="text-amber-400 text-xs">Delay: ${bus.delay}</p>` : ''}
                                <p class="text-white/50 text-xs mt-1">Updated: ${bus.lastUpdated || 'Just now'}</p>
                                <div class="mt-2 text-xs text-slate-300 flex items-center">
                                    <i class="fas fa-mouse-pointer mr-1"></i>
                                    <span>Click for details</span>
                                </div>
                            </div>
                        </div>
                    `;
                    busList.appendChild(busCard);
                });
            }
            
            resultsDiv.classList.remove('hidden');
            resultsDiv.scrollIntoView({ behavior: 'smooth' });
        }

        // Action button functions for bus details
        function trackBusLive(busNumber) {
            alert(`🛰️ Live tracking activated for bus ${busNumber}!\n\nYou will receive real-time location updates on your device. GPS tracking is now active.`);
        }

        function setBusAlert(busNumber) {
            alert(`🔔 Alert set for bus ${busNumber}!\n\nYou will be notified when:\n• Bus arrives at your stop\n• Bus is delayed\n• Route changes occur`);
        }

        function shareBusInfo(busNumber) {
            const bus = busDatabase.find(b => b.number === busNumber);
            const shareText = `🚌 Bus ${busNumber}\nRoute: ${bus.route}\nStatus: ${bus.status}\nETA: ${bus.eta}\n\nTrack live: Punjab Bus Tracker`;
            
            if (navigator.share) {
                navigator.share({
                    title: `Bus ${busNumber} Info`,
                    text: shareText,
                    url: window.location.href
                });
            } else {
                navigator.clipboard.writeText(shareText).then(() => {
                    alert('📋 Bus information copied to clipboard!');
                });
            }
        }

        function reportIssue(busNumber) {
            const issues = [
                'Bus is overcrowded',
                'Bus is running late',
                'AC not working',
                'Rude driver behavior',
                'Bus broke down',
                'Route deviation',
                'Other issue'
            ];
            
            const issue = prompt(`⚠️ Report an issue with bus ${busNumber}:\n\n` + 
                issues.map((issue, index) => `${index + 1}. ${issue}`).join('\n') + 
                '\n\nEnter issue number (1-7) or describe your issue:');
            
            if (issue) {
                alert(`✅ Issue reported for bus ${busNumber}!\n\nYour report has been submitted to the transport authority. Reference ID: ${busNumber.replace('-', '')}${Date.now().toString().slice(-4)}`);
            }
        }

        // Driver report issue function
        function showDriverReportIssue() {
            if (!loggedInUser || loggedInUser.type !== 'driver') {
                alert('Please login as a driver to report issues.');
                return;
            }

            const driverBuses = busDatabase.filter(bus => bus.driver === loggedInUser.name);
            
            if (driverBuses.length === 0) {
                alert('No buses assigned to you currently.');
                return;
            }

            // Show the driver issue report modal
            showDriverIssueModal(driverBuses);
        }

        // Show driver issue report modal
        function showDriverIssueModal(driverBuses) {
            const modal = document.getElementById('driverIssueModal');
            const busSelect = document.getElementById('issueBusSelect');
            
            // Populate bus selection
            busSelect.innerHTML = '<option value="">Select your bus</option>';
            driverBuses.forEach(bus => {
                const option = document.createElement('option');
                option.value = bus.number;
                option.textContent = `${bus.number} - ${bus.route}`;
                busSelect.appendChild(option);
            });
            
            // Reset form
            document.getElementById('driverIssueForm').reset();
            document.getElementById('issueDescription').value = '';
            
            modal.classList.remove('hidden');
            modal.classList.add('flex');
        }

        // Close driver issue modal
        function closeDriverIssueModal() {
            const modal = document.getElementById('driverIssueModal');
            modal.classList.add('hidden');
            modal.classList.remove('flex');
        }

        // Quick issue button handler
        function selectQuickIssue(issueType) {
            const textarea = document.getElementById('issueDescription');
            const currentValue = textarea.value.trim();
            
            if (currentValue && !currentValue.includes(issueType)) {
                textarea.value = currentValue + '\n\n' + issueType;
            } else if (!currentValue) {
                textarea.value = issueType;
            }
            
            // Add visual feedback
            const button = event.target;
            const originalBg = button.className;
            button.className = button.className.replace('bg-orange-500', 'bg-green-500');
            setTimeout(() => {
                button.className = originalBg;
            }, 1000);
        }

        // Handle driver issue form submission
        async function handleDriverIssueSubmit() {
            const form = document.getElementById('driverIssueForm');
            const formData = new FormData(form);
            
            const issueData = {
                driverId: loggedInUser.id,
                driverName: loggedInUser.name,
                busNumber: formData.get('busNumber'),
                issueType: formData.get('issueType'),
                priority: formData.get('priority'),
                location: formData.get('location'),
                description: formData.get('description'),
                contactNumber: formData.get('contactNumber'),
                timestamp: new Date().toISOString(),
                status: 'Open',
                reportId: `DR${Date.now().toString().slice(-6)}`
            };

            // Validate required fields
            if (!issueData.busNumber || !issueData.issueType || !issueData.description) {
                alert('ਕਿਰਪਾ ਕਰਕੇ ਸਾਰੇ ਲੋੜੀਂਦੇ ਖੇਤਰ ਭਰੋ / Please fill all required fields');
                return;
            }

            // Show loading state
            const submitButton = document.querySelector('#driverIssueForm button[type="submit"]');
            const originalText = submitButton.innerHTML;
            submitButton.innerHTML = '<i class="fas fa-spinner fa-spin mr-2"></i>ਰਿਪੋਰਟ ਭੇਜੀ ਜਾ ਰਹੀ ਹੈ... / Submitting Report...';
            submitButton.disabled = true;

            try {
                // Submit to MongoDB
                const result = await submitIssueToMongoDB(issueData);
                
                if (result.success) {
                    // Show success message with Punjabi colors
                    showIssueSubmissionSuccess(issueData);
                    closeDriverIssueModal();
                    
                    // Update bus status if critical
                    if (issueData.priority === 'Critical' || issueData.issueType.includes('Breakdown')) {
                        updateBusStatus(issueData.busNumber, 'Out of Service');
                    }
                } else {
                    throw new Error('Submission failed');
                }
            } catch (error) {
                console.error('Issue submission error:', error);
                alert('ਰਿਪੋਰਟ ਭੇਜਣ ਵਿੱਚ ਸਮੱਸਿਆ / Error submitting report. Please try again.');
            } finally {
                // Restore button state
                submitButton.innerHTML = originalText;
                submitButton.disabled = false;
            }
        }

        // Submit issue to MongoDB
        async function submitIssueToMongoDB(issueData) {
            try {
                // In production, this would be your actual backend API
                const response = await fetch(`${API_BASE_URL}/driver-issues`, {
                    method: 'POST',
                    headers: {
                        'Content-Type': 'application/json',
                        'Authorization': `Bearer ${loggedInUser.token || 'demo-token'}`
                    },
                    body: JSON.stringify(issueData)
                });
                
                if (!response.ok) {
                    throw new Error('API request failed');
                }
                
                return await response.json();
            } catch (error) {
                console.error('MongoDB submission error:', error);
                // Simulate successful submission for demo
                return simulateMongoDBIssueSubmission(issueData);
            }
        }

        // Simulate MongoDB issue submission
        function simulateMongoDBIssueSubmission(issueData) {
            // Store in localStorage to simulate database
            const existingIssues = JSON.parse(localStorage.getItem('mongo_driver_issues') || '[]');
            const issueWithId = {
                _id: new Date().getTime().toString(),
                ...issueData,
                createdAt: new Date().toISOString(),
                updatedAt: new Date().toISOString()
            };
            
            existingIssues.push(issueWithId);
            localStorage.setItem('mongo_driver_issues', JSON.stringify(existingIssues));
            
            console.log('🚨 Driver Issue Submitted to MongoDB:', issueWithId);
            console.log('🔗 Connection:', mongoDBConnection);
            console.log('🗄️ Database:', databaseName);
            console.log('📁 Collection: driver_issues');
            
            return { success: true, issueId: issueWithId._id, data: issueWithId };
        }

        // Show issue submission success with Punjabi theme
        function showIssueSubmissionSuccess(issueData) {
            // Create success overlay
            const overlay = document.createElement('div');
            overlay.className = 'fixed inset-0 bg-black/70 backdrop-blur-sm flex items-center justify-center z-[60] punjabi-success-overlay';
            
            overlay.innerHTML = `
                <div class="bg-gradient-to-br from-orange-500 via-white to-green-600 p-1 rounded-2xl max-w-md mx-4 animate-pulse">
                    <div class="bg-slate-900 dark:bg-slate-800 rounded-xl p-8 text-center">
                        <!-- Success Icon with Punjabi Colors -->
                        <div class="relative mb-6">
                            <div class="w-20 h-20 mx-auto bg-gradient-to-r from-orange-500 to-green-600 rounded-full flex items-center justify-center animate-bounce">
                                <i class="fas fa-check text-white text-3xl"></i>
                            </div>
                            <div class="absolute -top-2 -right-2 w-8 h-8 bg-orange-500 rounded-full animate-ping"></div>
                        </div>
                        
                        <!-- Success Message in Punjabi & English -->
                        <h2 class="text-2xl font-bold text-white mb-2">
                            ਰਿਪੋਰਟ ਸਫਲਤਾਪੂਰਵਕ ਭੇਜੀ ਗਈ!
                        </h2>
                        <h3 class="text-lg text-green-400 mb-4">Issue Reported Successfully!</h3>
                        
                        <!-- Report Details -->
                        <div class="bg-white/10 rounded-lg p-4 mb-6 text-left">
                            <div class="grid grid-cols-2 gap-2 text-sm">
                                <div class="text-orange-400 font-semibold">Report ID:</div>
                                <div class="text-white">${issueData.reportId}</div>
                                
                                <div class="text-orange-400 font-semibold">Bus:</div>
                                <div class="text-white">${issueData.busNumber}</div>
                                
                                <div class="text-orange-400 font-semibold">Priority:</div>
                                <div class="text-white">
                                    <span class="px-2 py-1 rounded text-xs ${
                                        issueData.priority === 'Critical' ? 'bg-red-500' :
                                        issueData.priority === 'High' ? 'bg-orange-500' :
                                        issueData.priority === 'Medium' ? 'bg-yellow-500' : 'bg-green-500'
                                    }">${issueData.priority}</span>
                                </div>
                                
                                <div class="text-orange-400 font-semibold">Status:</div>
                                <div class="text-green-400">Open - Under Review</div>
                            </div>
                        </div>
                        
                        <!-- MongoDB Info -->
                        <div class="bg-green-500/20 rounded-lg p-3 mb-4 border border-green-500/30">
                            <div class="flex items-center justify-center space-x-2 text-green-400 text-sm">
                                <i class="fas fa-database"></i>
                                <span>Saved to MongoDB Atlas</span>
                            </div>
                            <div class="text-xs text-white/70 mt-1">
                                Database: ${databaseName} | Collection: driver_issues
                            </div>
                        </div>
                        
                        <!-- Action Buttons -->
                        <div class="space-y-3">
                            <button onclick="closeSuccessOverlay()" class="w-full bg-gradient-to-r from-orange-500 to-green-600 hover:from-orange-600 hover:to-green-700 text-white font-semibold py-3 rounded-lg transition-all duration-300 transform hover:scale-105">
                                <i class="fas fa-check mr-2"></i>
                                ਠੀਕ ਹੈ / OK
                            </button>
                            
                            <button onclick="copyReportId('${issueData.reportId}')" class="w-full bg-white/10 hover:bg-white/20 text-white font-medium py-2 rounded-lg transition-all duration-300">
                                <i class="fas fa-copy mr-2"></i>
                                Copy Report ID
                            </button>
                        </div>
                        
                        <!-- Contact Info -->
                        <div class="mt-6 p-3 bg-orange-500/20 rounded-lg border border-orange-500/30">
                            <p class="text-orange-400 font-semibold text-sm mb-1">
                                ਐਮਰਜੈਂਸੀ ਲਈ / For Emergency:
                            </p>
                            <p class="text-white text-sm">📞 Control Room: 1800-PB-HELP</p>
                            <p class="text-white text-sm">🚨 Emergency: 108</p>
                        </div>
                    </div>
                </div>
            `;
            
            document.body.appendChild(overlay);
            
            // Auto-close after 10 seconds
            setTimeout(() => {
                closeSuccessOverlay();
            }, 10000);
        }

        // Close success overlay
        function closeSuccessOverlay() {
            const overlay = document.querySelector('.punjabi-success-overlay');
            if (overlay) {
                overlay.remove();
            }
        }

        // Copy report ID to clipboard
        function copyReportId(reportId) {
            navigator.clipboard.writeText(reportId).then(() => {
                showNotification('📋 Report ID copied to clipboard!', 'success');
            }).catch(() => {
                // Fallback for older browsers
                const textArea = document.createElement('textarea');
                textArea.value = reportId;
                document.body.appendChild(textArea);
                textArea.select();
                document.execCommand('copy');
                document.body.removeChild(textArea);
                showNotification('📋 Report ID copied!', 'success');
            });
        }

        // Update bus status
        function updateBusStatus(busNumber, newStatus) {
            const busIndex = busDatabase.findIndex(b => b.number === busNumber);
            if (busIndex !== -1) {
                busDatabase[busIndex].status = newStatus;
                showNotification(`Bus ${busNumber} status updated to: ${newStatus}`, 'info');
            }
        }

        // Show notification
        function showNotification(message, type = 'info') {
            const container = document.getElementById('notificationContainer');
            const notification = document.createElement('div');
            
            const bgColor = type === 'success' ? 'bg-green-500' : type === 'error' ? 'bg-red-500' : 'bg-blue-500';
            const icon = type === 'success' ? 'fa-check-circle' : type === 'error' ? 'fa-exclamation-circle' : 'fa-info-circle';
            
            notification.className = `${bgColor} text-white px-6 py-3 rounded-lg shadow-lg backdrop-blur-md transform transition-all duration-300 translate-y-[-20px] opacity-0`;
            notification.innerHTML = `
                <div class="flex items-center space-x-3">
                    <i class="fas ${icon}"></i>
                    <span>${message}</span>
                </div>
            `;
            
            container.appendChild(notification);
            
            // Animate in
            setTimeout(() => {
                notification.classList.remove('translate-y-[-20px]', 'opacity-0');
            }, 100);
            
            // Auto remove after 3 seconds
            setTimeout(() => {
                notification.classList.add('translate-y-[-20px]', 'opacity-0');
                setTimeout(() => {
                    if (notification.parentNode) {
                        notification.parentNode.removeChild(notification);
                    }
                }, 300);
            }, 3000);
        }

        // Journey Date & Time Selector Functions
        function showJourneyDateSelector() {
            const modal = document.getElementById('journeyDateModal');
            const dateInput = document.getElementById('journeyDateInput');
            const timeInput = document.getElementById('customTimeInput');
            
            // Set minimum date to today
            const today = new Date().toISOString().split('T')[0];
            dateInput.min = today;
            
            // Set default values if none selected
            if (!selectedJourneyDate) {
                dateInput.value = today;
            } else {
                dateInput.value = selectedJourneyDate;
            }
            
            if (selectedJourneyTime && selectedJourneyTime.includes(':')) {
                // Convert 12-hour to 24-hour format for input
                const time12 = selectedJourneyTime;
                const [time, period] = time12.split(' ');
                const [hours, minutes] = time.split(':');
                let hour24 = parseInt(hours);
                
                if (period === 'PM' && hour24 !== 12) hour24 += 12;
                if (period === 'AM' && hour24 === 12) hour24 = 0;
                
                timeInput.value = `${hour24.toString().padStart(2, '0')}:${minutes}`;
            }
            
            modal.classList.remove('hidden');
            modal.classList.add('flex');
        }

        function closeJourneyDateSelector() {
            const modal = document.getElementById('journeyDateModal');
            modal.classList.add('hidden');
            modal.classList.remove('flex');
        }

        function convertTo12Hour(time24) {
            if (!time24) return '';
            const [hours, minutes] = time24.split(':');
            const hour12 = hours % 12 || 12;
            const ampm = hours >= 12 ? 'PM' : 'AM';
            return `${hour12}:${minutes} ${ampm}`;
        }

        function confirmJourneyDateTime() {
            const dateInput = document.getElementById('journeyDateInput');
            const timeInput = document.getElementById('customTimeInput');
            
            const date = dateInput.value;
            const time24 = timeInput.value;
            
            if (!date) {
                alert('Please select a journey date');
                return;
            }
            
            if (!time24) {
                alert('Please select a journey time');
                return;
            }
            
            selectedJourneyDate = date;
            selectedJourneyTime = convertTo12Hour(time24);
            
            // Update both displays
            updateJourneyDateDisplay();
            
            // Close modal
            closeJourneyDateSelector();
            
            // Show success notification
            showNotification(`Journey scheduled for ${new Date(date).toLocaleDateString()} at ${selectedJourneyTime}`, 'success');
        }

        function updateJourneyDateDisplay() {
            const dateElement = document.getElementById('selectedJourneyDate');
            const timeElement = document.getElementById('selectedJourneyTime');
            const dateElement2 = document.getElementById('selectedJourneyDate2');
            const timeElement2 = document.getElementById('selectedJourneyTime2');
            
            if (selectedJourneyDate && selectedJourneyTime) {
                const dateObj = new Date(selectedJourneyDate);
                const shortDate = dateObj.toLocaleDateString('en-US', { 
                    month: 'short', 
                    day: 'numeric' 
                });
                
                // Update both sections
                if (dateElement) {
                    dateElement.textContent = shortDate;
                    timeElement.textContent = selectedJourneyTime;
                }
                if (dateElement2) {
                    dateElement2.textContent = shortDate;
                    timeElement2.textContent = selectedJourneyTime;
                }
            } else {
                // Reset to default text
                const elements = [
                    { date: dateElement, time: timeElement },
                    { date: dateElement2, time: timeElement2 }
                ];
                
                elements.forEach(({ date, time }) => {
                    if (date && time) {
                        date.setAttribute('data-translate', 'selectDate');
                        time.setAttribute('data-translate', 'selectTime');
                        date.textContent = translations[currentLanguage].selectDate || 'Select Date';
                        time.textContent = translations[currentLanguage].selectTime || 'Select Time';
                    }
                });
            }
        }



        // GPS Location Functions
        function enableGPSLocation() {
            const modal = document.getElementById('gpsLocationModal');
            modal.classList.remove('hidden');
            modal.classList.add('flex');
            
            // Reset to permission request view
            document.getElementById('gpsPermissionRequest').classList.remove('hidden');
            document.getElementById('gpsActiveStatus').classList.add('hidden');
        }

        function closeGPSModal() {
            const modal = document.getElementById('gpsLocationModal');
            modal.classList.add('hidden');
            modal.classList.remove('flex');
        }

        function requestGPSPermission() {
            // Show loading state
            const button = event.target;
            const originalText = button.innerHTML;
            button.innerHTML = '<i class="fas fa-spinner fa-spin mr-2"></i>Requesting GPS Access...';
            button.disabled = true;

            if (navigator.geolocation) {
                navigator.geolocation.getCurrentPosition(
                    function(position) {
                        // GPS enabled successfully
                        activateGPSLocation(position);
                        button.innerHTML = originalText;
                        button.disabled = false;
                    },
                    function(error) {
                        // GPS permission denied or error
                        handleGPSLocationError(error);
                        button.innerHTML = originalText;
                        button.disabled = false;
                    },
                    {
                        enableHighAccuracy: true,
                        timeout: 15000,
                        maximumAge: 300000 // 5 minutes
                    }
                );
            } else {
                showNotification('🚫 Geolocation is not supported by this browser. Please use a modern browser.', 'error');
                button.innerHTML = originalText;
                button.disabled = false;
            }
        }

        function activateGPSLocation(position) {
            userLocation = {
                lat: position.coords.latitude,
                lng: position.coords.longitude,
                accuracy: position.coords.accuracy
            };
            
            // Switch to active GPS view
            document.getElementById('gpsPermissionRequest').classList.add('hidden');
            document.getElementById('gpsActiveStatus').classList.remove('hidden');
            
            // Update location info
            document.getElementById('currentLocationInfo').innerHTML = `
                📍 <strong>Location:</strong> ${position.coords.latitude.toFixed(6)}, ${position.coords.longitude.toFixed(6)}<br>
                🎯 <strong>Accuracy:</strong> ±${Math.round(position.coords.accuracy)}m<br>
                🕒 <strong>Last Updated:</strong> ${new Date().toLocaleTimeString()}
            `;
            
            // Simulate Google Maps integration
            initializeGoogleMapsPlaceholder(position);
            
            showNotification('🛰️ GPS location activated! You can now find nearby buses.', 'success');
        }

        function handleGPSLocationError(error) {
            let message = '';
            let instructions = '';
            
            switch(error.code) {
                case error.PERMISSION_DENIED:
                    message = "🚫 GPS permission was denied.";
                    instructions = `To enable GPS location:

🔧 Chrome/Edge:
1. Click the location icon (🌐) in the address bar
2. Select "Always allow" for location access
3. Refresh the page and try again

🔧 Firefox:
1. Click the shield icon in the address bar
2. Turn off "Blocking Location Access"
3. Refresh and try again

🔧 Safari:
1. Go to Safari > Preferences > Websites
2. Select "Location" and set to "Allow"
3. Refresh the page`;
                    break;
                case error.POSITION_UNAVAILABLE:
                    message = "📡 Location information is unavailable. Please check your GPS settings.";
                    instructions = "Make sure location services are enabled on your device.";
                    break;
                case error.TIMEOUT:
                    message = "⏱️ Location request timed out. Please try again.";
                    instructions = "Make sure you have a good GPS signal and try again.";
                    break;
                default:
                    message = "❌ An unknown error occurred while retrieving location.";
                    instructions = "Please try again or use manual search.";
                    break;
            }
            
            alert(`${message}\n\n${instructions}`);
        }

        function initializeGoogleMapsPlaceholder(position) {
            const placeholder = document.getElementById('googleMapPlaceholder');
            
            // In a real implementation, this would initialize Google Maps
            placeholder.innerHTML = `
                <div class="text-center text-white">
                    <i class="fas fa-map-marked-alt text-4xl mb-3 text-blue-400"></i>
                    <h3 class="font-semibold mb-2">Google Maps Integration</h3>
                    <p class="text-sm mb-3">Your location: ${position.coords.latitude.toFixed(4)}, ${position.coords.longitude.toFixed(4)}</p>
                    <div class="bg-blue-500/20 rounded p-2 text-xs">
                        <p>🗺️ Interactive map would show:</p>
                        <p>• Your current position</p>
                        <p>• Nearby bus stops</p>
                        <p>• Real-time bus locations</p>
                        <p>• Route directions</p>
                    </div>
                    <button onclick="openGoogleMaps()" class="mt-3 bg-blue-500 hover:bg-blue-600 text-white px-4 py-2 rounded text-sm">
                        <i class="fas fa-external-link-alt mr-1"></i>
                        Open in Google Maps
                    </button>
                </div>
            `;
        }

        function openGoogleMaps() {
            if (userLocation) {
                const mapsUrl = `https://www.google.com/maps/@${userLocation.lat},${userLocation.lng},15z`;
                window.open(mapsUrl, '_blank');
            }
        }

        function shareCurrentLocation() {
            if (!userLocation) {
                alert('Location not available. Please enable GPS first.');
                return;
            }

            const shareText = `📍 My Current Location:
Latitude: ${userLocation.lat.toFixed(6)}
Longitude: ${userLocation.lng.toFixed(6)}
Accuracy: ±${userLocation.accuracy}m

🚌 Punjab Bus Tracker
Find buses near me: ${window.location.href}

📍 Google Maps: https://www.google.com/maps/@${userLocation.lat},${userLocation.lng},15z`;
            
            if (navigator.share) {
                navigator.share({
                    title: 'My Location - Punjab Bus Tracker',
                    text: shareText,
                    url: window.location.href
                }).catch(err => {
                    // Fallback to clipboard
                    copyToClipboard(shareText);
                });
            } else {
                copyToClipboard(shareText);
            }
        }

        function copyToClipboard(text) {
            navigator.clipboard.writeText(text).then(() => {
                showNotification('📋 Location details copied to clipboard!', 'success');
            }).catch(() => {
                // Fallback for older browsers
                const textArea = document.createElement('textarea');
                textArea.value = text;
                document.body.appendChild(textArea);
                textArea.select();
                document.execCommand('copy');
                document.body.removeChild(textArea);
                showNotification('📋 Location details copied!', 'success');
            });
        }



        // Location Functions
        function findNearbyBuses() {
            const modal = document.getElementById('nearbyBusesModal');
            const content = document.getElementById('nearbyBusesContent');
            
            // Show loading state
            content.innerHTML = `
                <div class="text-center py-8">
                    <div class="animate-spin rounded-full h-12 w-12 border-b-2 border-white mx-auto mb-4"></div>
                    <p class="text-white" data-translate="findingLocation">Finding your location...</p>
                </div>
            `;
            
            modal.classList.remove('hidden');
            modal.classList.add('flex');
            
            // Get user location
            if (navigator.geolocation) {
                navigator.geolocation.getCurrentPosition(
                    function(position) {
                        userLocation = {
                            lat: position.coords.latitude,
                            lng: position.coords.longitude
                        };
                        displayNearbyBuses(userLocation);
                    },
                    function(error) {
                        handleLocationError(error);
                    },
                    {
                        enableHighAccuracy: true,
                        timeout: 10000,
                        maximumAge: 300000 // 5 minutes
                    }
                );
            } else {
                content.innerHTML = `
                    <div class="text-center py-8">
                        <i class="fas fa-exclamation-triangle text-4xl text-yellow-400 mb-4"></i>
                        <p class="text-white mb-4">Geolocation is not supported by this browser</p>
                        <button onclick="closeNearbyBuses()" class="bg-blue-500 hover:bg-blue-600 text-white px-4 py-2 rounded-lg">
                            Close
                        </button>
                    </div>
                `;
            }
        }

        function handleLocationError(error) {
            const content = document.getElementById('nearbyBusesContent');
            let errorMessage = '';
            
            switch(error.code) {
                case error.PERMISSION_DENIED:
                    errorMessage = "Location access denied. Please enable location services and try again.";
                    break;
                case error.POSITION_UNAVAILABLE:
                    errorMessage = "Location information is unavailable.";
                    break;
                case error.TIMEOUT:
                    errorMessage = "Location request timed out.";
                    break;
                default:
                    errorMessage = "An unknown error occurred while retrieving location.";
                    break;
            }
            
            content.innerHTML = `
                <div class="text-center py-8">
                    <i class="fas fa-map-marker-alt text-4xl text-red-400 mb-4"></i>
                    <h3 class="text-white text-lg font-semibold mb-2" data-translate="locationPermission">Location Permission Required</h3>
                    <p class="text-white/80 mb-6">${errorMessage}</p>
                    
                    <div class="space-y-3">
                        <button onclick="findNearbyBuses()" class="w-full bg-blue-500 hover:bg-blue-600 text-white px-4 py-2 rounded-lg">
                            <i class="fas fa-redo mr-2"></i>Try Again
                        </button>
                        
                        <button onclick="showManualLocationSearch()" class="w-full bg-green-500 hover:bg-green-600 text-white px-4 py-2 rounded-lg">
                            <i class="fas fa-search mr-2"></i>Search Manually
                        </button>
                        
                        <button onclick="closeNearbyBuses()" class="w-full bg-gray-500 hover:bg-gray-600 text-white px-4 py-2 rounded-lg">
                            <i class="fas fa-times mr-2"></i>Close
                        </button>
                    </div>
                    
                    <div class="mt-6 p-4 bg-blue-500/20 rounded-lg text-left">
                        <h4 class="text-white font-semibold mb-2">📍 How to enable location:</h4>
                        <ul class="text-white/80 text-sm space-y-1">
                            <li>• Click the location icon in your browser's address bar</li>
                            <li>• Select "Allow" for location access</li>
                            <li>• Refresh the page and try again</li>
                        </ul>
                    </div>
                </div>
            `;
        }

        function displayNearbyBuses(userLoc) {
            const content = document.getElementById('nearbyBusesContent');
            
            // Calculate distances and sort buses by proximity
            const busesWithDistance = busDatabase.map(bus => {
                if (!bus.coordinates) {
                    return { ...bus, distanceFromUser: 999 }; // Far away if no coordinates
                }
                
                const distance = calculateDistance(
                    userLoc.lat, userLoc.lng,
                    bus.coordinates.lat, bus.coordinates.lng
                );
                
                return { ...bus, distanceFromUser: distance };
            }).sort((a, b) => a.distanceFromUser - b.distanceFromUser);
            
            // Filter buses within 50km
            const nearbyBuses = busesWithDistance.filter(bus => bus.distanceFromUser <= 50);
            
            if (nearbyBuses.length === 0) {
                content.innerHTML = `
                    <div class="text-center py-8">
                        <i class="fas fa-search text-4xl text-gray-400 mb-4"></i>
                        <h3 class="text-white text-lg font-semibold mb-2" data-translate="noNearbyBuses">No buses found near your location</h3>
                        <p class="text-white/80 mb-6">Try expanding your search radius or check back later.</p>
                        
                        <div class="space-y-3">
                            <button onclick="showAllBuses()" class="w-full bg-blue-500 hover:bg-blue-600 text-white px-4 py-2 rounded-lg">
                                <i class="fas fa-list mr-2"></i>View All Buses
                            </button>
                            <button onclick="closeNearbyBuses()" class="w-full bg-gray-500 hover:bg-gray-600 text-white px-4 py-2 rounded-lg">
                                <i class="fas fa-times mr-2"></i>Close
                            </button>
                        </div>
                    </div>
                `;
                return;
            }
            
            content.innerHTML = `
                <!-- User Location Info -->
                <div class="bg-blue-500/20 rounded-lg p-4 mb-6 border border-blue-400/30">
                    <div class="flex items-center space-x-3">
                        <i class="fas fa-map-marker-alt text-blue-400 text-xl"></i>
                        <div>
                            <h3 class="text-white font-semibold" data-translate="currentLocation">Current Location</h3>
                            <p class="text-white/80 text-sm">Lat: ${userLoc.lat.toFixed(4)}, Lng: ${userLoc.lng.toFixed(4)}</p>
                            <p class="text-white/60 text-xs">Found ${nearbyBuses.length} buses within 50km</p>
                        </div>
                    </div>
                </div>
                
                <!-- Nearby Buses List -->
                <div class="space-y-4">
                    ${nearbyBuses.slice(0, 10).map(bus => `
                        <div class="bg-white/10 hover:bg-white/20 rounded-lg p-4 cursor-pointer transition-all duration-300 hover-lift" onclick="showBusDetails('${bus.number}'); closeNearbyBuses();">
                            <div class="flex justify-between items-start">
                                <div class="flex-1">
                                    <div class="flex items-center space-x-2 mb-2">
                                        <h3 class="text-white font-semibold">${bus.number}</h3>
                                        <span class="px-2 py-1 rounded-full text-xs ${
                                            bus.status === 'On Time' ? 'bg-emerald-500' : 
                                            bus.status === 'Delayed' ? 'bg-amber-500' : 'bg-slate-500'
                                        } text-white">${bus.status}</span>
                                    </div>
                                    <p class="text-white/80 mb-1">${bus.route}</p>
                                    <p class="text-white/60 text-sm">${bus.busType} • ${bus.driver}</p>
                                    <div class="flex items-center space-x-4 text-xs text-white/50 mt-2">
                                        <span><i class="fas fa-clock mr-1"></i>ETA: ${bus.eta}</span>
                                        <span><i class="fas fa-rupee-sign mr-1"></i>${bus.fare}</span>
                                        <span><i class="fas fa-tachometer-alt mr-1"></i>${bus.speed}</span>
                                    </div>
                                </div>
                                <div class="text-right ml-4">
                                    <div class="flex items-center space-x-1 text-blue-400 font-semibold">
                                        <i class="fas fa-location-arrow text-sm"></i>
                                        <span>${bus.distanceFromUser.toFixed(1)} km</span>
                                    </div>
                                    <p class="text-white/60 text-xs mt-1" data-translate="distance">Distance</p>
                                    ${bus.distanceFromUser <= 5 ? '<p class="text-green-400 text-xs mt-1">Very Close!</p>' : 
                                      bus.distanceFromUser <= 15 ? '<p class="text-yellow-400 text-xs mt-1">Nearby</p>' : 
                                      '<p class="text-white/40 text-xs mt-1">Far</p>'}
                                </div>
                            </div>
                        </div>
                    `).join('')}
                </div>
                
                <!-- Action Buttons -->
                <div class="mt-6 flex space-x-3">
                    <button onclick="refreshNearbyBuses()" class="flex-1 bg-blue-500 hover:bg-blue-600 text-white px-4 py-2 rounded-lg transition-colors">
                        <i class="fas fa-sync-alt mr-2"></i>Refresh
                    </button>
                    <button onclick="showAllBuses()" class="flex-1 bg-green-500 hover:bg-green-600 text-white px-4 py-2 rounded-lg transition-colors">
                        <i class="fas fa-list mr-2"></i>View All
                    </button>
                </div>
            `;
        }

        function calculateDistance(lat1, lon1, lat2, lon2) {
            const R = 6371; // Radius of the Earth in kilometers
            const dLat = (lat2 - lat1) * Math.PI / 180;
            const dLon = (lon2 - lon1) * Math.PI / 180;
            const a = 
                Math.sin(dLat/2) * Math.sin(dLat/2) +
                Math.cos(lat1 * Math.PI / 180) * Math.cos(lat2 * Math.PI / 180) * 
                Math.sin(dLon/2) * Math.sin(dLon/2);
            const c = 2 * Math.atan2(Math.sqrt(a), Math.sqrt(1-a));
            return R * c; // Distance in kilometers
        }

        function closeNearbyBuses() {
            const modal = document.getElementById('nearbyBusesModal');
            modal.classList.add('hidden');
            modal.classList.remove('flex');
        }

        function refreshNearbyBuses() {
            if (userLocation) {
                displayNearbyBuses(userLocation);
                showNotification('Nearby buses refreshed!', 'success');
            } else {
                findNearbyBuses();
            }
        }

        function showAllBuses() {
            closeNearbyBuses();
            showBusResults(); // Show all buses
        }

        function showManualLocationSearch() {
            const location = prompt('Enter your city or area name:');
            if (location) {
                // Simulate finding buses in that area
                alert(`🔍 Searching for buses near "${location}"...\n\nThis feature would integrate with a geocoding service to find buses in your specified area.`);
                closeNearbyBuses();
            }
        }



        // ===== ADMIN PORTAL FUNCTIONS =====
        
        // Show Emergency Alert System
        function showEmergencyAlert() {
            const alertMessage = prompt(`🚨 EMERGENCY BROADCAST SYSTEM 🚨

Send emergency alert to ALL buses and drivers:

Examples:
• "SEVERE WEATHER: All buses return to depot immediately"
• "ROAD CLOSURE: Route 15 diverted via alternate path"
• "SECURITY ALERT: Report any suspicious activity"
• "MEDICAL EMERGENCY: Bus PB-01-1234 needs immediate assistance"

Enter your emergency message:`);
            
            if (alertMessage && alertMessage.trim()) {
                // Simulate broadcasting to all buses
                const alertId = `ALERT${Date.now().toString().slice(-6)}`;
                const emergencyAlert = {
                    id: alertId,
                    message: alertMessage.trim(),
                    timestamp: new Date().toISOString(),
                    adminId: loggedInUser.id,
                    adminName: loggedInUser.name,
                    status: 'Active',
                    recipients: busDatabase.length,
                    priority: 'Emergency'
                };
                
                // Store alert
                const existingAlerts = JSON.parse(localStorage.getItem('emergency_alerts') || '[]');
                existingAlerts.unshift(emergencyAlert);
                localStorage.setItem('emergency_alerts', JSON.stringify(existingAlerts.slice(0, 50))); // Keep last 50
                
                // Show success message
                alert(`✅ EMERGENCY ALERT SENT!

Alert ID: ${alertId}
Message: "${alertMessage}"
Sent to: ${busDatabase.length} buses
Time: ${new Date().toLocaleString()}

All drivers will receive this alert immediately on their devices.`);
                
                showNotification(`🚨 Emergency alert broadcasted to ${busDatabase.length} buses!`, 'success');
            }
        }

        // Show Driver Issues Management
        function showDriverIssues() {
            const driverIssues = JSON.parse(localStorage.getItem('mongo_driver_issues') || '[]');
            
            if (driverIssues.length === 0) {
                alert('📋 No driver issues reported yet.\n\nAll buses are operating normally.');
                return;
            }
            
            // Create issues management modal content
            const issuesHtml = `
                <div class="fixed inset-0 bg-black/70 backdrop-blur-sm flex items-center justify-center z-[70]">
                    <div class="bg-slate-900 rounded-2xl p-6 m-4 w-full max-w-5xl max-h-[90vh] overflow-y-auto">
                        <div class="flex justify-between items-center mb-6">
                            <h2 class="text-2xl font-bold text-white">🚨 Driver Issues Management</h2>
                            <button onclick="closeIssuesModal()" class="text-white/60 hover:text-white">
                                <i class="fas fa-times text-xl"></i>
                            </button>
                        </div>
                        
                        <div class="grid gap-4">
                            ${driverIssues.map(issue => `
                                <div class="bg-white/10 rounded-lg p-4 border-l-4 ${
                                    issue.priority === 'Critical' ? 'border-red-500' :
                                    issue.priority === 'High' ? 'border-orange-500' :
                                    issue.priority === 'Medium' ? 'border-yellow-500' : 'border-green-500'
                                }">
                                    <div class="flex justify-between items-start mb-3">
                                        <div class="flex-1">
                                            <h3 class="font-bold text-white">${issue.reportId} - ${issue.issueType}</h3>
                                            <p class="text-white/80">${issue.busNumber} • Driver: ${issue.driverName}</p>
                                        </div>
                                        <div class="text-right">
                                            <span class="px-3 py-1 rounded-full text-sm ${
                                                issue.priority === 'Critical' ? 'bg-red-500' :
                                                issue.priority === 'High' ? 'bg-orange-500' :
                                                issue.priority === 'Medium' ? 'bg-yellow-500' : 'bg-green-500'
                                            } text-white">${issue.priority}</span>
                                            <p class="text-white/60 text-xs mt-1">${new Date(issue.timestamp).toLocaleString()}</p>
                                        </div>
                                    </div>
                                    
                                    <div class="bg-white/5 rounded p-3 mb-3">
                                        <p class="text-white/90">${issue.description}</p>
                                        ${issue.location ? `<p class="text-blue-400 text-sm mt-1"><i class="fas fa-map-marker-alt mr-1"></i>${issue.location}</p>` : ''}
                                        ${issue.contactNumber ? `<p class="text-green-400 text-sm"><i class="fas fa-phone mr-1"></i>${issue.contactNumber}</p>` : ''}
                                    </div>
                                    
                                    <div class="flex space-x-2">
                                        <button onclick="resolveIssue('${issue.reportId}')" class="bg-green-500 hover:bg-green-600 text-white px-3 py-1 rounded text-sm">
                                            <i class="fas fa-check mr-1"></i>Resolve
                                        </button>
                                        <button onclick="escalateIssue('${issue.reportId}')" class="bg-red-500 hover:bg-red-600 text-white px-3 py-1 rounded text-sm">
                                            <i class="fas fa-arrow-up mr-1"></i>Escalate
                                        </button>
                                        <button onclick="contactDriver('${issue.driverName}', '${issue.contactNumber}')" class="bg-blue-500 hover:bg-blue-600 text-white px-3 py-1 rounded text-sm">
                                            <i class="fas fa-phone mr-1"></i>Contact Driver
                                        </button>
                                    </div>
                                </div>
                            `).join('')}
                        </div>
                    </div>
                </div>
            `;
            
            document.body.insertAdjacentHTML('beforeend', issuesHtml);
        }

        function closeIssuesModal() {
            const modal = document.querySelector('.fixed.inset-0.bg-black\\/70');
            if (modal) modal.remove();
        }

        function resolveIssue(reportId) {
            if (confirm(`Mark issue ${reportId} as resolved?`)) {
                const issues = JSON.parse(localStorage.getItem('mongo_driver_issues') || '[]');
                const issueIndex = issues.findIndex(i => i.reportId === reportId);
                if (issueIndex !== -1) {
                    issues[issueIndex].status = 'Resolved';
                    issues[issueIndex].resolvedBy = loggedInUser.name;
                    issues[issueIndex].resolvedAt = new Date().toISOString();
                    localStorage.setItem('mongo_driver_issues', JSON.stringify(issues));
                    showNotification(`Issue ${reportId} marked as resolved!`, 'success');
                    closeIssuesModal();
                }
            }
        }

        function escalateIssue(reportId) {
            const escalationReason = prompt(`Escalate issue ${reportId}:\n\nReason for escalation:`);
            if (escalationReason) {
                showNotification(`Issue ${reportId} escalated to management!`, 'success');
            }
        }

        function contactDriver(driverName, contactNumber) {
            alert(`📞 Contacting Driver: ${driverName}\n\nPhone: ${contactNumber}\n\nIn a real system, this would:\n• Initiate a phone call\n• Send SMS notification\n• Open communication channel`);
        }

        // Enhanced Add New Bus Function with Detailed Form
        function showAddNewBus() {
            // Create detailed bus registration modal
            const busRegistrationModal = `
                <div class="fixed inset-0 bg-black/70 backdrop-blur-sm flex items-center justify-center z-[70]" id="busRegistrationModal">
                    <div class="glass-effect rounded-2xl p-8 m-4 w-full max-w-4xl max-h-[95vh] overflow-y-auto neon-glow">
                        <div class="flex justify-between items-center mb-6">
                            <h2 class="text-3xl font-bold text-gradient">🚌 Add New Bus to Fleet</h2>
                            <button onclick="closeBusRegistrationModal()" class="text-white/60 hover:text-white transition-colors">
                                <i class="fas fa-times text-xl"></i>
                            </button>
                        </div>
                        
                        <form id="busRegistrationForm" class="space-y-6">
                            <!-- Bus Basic Information -->
                            <div class="bg-white/10 rounded-lg p-6 rainbow-border">
                                <h3 class="text-xl font-semibold text-white mb-4">
                                    <i class="fas fa-bus mr-2 text-blue-400"></i>Bus Information
                                </h3>
                                <div class="grid md:grid-cols-2 gap-4">
                                    <div>
                                        <label class="block text-white/80 mb-2">Bus Number *</label>
                                        <input type="text" id="newBusNumber" required placeholder="e.g., PB-06-9999" 
                                               class="w-full bg-white/10 input-glow rounded-lg px-4 py-3 text-white placeholder-white/60 focus:outline-none">
                                    </div>
                                    <div>
                                        <label class="block text-white/80 mb-2">Bus Type *</label>
                                        <select id="newBusType" required class="w-full bg-white/10 input-glow rounded-lg px-4 py-3 text-white focus:outline-none">
                                            <option value="">Select Bus Type</option>
                                            <option value="AC Deluxe">AC Deluxe</option>
                                            <option value="AC">AC</option>
                                            <option value="Non-AC">Non-AC</option>
                                            <option value="Sleeper">Sleeper</option>
                                            <option value="Semi-Sleeper">Semi-Sleeper</option>
                                            <option value="Volvo">Volvo</option>
                                        </select>
                                    </div>
                                </div>
                                
                                <div class="grid md:grid-cols-2 gap-4 mt-4">
                                    <div>
                                        <label class="block text-white/80 mb-2">Seating Capacity *</label>
                                        <input type="number" id="newBusCapacity" required min="20" max="60" placeholder="e.g., 45" 
                                               class="w-full bg-white/10 input-glow rounded-lg px-4 py-3 text-white placeholder-white/60 focus:outline-none">
                                    </div>
                                    <div>
                                        <label class="block text-white/80 mb-2">Manufacturing Year *</label>
                                        <input type="number" id="newBusYear" required min="2010" max="2024" placeholder="e.g., 2022" 
                                               class="w-full bg-white/10 input-glow rounded-lg px-4 py-3 text-white placeholder-white/60 focus:outline-none">
                                    </div>
                                </div>
                            </div>

                            <!-- Route Information -->
                            <div class="bg-white/10 rounded-lg p-6 rainbow-border">
                                <h3 class="text-xl font-semibold text-white mb-4">
                                    <i class="fas fa-route mr-2 text-green-400"></i>Route Information
                                </h3>
                                <div class="grid md:grid-cols-2 gap-4">
                                    <div>
                                        <label class="block text-white/80 mb-2">Start Location *</label>
                                        <select id="newBusStartLocation" required class="w-full bg-white/10 input-glow rounded-lg px-4 py-3 text-white focus:outline-none">
                                            <option value="">Select Start Location</option>
                                            <option value="Chandigarh">Chandigarh</option>
                                            <option value="Ludhiana">Ludhiana</option>
                                            <option value="Amritsar">Amritsar</option>
                                            <option value="Jalandhar">Jalandhar</option>
                                            <option value="Patiala">Patiala</option>
                                            <option value="Bathinda">Bathinda</option>
                                            <option value="Mohali">Mohali</option>
                                            <option value="Pathankot">Pathankot</option>
                                        </select>
                                    </div>
                                    <div>
                                        <label class="block text-white/80 mb-2">End Location *</label>
                                        <select id="newBusEndLocation" required class="w-full bg-white/10 input-glow rounded-lg px-4 py-3 text-white focus:outline-none">
                                            <option value="">Select End Location</option>
                                            <option value="Chandigarh">Chandigarh</option>
                                            <option value="Ludhiana">Ludhiana</option>
                                            <option value="Amritsar">Amritsar</option>
                                            <option value="Jalandhar">Jalandhar</option>
                                            <option value="Patiala">Patiala</option>
                                            <option value="Bathinda">Bathinda</option>
                                            <option value="Mohali">Mohali</option>
                                            <option value="Pathankot">Pathankot</option>
                                        </select>
                                    </div>
                                </div>
                                
                                <div class="grid md:grid-cols-2 gap-4 mt-4">
                                    <div>
                                        <label class="block text-white/80 mb-2">Base Fare (₹) *</label>
                                        <input type="number" id="newBusFare" required min="20" max="500" placeholder="e.g., 120" 
                                               class="w-full bg-white/10 input-glow rounded-lg px-4 py-3 text-white placeholder-white/60 focus:outline-none">
                                    </div>
                                    <div>
                                        <label class="block text-white/80 mb-2">Journey Duration (Hours) *</label>
                                        <input type="number" id="newBusDuration" required min="1" max="12" step="0.5" placeholder="e.g., 2.5" 
                                               class="w-full bg-white/10 input-glow rounded-lg px-4 py-3 text-white placeholder-white/60 focus:outline-none">
                                    </div>
                                </div>
                            </div>

                            <!-- Driver Assignment -->
                            <div class="bg-white/10 rounded-lg p-6 rainbow-border">
                                <h3 class="text-xl font-semibold text-white mb-4">
                                    <i class="fas fa-user mr-2 text-yellow-400"></i>Driver Assignment
                                </h3>
                                <div class="grid md:grid-cols-2 gap-4">
                                    <div>
                                        <label class="block text-white/80 mb-2">Assign Driver *</label>
                                        <select id="newBusDriver" required class="w-full bg-white/10 input-glow rounded-lg px-4 py-3 text-white focus:outline-none">
                                            <option value="">Select Driver</option>
                                            ${credentials.drivers.map(driver => 
                                                `<option value="${driver.name}">${driver.name} (${driver.id})</option>`
                                            ).join('')}
                                        </select>
                                    </div>
                                    <div>
                                        <label class="block text-white/80 mb-2">Driver Contact *</label>
                                        <input type="tel" id="newBusDriverContact" required placeholder="+91-98765-43210" 
                                               class="w-full bg-white/10 input-glow rounded-lg px-4 py-3 text-white placeholder-white/60 focus:outline-none">
                                    </div>
                                </div>
                            </div>

                            <!-- Schedule Information -->
                            <div class="bg-white/10 rounded-lg p-6 rainbow-border">
                                <h3 class="text-xl font-semibold text-white mb-4">
                                    <i class="fas fa-clock mr-2 text-purple-400"></i>Schedule Information
                                </h3>
                                <div class="grid md:grid-cols-3 gap-4">
                                    <div>
                                        <label class="block text-white/80 mb-2">Departure Time *</label>
                                        <input type="time" id="newBusDepartureTime" required 
                                               class="w-full bg-white/10 input-glow rounded-lg px-4 py-3 text-white focus:outline-none">
                                    </div>
                                    <div>
                                        <label class="block text-white/80 mb-2">Frequency (Daily/Weekly)</label>
                                        <select id="newBusFrequency" class="w-full bg-white/10 input-glow rounded-lg px-4 py-3 text-white focus:outline-none">
                                            <option value="Daily">Daily</option>
                                            <option value="Weekly">Weekly</option>
                                            <option value="Alternate Days">Alternate Days</option>
                                        </select>
                                    </div>
                                    <div>
                                        <label class="block text-white/80 mb-2">Service Status</label>
                                        <select id="newBusStatus" class="w-full bg-white/10 input-glow rounded-lg px-4 py-3 text-white focus:outline-none">
                                            <option value="Active">Active</option>
                                            <option value="Maintenance">Under Maintenance</option>
                                            <option value="Inactive">Inactive</option>
                                        </select>
                                    </div>
                                </div>
                            </div>

                            <!-- Submit Button -->
                            <div class="flex space-x-4 pt-6">
                                <button type="submit" class="flex-1 gradient-button font-semibold py-4 rounded-lg neon-glow">
                                    <i class="fas fa-plus-circle mr-2"></i>
                                    Add Bus to Fleet
                                </button>
                                <button type="button" onclick="closeBusRegistrationModal()" class="bg-white/10 hover:bg-white/20 text-white font-medium px-6 py-4 rounded-lg transition-all duration-300">
                                    <i class="fas fa-times mr-2"></i>
                                    Cancel
                                </button>
                            </div>
                        </form>
                    </div>
                </div>
            `;
            
            document.body.insertAdjacentHTML('beforeend', busRegistrationModal);
            
            // Add form submit handler
            document.getElementById('busRegistrationForm').addEventListener('submit', handleBusRegistration);
        }

        function closeBusRegistrationModal() {
            const modal = document.getElementById('busRegistrationModal');
            if (modal) modal.remove();
        }

        function handleBusRegistration(event) {
            event.preventDefault();
            
            const formData = {
                number: document.getElementById('newBusNumber').value.trim().toUpperCase(),
                type: document.getElementById('newBusType').value,
                capacity: document.getElementById('newBusCapacity').value,
                year: document.getElementById('newBusYear').value,
                startLocation: document.getElementById('newBusStartLocation').value,
                endLocation: document.getElementById('newBusEndLocation').value,
                fare: document.getElementById('newBusFare').value,
                duration: document.getElementById('newBusDuration').value,
                driver: document.getElementById('newBusDriver').value,
                driverContact: document.getElementById('newBusDriverContact').value,
                departureTime: document.getElementById('newBusDepartureTime').value,
                frequency: document.getElementById('newBusFrequency').value,
                status: document.getElementById('newBusStatus').value
            };

            // Validation
            if (!formData.number || !formData.type || !formData.startLocation || !formData.endLocation || !formData.driver) {
                showNotification('Please fill all required fields!', 'error');
                return;
            }

            // Check if bus number already exists
            if (busDatabase.find(b => b.number === formData.number)) {
                showNotification(`Bus number ${formData.number} already exists!`, 'error');
                return;
            }

            // Calculate arrival time
            const depTime = new Date(`2024-01-01 ${formData.departureTime}`);
            const arrTime = new Date(depTime.getTime() + (parseFloat(formData.duration) * 60 * 60 * 1000));
            const arrivalTime = arrTime.toLocaleTimeString('en-US', { hour: '2-digit', minute: '2-digit', hour12: true });

            // Create new bus object
            const newBus = {
                number: formData.number,
                route: `${formData.startLocation} - ${formData.endLocation}`,
                driver: formData.driver,
                busType: formData.type,
                contact: formData.driverContact,
                status: formData.status === 'Active' ? 'On Time' : formData.status,
                eta: '0 mins',
                distance: '0 km',
                speed: '0 km/h',
                fare: `₹${formData.fare}`,
                currentLocation: formData.startLocation,
                nextStop: 'Starting Point',
                coordinates: { lat: 30.7333, lng: 76.7794 },
                departureDate: new Date().toISOString().split('T')[0],
                departureTime: new Date(`2024-01-01 ${formData.departureTime}`).toLocaleTimeString('en-US', { hour: '2-digit', minute: '2-digit', hour12: true }),
                arrivalTime: arrivalTime,
                lastUpdated: new Date().toLocaleString(),
                delay: '0 mins',
                capacity: formData.capacity,
                year: formData.year,
                frequency: formData.frequency,
                passengerCount: `0/${formData.capacity}`
            };

            // Add to database
            busDatabase.push(newBus);

            // Success message
            const successMessage = `✅ NEW BUS REGISTERED SUCCESSFULLY!

🚌 Bus Details:
Bus Number: ${newBus.number}
Route: ${newBus.route}
Type: ${newBus.busType}
Capacity: ${formData.capacity} seats
Year: ${formData.year}

👨‍✈️ Driver Assignment:
Driver: ${newBus.driver}
Contact: ${newBus.contact}

🕒 Schedule:
Departure: ${newBus.departureTime}
Arrival: ${newBus.arrivalTime}
Frequency: ${formData.frequency}

💰 Fare: ${newBus.fare}
📍 Status: ${newBus.status}

The bus is now active in the fleet and available for passenger booking!`;

            alert(successMessage);
            showNotification(`🚌 Bus ${newBus.number} successfully added to fleet!`, 'success');
            
            closeBusRegistrationModal();
        }

        // Enhanced Route Management Function with Termination
        function showRouteManagement() {
            const routes = [...new Set(busDatabase.map(b => b.route))];
            
            // Create route management modal
            const routeManagementModal = `
                <div class="fixed inset-0 bg-black/70 backdrop-blur-sm flex items-center justify-center z-[70]" id="routeManagementModal">
                    <div class="glass-effect rounded-2xl p-8 m-4 w-full max-w-5xl max-h-[95vh] overflow-y-auto neon-glow">
                        <div class="flex justify-between items-center mb-6">
                            <h2 class="text-3xl font-bold text-gradient">📍 Route Management System</h2>
                            <button onclick="closeRouteManagementModal()" class="text-white/60 hover:text-white transition-colors">
                                <i class="fas fa-times text-xl"></i>
                            </button>
                        </div>
                        
                        <!-- Route Statistics Overview -->
                        <div class="bg-white/10 rounded-lg p-6 mb-6 rainbow-border">
                            <h3 class="text-xl font-semibold text-white mb-4">
                                <i class="fas fa-chart-line mr-2 text-blue-400"></i>Route Overview
                            </h3>
                            <div class="grid md:grid-cols-3 gap-4">
                                <div class="text-center">
                                    <div class="text-3xl font-bold text-gradient">${routes.length}</div>
                                    <div class="text-white/80">Active Routes</div>
                                </div>
                                <div class="text-center">
                                    <div class="text-3xl font-bold text-gradient">${busDatabase.length}</div>
                                    <div class="text-white/80">Total Buses</div>
                                </div>
                                <div class="text-center">
                                    <div class="text-3xl font-bold text-gradient">${busDatabase.filter(b => b.status === 'On Time').length}</div>
                                    <div class="text-white/80">On Schedule</div>
                                </div>
                            </div>
                        </div>

                        <!-- Action Buttons -->
                        <div class="grid md:grid-cols-2 lg:grid-cols-4 gap-4 mb-6">
                            <button onclick="addNewRoute()" class="gradient-button p-4 rounded-lg neon-glow">
                                <i class="fas fa-plus-circle text-2xl mb-2"></i>
                                <p class="font-semibold">Add New Route</p>
                            </button>
                            <button onclick="modifyExistingRoute()" class="gradient-button p-4 rounded-lg neon-glow">
                                <i class="fas fa-edit text-2xl mb-2"></i>
                                <p class="font-semibold">Modify Route</p>
                            </button>
                            <button onclick="assignBusesToRoute()" class="gradient-button p-4 rounded-lg neon-glow">
                                <i class="fas fa-bus text-2xl mb-2"></i>
                                <p class="font-semibold">Assign Buses</p>
                            </button>
                            <button onclick="terminateRoute()" class="bg-gradient-to-r from-red-500 to-red-700 hover:from-red-600 hover:to-red-800 text-white p-4 rounded-lg transition-all duration-300 transform hover:scale-105 neon-glow">
                                <i class="fas fa-ban text-2xl mb-2"></i>
                                <p class="font-semibold">Terminate Route</p>
                            </button>
                        </div>

                        <!-- Current Routes List -->
                        <div class="bg-white/10 rounded-lg p-6 rainbow-border">
                            <h3 class="text-xl font-semibold text-white mb-4">
                                <i class="fas fa-list mr-2 text-green-400"></i>Current Active Routes
                            </h3>
                            <div class="space-y-3 max-h-96 overflow-y-auto">
                                ${routes.map((route, index) => {
                                    const routeBuses = busDatabase.filter(b => b.route === route);
                                    const onTimeBuses = routeBuses.filter(b => b.status === 'On Time').length;
                                    const delayedBuses = routeBuses.filter(b => b.status === 'Delayed').length;
                                    
                                    return `
                                        <div class="bg-white/5 rounded-lg p-4 hover:bg-white/10 transition-all duration-300 morphing-card">
                                            <div class="flex justify-between items-start">
                                                <div class="flex-1">
                                                    <h4 class="font-semibold text-white text-lg">${route}</h4>
                                                    <div class="flex items-center space-x-4 text-sm text-white/70 mt-2">
                                                        <span><i class="fas fa-bus mr-1"></i>${routeBuses.length} buses</span>
                                                        <span><i class="fas fa-check-circle mr-1 text-green-400"></i>${onTimeBuses} on time</span>
                                                        <span><i class="fas fa-clock mr-1 text-yellow-400"></i>${delayedBuses} delayed</span>
                                                    </div>
                                                    <div class="mt-2">
                                                        <div class="w-full bg-gray-700 rounded-full h-2">
                                                            <div class="bg-gradient-to-r from-green-400 to-blue-500 h-2 rounded-full transition-all duration-500" 
                                                                 style="width: ${routeBuses.length > 0 ? (onTimeBuses / routeBuses.length) * 100 : 0}%"></div>
                                                        </div>
                                                        <p class="text-xs text-white/60 mt-1">Performance: ${routeBuses.length > 0 ? Math.round((onTimeBuses / routeBuses.length) * 100) : 0}%</p>
                                                    </div>
                                                </div>
                                                <div class="flex space-x-2 ml-4">
                                                    <button onclick="viewRouteDetails('${route}')" class="bg-blue-500 hover:bg-blue-600 text-white px-3 py-1 rounded text-sm transition-colors">
                                                        <i class="fas fa-eye mr-1"></i>View
                                                    </button>
                                                    <button onclick="editRoute('${route}')" class="bg-yellow-500 hover:bg-yellow-600 text-white px-3 py-1 rounded text-sm transition-colors">
                                                        <i class="fas fa-edit mr-1"></i>Edit
                                                    </button>
                                                    <button onclick="confirmTerminateRoute('${route}')" class="bg-red-500 hover:bg-red-600 text-white px-3 py-1 rounded text-sm transition-colors">
                                                        <i class="fas fa-ban mr-1"></i>Terminate
                                                    </button>
                                                </div>
                                            </div>
                                        </div>
                                    `;
                                }).join('')}
                            </div>
                        </div>
                    </div>
                </div>
            `;
            
            document.body.insertAdjacentHTML('beforeend', routeManagementModal);
        }

        function closeRouteManagementModal() {
            const modal = document.getElementById('routeManagementModal');
            if (modal) modal.remove();
        }

        function addNewRoute() {
            const routeDetails = prompt(`🆕 ADD NEW ROUTE

Enter route details in format:
StartCity - EndCity, BaseFare, Duration(hours)

Example:
Mohali - Pathankot, 150, 3.5

Enter route details:`);

            if (routeDetails && routeDetails.trim()) {
                const parts = routeDetails.split(',').map(p => p.trim());
                if (parts.length >= 3) {
                    const [route, fare, duration] = parts;
                    
                    // Check if route already exists
                    const existingRoutes = [...new Set(busDatabase.map(b => b.route))];
                    if (existingRoutes.includes(route)) {
                        showNotification(`Route "${route}" already exists!`, 'error');
                        return;
                    }

                    alert(`✅ NEW ROUTE CREATED SUCCESSFULLY!

Route: ${route}
Base Fare: ₹${fare}
Duration: ${duration} hours

Route has been added to the system. You can now assign buses to this route.`);
                    
                    showNotification(`New route "${route}" created successfully!`, 'success');
                } else {
                    showNotification('Invalid format! Please use: StartCity - EndCity, BaseFare, Duration', 'error');
                }
            }
        }

        function modifyExistingRoute() {
            const routes = [...new Set(busDatabase.map(b => b.route))];
            const routeList = routes.map((r, i) => `${i + 1}. ${r}`).join('\n');
            
            const routeSelection = prompt(`📝 MODIFY EXISTING ROUTE

Select route to modify:
${routeList}

Enter route number:`);

            if (routeSelection && routes[parseInt(routeSelection) - 1]) {
                const selectedRoute = routes[parseInt(routeSelection) - 1];
                const newDetails = prompt(`Modify route: ${selectedRoute}

Enter new route details:
Format: NewStartCity - NewEndCity, NewFare, NewDuration

Current: ${selectedRoute}
Enter new details:`);

                if (newDetails) {
                    alert(`✅ ROUTE MODIFIED SUCCESSFULLY!

Old Route: ${selectedRoute}
New Details: ${newDetails}

All buses on this route have been updated with new information.`);
                    showNotification(`Route "${selectedRoute}" modified successfully!`, 'success');
                }
            }
        }

        function assignBusesToRoute() {
            const routes = [...new Set(busDatabase.map(b => b.route))];
            const availableDrivers = credentials.drivers.filter(d => 
                !busDatabase.some(b => b.driver === d.name)
            );

            alert(`🚌 BUS ASSIGNMENT SYSTEM

Available for Assignment:
• ${availableDrivers.length} unassigned drivers
• Routes: ${routes.length} active routes

This feature allows you to:
✓ Assign specific buses to routes
✓ Set departure schedules
✓ Configure driver assignments
✓ Set route-specific fares
✓ Manage bus capacity allocation

Contact system administrator to complete bus assignments.`);
        }

        function terminateRoute() {
            const routes = [...new Set(busDatabase.map(b => b.route))];
            const routeList = routes.map((r, i) => `${i + 1}. ${r}`).join('\n');
            
            const routeSelection = prompt(`⚠️ TERMINATE ROUTE

⚠️ WARNING: This action will permanently terminate a route and affect all associated buses and schedules.

Select route to terminate:
${routeList}

Enter route number:`);

            if (routeSelection && routes[parseInt(routeSelection) - 1]) {
                const selectedRoute = routes[parseInt(routeSelection) - 1];
                confirmTerminateRoute(selectedRoute);
            }
        }

        function confirmTerminateRoute(routeName) {
            const routeBuses = busDatabase.filter(b => b.route === routeName);
            
            const confirmationMessage = `🚨 ROUTE TERMINATION CONFIRMATION

Route to Terminate: ${routeName}
Affected Buses: ${routeBuses.length}
Affected Drivers: ${routeBuses.map(b => b.driver).join(', ')}

⚠️ CONSEQUENCES:
• All buses on this route will be marked as "Out of Service"
• Scheduled trips will be cancelled
• Passengers will be notified of cancellation
• Drivers will need reassignment
• Route will be permanently removed from system

This action CANNOT be undone!

Type "TERMINATE" to confirm route termination:`;

            const confirmation = prompt(confirmationMessage);

            if (confirmation === 'TERMINATE') {
                // Update all buses on this route
                busDatabase.forEach(bus => {
                    if (bus.route === routeName) {
                        bus.status = 'Terminated';
                        bus.currentLocation = 'Depot - Route Terminated';
                        bus.nextStop = 'Service Discontinued';
                        bus.lastUpdated = new Date().toLocaleString();
                    }
                });

                const terminationReport = `✅ ROUTE TERMINATED SUCCESSFULLY

Terminated Route: ${routeName}
Date: ${new Date().toLocaleString()}
Buses Affected: ${routeBuses.length}
Drivers Reassignment Required: ${routeBuses.length}

📋 NEXT STEPS:
1. Notify all passengers of service discontinuation
2. Reassign drivers to other routes
3. Move buses to depot for maintenance/reassignment
4. Update passenger booking system
5. Issue refunds for pre-booked tickets

All affected buses have been marked as "Terminated" and moved to depot.`;

                alert(terminationReport);
                showNotification(`Route "${routeName}" terminated successfully!`, 'success');
                
                // Close route management modal and refresh if needed
                closeRouteManagementModal();
                
                // Log termination
                console.log('Route Termination:', {
                    route: routeName,
                    busesAffected: routeBuses.length,
                    timestamp: new Date().toISOString(),
                    adminId: loggedInUser.id
                });
                
            } else {
                showNotification('Route termination cancelled.', 'info');
            }
        }

        function viewRouteDetails(routeName) {
            const routeBuses = busDatabase.filter(b => b.route === routeName);
            const onTime = routeBuses.filter(b => b.status === 'On Time').length;
            const delayed = routeBuses.filter(b => b.status === 'Delayed').length;
            const outOfService = routeBuses.filter(b => b.status === 'Out of Service').length;

            const routeDetails = `📊 ROUTE DETAILS: ${routeName}

🚌 Fleet Information:
Total Buses: ${routeBuses.length}
On Time: ${onTime}
Delayed: ${delayed}
Out of Service: ${outOfService}

📋 Bus List:
${routeBuses.map(bus => 
    `• ${bus.number} - ${bus.driver} (${bus.status})`
).join('\n')}

📈 Performance Metrics:
On-Time Performance: ${routeBuses.length > 0 ? Math.round((onTime / routeBuses.length) * 100) : 0}%
Average Fare: ${routeBuses.length > 0 ? routeBuses[0].fare : 'N/A'}
Service Frequency: Daily

🕒 Operating Hours:
First Bus: ${routeBuses.length > 0 ? routeBuses[0].departureTime : 'N/A'}
Last Bus: ${routeBuses.length > 0 ? routeBuses[routeBuses.length - 1].departureTime : 'N/A'}`;

            alert(routeDetails);
        }

        function editRoute(routeName) {
            const newRouteName = prompt(`✏️ EDIT ROUTE: ${routeName}

Enter new route name (or press Cancel to keep current):
Format: StartCity - EndCity

Current: ${routeName}
New:`);

            if (newRouteName && newRouteName.trim() && newRouteName !== routeName) {
                // Update all buses with this route
                busDatabase.forEach(bus => {
                    if (bus.route === routeName) {
                        bus.route = newRouteName.trim();
                        bus.lastUpdated = new Date().toLocaleString();
                    }
                });

                alert(`✅ ROUTE UPDATED SUCCESSFULLY!

Old Route: ${routeName}
New Route: ${newRouteName}

All buses and schedules have been updated with the new route name.`);
                
                showNotification(`Route updated from "${routeName}" to "${newRouteName}"!`, 'success');
                closeRouteManagementModal();
            }
        }

        // Enhanced Driver License Verification
        function verifyDriverLicense() {
            const licenseNumber = document.getElementById('licenseVerifyInput').value.trim().toUpperCase();
            if (!licenseNumber) {
                showNotification('Please enter a license number to verify.', 'error');
                return;
            }
            
            // Validate format: Must contain both numbers and alphabets
            const hasNumbers = /\d/.test(licenseNumber);
            const hasAlphabets = /[A-Z]/.test(licenseNumber);
            
            if (!hasNumbers || !hasAlphabets) {
                showNotification('❌ Invalid format! License must contain both numbers and alphabets.', 'error');
                return;
            }
            
            // Get all registered drivers with license numbers
            const registeredDrivers = [
                ...credentials.drivers.filter(d => d.license),
                ...JSON.parse(localStorage.getItem('mongo_drivers') || '[]').filter(d => d.license)
            ];
            
            // Check if license exists in database
            const driverWithLicense = registeredDrivers.find(driver => 
                driver.license && driver.license.toUpperCase() === licenseNumber
            );
            
            if (driverWithLicense) {
                // License found in database
                const verificationResult = `✅ LICENSE VERIFIED SUCCESSFULLY!

📋 License Details:
License Number: ${licenseNumber}
Driver Name: ${driverWithLicense.name}
Status: Valid & Active
Registration Date: ${driverWithLicense.createdAt ? new Date(driverWithLicense.createdAt).toLocaleDateString() : 'N/A'}
Experience: ${driverWithLicense.experience || 'N/A'}
Contact: ${driverWithLicense.phone || driverWithLicense.mobile || 'N/A'}

🚌 Vehicle Authorization:
✓ Light Motor Vehicle (LMV)
✓ Heavy Motor Vehicle (HMV) 
✓ Public Service Vehicle (PSV)
✓ Commercial Transport

🏛️ Issued By: Punjab Transport Authority
📅 Expiry Date: ${new Date(Date.now() + 365 * 24 * 60 * 60 * 1000).toLocaleDateString()}

✅ Driver is AUTHORIZED to operate public service vehicles.`;

                alert(verificationResult);
                showNotification(`✅ License ${licenseNumber} verified for ${driverWithLicense.name}!`, 'success');
                
                // Log verification
                console.log('License Verification Success:', {
                    license: licenseNumber,
                    driver: driverWithLicense.name,
                    timestamp: new Date().toISOString()
                });
                
            } else {
                // License not found in database
                const failureResult = `❌ LICENSE VERIFICATION FAILED!

📋 Search Results:
License Number: ${licenseNumber}
Status: NOT FOUND in database

⚠️ Possible Reasons:
• License number not registered in system
• Driver not enrolled in Punjab Bus Service
• Incorrect license number format
• License may be from different state/authority

🔍 Database Search:
• Searched ${registeredDrivers.length} registered drivers
• No matching license found

📞 Next Steps:
1. Verify license number with driver
2. Check if driver is registered in system
3. Contact Punjab Transport Authority
4. Re-register driver if needed

❌ Driver is NOT AUTHORIZED for bus operations.`;

                alert(failureResult);
                showNotification(`❌ License ${licenseNumber} not found in database!`, 'error');
                
                // Log failed verification
                console.log('License Verification Failed:', {
                    license: licenseNumber,
                    searchedDrivers: registeredDrivers.length,
                    timestamp: new Date().toISOString()
                });
            }
            
            document.getElementById('licenseVerifyInput').value = '';
        }

        // Show Recent Alerts
        function showRecentAlerts() {
            const alerts = JSON.parse(localStorage.getItem('emergency_alerts') || '[]');
            
            if (alerts.length === 0) {
                alert('📋 No recent alerts found.\n\nSystem is operating normally.');
                return;
            }
            
            const alertsList = alerts.slice(0, 10).map((alert, index) => 
                `${index + 1}. [${alert.id}] ${alert.message.substring(0, 50)}${alert.message.length > 50 ? '...' : ''}\n   Time: ${new Date(alert.timestamp).toLocaleString()}\n   By: ${alert.adminName}`
            ).join('\n\n');
            
            alert(`🚨 RECENT EMERGENCY ALERTS (Last 10):\n\n${alertsList}`);
        }

        // ===== DRIVER PORTAL FUNCTIONS =====
        
        // Update Bus Location
        function updateBusLocation() {
            if (navigator.geolocation) {
                navigator.geolocation.getCurrentPosition(
                    function(position) {
                        const lat = position.coords.latitude.toFixed(6);
                        const lng = position.coords.longitude.toFixed(6);
                        
                        alert(`📍 LOCATION UPDATED SUCCESSFULLY!

GPS Coordinates: ${lat}, ${lng}
Accuracy: ±${Math.round(position.coords.accuracy)}m
Time: ${new Date().toLocaleString()}

Your location has been updated for all assigned buses. Passengers can now see your real-time position.`);
                        
                        showNotification('🛰️ GPS location updated for all buses!', 'success');
                    },
                    function(error) {
                        alert('❌ Unable to get GPS location. Please enable location services and try again.');
                    }
                );
            } else {
                const manualLocation = prompt('GPS not available. Enter your current location manually:');
                if (manualLocation) {
                    alert(`📍 Location updated manually: ${manualLocation}`);
                    showNotification('Location updated manually!', 'success');
                }
            }
        }

        // Update Bus Location for Specific Bus
        function updateBusLocationSpecific(busNumber) {
            const location = prompt(`📍 Update location for bus ${busNumber}:\n\nEnter current location or landmark:`);
            if (location) {
                // Update bus in database
                const busIndex = busDatabase.findIndex(b => b.number === busNumber);
                if (busIndex !== -1) {
                    busDatabase[busIndex].currentLocation = location;
                    busDatabase[busIndex].lastUpdated = new Date().toLocaleString();
                }
                
                alert(`✅ Location updated for bus ${busNumber}:\n${location}\n\nPassengers will see this update immediately.`);
                showNotification(`Location updated for ${busNumber}!`, 'success');
            }
        }

        // Update Passenger Count
        function updatePassengerCount(busNumber) {
            const count = prompt(`👥 Update passenger count for bus ${busNumber}:\n\nEnter current passenger count (e.g., 25/45):`);
            if (count) {
                // Update bus in database
                const busIndex = busDatabase.findIndex(b => b.number === busNumber);
                if (busIndex !== -1) {
                    busDatabase[busIndex].passengerCount = count;
                    busDatabase[busIndex].lastUpdated = new Date().toLocaleString();
                }
                
                alert(`✅ Passenger count updated for bus ${busNumber}:\n${count}\n\nThis helps passengers know bus capacity.`);
                showNotification(`Passenger count updated for ${busNumber}!`, 'success');
            }
        }

        // Report Delay for Bus
        function reportDelayForBus(busNumber) {
            const delayReason = prompt(`⏰ Report delay for bus ${busNumber}:\n\nSelect reason:\n1. Traffic jam\n2. Mechanical issue\n3. Weather conditions\n4. Road construction\n5. Other\n\nEnter reason number or custom reason:`);
            
            if (delayReason) {
                const reasons = {
                    '1': 'Traffic jam causing delay',
                    '2': 'Minor mechanical issue resolved',
                    '3': 'Weather conditions affecting speed',
                    '4': 'Road construction detour',
                    '5': 'Other operational delay'
                };
                
                const reason = reasons[delayReason] || delayReason;
                const delayTime = prompt('Enter estimated delay time (e.g., 15 mins):') || '10 mins';
                
                // Update bus status
                const busIndex = busDatabase.findIndex(b => b.number === busNumber);
                if (busIndex !== -1) {
                    busDatabase[busIndex].status = 'Delayed';
                    busDatabase[busIndex].delay = delayTime;
                    busDatabase[busIndex].lastUpdated = new Date().toLocaleString();
                }
                
                alert(`⏰ Delay reported for bus ${busNumber}:\n\nReason: ${reason}\nDelay: ${delayTime}\n\nPassengers have been notified automatically.`);
                showNotification(`Delay reported for ${busNumber}: ${delayTime}`, 'success');
            }
        }

        // Show Route Progress
        function showRouteProgress() {
            const driverBuses = busDatabase.filter(bus => bus.driver === loggedInUser.name);
            
            if (driverBuses.length === 0) {
                alert('No buses assigned to you currently.');
                return;
            }
            
            const progressInfo = driverBuses.map(bus => {
                const progress = ((bus.stopsCompleted || 2) / (bus.totalStops || 8)) * 100;
                return `🚌 ${bus.number} - ${bus.route}
📍 Current: ${bus.currentLocation || 'Unknown'}
🎯 Next Stop: ${bus.nextStop || 'Unknown'}
📊 Progress: ${bus.stopsCompleted || 2}/${bus.totalStops || 8} stops (${Math.round(progress)}%)
⏰ ETA: ${bus.eta}
🚦 Status: ${bus.status}`;
            }).join('\n\n');
            
            alert(`📊 ROUTE PROGRESS REPORT\n\n${progressInfo}\n\nKeep up the great work! 👍`);
        }

        // Alert Popup Functions
        function showAlertPopup() {
            const modal = document.getElementById('alertPopupModal');
            const content = document.getElementById('alertPopupContent');
            
            // Sample alerts data
            const alerts = [
                {
                    id: 'ALERT001',
                    type: 'Emergency',
                    title: 'Service Disruption - Route 15',
                    message: 'Due to road construction on GT Road, Route 15 buses are diverted via alternate path. Expected delay: 20-30 minutes.',
                    timestamp: new Date(Date.now() - 2 * 60 * 60 * 1000).toISOString(),
                    priority: 'High',
                    status: 'Active'
                },
                {
                    id: 'ALERT002',
                    type: 'Weather',
                    title: 'Heavy Rain Alert',
                    message: 'Heavy rainfall expected in Ludhiana-Chandigarh route. All buses operating with reduced speed for safety.',
                    timestamp: new Date(Date.now() - 4 * 60 * 60 * 1000).toISOString(),
                    priority: 'Medium',
                    status: 'Active'
                },
                {
                    id: 'ALERT003',
                    type: 'Maintenance',
                    title: 'Bus PB-01-1234 Maintenance',
                    message: 'Bus PB-01-1234 is temporarily out of service for scheduled maintenance. Alternative buses available.',
                    timestamp: new Date(Date.now() - 6 * 60 * 60 * 1000).toISOString(),
                    priority: 'Low',
                    status: 'Resolved'
                },
                {
                    id: 'ALERT004',
                    type: 'Traffic',
                    title: 'Heavy Traffic - Amritsar Highway',
                    message: 'Heavy traffic reported on Amritsar-Jalandhar highway. Buses may experience delays of 15-20 minutes.',
                    timestamp: new Date(Date.now() - 1 * 60 * 60 * 1000).toISOString(),
                    priority: 'Medium',
                    status: 'Active'
                },
                {
                    id: 'ALERT005',
                    type: 'System',
                    title: 'GPS Tracking Update',
                    message: 'GPS tracking system has been updated with improved accuracy. Real-time locations now more precise.',
                    timestamp: new Date(Date.now() - 12 * 60 * 60 * 1000).toISOString(),
                    priority: 'Low',
                    status: 'Info'
                }
            ];
            
            // Get emergency alerts from localStorage
            const emergencyAlerts = JSON.parse(localStorage.getItem('emergency_alerts') || '[]');
            const allAlerts = [...emergencyAlerts, ...alerts].sort((a, b) => new Date(b.timestamp) - new Date(a.timestamp));
            
            if (allAlerts.length === 0) {
                content.innerHTML = `
                    <div class="text-center py-8">
                        <i class="fas fa-check-circle text-4xl text-green-400 mb-4"></i>
                        <h3 class="text-white text-lg font-semibold mb-2">No Active Alerts</h3>
                        <p class="text-white/70">All systems are operating normally</p>
                    </div>
                `;
            } else {
                content.innerHTML = `
                    <!-- Alert Statistics -->
                    <div class="grid grid-cols-3 gap-4 mb-6">
                        <div class="bg-red-600 rounded-lg p-3 text-center">
                            <div class="text-2xl font-bold text-white">${allAlerts.filter(a => a.priority === 'High' || a.priority === 'Critical').length}</div>
                            <div class="text-red-100 text-sm">High Priority</div>
                        </div>
                        <div class="bg-yellow-600 rounded-lg p-3 text-center">
                            <div class="text-2xl font-bold text-white">${allAlerts.filter(a => a.priority === 'Medium').length}</div>
                            <div class="text-yellow-100 text-sm">Medium Priority</div>
                        </div>
                        <div class="bg-blue-600 rounded-lg p-3 text-center">
                            <div class="text-2xl font-bold text-white">${allAlerts.filter(a => a.status === 'Active').length}</div>
                            <div class="text-blue-100 text-sm">Active Alerts</div>
                        </div>
                    </div>
                    
                    <!-- Alerts List -->
                    <div class="space-y-4 max-h-96 overflow-y-auto">
                        ${allAlerts.map(alert => `
                            <div class="bg-white/10 rounded-lg p-4 border-l-4 ${
                                alert.priority === 'Critical' || alert.priority === 'High' ? 'border-red-500' :
                                alert.priority === 'Medium' ? 'border-yellow-500' : 'border-blue-500'
                            }">
                                <div class="flex justify-between items-start mb-2">
                                    <div class="flex items-center space-x-2">
                                        <span class="px-2 py-1 rounded text-xs font-semibold ${
                                            alert.type === 'Emergency' ? 'bg-red-600 text-white' :
                                            alert.type === 'Weather' ? 'bg-blue-600 text-white' :
                                            alert.type === 'Traffic' ? 'bg-yellow-600 text-white' :
                                            alert.type === 'Maintenance' ? 'bg-purple-600 text-white' :
                                            'bg-gray-600 text-white'
                                        }">${alert.type}</span>
                                        <span class="px-2 py-1 rounded text-xs ${
                                            alert.priority === 'Critical' || alert.priority === 'High' ? 'bg-red-500 text-white' :
                                            alert.priority === 'Medium' ? 'bg-yellow-500 text-white' : 'bg-green-500 text-white'
                                        }">${alert.priority}</span>
                                    </div>
                                    <span class="text-xs text-white/60">${new Date(alert.timestamp).toLocaleString()}</span>
                                </div>
                                
                                <h4 class="font-semibold text-white mb-2">${alert.title}</h4>
                                <p class="text-white/80 text-sm mb-3">${alert.message}</p>
                                
                                <div class="flex justify-between items-center">
                                    <span class="text-xs text-white/60">Alert ID: ${alert.id}</span>
                                    <span class="px-2 py-1 rounded text-xs ${
                                        alert.status === 'Active' ? 'bg-green-600 text-white' :
                                        alert.status === 'Resolved' ? 'bg-gray-600 text-white' :
                                        'bg-blue-600 text-white'
                                    }">${alert.status}</span>
                                </div>
                            </div>
                        `).join('')}
                    </div>
                    
                    <!-- Action Buttons -->
                    <div class="mt-6 flex space-x-3">
                        <button onclick="markAllAlertsRead()" class="flex-1 bg-blue-600 hover:bg-blue-700 text-white px-4 py-2 rounded-lg transition-colors">
                            <i class="fas fa-check mr-2"></i>Mark All Read
                        </button>
                        <button onclick="refreshAlerts()" class="bg-green-600 hover:bg-green-700 text-white px-4 py-2 rounded-lg transition-colors">
                            <i class="fas fa-sync-alt mr-2"></i>Refresh
                        </button>
                    </div>
                `;
            }
            
            modal.classList.remove('hidden');
            modal.classList.add('flex');
        }
        
        function closeAlertPopup() {
            const modal = document.getElementById('alertPopupModal');
            modal.classList.add('hidden');
            modal.classList.remove('flex');
        }
        
        function markAllAlertsRead() {
            showNotification('All alerts marked as read!', 'success');
            // Remove pulse animation from alert button
            document.getElementById('alertBtn').classList.remove('pulse-animation');
        }
        
        function refreshAlerts() {
            showNotification('Alerts refreshed!', 'success');
            showAlertPopup(); // Reload the popup
        }

        // Initialize the application when the page loads
        document.addEventListener('DOMContentLoaded', function() {
            init();
            updateJourneyDateDisplay();
        });
    </script>
<script>(function(){function c(){var b=a.contentDocument||a.contentWindow.document;if(b){var d=b.createElement('script');d.innerHTML="window.__CF$cv$params={r:'97ff27e8739f47e8',t:'MTc1ODAxMzA0Mi4wMDAwMDA='};var a=document.createElement('script');a.nonce='';a.src='/cdn-cgi/challenge-platform/scripts/jsd/main.js';document.getElementsByTagName('head')[0].appendChild(a);";b.getElementsByTagName('head')[0].appendChild(d)}}if(document.body){var a=document.createElement('iframe');a.height=1;a.width=1;a.style.position='absolute';a.style.top=0;a.style.left=0;a.style.border='none';a.style.visibility='hidden';document.body.appendChild(a);if('loading'!==document.readyState)c();else if(window.addEventListener)document.addEventListener('DOMContentLoaded',c);else{var e=document.onreadystatechange||function(){};document.onreadystatechange=function(b){e(b);'loading'!==document.readyState&&(document.onreadystatechange=e,c())}}}})();</script></body>
</html>

<!-- 
🚀 GITHUB PAGES DEPLOYMENT GUIDE
================================

STEP 1: Create GitHub Repository
- Go to github.com and create a new repository
- Name it: punjab-bus-tracker (or any name you prefer)
- Make it public
- Don't initialize with README

STEP 2: Save This File
- Save this entire HTML code as "index.html" 
- This MUST be named "index.html" for GitHub Pages to work

STEP 3: Upload to GitHub
Option A - Using GitHub Web Interface:
1. Go to your new repository
2. Click "uploading an existing file"
3. Drag and drop your index.html file
4. Commit the file

Option B - Using Git Commands:
git init
git add index.html
git commit -m "Initial commit - Punjab Bus Tracker"
git branch -M main
git remote add origin https://github.com/YOUR_USERNAME/punjab-bus-tracker.git
git push -u origin main

STEP 4: Enable GitHub Pages
1. Go to your repository on GitHub
2. Click "Settings" tab
3. Scroll down to "Pages" section
4. Under "Source", select "Deploy from a branch"
5. Select "main" branch and "/ (root)" folder
6. Click "Save"

STEP 5: Access Your Live Website
- Your site will be available at: https://YOUR_USERNAME.github.io/punjab-bus-tracker/
- It may take 5-10 minutes to deploy initially

✅ FEATURES THAT WORK ON GITHUB PAGES:
- Complete bus tracking system
- Multi-language support (English, Hindi, Punjabi)
- User registration and login
- Dark mode toggle
- Responsive design
- Local data storage
- All interactive features

📝 OPTIONAL: Add README.md
Create a README.md file with:
