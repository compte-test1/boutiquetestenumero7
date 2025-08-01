# boutiquetestenumero7
<!DOCTYPE html>
<html lang="fr">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title id="siteTitle">NG_chopi_DIAMS - Boutique de Luxe</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        .gold-text {
            background: linear-gradient(135deg, #fbbf24, #f59e0b, #d97706);
            -webkit-background-clip: text;
            background-clip: text;
            color: transparent;
        }
        .product-card:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 25px rgba(251, 191, 36, 0.2);
        }
        .cart-badge {
            animation: bounce 0.5s;
        }
        @keyframes bounce {
            0%, 100% { transform: translateY(0); }
            50% { transform: translateY(-5px); }
        }
    </style>
</head>
<body class="bg-gray-900 text-gray-100">
    <!-- Header -->
    <header class="bg-gradient-to-r from-black via-gray-900 to-black border-b border-yellow-400 sticky top-0 z-50">
        <div class="container mx-auto px-4 py-4 flex justify-between items-center">
            <div class="flex items-center space-x-2">
                <h1 id="siteTitleHeader" class="text-3xl font-bold gold-text">NG_chopi</h1>
                <span id="siteSubtitle" class="text-yellow-400 font-semibold">DIAMS</span>
            </div>
            
            <div class="hidden md:flex space-x-6 items-center">
                <a href="#" id="navNew" class="text-gray-300 hover:text-yellow-400">Nouveautés</a>
                <a href="#" id="navWomen" class="text-gray-300 hover:text-yellow-400">Femmes</a>
                <a href="#" id="navMen" class="text-gray-300 hover:text-yellow-400">Hommes</a>
                <a href="#" id="navCollection" class="text-yellow-400 font-bold">COLLECTION</a>
                <select id="languageSelector" class="language-selector text-black rounded px-2 py-1 ml-4">
                  <option value="fr">Français</option>
                  <option value="en">English</option>
                  <option value="ln">Lingala</option>
                </select>
            </div>
            
            <div class="flex items-center space-x-4">
                <button id="adminBtn" class="text-yellow-400 hover:text-yellow-300" title="Admin">
                    <!-- SVG admin icon -->
                    <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M10.325 4.317c.426-1.756 2.924-1.756 3.35 0a1.724 1.724 0 002.573 1.066c1.543-.94 3.31.826 2.37 2.37a1.724 1.724 0 001.065 2.572c1.756.426 1.756 2.924 0 3.35a1.724 1.724 0 00-1.066 2.573c.94 1.543-.826 3.31-2.37 2.37a1.724 1.724 0 00-2.572 1.065c-.426 1.756-2.924 1.756-3.35 0a1.724 1.724 0 00-2.573-1.066c-1.543.94-3.31-.826-2.37-2.37a1.724 1.724 0 00-1.065-2.572c-1.756-.426-1.756-2.924 0-3.35a1.724 1.724 0 001.066-2.573c-.94-1.543.826-3.31 2.37-2.37.996.608 2.296.07 2.572-1.065z" />
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M15 12a3 3 0 11-6 0 3 3 0 016 0z" />
                    </svg>
                </button>
                <button id="cartBtn" class="relative text-yellow-400 hover:text-yellow-300" title="Panier">
                    <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                        <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M3 3h2l.4 2M7 13h10l4-8H5.4M7 13L5.4 5M7 13l-2.293 2.293c-.63.63-.184 1.707.707 1.707H17m0 0a2 2 0 100 4 2 2 0 000-4zm-8 2a2 2 0 11-4 0 2 2 0 014 0z" />
                    </svg>
                    <span id="cartCount" class="absolute -top-2 -right-2 bg-yellow-400 text-black text-xs rounded-full h-5 w-5 flex items-center justify-center font-bold hidden">0</span>
                </button>
            </div>
        </div>
    </header>

    <!-- Bannière Hero -->
    <section class="bg-gradient-to-r from-yellow-400 to-yellow-600 text-black py-16 text-center">
        <div class="container mx-auto px-4">
            <h2 id="heroTitle" class="text-4xl md:text-5xl font-bold mb-4">COLLECTION EXCLUSIVE</h2>
            <p id="heroSubtitle" class="text-xl mb-8">Articles de luxe à prix exceptionnels</p>
            <button id="heroButton" class="bg-black text-yellow-400 px-8 py-3 rounded-full font-bold hover:bg-gray-900 transition">
                Découvrir
            </button>
        </div>
    </section>

    <!-- Produits -->
    <section class="container mx-auto px-4 py-12">
        <div class="grid grid-cols-1 sm:grid-cols-2 md:grid-cols-3 lg:grid-cols-4 gap-8" id="productsContainer">
            <!-- Les produits seront chargés ici par JavaScript -->
        </div>
    </section>

    <!-- Panier -->
    <div id="cartOverlay" class="fixed inset-0 bg-black bg-opacity-75 z-50 hidden">
        <div class="absolute right-0 top-0 h-full w-full max-w-md bg-gray-900 border-l border-yellow-400 overflow-y-auto">
            <div class="p-6">
                <div class="flex justify-between items-center mb-6">
                    <h2 id="cartTitle" class="text-xl font-bold text-yellow-400">Votre Panier</h2>
                    <button id="closeCart" class="text-yellow-400 hover:text-yellow-300">
                        <svg class="w-6 h-6" fill="none" stroke="currentColor" viewBox="0 0 24 24">
                            <path stroke-linecap="round" stroke-linejoin="round" stroke-width="2" d="M6 18L18 6M6 6l12 12" />
                        </svg>
                    </button>
                </div>
                
                <div id="cartItems" class="space-y-4 mb-6">
                    <p id="cartEmpty" class="text-gray-400 text-center py-12">Votre panier est vide</p>
                </div>
                
                <div class="border-t border-yellow-400/30 pt-6">
                    <div class="flex justify-between items-center mb-6">
                        <span id="cartTotalLabel" class="text-lg font-semibold">Total:</span>
                        <span id="cartTotal" class="text-xl font-bold gold-text">0 FCFA</span>
                    </div>
                    <!-- Formulaire client -->
                    <div id="clientForm" class="hidden">
                        <div class="mb-4">
                            <label id="clientNameLabel" class="block text-yellow-400 mb-2">Nom et Prénom</label>
                            <input type="text" id="clientName" class="w-full bg-gray-800 border border-yellow-400/30 rounded-lg px-4 py-2 focus:outline-none focus:ring-2 focus:ring-yellow-400" required>
                        </div>
                        <div class="mb-4">
                            <label id="clientPhoneLabel" class="block text-yellow-400 mb-2">Numéro de téléphone</label>
                            <input type="tel" id="clientPhone" class="w-full bg-gray-800 border border-yellow-400/30 rounded-lg px-4 py-2 focus:outline-none focus:ring-2 focus:ring-yellow-400" required>
                        </div>
                        <div class="mb-4">
                            <label id="clientCityLabel" class="block text-yellow-400 mb-2">Ville</label>
                            <input type="text" id="clientCity" class="w-full bg-gray-800 border border-yellow-400/30 rounded-lg px-4 py-2 focus:outline-none focus:ring-2 focus:ring-yellow-400" required>
                        </div>
                        <div class="mb-4">
                            <label id="clientNeighborhoodLabel" class="block text-yellow-400 mb-2">Quartier</label>
                            <input type="text" id="clientNeighborhood" class="w-full bg-gray-800 border border-yellow-400/30 rounded-lg px-4 py-2 focus:outline-none focus:ring-2 focus:ring-yellow-400" required>
                        </div>
                        <div class="mb-6">
                            <label id="clientStreetLabel" class="block text-yellow-400 mb-2">Rue et Numéro</label>
                            <input type="text" id="clientStreet" class="w-full bg-gray-800 border border-yellow-400/30 rounded-lg px-4 py-2 focus:outline-none focus:ring-2 focus:ring-yellow-400" required>
                        </div>
                        <button id="confirmOrderBtn" class="w-full bg-gradient-to-r from-green-500 to-green-600 text-white py-3 rounded-lg font-bold hover:opacity-90 transition">
                            Confirmer la commande
                        </button>
                    </div>
                    <button id="validateOrderBtn" class="w-full bg-gradient-to-r from-yellow-400 to-yellow-600 text-black py-3 rounded-lg font-bold hover:opacity-90 transition">
                        Valider votre commande
                    </button>
                </div>
            </div>
        </div>
    </div>
    <!-- ... (le reste de ton code, y compris JS etc.) ... -->

<script>
/* Ajoute ce script tout à la fin de ton body (juste avant </body>) */
const translations = {
  fr: {
    siteTitle: "NG_chopi_DIAMS - Boutique de Luxe",
    siteTitleHeader: "NG_chopi",
    siteSubtitle: "DIAMS",
    navNew: "Nouveautés",
    navWomen: "Femmes",
    navMen: "Hommes",
    navCollection: "COLLECTION",
    heroTitle: "COLLECTION EXCLUSIVE",
    heroSubtitle: "Articles de luxe à prix exceptionnels",
    heroButton: "Découvrir",
    cartTitle: "Votre Panier",
    cartEmpty: "Votre panier est vide",
    cartTotalLabel: "Total:",
    validateOrderBtn: "Valider votre commande",
    confirmOrderBtn: "Confirmer la commande",
    clientNameLabel: "Nom et Prénom",
    clientPhoneLabel: "Numéro de téléphone",
    clientCityLabel: "Ville",
    clientNeighborhoodLabel: "Quartier",
    clientStreetLabel: "Rue et Numéro"
  },
  en: {
    siteTitle: "NG_chopi_DIAMS - Luxury Boutique",
    siteTitleHeader: "NG_chopi",
    siteSubtitle: "DIAMS",
    navNew: "New",
    navWomen: "Women",
    navMen: "Men",
    navCollection: "COLLECTION",
    heroTitle: "EXCLUSIVE COLLECTION",
    heroSubtitle: "Luxury items at exceptional prices",
    heroButton: "Discover",
    cartTitle: "Your Cart",
    cartEmpty: "Your cart is empty",
    cartTotalLabel: "Total:",
    validateOrderBtn: "Validate your order",
    confirmOrderBtn: "Confirm order",
    clientNameLabel: "Full Name",
    clientPhoneLabel: "Phone number",
    clientCityLabel: "City",
    clientNeighborhoodLabel: "Neighborhood",
    clientStreetLabel: "Street and Number"
  },
  ln: {
    siteTitle: "NG_chopi_DIAMS - Boutique ya Motuya",
    siteTitleHeader: "NG_chopi",
    siteSubtitle: "DIAMS",
    navNew: "Ya sika",
    navWomen: "Basi",
    navMen: "Mobali",
    navCollection: "BOKOLE",
    heroTitle: "BOKOLE YA KAKA",
    heroSubtitle: "Biloko ya motuya na motuya ya kitoko",
    heroButton: "Kumona",
    cartTitle: "Panier na yo",
    cartEmpty: "Panier na yo ezali mpamba",
    cartTotalLabel: "Total:",
    validateOrderBtn: "Kokakola commande na yo",
    confirmOrderBtn: "Kondima commande",
    clientNameLabel: "Kombo na yo",
    clientPhoneLabel: "Numero ya telefone",
    clientCityLabel: "Engumba",
    clientNeighborhoodLabel: "Quartier",
    clientStreetLabel: "Avenue na numero"
  }
};

function updateLanguage(lang) {
  for(const key in translations[lang]) {
    const el = document.getElementById(key);
    if(el) el.textContent = translations[lang][key];
    // Exception : title du <head>
    if(key === "siteTitle" && document.title !== translations[lang][key]) {
      document.title = translations[lang][key];
    }
  }
}

document.getElementById('languageSelector').addEventListener('change', function(e) {
  updateLanguage(e.target.value);
});

updateLanguage('fr');
</script>
</body>
</html>
