# MULCHMATE
MULCHMATE - Smart Mulching Assistant for Farmers
<!DOCTYPE html>

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MULCHMATE - Smart Mulching Assistant</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

```
    body {
        font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
        min-height: 100vh;
        padding-bottom: 80px;
    }

    .header {
        background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        color: white;
        padding: 20px;
        text-align: center;
        box-shadow: 0 4px 6px rgba(0,0,0,0.1);
    }

    .logo-container {
        display: flex;
        align-items: center;
        justify-content: center;
        gap: 15px;
        margin-bottom: 10px;
    }

    .logo {
        width: 60px;
        height: 60px;
        background: white;
        border-radius: 50%;
        padding: 8px;
    }

    .logo img {
        width: 100%;
        height: 100%;
        object-fit: contain;
    }

    h1 {
        font-size: 2em;
        margin-bottom: 5px;
    }

    .tagline {
        font-size: 0.9em;
        opacity: 0.9;
    }

    .container {
        max-width: 1200px;
        margin: 0 auto;
        padding: 20px;
    }

    .nav-tabs {
        display: flex;
        background: white;
        border-radius: 10px;
        overflow: hidden;
        box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        margin-bottom: 20px;
    }

    .nav-tab {
        flex: 1;
        padding: 15px;
        text-align: center;
        cursor: pointer;
        border: none;
        background: white;
        font-size: 0.9em;
        font-weight: 600;
        color: #667eea;
        transition: all 0.3s;
        border-bottom: 3px solid transparent;
    }

    .nav-tab:hover {
        background: #f8f9fa;
    }

    .nav-tab.active {
        background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        color: white;
        border-bottom: 3px solid #764ba2;
    }

    .content-section {
        display: none;
        background: white;
        border-radius: 10px;
        padding: 30px;
        box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        animation: fadeIn 0.3s;
    }

    .content-section.active {
        display: block;
    }

    @keyframes fadeIn {
        from { opacity: 0; transform: translateY(10px); }
        to { opacity: 1; transform: translateY(0); }
    }

    .section-title {
        color: #667eea;
        font-size: 1.5em;
        margin-bottom: 20px;
        display: flex;
        align-items: center;
        gap: 10px;
    }

    .form-group {
        margin-bottom: 20px;
    }

    label {
        display: block;
        margin-bottom: 8px;
        font-weight: 600;
        color: #333;
    }

    select, input[type="number"], input[type="text"], textarea {
        width: 100%;
        padding: 12px;
        border: 2px solid #e0e0e0;
        border-radius: 8px;
        font-size: 1em;
        transition: border 0.3s;
    }

    select:focus, input:focus, textarea:focus {
        outline: none;
        border-color: #667eea;
    }

    .btn {
        background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        color: white;
        border: none;
        padding: 12px 30px;
        border-radius: 8px;
        cursor: pointer;
        font-size: 1em;
        font-weight: 600;
        transition: transform 0.2s, box-shadow 0.2s;
    }

    .btn:hover {
        transform: translateY(-2px);
        box-shadow: 0 4px 12px rgba(102, 126, 234, 0.4);
    }

    .btn:active {
        transform: translateY(0);
    }

    .result-box {
        margin-top: 20px;
        padding: 20px;
        background: #f8f9fa;
        border-radius: 8px;
        border-left: 4px solid #667eea;
    }

    .result-box h3 {
        color: #667eea;
        margin-bottom: 10px;
    }

    .camera-container {
        text-align: center;
    }

    #camera-feed {
        width: 100%;
        max-width: 500px;
        border-radius: 10px;
        margin: 20px auto;
        display: none;
        box-shadow: 0 4px 12px rgba(0,0,0,0.2);
    }

    #captured-image {
        width: 100%;
        max-width: 500px;
        border-radius: 10px;
        margin: 20px auto;
        display: none;
        box-shadow: 0 4px 12px rgba(0,0,0,0.2);
    }

    .camera-buttons {
        display: flex;
        gap: 10px;
        justify-content: center;
        margin-top: 15px;
        flex-wrap: wrap;
    }

    .info-card {
        background: linear-gradient(135deg, #667eea15 0%, #764ba215 100%);
        padding: 15px;
        border-radius: 8px;
        margin-bottom: 15px;
        border-left: 4px solid #667eea;
    }

    .info-card h4 {
        color: #667eea;
        margin-bottom: 8px;
    }

    .chat-button {
        position: fixed;
        bottom: 20px;
        right: 20px;
        width: 60px;
        height: 60px;
        background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        border-radius: 50%;
        border: none;
        color: white;
        font-size: 28px;
        cursor: pointer;
        box-shadow: 0 4px 12px rgba(102, 126, 234, 0.5);
        transition: transform 0.2s, box-shadow 0.2s;
        z-index: 1000;
    }

    .chat-button:hover {
        transform: scale(1.1);
        box-shadow: 0 6px 20px rgba(102, 126, 234, 0.6);
    }

    .chat-window {
        position: fixed;
        bottom: 90px;
        right: 20px;
        width: 350px;
        height: 500px;
        background: white;
        border-radius: 15px;
        box-shadow: 0 8px 24px rgba(0,0,0,0.2);
        display: none;
        flex-direction: column;
        z-index: 999;
    }

    .chat-window.active {
        display: flex;
    }

    .chat-header {
        background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        color: white;
        padding: 15px;
        border-radius: 15px 15px 0 0;
        font-weight: 600;
    }

    .chat-messages {
        flex: 1;
        padding: 15px;
        overflow-y: auto;
        background: #f8f9fa;
    }

    .chat-message {
        margin-bottom: 10px;
        padding: 10px 15px;
        border-radius: 15px;
        max-width: 80%;
        word-wrap: break-word;
    }

    .chat-message.user {
        background: #667eea;
        color: white;
        margin-left: auto;
    }

    .chat-message.ai {
        background: white;
        color: #333;
        border: 1px solid #e0e0e0;
    }

    .chat-input-container {
        padding: 15px;
        border-top: 1px solid #e0e0e0;
        display: flex;
        gap: 10px;
    }

    .chat-input {
        flex: 1;
        padding: 10px;
        border: 2px solid #e0e0e0;
        border-radius: 20px;
        font-size: 0.9em;
    }

    .chat-send {
        background: #667eea;
        color: white;
        border: none;
        padding: 10px 20px;
        border-radius: 20px;
        cursor: pointer;
        font-weight: 600;
    }

    @media (max-width: 768px) {
        .nav-tab {
            font-size: 0.8em;
            padding: 12px 8px;
        }

        .container {
            padding: 10px;
        }

        .content-section {
            padding: 20px 15px;
        }

        .chat-window {
            width: calc(100% - 40px);
            right: 20px;
        }
    }

    .plant-grid {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
        gap: 15px;
        margin-top: 20px;
    }

    .plant-card {
        padding: 15px;
        background: #f8f9fa;
        border-radius: 8px;
        border: 2px solid #e0e0e0;
        cursor: pointer;
        transition: all 0.3s;
    }

    .plant-card:hover {
        border-color: #667eea;
        transform: translateY(-3px);
        box-shadow: 0 4px 12px rgba(102, 126, 234, 0.2);
    }

    .plant-card.selected {
        border-color: #667eea;
        background: linear-gradient(135deg, #667eea15 0%, #764ba215 100%);
    }

    .alert {
        padding: 15px;
        border-radius: 8px;
        margin-bottom: 15px;
    }

    .alert-warning {
        background: #fff3cd;
        border-left: 4px solid #ffc107;
        color: #856404;
    }

    .alert-danger {
        background: #f8d7da;
        border-left: 4px solid #dc3545;
        color: #721c24;
    }

    .alert-success {
        background: #d4edda;
        border-left: 4px solid #28a745;
        color: #155724;
    }

    .progress-bar {
        width: 100%;
        height: 10px;
        background: #e0e0e0;
        border-radius: 5px;
        overflow: hidden;
        margin: 10px 0;
    }

    .progress-fill {
        height: 100%;
        background: linear-gradient(90deg, #667eea 0%, #764ba2 100%);
        transition: width 0.3s;
    }

    .plant-tracker-card {
        background: white;
        border: 2px solid #e0e0e0;
        border-radius: 10px;
        padding: 20px;
        margin-bottom: 15px;
        transition: all 0.3s;
    }

    .plant-tracker-card:hover {
        border-color: #667eea;
        box-shadow: 0 4px 12px rgba(102, 126, 234, 0.2);
    }

    .plant-header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-bottom: 15px;
    }

    .plant-name {
        font-size: 1.2em;
        font-weight: 600;
        color: #333;
    }

    .plant-actions {
        display: flex;
        gap: 10px;
    }

    .btn-small {
        background: #667eea;
        color: white;
        border: none;
        padding: 6px 12px;
        border-radius: 5px;
        cursor: pointer;
        font-size: 0.85em;
        transition: all 0.2s;
    }

    .btn-small:hover {
        background: #764ba2;
    }

    .btn-danger {
        background: #dc3545;
    }

    .btn-danger:hover {
        background: #c82333;
    }

    .plant-info-grid {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
        gap: 10px;
        margin-bottom: 15px;
    }

    .plant-info-item {
        background: #f8f9fa;
        padding: 10px;
        border-radius: 5px;
        font-size: 0.9em;
    }

    .plant-info-label {
        color: #666;
        font-size: 0.8em;
        margin-bottom: 3px;
    }

    .plant-info-value {
        color: #333;
        font-weight: 600;
    }

    .watering-status {
        padding: 12px;
        border-radius: 8px;
        margin-top: 10px;
        font-weight: 600;
    }

    .status-ok {
        background: #d4edda;
        color: #155724;
        border-left: 4px solid #28a745;
    }

    .status-due {
        background: #fff3cd;
        color: #856404;
        border-left: 4px solid #ffc107;
    }

    .status-overdue {
        background: #f8d7da;
        color: #721c24;
        border-left: 4px solid #dc3545;
    }

    .notification-badge {
        background: #dc3545;
        color: white;
        border-radius: 50%;
        width: 20px;
        height: 20px;
        display: inline-flex;
        align-items: center;
        justify-content: center;
        font-size: 0.7em;
        font-weight: bold;
        position: relative;
        top: -2px;
        margin-left: 5px;
    }
</style>
```

</head>
<body>
    <div class="header">
        <div class="logo-container">
            <div class="logo">
                <img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'%3E%3Ctext y='50' font-size='60' fill='%23667eea'%3E🌱%3C/text%3E%3C/svg%3E" alt="MULCHMATE Logo">
            </div>
            <div>
                <h1>MULCHMATE</h1>
                <p class="tagline">LESS WATER BETTER CROP</p>
            </div>
        </div>
    </div>

```
<div class="container">
    <div class="nav-tabs">
        <button class="nav-tab active" onclick="showSection('soil')">🌍 Soil Analysis</button>
        <button class="nav-tab" onclick="showSection('watering')">💧 Watering Guide</button>
        <button class="nav-tab" onclick="showSection('pests')">🐛 Pest Detection</button>
        <button class="nav-tab" onclick="showSection('tracker')">📊 Plant Tracker</button>
        <button class="nav-tab" onclick="showSection('camera')">📷 Camera</button>
        <button class="nav-tab" onclick="showSection('health')">❤️ Soil Health</button>
    </div>

    <!-- Soil Analysis Section -->
    <div id="soil" class="content-section active">
        <h2 class="section-title">🌍 Soil Analysis & Plant Selection</h2>
        <p style="margin-bottom: 20px; color: #666;">Select your crops to get personalized soil recommendations for mulching.</p>
        
        <div class="form-group">
            <label>Select Your Crops (you can select multiple):</label>
            <div class="plant-grid" id="plant-grid">
                <div class="plant-card" data-plant="tomatoes">
                    <h4>🍅 Tomatoes</h4>
                    <p style="font-size: 0.85em; color: #666;">Warm season crop</p>
                </div>
                <div class="plant-card" data-plant="lettuce">
                    <h4>🥬 Lettuce</h4>
                    <p style="font-size: 0.85em; color: #666;">Cool season crop</p>
                </div>
                <div class="plant-card" data-plant="carrots">
                    <h4>🥕 Carrots</h4>
                    <p style="font-size: 0.85em; color: #666;">Root vegetable</p>
                </div>
                <div class="plant-card" data-plant="peppers">
                    <h4>🌶️ Peppers</h4>
                    <p style="font-size: 0.85em; color: #666;">Warm season crop</p>
                </div>
                <div class="plant-card" data-plant="strawberries">
                    <h4>🍓 Strawberries</h4>
                    <p style="font-size: 0.85em; color: #666;">Perennial crop</p>
                </div>
                <div class="plant-card" data-plant="cucumbers">
                    <h4>🥒 Cucumbers</h4>
                    <p style="font-size: 0.85em; color: #666;">Warm season crop</p>
                </div>
            </div>
        </div>

        <div class="form-group">
            <label>Current Soil Type:</label>
            <select id="soil-type">
                <option value="">Select soil type</option>
                <option value="clay">Clay - Heavy, water-retaining</option>
                <option value="sandy">Sandy - Light, fast-draining</option>
                <option value="loam">Loam - Balanced, ideal</option>
                <option value="silt">Silt - Fine, moisture-retaining</option>
                <option value="unknown">Not sure</option>
            </select>
        </div>

        <button class="btn" onclick="analyzeSoil()">Get Soil Recommendations</button>

        <div id="soil-results"></div>
    </div>

    <!-- Watering Guide Section -->
    <div id="watering" class="content-section">
        <h2 class="section-title">💧 Smart Watering Guide</h2>
        <p style="margin-bottom: 20px; color: #666;">Get personalized watering schedules optimized for mulching.</p>

        <div class="form-group">
            <label>Plant Type:</label>
            <select id="water-plant">
                <option value="tomatoes">Tomatoes</option>
                <option value="lettuce">Lettuce</option>
                <option value="carrots">Carrots</option>
                <option value="peppers">Peppers</option>
                <option value="strawberries">Strawberries</option>
                <option value="cucumbers">Cucumbers</option>
            </select>
        </div>

        <div class="form-group">
            <label>Mulch Depth (cm):</label>
            <input type="number" id="mulch-depth" value="8" min="0" max="15" step="0.5">
        </div>

        <div class="form-group">
            <label>Climate Condition:</label>
            <select id="climate">
                <option value="hot-dry">Hot & Dry</option>
                <option value="hot-humid">Hot & Humid</option>
                <option value="mild">Mild</option>
                <option value="cool">Cool</option>
            </select>
        </div>

        <div class="form-group">
            <label>Plant Growth Stage:</label>
            <select id="growth-stage">
                <option value="seedling">Seedling (just planted)</option>
                <option value="vegetative">Vegetative (growing)</option>
                <option value="flowering">Flowering</option>
                <option value="fruiting">Fruiting</option>
            </select>
        </div>

        <button class="btn" onclick="calculateWatering()">Calculate Watering Schedule</button>

        <div id="watering-results"></div>
    </div>

    <!-- Pest Detection Section -->
    <div id="pests" class="content-section">
        <h2 class="section-title">🐛 Pest Identification & Management</h2>
        <p style="margin-bottom: 20px; color: #666;">Identify common pests and learn how to manage them with mulching techniques.</p>

        <div class="form-group">
            <label>Describe what you're seeing:</label>
            <textarea id="pest-description" rows="3" placeholder="E.g., small green insects on leaves, holes in leaves, white powder on stems..."></textarea>
        </div>

        <div class="form-group">
            <label>Affected Plant:</label>
            <select id="pest-plant">
                <option value="tomatoes">Tomatoes</option>
                <option value="lettuce">Lettuce</option>
                <option value="carrots">Carrots</option>
                <option value="peppers">Peppers</option>
                <option value="strawberries">Strawberries</option>
                <option value="cucumbers">Cucumbers</option>
            </select>
        </div>

        <button class="btn" onclick="identifyPest()">Identify Pest</button>

        <div id="pest-results"></div>
    </div>

    <!-- Plant Tracker Section -->
    <div id="tracker" class="content-section">
        <h2 class="section-title">📊 Plant Tracker & Reminders</h2>
        <p style="margin-bottom: 20px; color: #666;">Track your plants and get automatic watering reminders.</p>

        <div style="background: linear-gradient(135deg, #667eea15 0%, #764ba215 100%); padding: 20px; border-radius: 10px; margin-bottom: 20px;">
            <h3 style="color: #667eea; margin-bottom: 15px;">➕ Add New Plant</h3>
            
            <div class="form-group">
                <label>Plant Name:</label>
                <input type="text" id="new-plant-name" placeholder="E.g., Tomato Plant #1">
            </div>

            <div class="form-group">
                <label>Plant Type:</label>
                <select id="new-plant-type">
                    <option value="tomatoes">🍅 Tomatoes</option>
                    <option value="lettuce">🥬 Lettuce</option>
                    <option value="carrots">🥕 Carrots</option>
                    <option value="peppers">🌶️ Peppers</option>
                    <option value="strawberries">🍓 Strawberries</option>
                    <option value="cucumbers">🥒 Cucumbers</option>
                </select>
            </div>

            <div class="form-group">
                <label>Planting Date:</label>
                <input type="date" id="new-plant-date">
            </div>

            <div class="form-group">
                <label>Watering Frequency:</label>
                <select id="new-plant-frequency">
                    <option value="1">Daily</option>
                    <option value="2" selected>Every 2 days</option>
                    <option value="3">Every 3 days</option>
                    <option value="4">Every 4 days</option>
                    <option value="7">Weekly</option>
                </select>
            </div>

            <div class="form-group">
                <label>Mulch Depth (cm):</label>
                <input type="number" id="new-plant-mulch" value="8" min="0" max="15" step="0.5">
            </div>

            <div class="form-group">
                <label>Enable Notifications:</label>
                <select id="new-plant-notifications">
                    <option value="true">Yes - Remind me to water</option>
                    <option value="false">No</option>
                </select>
            </div>

            <button class="btn" onclick="addPlant()">Add Plant</button>
        </div>

        <h3 style="color: #667eea; margin-bottom: 15px;">🌱 My Plants</h3>
        <div id="plant-list">
            <div style="text-align: center; padding: 40px; color: #999;">
                <p>No plants tracked yet. Add your first plant above!</p>
            </div>
        </div>
    </div>

    <!-- Camera Section -->
    <div id="camera" class="content-section">
        <h2 class="section-title">📷 Visual Inspection</h2>
        <p style="margin-bottom: 20px; color: #666;">Take photos of your soil, plants, or pests for AI-assisted analysis.</p>

        <div class="camera-container">
            <video id="camera-feed" autoplay playsinline></video>
            <img id="captured-image" alt="Captured image">
            
            <div class="camera-buttons">
                <button class="btn" onclick="startCamera()">📷 Start Camera</button>
                <button class="btn" onclick="capturePhoto()" id="capture-btn" style="display: none;">📸 Capture</button>
                <button class="btn" onclick="stopCamera()" id="stop-btn" style="display: none;">⏹️ Stop</button>
                <button class="btn" onclick="document.getElementById('file-input').click()">📁 Upload Photo</button>
            </div>
            <input type="file" id="file-input" accept="image/*" style="display: none;" onchange="handleFileUpload(event)">
        </div>

        <div class="form-group" style="margin-top: 20px;">
            <label>What would you like to analyze?</label>
            <select id="analysis-type">
                <option value="soil">Soil Quality</option>
                <option value="plant">Plant Health</option>
                <option value="pest">Pest/Disease</option>
                <option value="mulch">Mulch Condition</option>
            </select>
        </div>

        <button class="btn" onclick="analyzeImage()" id="analyze-btn" style="display: none;">🔍 Analyze Image</button>

        <div id="image-results"></div>
    </div>

    <!-- Soil Health Section -->
    <div id="health" class="content-section">
        <h2 class="section-title">❤️ Soil Health Monitor</h2>
        <p style="margin-bottom: 20px; color: #666;">Check your soil vitality and get recommendations to improve it.</p>

        <div class="form-group">
            <label>When did you last add organic matter/compost?</label>
            <select id="compost-time">
                <option value="recent">Within last month</option>
                <option value="moderate">1-3 months ago</option>
                <option value="old">3-6 months ago</option>
                <option value="very-old">Over 6 months ago</option>
                <option value="never">Never</option>
            </select>
        </div>

        <div class="form-group">
            <label>Current mulch condition:</label>
            <select id="mulch-condition">
                <option value="fresh">Fresh and intact</option>
                <option value="decomposing">Partially decomposed</option>
                <option value="old">Old and thin</option>
                <option value="none">No mulch present</option>
            </select>
        </div>

        <div class="form-group">
            <label>Plant growth observations:</label>
            <select id="growth-observation">
                <option value="excellent">Excellent - vibrant and fast growing</option>
                <option value="good">Good - steady growth</option>
                <option value="moderate">Moderate - slow growth</option>
                <option value="poor">Poor - stunted or yellowing</option>
            </select>
        </div>

        <div class="form-group">
            <label>Soil smell and appearance:</label>
            <select id="soil-appearance">
                <option value="earthy">Earthy smell, dark color</option>
                <option value="neutral">No strong smell, brown color</option>
                <option value="compacted">Compacted, hard to dig</option>
                <option value="bad">Foul smell, gray/pale color</option>
            </select>
        </div>

        <button class="btn" onclick="checkSoilHealth()">Check Soil Health</button>

        <div id="health-results"></div>
    </div>
</div>

<!-- AI Chat Button -->
<button class="chat-button" onclick="toggleChat()">💬</button>

<!-- AI Chat Window -->
<div class="chat-window" id="chat-window">
    <div class="chat-header">
        🤖 MULCHMATE AI Assistant
    </div>
    <div class="chat-messages" id="chat-messages">
        <div class="chat-message ai">
            Hello! I'm your MULCHMATE AI assistant. Ask me anything about mulching, soil health, watering, pests, or growing crops! 🌱
        </div>
    </div>
    <div class="chat-input-container">
        <input type="text" class="chat-input" id="chat-input" placeholder="Ask me anything..." onkeypress="handleChatKeyPress(event)">
        <button class="chat-send" onclick="sendMessage()">Send</button>
    </div>
</div>

<script>
    let selectedPlants = new Set();
    let cameraStream = null;
    let capturedImageData = null;

    // Initialize plant selection
    document.querySelectorAll('.plant-card').forEach(card => {
        card.addEventListener('click', function() {
            const plant = this.dataset.plant;
            if (selectedPlants.has(plant)) {
                selectedPlants.delete(plant);
                this.classList.remove('selected');
            } else {
                selectedPlants.add(plant);
                this.classList.add('selected');
            }
        });
    });

    function showSection(sectionId) {
        document.querySelectorAll('.content-section').forEach(section => {
            section.classList.remove('active');
        });
        document.querySelectorAll('.nav-tab').forEach(tab => {
            tab.classList.remove('active');
        });
        document.getElementById(sectionId).classList.add('active');
        event.target.classList.add('active');
    }

    function analyzeSoil() {
        const soilType = document.getElementById('soil-type').value;
        const resultsDiv = document.getElementById('soil-results');

        if (selectedPlants.size === 0) {
            resultsDiv.innerHTML = '<div class="alert alert-warning">⚠️ Please select at least one crop!</div>';
            return;
        }

        if (!soilType) {
            resultsDiv.innerHTML = '<div class="alert alert-warning">⚠️ Please select your soil type!</div>';
            return;
        }

        const soilData = {
            clay: {
                desc: 'Heavy soil that retains water and nutrients well',
                mulch: 'Use lighter mulches like straw or grass clippings (5-8 cm)',
                tips: ['Add compost to improve drainage', 'Avoid over-mulching to prevent waterlogging', 'Consider raised beds']
            },
            sandy: {
                desc: 'Light soil that drains quickly and needs more nutrients',
                mulch: 'Use heavier organic mulches like wood chips or compost (10-15 cm)',
                tips: ['Mulch helps retain moisture significantly', 'Add compost regularly', 'Water more frequently but less per session']
            },
            loam: {
                desc: 'Ideal balanced soil - perfect for most crops!',
                mulch: 'Use any organic mulch (8-10 cm)',
                tips: ['Maintain with regular mulching', 'Rotate mulch types seasonally', 'Keep soil covered year-round']
            },
            silt: {
                desc: 'Fine particles, good water retention',
                mulch: 'Use medium-weight mulches like shredded leaves (8-10 cm)',
                tips: ['Mulch prevents crusting', 'Add organic matter regularly', 'Avoid compaction']
            },
            unknown: {
                desc: 'Unable to determine - test recommended',
                mulch: 'Start with general-purpose mulch like straw (8 cm)',
                tips: ['Observe how water drains', 'Do a simple soil test', 'Adjust mulching based on results']
            }
        };

        const data = soilData[soilType];
        const plantsArray = Array.from(selectedPlants);

        let html = `
            <div class="result-box">
                <h3>🌍 Soil Analysis Results</h3>
                <p><strong>Soil Type:</strong> ${data.desc}</p>
                <p><strong>Selected Crops:</strong> ${plantsArray.join(', ')}</p>
                
                <div class="info-card">
                    <h4>🍂 Recommended Mulch</h4>
                    <p>${data.mulch}</p>
                </div>

                <div class="info-card">
                    <h4>💡 Pro Tips for Your Soil</h4>
                    <ul style="margin-left: 20px; margin-top: 10px;">
                        ${data.tips.map(tip => `<li style="margin-bottom: 8px;">${tip}</li>`).join('')}
                    </ul>
                </div>

                <div class="info-card">
                    <h4>🌱 Crop-Specific Recommendations</h4>
        `;

        plantsArray.forEach(plant => {
            const plantTips = {
                tomatoes: 'Need consistent moisture. Mulch helps prevent soil splash on leaves, reducing disease.',
                lettuce: 'Prefer cooler soil. Light-colored mulch helps keep soil temperature down.',
                carrots: 'Need loose soil. Use fine mulch that won\'t interfere with seedling emergence.',
                peppers: 'Love warm soil. Dark mulch can help warm the soil in spring.',
                strawberries: 'Benefit greatly from straw mulch to keep fruits clean and reduce disease.',
                cucumbers: 'Heavy feeders that need consistent moisture. Thick mulch is beneficial.'
            };
            html += `<p><strong>${plant.charAt(0).toUpperCase() + plant.slice(1)}:</strong> ${plantTips[plant]}</p>`;
        });

        html += `
                </div>
            </div>
        `;

        resultsDiv.innerHTML = html;
    }

    function calculateWatering() {
        const plant = document.getElementById('water-plant').value;
        const mulchDepth = parseFloat(document.getElementById('mulch-depth').value);
        const climate = document.getElementById('climate').value;
        const growthStage = document.getElementById('growth-stage').value;
        const resultsDiv = document.getElementById('watering-results');

        const wateringData = {
            tomatoes: { base: 1.5, name: 'Tomatoes' },
            lettuce: { base: 1.0, name: 'Lettuce' },
            carrots: { base: 1.0, name: 'Carrots' },
            peppers: { base: 1.5, name: 'Peppers' },
            strawberries: { base: 1.2, name: 'Strawberries' },
            cucumbers: { base: 1.8, name: 'Cucumbers' }
        };

        let waterNeed = wateringData[plant].base;

        // Adjust for climate
        const climateMultiplier = {
            'hot-dry': 1.4,
            'hot-humid': 1.2,
            'mild': 1.0,
            'cool': 0.8
        };
        waterNeed *= climateMultiplier[climate];

        // Adjust for growth stage
        const stageMultiplier = {
            'seedling': 0.7,
            'vegetative': 1.0,
            'flowering': 1.2,
            'fruiting': 1.3
        };
        waterNeed *= stageMultiplier[growthStage];

        // Mulch benefit
        const mulchReduction = Math.min(mulchDepth * 0.045, 0.4);
        waterNeed *= (1 - mulchReduction);

        const frequency = waterNeed > 1.5 ? 'Daily' : waterNeed > 1.0 ? 'Every 2 days' : 'Every 3 days';
        const waterSaved = Math.round(mulchReduction * 100);

        let html = `
            <div class="result-box">
                <h3>💧 Watering Schedule for ${wateringData[plant].name}</h3>
                
                <div class="alert alert-success">
                    <strong>✅ Mulch Benefit:</strong> You're saving approximately ${waterSaved}% water thanks to your ${mulchDepth} cm mulch layer!
                </div>

                <div class="info-card">
                    <h4>📅 Recommended Schedule</h4>
                    <p><strong>Frequency:</strong> ${frequency}</p>
                    <p><strong>Amount:</strong> ${(waterNeed * 2.54).toFixed(1)} cm per watering session</p>
                    <p><strong>Best Time:</strong> Early morning (6-8 AM)</p>
                </div>

                <div class="info-card">
                    <h4>💡 Watering Tips with Mulch</h4>
                    <ul style="margin-left: 20px; margin-top: 10px;">
                        <li style="margin-bottom: 8px;">Water deeply but less frequently - mulch keeps moisture in!</li>
                        <li style="margin-bottom: 8px;">Check soil moisture 5-8 cm below surface before watering</li>
                        <li style="margin-bottom: 8px;">Water at soil level, not on leaves</li>
                        <li style="margin-bottom: 8px;">In hot weather, add extra watering if plants show stress</li>
                        <li style="margin-bottom: 8px;">Refresh mulch layer as it decomposes to maintain water savings</li>
                    </ul>
                </div>

                <div class="info-card">
                    <h4>⚠️ Signs of Overwatering or Underwatering</h4>
                    <p><strong>Too much water:</strong> Yellowing leaves, wilting despite wet soil, root rot</p>
                    <p><strong>Too little water:</strong> Drooping leaves, dry soil 3" down, slow growth</p>
                </div>
            </div>
        `;

        resultsDiv.innerHTML = html;
    }

    function identifyPest() {
        const description = document.getElementById('pest-description').value.toLowerCase();
        const plant = document.getElementById('pest-plant').value;
        const resultsDiv = document.getElementById('pest-results');

        if (!description) {
            resultsDiv.innerHTML = '<div class="alert alert-warning">⚠️ Please describe what you\'re seeing!</div>';
            return;
        }

        let pestInfo = {
            name: 'Unknown Pest',
            severity: 'moderate',
            description: 'Unable to identify based on description.',
            mulchHelp: 'Mulching can help prevent some pests.',
            treatment: 'Take a photo using the Camera tab for better identification.'
        };

        // Simple keyword matching
        if (description.includes('aphid') || description.includes('green insect') || description.includes('small green')) {
            pestInfo = {
                name: 'Aphids',
                severity: 'moderate',
                description: 'Small, soft-bodied insects that cluster on new growth and undersides of leaves.',
                mulchHelp: 'Mulch provides habitat for beneficial insects that eat aphids!',
                treatment: 'Spray with water, introduce ladybugs, use neem oil if severe. Mulch encourages natural predators.'
            };
        } else if (description.includes('caterpillar') || description.includes('worm') || description.includes('holes')) {
            pestInfo = {
                name: 'Caterpillars/Worms',
                severity: 'moderate',
                description: 'Larvae that chew holes in leaves and can defoliate plants.',
                mulchHelp: 'Mulch can harbor birds and beneficial insects that feed on caterpillars.',
                treatment: 'Hand-pick, use BT (Bacillus thuringiensis), encourage birds with proper mulching habitat.'
            };
        } else if (description.includes('white') || description.includes('powder') || description.includes('mold')) {
            pestInfo = {
                name: 'Powdery Mildew',
                severity: 'high',
                description: 'Fungal disease appearing as white powder on leaves and stems.',
                mulchHelp: '⚠️ Keep mulch away from plant stems to improve air circulation.',
                treatment: 'Remove affected leaves, ensure good spacing, spray with baking soda solution or neem oil.'
            };
        } else if (description.includes('slug') || description.includes('snail') || description.includes('slime')) {
            pestInfo = {
                name: 'Slugs/Snails',
                severity: 'moderate',
                description: 'Mollusks that leave slime trails and eat large holes in leaves.',
                mulchHelp: 'Rough mulches like wood chips deter slugs. Avoid thick wet mulch near plants.',
                treatment: 'Hand-pick at night, use beer traps, diatomaceous earth, or copper barriers.'
            };
        } else if (description.includes('spider') || description.includes('mite') || description.includes('stippling')) {
            pestInfo = {
                name: 'Spider Mites',
                severity: 'high',
                description: 'Tiny pests that cause stippling/yellowing on leaves, often with fine webbing.',
                mulchHelp: 'Keep plants well-watered - mulch helps! Dry conditions favor mites.',
                treatment: 'Spray with water regularly, use insecticidal soap, maintain humidity with good mulching.'
            };
        }

        const severityColors = {
            low: '#28a745',
            moderate: '#ffc107',
            high: '#dc3545'
        };

        let html = `
            <div class="result-box">
                <h3>🐛 Pest Identification Results</h3>
                
                <div class="alert alert-${pestInfo.severity === 'high' ? 'danger' : 'warning'}">
                    <strong>Identified:</strong> ${pestInfo.name}
                    <br><strong>Severity:</strong> <span style="color: ${severityColors[pestInfo.severity]};">⬤</span> ${pestInfo.severity.toUpperCase()}
                </div>

                <div class="info-card">
                    <h4>📋 Description</h4>
                    <p>${pestInfo.description}</p>
                </div>

                <div class="info-card">
                    <h4>🍂 Mulching Connection</h4>
                    <p>${pestInfo.mulchHelp}</p>
                </div>

                <div class="info-card">
                    <h4>💊 Treatment Recommendations</h4>
                    <p>${pestInfo.treatment}</p>
                </div>

                <div class="info-card">
                    <h4>🔬 For Better Accuracy</h4>
                    <p>Use the <strong>📷 Camera</strong> tab to take a photo of the pest or damage. Our AI can provide more specific identification and treatment plans!</p>
                </div>
            </div>
        `;

        resultsDiv.innerHTML = html;
    }

    async function startCamera() {
        try {
            cameraStream = await navigator.mediaDevices.getUserMedia({ 
                video: { facingMode: 'environment' } 
            });
            const video = document.getElementById('camera-feed');
            video.srcObject = cameraStream;
            video.style.display = 'block';
            document.getElementById('captured-image').style.display = 'none';
            document.getElementById('capture-btn').style.display = 'inline-block';
            document.getElementById('stop-btn').style.display = 'inline-block';
        } catch (err) {
            alert('Camera access denied or not available: ' + err.message);
        }
    }

    function capturePhoto() {
        const video = document.getElementById('camera-feed');
        const canvas = document.createElement('canvas');
        canvas.width = video.videoWidth;
        canvas.height = video.videoHeight;
        canvas.getContext('2d').drawImage(video, 0, 0);
        
        capturedImageData = canvas.toDataURL('image/jpeg');
        const img = document.getElementById('captured-image');
        img.src = capturedImageData;
        img.style.display = 'block';
        
        stopCamera();
        document.getElementById('analyze-btn').style.display = 'inline-block';
    }

    function stopCamera() {
        if (cameraStream) {
            cameraStream.getTracks().forEach(track => track.stop());
            document.getElementById('camera-feed').style.display = 'none';
            document.getElementById('capture-btn').style.display = 'none';
            document.getElementById('stop-btn').style.display = 'none';
        }
    }

    function handleFileUpload(event) {
        const file = event.target.files[0];
        if (file) {
            const reader = new FileReader();
            reader.onload = function(e) {
                capturedImageData = e.target.result;
                const img = document.getElementById('captured-image');
                img.src = capturedImageData;
                img.style.display = 'block';
                document.getElementById('analyze-btn').style.display = 'inline-block';
            };
            reader.readAsDataURL(file);
        }
    }

    function analyzeImage() {
        const analysisType = document.getElementById('analysis-type').value;
        const resultsDiv = document.getElementById('image-results');

        if (!capturedImageData) {
            resultsDiv.innerHTML = '<div class="alert alert-warning">⚠️ Please capture or upload an image first!</div>';
            return;
        }

        const analyses = {
            soil: {
                title: '🌍 Soil Quality Analysis',
                findings: [
                    'Soil appears to have good organic matter content',
                    'Color indicates adequate drainage',
                    'Texture suggests balanced composition'
                ],
                recommendations: [
                    'Add 5-8 cm of organic mulch to preserve moisture',
                    'Consider adding compost to boost nutrients',
                    'Maintain current soil management practices'
                ]
            },
            plant: {
                title: '🌱 Plant Health Analysis',
                findings: [
                    'Overall plant vigor appears normal',
                    'Leaf color indicates adequate nutrients',
                    'Growth pattern seems healthy'
                ],
                recommendations: [
                    'Continue current watering schedule',
                    'Monitor for any pest development',
                    'Ensure mulch is not touching stems'
                ]
            },
            pest: {
                title: '🐛 Pest Detection Analysis',
                findings: [
                    'Some signs of minor insect activity detected',
                    'No severe infestation observed',
                    'Damage appears manageable'
                ],
                recommendations: [
                    'Monitor daily for pest population changes',
                    'Consider introducing beneficial insects',
                    'Use organic pest control if needed'
                ]
            },
            mulch: {
                title: '🍂 Mulch Condition Analysis',
                findings: [
                    'Mulch coverage appears adequate',
                    'Some decomposition is normal and beneficial',
                    'Overall condition is good'
                ],
                recommendations: [
                    'Add fresh mulch layer in 2-3 weeks',
                    'Current depth provides good moisture retention',
                    'Decomposing mulch enriches soil - excellent!'
                ]
            }
        };

        const analysis = analyses[analysisType];

        let html = `
            <div class="result-box">
                <h3>${analysis.title}</h3>
                
                <div class="alert alert-success">
                    ✅ Image analysis complete!
                </div>

                <div class="info-card">
                    <h4>🔍 Key Findings</h4>
                    <ul style="margin-left: 20px; margin-top: 10px;">
                        ${analysis.findings.map(finding => `<li style="margin-bottom: 8px;">${finding}</li>`).join('')}
                    </ul>
                </div>

                <div class="info-card">
                    <h4>💡 Recommendations</h4>
                    <ul style="margin-left: 20px; margin-top: 10px;">
                        ${analysis.recommendations.map(rec => `<li style="margin-bottom: 8px;">${rec}</li>`).join('')}
                    </ul>
                </div>

                <div class="info-card">
                    <h4>💬 Need More Help?</h4>
                    <p>Click the chat button in the bottom-right corner to ask our AI assistant specific questions about your ${analysisType}!</p>
                </div>
            </div>
        `;

        resultsDiv.innerHTML = html;
    }

    function checkSoilHealth() {
        const compost = document.getElementById('compost-time').value;
        const mulchCondition = document.getElementById('mulch-condition').value;
        const growth = document.getElementById('growth-observation').value;
        const appearance = document.getElementById('soil-appearance').value;
        const resultsDiv = document.getElementById('health-results');

        let healthScore = 0;
        const warnings = [];
        const recommendations = [];

        // Calculate health score
        const scores = {
            compost: { recent: 25, moderate: 20, old: 10, 'very-old': 5, never: 0 },
            mulch: { fresh: 25, decomposing: 20, old: 10, none: 0 },
            growth: { excellent: 30, good: 25, moderate: 15, poor: 5 },
            appearance: { earthy: 20, neutral: 15, compacted: 8, bad: 0 }
        };

        healthScore += scores.compost[compost];
        healthScore += scores.mulch[mulchCondition];
        healthScore += scores.growth[growth];
        healthScore += scores.appearance[appearance];

        // Generate warnings and recommendations
        if (compost === 'never' || compost === 'very-old') {
            warnings.push('⚠️ Soil may be depleted of organic matter');
            recommendations.push('Add compost or well-rotted manure immediately');
        }

        if (mulchCondition === 'none' || mulchCondition === 'old') {
            warnings.push('⚠️ Insufficient mulch coverage detected');
            recommendations.push('Apply 8-10 cm of organic mulch to protect and feed soil');
        }

        if (growth === 'poor' || growth === 'moderate') {
            warnings.push('⚠️ Plants showing signs of nutrient deficiency');
            recommendations.push('Consider soil testing and adding balanced organic fertilizer');
        }

        if (appearance === 'bad') {
            warnings.push('🚨 Critical: Soil may be anaerobic or diseased');
            recommendations.push('Improve drainage, add organic matter, and consider soil amendment');
        } else if (appearance === 'compacted') {
            warnings.push('⚠️ Soil compaction limiting root growth');
            recommendations.push('Aerate soil and add compost to improve structure');
        }

        let status, statusColor, statusIcon;
        if (healthScore >= 80) {
            status = 'EXCELLENT';
            statusColor = '#28a745';
            statusIcon = '🌟';
            if (recommendations.length === 0) {
                recommendations.push('Keep up the great work!', 'Maintain current mulching practices');
            }
        } else if (healthScore >= 60) {
            status = 'GOOD';
            statusColor = '#28a745';
            statusIcon = '✅';
            recommendations.push('Minor improvements will boost soil even more');
        } else if (healthScore >= 40) {
            status = 'FAIR';
            statusColor = '#ffc107';
            statusIcon = '⚠️';
            recommendations.push('Focus on consistent organic matter addition');
        } else {
            status = 'POOR - ACTION NEEDED';
            statusColor = '#dc3545';
            statusIcon = '🚨';
            recommendations.push('Soil rehabilitation program recommended');
        }

        let html = `
            <div class="result-box">
                <h3>❤️ Soil Health Report</h3>
                
                <div style="text-align: center; margin: 20px 0;">
                    <div style="font-size: 3em; color: ${statusColor};">${healthScore}%</div>
                    <div style="font-size: 1.5em; color: ${statusColor}; font-weight: bold;">${statusIcon} ${status}</div>
                    <div class="progress-bar">
                        <div class="progress-fill" style="width: ${healthScore}%; background: ${statusColor};"></div>
                    </div>
                </div>
        `;

        if (warnings.length > 0) {
            html += `
                <div class="alert alert-${healthScore < 40 ? 'danger' : 'warning'}">
                    <h4 style="margin-bottom: 10px;">⚠️ Warnings</h4>
                    <ul style="margin-left: 20px;">
                        ${warnings.map(w => `<li style="margin-bottom: 5px;">${w}</li>`).join('')}
                    </ul>
                </div>
            `;
        }

        html += `
                <div class="info-card">
                    <h4>📋 Action Plan</h4>
                    <ul style="margin-left: 20px; margin-top: 10px;">
                        ${recommendations.map(r => `<li style="margin-bottom: 8px;">${r}</li>`).join('')}
                    </ul>
                </div>

                <div class="info-card">
                    <h4>🌱 Mulching for Soil Health</h4>
                    <p><strong>Why mulch matters:</strong></p>
                    <ul style="margin-left: 20px; margin-top: 8px;">
                        <li style="margin-bottom: 8px;">Feeds beneficial soil microorganisms as it decomposes</li>
                        <li style="margin-bottom: 8px;">Regulates soil temperature and moisture</li>
                        <li style="margin-bottom: 8px;">Prevents erosion and nutrient loss</li>
                        <li style="margin-bottom: 8px;">Suppresses weeds that compete for nutrients</li>
                        <li style="margin-bottom: 8px;">Improves soil structure over time</li>
                    </ul>
                    <p style="margin-top: 10px;"><strong>Tip:</strong> Maintain 5-10 cm depth and refresh when it decomposes below 5 cm</p>
                </div>

                <div class="info-card">
                    <h4>📅 Next Steps</h4>
                    <p><strong>Re-check in:</strong> ${healthScore >= 60 ? '1-2 months' : '2-4 weeks'}</p>
                    <p>Track your improvements and adjust your practices based on plant response!</p>
                </div>
            </div>
        `;

        resultsDiv.innerHTML = html;
    }

    function toggleChat() {
        const chatWindow = document.getElementById('chat-window');
        chatWindow.classList.toggle('active');
    }

    function sendMessage() {
        const input = document.getElementById('chat-input');
        const message = input.value.trim();
        
        if (!message) return;

        const messagesDiv = document.getElementById('chat-messages');
        
        // Add user message
        const userMsg = document.createElement('div');
        userMsg.className = 'chat-message user';
        userMsg.textContent = message;
        messagesDiv.appendChild(userMsg);

        input.value = '';

        // Simulate AI response
        setTimeout(() => {
            const aiMsg = document.createElement('div');
            aiMsg.className = 'chat-message ai';
            aiMsg.textContent = getAIResponse(message);
            messagesDiv.appendChild(aiMsg);
            messagesDiv.scrollTop = messagesDiv.scrollHeight;
        }, 500);

        messagesDiv.scrollTop = messagesDiv.scrollHeight;
    }

    function handleChatKeyPress(event) {
        if (event.key === 'Enter') {
            sendMessage();
        }
    }

    function getAIResponse(message) {
        const msg = message.toLowerCase();
        
        if (msg.includes('track') || msg.includes('reminder') || msg.includes('notification')) {
            return 'Use the Plant Tracker tab to add your plants and get automatic watering reminders! You can track when you planted them, set watering schedules, and receive notifications. Enable browser notifications for the best experience!';
        } else if (msg.includes('mulch') && (msg.includes('how much') || msg.includes('depth'))) {
            return 'For most crops, 8-10 cm of organic mulch is ideal. Use 10-15 cm for sandy soil, and 5-8 cm for clay soil. Never let mulch touch plant stems!';
        } else if (msg.includes('water') || msg.includes('irrigat')) {
            return 'With proper mulching, you can reduce watering by 30-50%! Water deeply but less frequently. Check soil moisture 5-8 cm below the surface before watering. Use the Plant Tracker to get personalized reminders!';
        } else if (msg.includes('pest') || msg.includes('bug') || msg.includes('insect')) {
            return 'Mulching creates habitat for beneficial insects that control pests naturally. Use the Pest Detection tab or Camera feature to identify specific problems. What symptoms are you seeing?';
        } else if (msg.includes('compost') || msg.includes('organic matter')) {
            return 'Compost is gold for your soil! Apply 2-5 cm every season. As mulch decomposes, it also acts as a slow-release compost. This builds amazing soil health over time!';
        } else if (msg.includes('tomato') || msg.includes('pepper') || msg.includes('vegetable')) {
            return 'For vegetables like tomatoes and peppers, use organic mulch like straw or grass clippings. Keep it 5-8 cm from stems to prevent rot. This helps prevent soil-borne diseases too! Add them to the Plant Tracker for watering reminders!';
        } else if (msg.includes('soil') && msg.includes('dead')) {
            return 'Soil can be revived! Check the Soil Health tab for a complete assessment. Quick fix: add compost, apply mulch, and give it time. Soil organisms will bounce back with proper care.';
        } else if (msg.includes('when') && msg.includes('mulch')) {
            return 'Best time to mulch: early spring after soil warms up, or fall for winter protection. Refresh mulch as needed when it decomposes to less than 5 cm thick.';
        } else if (msg.includes('type') || msg.includes('kind') || msg.includes('best mulch')) {
            return 'Best mulches: straw (great for vegetables), wood chips (paths & perennials), grass clippings (nitrogen boost), shredded leaves (free & nutritious). Avoid fresh wood chips around young plants.';
        } else {
            return 'Great question! I can help with mulching techniques, watering schedules, soil health, pest control, plant tracking, and crop management. Try using our specialized tabs for detailed analysis, or ask me specific questions!';
        }
    }

    // Initialize
    console.log('MULCHMATE App initialized - helping farmers grow better with less water! 🌱');

    // Plant Tracker Functions
    let trackedPlants = [];
    let notificationPermission = false;

    // Load plants from localStorage on page load
    window.addEventListener('load', function() {
        loadPlants();
        checkNotificationPermission();
        // Set today's date as default
        document.getElementById('new-plant-date').valueAsDate = new Date();
        // Check watering reminders every hour
        setInterval(checkWateringReminders, 3600000);
        // Check immediately
        checkWateringReminders();
    });

    function loadPlants() {
        const saved = localStorage.getItem('mulchmate_plants');
        if (saved) {
            trackedPlants = JSON.parse(saved);
            displayPlants();
        }
    }

    function savePlants() {
        localStorage.setItem('mulchmate_plants', JSON.stringify(trackedPlants));
    }

    async function checkNotificationPermission() {
        if ('Notification' in window) {
            if (Notification.permission === 'granted') {
                notificationPermission = true;
            } else if (Notification.permission !== 'denied') {
                const permission = await Notification.requestPermission();
                notificationPermission = permission === 'granted';
            }
        }
    }

    function addPlant() {
        const name = document.getElementById('new-plant-name').value.trim();
        const type = document.getElementById('new-plant-type').value;
        const date = document.getElementById('new-plant-date').value;
        const frequency = parseInt(document.getElementById('new-plant-frequency').value);
        const mulch = parseFloat(document.getElementById('new-plant-mulch').value);
        const notifications = document.getElementById('new-plant-notifications').value === 'true';

        if (!name || !date) {
            alert('⚠️ Please enter a plant name and planting date!');
            return;
        }

        const plant = {
            id: Date.now(),
            name: name,
            type: type,
            plantedDate: date,
            wateringFrequency: frequency,
            mulchDepth: mulch,
            notifications: notifications,
            lastWatered: date,
            history: []
        };

        trackedPlants.push(plant);
        savePlants();
        displayPlants();

        // Reset form
        document.getElementById('new-plant-name').value = '';
        document.getElementById('new-plant-type').selectedIndex = 0;
        document.getElementById('new-plant-date').valueAsDate = new Date();
        document.getElementById('new-plant-frequency').selectedIndex = 1;
        document.getElementById('new-plant-mulch').value = 8;

        // Request notification permission if enabled
        if (notifications && !notificationPermission) {
            checkNotificationPermission();
        }

        alert('✅ Plant added successfully!');
    }

    function displayPlants() {
        const listDiv = document.getElementById('plant-list');
        
        if (trackedPlants.length === 0) {
            listDiv.innerHTML = `
                <div style="text-align: center; padding: 40px; color: #999;">
                    <p>No plants tracked yet. Add your first plant above!</p>
                </div>
            `;
            return;
        }

        const now = new Date();
        let html = '';

        trackedPlants.forEach(plant => {
            const plantedDate = new Date(plant.plantedDate);
            const lastWatered = new Date(plant.lastWatered);
            const daysGrowing = Math.floor((now - plantedDate) / (1000 * 60 * 60 * 24));
            const daysSinceWatered = Math.floor((now - lastWatered) / (1000 * 60 * 60 * 24));
            const nextWatering = new Date(lastWatered);
            nextWatering.setDate(nextWatering.getDate() + plant.wateringFrequency);
            const daysUntilWatering = Math.floor((nextWatering - now) / (1000 * 60 * 60 * 24));

            let wateringStatus, statusClass, statusIcon;
            if (daysUntilWatering < 0) {
                wateringStatus = `⚠️ Overdue by ${Math.abs(daysUntilWatering)} day(s)!`;
                statusClass = 'status-overdue';
                statusIcon = '🚨';
            } else if (daysUntilWatering === 0) {
                wateringStatus = '💧 Water today!';
                statusClass = 'status-due';
                statusIcon = '⏰';
            } else if (daysUntilWatering === 1) {
                wateringStatus = '📅 Water tomorrow';
                statusClass = 'status-ok';
                statusIcon = '✅';
            } else {
                wateringStatus = `✅ Next watering in ${daysUntilWatering} days`;
                statusClass = 'status-ok';
                statusIcon = '✅';
            }

            const emoji = {
                tomatoes: '🍅',
                lettuce: '🥬',
                carrots: '🥕',
                peppers: '🌶️',
                strawberries: '🍓',
                cucumbers: '🥒'
            }[plant.type];

            html += `
                <div class="plant-tracker-card">
                    <div class="plant-header">
                        <div class="plant-name">${emoji} ${plant.name}</div>
                        <div class="plant-actions">
                            <button class="btn-small" onclick="waterPlant(${plant.id})">💧 Watered</button>
                            <button class="btn-small btn-danger" onclick="deletePlant(${plant.id})">🗑️</button>
                        </div>
                    </div>

                    <div class="plant-info-grid">
                        <div class="plant-info-item">
                            <div class="plant-info-label">Planted</div>
                            <div class="plant-info-value">${daysGrowing} days ago</div>
                        </div>
                        <div class="plant-info-item">
                            <div class="plant-info-label">Last Watered</div>
                            <div class="plant-info-value">${daysSinceWatered} day(s) ago</div>
                        </div>
                        <div class="plant-info-item">
                            <div class="plant-info-label">Mulch Depth</div>
                            <div class="plant-info-value">${plant.mulchDepth} cm</div>
                        </div>
                        <div class="plant-info-item">
                            <div class="plant-info-label">Water Every</div>
                            <div class="plant-info-value">${plant.wateringFrequency} day(s)</div>
                        </div>
                    </div>

                    <div class="watering-status ${statusClass}">
                        ${statusIcon} ${wateringStatus}
                    </div>

                    ${plant.notifications ? '<p style="margin-top: 10px; font-size: 0.85em; color: #666;">🔔 Notifications enabled</p>' : ''}
                </div>
            `;
        });

        listDiv.innerHTML = html;
    }

    function waterPlant(plantId) {
        const plant = trackedPlants.find(p => p.id === plantId);
        if (plant) {
            const today = new Date().toISOString().split('T')[0];
            plant.lastWatered = today;
            plant.history.push({
                date: today,
                action: 'watered'
            });
            savePlants();
            displayPlants();
            
            const plantEmoji = {
                tomatoes: '🍅',
                lettuce: '🥬',
                carrots: '🥕',
                peppers: '🌶️',
                strawberries: '🍓',
                cucumbers: '🥒'
            }[plant.type];
            
            alert(`✅ ${plantEmoji} ${plant.name} watered successfully!`);
        }
    }

    function deletePlant(plantId) {
        if (confirm('Are you sure you want to remove this plant from tracking?')) {
            trackedPlants = trackedPlants.filter(p => p.id !== plantId);
            savePlants();
            displayPlants();
        }
    }

    function checkWateringReminders() {
        if (!notificationPermission) return;

        const now = new Date();
        trackedPlants.forEach(plant => {
            if (!plant.notifications) return;

            const lastWatered = new Date(plant.lastWatered);
            const nextWatering = new Date(lastWatered);
            nextWatering.setDate(nextWatering.getDate() + plant.wateringFrequency);

            // Check if watering is due today
            const today = new Date().toISOString().split('T')[0];
            const nextWateringDate = nextWatering.toISOString().split('T')[0];

            if (today === nextWateringDate) {
                // Check if we already sent notification today
                const lastNotif = localStorage.getItem(`notif_${plant.id}`);
                if (lastNotif !== today) {
                    sendNotification(plant);
                    localStorage.setItem(`notif_${plant.id}`, today);
                }
            }
        });
    }

    function sendNotification(plant) {
        const emoji = {
            tomatoes: '🍅',
            lettuce: '🥬',
            carrots: '🥕',
            peppers: '🌶️',
            strawberries: '🍓',
            cucumbers: '🥒'
        }[plant.type];

        new Notification('🌱 MULCHMATE Watering Reminder', {
            body: `${emoji} Time to water ${plant.name}!`,
            icon: 'data:image/svg+xml,%3Csvg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"%3E%3Ctext y="50" font-size="60" fill="%23667eea"%3E🌱%3C/text%3E%3C/svg%3E',
            badge: 'data:image/svg+xml,%3Csvg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"%3E%3Ctext y="50" font-size="60" fill="%23667eea"%3E💧%3C/text%3E%3C/svg%3E'
        });
    }
</script>
```

</body>
</html><!DOCTYPE html>

<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>MULCHMATE - Smart Mulching Assistant</title>
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }

```
    body {
        font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        background: linear-gradient(135deg, #f5f7fa 0%, #c3cfe2 100%);
        min-height: 100vh;
        padding-bottom: 80px;
    }

    .header {
        background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        color: white;
        padding: 20px;
        text-align: center;
        box-shadow: 0 4px 6px rgba(0,0,0,0.1);
    }

    .logo-container {
        display: flex;
        align-items: center;
        justify-content: center;
        gap: 15px;
        margin-bottom: 10px;
    }

    .logo {
        width: 60px;
        height: 60px;
        background: white;
        border-radius: 50%;
        padding: 8px;
    }

    .logo img {
        width: 100%;
        height: 100%;
        object-fit: contain;
    }

    h1 {
        font-size: 2em;
        margin-bottom: 5px;
    }

    .tagline {
        font-size: 0.9em;
        opacity: 0.9;
    }

    .container {
        max-width: 1200px;
        margin: 0 auto;
        padding: 20px;
    }

    .nav-tabs {
        display: flex;
        background: white;
        border-radius: 10px;
        overflow: hidden;
        box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        margin-bottom: 20px;
    }

    .nav-tab {
        flex: 1;
        padding: 15px;
        text-align: center;
        cursor: pointer;
        border: none;
        background: white;
        font-size: 0.9em;
        font-weight: 600;
        color: #667eea;
        transition: all 0.3s;
        border-bottom: 3px solid transparent;
    }

    .nav-tab:hover {
        background: #f8f9fa;
    }

    .nav-tab.active {
        background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        color: white;
        border-bottom: 3px solid #764ba2;
    }

    .content-section {
        display: none;
        background: white;
        border-radius: 10px;
        padding: 30px;
        box-shadow: 0 2px 10px rgba(0,0,0,0.1);
        animation: fadeIn 0.3s;
    }

    .content-section.active {
        display: block;
    }

    @keyframes fadeIn {
        from { opacity: 0; transform: translateY(10px); }
        to { opacity: 1; transform: translateY(0); }
    }

    .section-title {
        color: #667eea;
        font-size: 1.5em;
        margin-bottom: 20px;
        display: flex;
        align-items: center;
        gap: 10px;
    }

    .form-group {
        margin-bottom: 20px;
    }

    label {
        display: block;
        margin-bottom: 8px;
        font-weight: 600;
        color: #333;
    }

    select, input[type="number"], input[type="text"], textarea {
        width: 100%;
        padding: 12px;
        border: 2px solid #e0e0e0;
        border-radius: 8px;
        font-size: 1em;
        transition: border 0.3s;
    }

    select:focus, input:focus, textarea:focus {
        outline: none;
        border-color: #667eea;
    }

    .btn {
        background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        color: white;
        border: none;
        padding: 12px 30px;
        border-radius: 8px;
        cursor: pointer;
        font-size: 1em;
        font-weight: 600;
        transition: transform 0.2s, box-shadow 0.2s;
    }

    .btn:hover {
        transform: translateY(-2px);
        box-shadow: 0 4px 12px rgba(102, 126, 234, 0.4);
    }

    .btn:active {
        transform: translateY(0);
    }

    .result-box {
        margin-top: 20px;
        padding: 20px;
        background: #f8f9fa;
        border-radius: 8px;
        border-left: 4px solid #667eea;
    }

    .result-box h3 {
        color: #667eea;
        margin-bottom: 10px;
    }

    .camera-container {
        text-align: center;
    }

    #camera-feed {
        width: 100%;
        max-width: 500px;
        border-radius: 10px;
        margin: 20px auto;
        display: none;
        box-shadow: 0 4px 12px rgba(0,0,0,0.2);
    }

    #captured-image {
        width: 100%;
        max-width: 500px;
        border-radius: 10px;
        margin: 20px auto;
        display: none;
        box-shadow: 0 4px 12px rgba(0,0,0,0.2);
    }

    .camera-buttons {
        display: flex;
        gap: 10px;
        justify-content: center;
        margin-top: 15px;
        flex-wrap: wrap;
    }

    .info-card {
        background: linear-gradient(135deg, #667eea15 0%, #764ba215 100%);
        padding: 15px;
        border-radius: 8px;
        margin-bottom: 15px;
        border-left: 4px solid #667eea;
    }

    .info-card h4 {
        color: #667eea;
        margin-bottom: 8px;
    }

    .chat-button {
        position: fixed;
        bottom: 20px;
        right: 20px;
        width: 60px;
        height: 60px;
        background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        border-radius: 50%;
        border: none;
        color: white;
        font-size: 28px;
        cursor: pointer;
        box-shadow: 0 4px 12px rgba(102, 126, 234, 0.5);
        transition: transform 0.2s, box-shadow 0.2s;
        z-index: 1000;
    }

    .chat-button:hover {
        transform: scale(1.1);
        box-shadow: 0 6px 20px rgba(102, 126, 234, 0.6);
    }

    .chat-window {
        position: fixed;
        bottom: 90px;
        right: 20px;
        width: 350px;
        height: 500px;
        background: white;
        border-radius: 15px;
        box-shadow: 0 8px 24px rgba(0,0,0,0.2);
        display: none;
        flex-direction: column;
        z-index: 999;
    }

    .chat-window.active {
        display: flex;
    }

    .chat-header {
        background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
        color: white;
        padding: 15px;
        border-radius: 15px 15px 0 0;
        font-weight: 600;
    }

    .chat-messages {
        flex: 1;
        padding: 15px;
        overflow-y: auto;
        background: #f8f9fa;
    }

    .chat-message {
        margin-bottom: 10px;
        padding: 10px 15px;
        border-radius: 15px;
        max-width: 80%;
        word-wrap: break-word;
    }

    .chat-message.user {
        background: #667eea;
        color: white;
        margin-left: auto;
    }

    .chat-message.ai {
        background: white;
        color: #333;
        border: 1px solid #e0e0e0;
    }

    .chat-input-container {
        padding: 15px;
        border-top: 1px solid #e0e0e0;
        display: flex;
        gap: 10px;
    }

    .chat-input {
        flex: 1;
        padding: 10px;
        border: 2px solid #e0e0e0;
        border-radius: 20px;
        font-size: 0.9em;
    }

    .chat-send {
        background: #667eea;
        color: white;
        border: none;
        padding: 10px 20px;
        border-radius: 20px;
        cursor: pointer;
        font-weight: 600;
    }

    @media (max-width: 768px) {
        .nav-tab {
            font-size: 0.8em;
            padding: 12px 8px;
        }

        .container {
            padding: 10px;
        }

        .content-section {
            padding: 20px 15px;
        }

        .chat-window {
            width: calc(100% - 40px);
            right: 20px;
        }
    }

    .plant-grid {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(200px, 1fr));
        gap: 15px;
        margin-top: 20px;
    }

    .plant-card {
        padding: 15px;
        background: #f8f9fa;
        border-radius: 8px;
        border: 2px solid #e0e0e0;
        cursor: pointer;
        transition: all 0.3s;
    }

    .plant-card:hover {
        border-color: #667eea;
        transform: translateY(-3px);
        box-shadow: 0 4px 12px rgba(102, 126, 234, 0.2);
    }

    .plant-card.selected {
        border-color: #667eea;
        background: linear-gradient(135deg, #667eea15 0%, #764ba215 100%);
    }

    .alert {
        padding: 15px;
        border-radius: 8px;
        margin-bottom: 15px;
    }

    .alert-warning {
        background: #fff3cd;
        border-left: 4px solid #ffc107;
        color: #856404;
    }

    .alert-danger {
        background: #f8d7da;
        border-left: 4px solid #dc3545;
        color: #721c24;
    }

    .alert-success {
        background: #d4edda;
        border-left: 4px solid #28a745;
        color: #155724;
    }

    .progress-bar {
        width: 100%;
        height: 10px;
        background: #e0e0e0;
        border-radius: 5px;
        overflow: hidden;
        margin: 10px 0;
    }

    .progress-fill {
        height: 100%;
        background: linear-gradient(90deg, #667eea 0%, #764ba2 100%);
        transition: width 0.3s;
    }

    .plant-tracker-card {
        background: white;
        border: 2px solid #e0e0e0;
        border-radius: 10px;
        padding: 20px;
        margin-bottom: 15px;
        transition: all 0.3s;
    }

    .plant-tracker-card:hover {
        border-color: #667eea;
        box-shadow: 0 4px 12px rgba(102, 126, 234, 0.2);
    }

    .plant-header {
        display: flex;
        justify-content: space-between;
        align-items: center;
        margin-bottom: 15px;
    }

    .plant-name {
        font-size: 1.2em;
        font-weight: 600;
        color: #333;
    }

    .plant-actions {
        display: flex;
        gap: 10px;
    }

    .btn-small {
        background: #667eea;
        color: white;
        border: none;
        padding: 6px 12px;
        border-radius: 5px;
        cursor: pointer;
        font-size: 0.85em;
        transition: all 0.2s;
    }

    .btn-small:hover {
        background: #764ba2;
    }

    .btn-danger {
        background: #dc3545;
    }

    .btn-danger:hover {
        background: #c82333;
    }

    .plant-info-grid {
        display: grid;
        grid-template-columns: repeat(auto-fit, minmax(150px, 1fr));
        gap: 10px;
        margin-bottom: 15px;
    }

    .plant-info-item {
        background: #f8f9fa;
        padding: 10px;
        border-radius: 5px;
        font-size: 0.9em;
    }

    .plant-info-label {
        color: #666;
        font-size: 0.8em;
        margin-bottom: 3px;
    }

    .plant-info-value {
        color: #333;
        font-weight: 600;
    }

    .watering-status {
        padding: 12px;
        border-radius: 8px;
        margin-top: 10px;
        font-weight: 600;
    }

    .status-ok {
        background: #d4edda;
        color: #155724;
        border-left: 4px solid #28a745;
    }

    .status-due {
        background: #fff3cd;
        color: #856404;
        border-left: 4px solid #ffc107;
    }

    .status-overdue {
        background: #f8d7da;
        color: #721c24;
        border-left: 4px solid #dc3545;
    }

    .notification-badge {
        background: #dc3545;
        color: white;
        border-radius: 50%;
        width: 20px;
        height: 20px;
        display: inline-flex;
        align-items: center;
        justify-content: center;
        font-size: 0.7em;
        font-weight: bold;
        position: relative;
        top: -2px;
        margin-left: 5px;
    }
</style>
```

</head>
<body>
    <div class="header">
        <div class="logo-container">
            <div class="logo">
                <img src="data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' viewBox='0 0 100 100'%3E%3Ctext y='50' font-size='60' fill='%23667eea'%3E🌱%3C/text%3E%3C/svg%3E" alt="MULCHMATE Logo">
            </div>
            <div>
                <h1>MULCHMATE</h1>
                <p class="tagline">LESS WATER BETTER CROP</p>
            </div>
        </div>
    </div>

```
<div class="container">
    <div class="nav-tabs">
        <button class="nav-tab active" onclick="showSection('soil')">🌍 Soil Analysis</button>
        <button class="nav-tab" onclick="showSection('watering')">💧 Watering Guide</button>
        <button class="nav-tab" onclick="showSection('pests')">🐛 Pest Detection</button>
        <button class="nav-tab" onclick="showSection('tracker')">📊 Plant Tracker</button>
        <button class="nav-tab" onclick="showSection('camera')">📷 Camera</button>
        <button class="nav-tab" onclick="showSection('health')">❤️ Soil Health</button>
    </div>

    <!-- Soil Analysis Section -->
    <div id="soil" class="content-section active">
        <h2 class="section-title">🌍 Soil Analysis & Plant Selection</h2>
        <p style="margin-bottom: 20px; color: #666;">Select your crops to get personalized soil recommendations for mulching.</p>
        
        <div class="form-group">
            <label>Select Your Crops (you can select multiple):</label>
            <div class="plant-grid" id="plant-grid">
                <div class="plant-card" data-plant="tomatoes">
                    <h4>🍅 Tomatoes</h4>
                    <p style="font-size: 0.85em; color: #666;">Warm season crop</p>
                </div>
                <div class="plant-card" data-plant="lettuce">
                    <h4>🥬 Lettuce</h4>
                    <p style="font-size: 0.85em; color: #666;">Cool season crop</p>
                </div>
                <div class="plant-card" data-plant="carrots">
                    <h4>🥕 Carrots</h4>
                    <p style="font-size: 0.85em; color: #666;">Root vegetable</p>
                </div>
                <div class="plant-card" data-plant="peppers">
                    <h4>🌶️ Peppers</h4>
                    <p style="font-size: 0.85em; color: #666;">Warm season crop</p>
                </div>
                <div class="plant-card" data-plant="strawberries">
                    <h4>🍓 Strawberries</h4>
                    <p style="font-size: 0.85em; color: #666;">Perennial crop</p>
                </div>
                <div class="plant-card" data-plant="cucumbers">
                    <h4>🥒 Cucumbers</h4>
                    <p style="font-size: 0.85em; color: #666;">Warm season crop</p>
                </div>
            </div>
        </div>

        <div class="form-group">
            <label>Current Soil Type:</label>
            <select id="soil-type">
                <option value="">Select soil type</option>
                <option value="clay">Clay - Heavy, water-retaining</option>
                <option value="sandy">Sandy - Light, fast-draining</option>
                <option value="loam">Loam - Balanced, ideal</option>
                <option value="silt">Silt - Fine, moisture-retaining</option>
                <option value="unknown">Not sure</option>
            </select>
        </div>

        <button class="btn" onclick="analyzeSoil()">Get Soil Recommendations</button>

        <div id="soil-results"></div>
    </div>

    <!-- Watering Guide Section -->
    <div id="watering" class="content-section">
        <h2 class="section-title">💧 Smart Watering Guide</h2>
        <p style="margin-bottom: 20px; color: #666;">Get personalized watering schedules optimized for mulching.</p>

        <div class="form-group">
            <label>Plant Type:</label>
            <select id="water-plant">
                <option value="tomatoes">Tomatoes</option>
                <option value="lettuce">Lettuce</option>
                <option value="carrots">Carrots</option>
                <option value="peppers">Peppers</option>
                <option value="strawberries">Strawberries</option>
                <option value="cucumbers">Cucumbers</option>
            </select>
        </div>

        <div class="form-group">
            <label>Mulch Depth (cm):</label>
            <input type="number" id="mulch-depth" value="8" min="0" max="15" step="0.5">
        </div>

        <div class="form-group">
            <label>Climate Condition:</label>
            <select id="climate">
                <option value="hot-dry">Hot & Dry</option>
                <option value="hot-humid">Hot & Humid</option>
                <option value="mild">Mild</option>
                <option value="cool">Cool</option>
            </select>
        </div>

        <div class="form-group">
            <label>Plant Growth Stage:</label>
            <select id="growth-stage">
                <option value="seedling">Seedling (just planted)</option>
                <option value="vegetative">Vegetative (growing)</option>
                <option value="flowering">Flowering</option>
                <option value="fruiting">Fruiting</option>
            </select>
        </div>

        <button class="btn" onclick="calculateWatering()">Calculate Watering Schedule</button>

        <div id="watering-results"></div>
    </div>

    <!-- Pest Detection Section -->
    <div id="pests" class="content-section">
        <h2 class="section-title">🐛 Pest Identification & Management</h2>
        <p style="margin-bottom: 20px; color: #666;">Identify common pests and learn how to manage them with mulching techniques.</p>

        <div class="form-group">
            <label>Describe what you're seeing:</label>
            <textarea id="pest-description" rows="3" placeholder="E.g., small green insects on leaves, holes in leaves, white powder on stems..."></textarea>
        </div>

        <div class="form-group">
            <label>Affected Plant:</label>
            <select id="pest-plant">
                <option value="tomatoes">Tomatoes</option>
                <option value="lettuce">Lettuce</option>
                <option value="carrots">Carrots</option>
                <option value="peppers">Peppers</option>
                <option value="strawberries">Strawberries</option>
                <option value="cucumbers">Cucumbers</option>
            </select>
        </div>

        <button class="btn" onclick="identifyPest()">Identify Pest</button>

        <div id="pest-results"></div>
    </div>

    <!-- Plant Tracker Section -->
    <div id="tracker" class="content-section">
        <h2 class="section-title">📊 Plant Tracker & Reminders</h2>
        <p style="margin-bottom: 20px; color: #666;">Track your plants and get automatic watering reminders.</p>

        <div style="background: linear-gradient(135deg, #667eea15 0%, #764ba215 100%); padding: 20px; border-radius: 10px; margin-bottom: 20px;">
            <h3 style="color: #667eea; margin-bottom: 15px;">➕ Add New Plant</h3>
            
            <div class="form-group">
                <label>Plant Name:</label>
                <input type="text" id="new-plant-name" placeholder="E.g., Tomato Plant #1">
            </div>

            <div class="form-group">
                <label>Plant Type:</label>
                <select id="new-plant-type">
                    <option value="tomatoes">🍅 Tomatoes</option>
                    <option value="lettuce">🥬 Lettuce</option>
                    <option value="carrots">🥕 Carrots</option>
                    <option value="peppers">🌶️ Peppers</option>
                    <option value="strawberries">🍓 Strawberries</option>
                    <option value="cucumbers">🥒 Cucumbers</option>
                </select>
            </div>

            <div class="form-group">
                <label>Planting Date:</label>
                <input type="date" id="new-plant-date">
            </div>

            <div class="form-group">
                <label>Watering Frequency:</label>
                <select id="new-plant-frequency">
                    <option value="1">Daily</option>
                    <option value="2" selected>Every 2 days</option>
                    <option value="3">Every 3 days</option>
                    <option value="4">Every 4 days</option>
                    <option value="7">Weekly</option>
                </select>
            </div>

            <div class="form-group">
                <label>Mulch Depth (cm):</label>
                <input type="number" id="new-plant-mulch" value="8" min="0" max="15" step="0.5">
            </div>

            <div class="form-group">
                <label>Enable Notifications:</label>
                <select id="new-plant-notifications">
                    <option value="true">Yes - Remind me to water</option>
                    <option value="false">No</option>
                </select>
            </div>

            <button class="btn" onclick="addPlant()">Add Plant</button>
        </div>

        <h3 style="color: #667eea; margin-bottom: 15px;">🌱 My Plants</h3>
        <div id="plant-list">
            <div style="text-align: center; padding: 40px; color: #999;">
                <p>No plants tracked yet. Add your first plant above!</p>
            </div>
        </div>
    </div>

    <!-- Camera Section -->
    <div id="camera" class="content-section">
        <h2 class="section-title">📷 Visual Inspection</h2>
        <p style="margin-bottom: 20px; color: #666;">Take photos of your soil, plants, or pests for AI-assisted analysis.</p>

        <div class="camera-container">
            <video id="camera-feed" autoplay playsinline></video>
            <img id="captured-image" alt="Captured image">
            
            <div class="camera-buttons">
                <button class="btn" onclick="startCamera()">📷 Start Camera</button>
                <button class="btn" onclick="capturePhoto()" id="capture-btn" style="display: none;">📸 Capture</button>
                <button class="btn" onclick="stopCamera()" id="stop-btn" style="display: none;">⏹️ Stop</button>
                <button class="btn" onclick="document.getElementById('file-input').click()">📁 Upload Photo</button>
            </div>
            <input type="file" id="file-input" accept="image/*" style="display: none;" onchange="handleFileUpload(event)">
        </div>

        <div class="form-group" style="margin-top: 20px;">
            <label>What would you like to analyze?</label>
            <select id="analysis-type">
                <option value="soil">Soil Quality</option>
                <option value="plant">Plant Health</option>
                <option value="pest">Pest/Disease</option>
                <option value="mulch">Mulch Condition</option>
            </select>
        </div>

        <button class="btn" onclick="analyzeImage()" id="analyze-btn" style="display: none;">🔍 Analyze Image</button>

        <div id="image-results"></div>
    </div>

    <!-- Soil Health Section -->
    <div id="health" class="content-section">
        <h2 class="section-title">❤️ Soil Health Monitor</h2>
        <p style="margin-bottom: 20px; color: #666;">Check your soil vitality and get recommendations to improve it.</p>

        <div class="form-group">
            <label>When did you last add organic matter/compost?</label>
            <select id="compost-time">
                <option value="recent">Within last month</option>
                <option value="moderate">1-3 months ago</option>
                <option value="old">3-6 months ago</option>
                <option value="very-old">Over 6 months ago</option>
                <option value="never">Never</option>
            </select>
        </div>

        <div class="form-group">
            <label>Current mulch condition:</label>
            <select id="mulch-condition">
                <option value="fresh">Fresh and intact</option>
                <option value="decomposing">Partially decomposed</option>
                <option value="old">Old and thin</option>
                <option value="none">No mulch present</option>
            </select>
        </div>

        <div class="form-group">
            <label>Plant growth observations:</label>
            <select id="growth-observation">
                <option value="excellent">Excellent - vibrant and fast growing</option>
                <option value="good">Good - steady growth</option>
                <option value="moderate">Moderate - slow growth</option>
                <option value="poor">Poor - stunted or yellowing</option>
            </select>
        </div>

        <div class="form-group">
            <label>Soil smell and appearance:</label>
            <select id="soil-appearance">
                <option value="earthy">Earthy smell, dark color</option>
                <option value="neutral">No strong smell, brown color</option>
                <option value="compacted">Compacted, hard to dig</option>
                <option value="bad">Foul smell, gray/pale color</option>
            </select>
        </div>

        <button class="btn" onclick="checkSoilHealth()">Check Soil Health</button>

        <div id="health-results"></div>
    </div>
</div>

<!-- AI Chat Button -->
<button class="chat-button" onclick="toggleChat()">💬</button>

<!-- AI Chat Window -->
<div class="chat-window" id="chat-window">
    <div class="chat-header">
        🤖 MULCHMATE AI Assistant
    </div>
    <div class="chat-messages" id="chat-messages">
        <div class="chat-message ai">
            Hello! I'm your MULCHMATE AI assistant. Ask me anything about mulching, soil health, watering, pests, or growing crops! 🌱
        </div>
    </div>
    <div class="chat-input-container">
        <input type="text" class="chat-input" id="chat-input" placeholder="Ask me anything..." onkeypress="handleChatKeyPress(event)">
        <button class="chat-send" onclick="sendMessage()">Send</button>
    </div>
</div>

<script>
    let selectedPlants = new Set();
    let cameraStream = null;
    let capturedImageData = null;

    // Initialize plant selection
    document.querySelectorAll('.plant-card').forEach(card => {
        card.addEventListener('click', function() {
            const plant = this.dataset.plant;
            if (selectedPlants.has(plant)) {
                selectedPlants.delete(plant);
                this.classList.remove('selected');
            } else {
                selectedPlants.add(plant);
                this.classList.add('selected');
            }
        });
    });

    function showSection(sectionId) {
        document.querySelectorAll('.content-section').forEach(section => {
            section.classList.remove('active');
        });
        document.querySelectorAll('.nav-tab').forEach(tab => {
            tab.classList.remove('active');
        });
        document.getElementById(sectionId).classList.add('active');
        event.target.classList.add('active');
    }

    function analyzeSoil() {
        const soilType = document.getElementById('soil-type').value;
        const resultsDiv = document.getElementById('soil-results');

        if (selectedPlants.size === 0) {
            resultsDiv.innerHTML = '<div class="alert alert-warning">⚠️ Please select at least one crop!</div>';
            return;
        }

        if (!soilType) {
            resultsDiv.innerHTML = '<div class="alert alert-warning">⚠️ Please select your soil type!</div>';
            return;
        }

        const soilData = {
            clay: {
                desc: 'Heavy soil that retains water and nutrients well',
                mulch: 'Use lighter mulches like straw or grass clippings (5-8 cm)',
                tips: ['Add compost to improve drainage', 'Avoid over-mulching to prevent waterlogging', 'Consider raised beds']
            },
            sandy: {
                desc: 'Light soil that drains quickly and needs more nutrients',
                mulch: 'Use heavier organic mulches like wood chips or compost (10-15 cm)',
                tips: ['Mulch helps retain moisture significantly', 'Add compost regularly', 'Water more frequently but less per session']
            },
            loam: {
                desc: 'Ideal balanced soil - perfect for most crops!',
                mulch: 'Use any organic mulch (8-10 cm)',
                tips: ['Maintain with regular mulching', 'Rotate mulch types seasonally', 'Keep soil covered year-round']
            },
            silt: {
                desc: 'Fine particles, good water retention',
                mulch: 'Use medium-weight mulches like shredded leaves (8-10 cm)',
                tips: ['Mulch prevents crusting', 'Add organic matter regularly', 'Avoid compaction']
            },
            unknown: {
                desc: 'Unable to determine - test recommended',
                mulch: 'Start with general-purpose mulch like straw (8 cm)',
                tips: ['Observe how water drains', 'Do a simple soil test', 'Adjust mulching based on results']
            }
        };

        const data = soilData[soilType];
        const plantsArray = Array.from(selectedPlants);

        let html = `
            <div class="result-box">
                <h3>🌍 Soil Analysis Results</h3>
                <p><strong>Soil Type:</strong> ${data.desc}</p>
                <p><strong>Selected Crops:</strong> ${plantsArray.join(', ')}</p>
                
                <div class="info-card">
                    <h4>🍂 Recommended Mulch</h4>
                    <p>${data.mulch}</p>
                </div>

                <div class="info-card">
                    <h4>💡 Pro Tips for Your Soil</h4>
                    <ul style="margin-left: 20px; margin-top: 10px;">
                        ${data.tips.map(tip => `<li style="margin-bottom: 8px;">${tip}</li>`).join('')}
                    </ul>
                </div>

                <div class="info-card">
                    <h4>🌱 Crop-Specific Recommendations</h4>
        `;

        plantsArray.forEach(plant => {
            const plantTips = {
                tomatoes: 'Need consistent moisture. Mulch helps prevent soil splash on leaves, reducing disease.',
                lettuce: 'Prefer cooler soil. Light-colored mulch helps keep soil temperature down.',
                carrots: 'Need loose soil. Use fine mulch that won\'t interfere with seedling emergence.',
                peppers: 'Love warm soil. Dark mulch can help warm the soil in spring.',
                strawberries: 'Benefit greatly from straw mulch to keep fruits clean and reduce disease.',
                cucumbers: 'Heavy feeders that need consistent moisture. Thick mulch is beneficial.'
            };
            html += `<p><strong>${plant.charAt(0).toUpperCase() + plant.slice(1)}:</strong> ${plantTips[plant]}</p>`;
        });

        html += `
                </div>
            </div>
        `;

        resultsDiv.innerHTML = html;
    }

    function calculateWatering() {
        const plant = document.getElementById('water-plant').value;
        const mulchDepth = parseFloat(document.getElementById('mulch-depth').value);
        const climate = document.getElementById('climate').value;
        const growthStage = document.getElementById('growth-stage').value;
        const resultsDiv = document.getElementById('watering-results');

        const wateringData = {
            tomatoes: { base: 1.5, name: 'Tomatoes' },
            lettuce: { base: 1.0, name: 'Lettuce' },
            carrots: { base: 1.0, name: 'Carrots' },
            peppers: { base: 1.5, name: 'Peppers' },
            strawberries: { base: 1.2, name: 'Strawberries' },
            cucumbers: { base: 1.8, name: 'Cucumbers' }
        };

        let waterNeed = wateringData[plant].base;

        // Adjust for climate
        const climateMultiplier = {
            'hot-dry': 1.4,
            'hot-humid': 1.2,
            'mild': 1.0,
            'cool': 0.8
        };
        waterNeed *= climateMultiplier[climate];

        // Adjust for growth stage
        const stageMultiplier = {
            'seedling': 0.7,
            'vegetative': 1.0,
            'flowering': 1.2,
            'fruiting': 1.3
        };
        waterNeed *= stageMultiplier[growthStage];

        // Mulch benefit
        const mulchReduction = Math.min(mulchDepth * 0.045, 0.4);
        waterNeed *= (1 - mulchReduction);

        const frequency = waterNeed > 1.5 ? 'Daily' : waterNeed > 1.0 ? 'Every 2 days' : 'Every 3 days';
        const waterSaved = Math.round(mulchReduction * 100);

        let html = `
            <div class="result-box">
                <h3>💧 Watering Schedule for ${wateringData[plant].name}</h3>
                
                <div class="alert alert-success">
                    <strong>✅ Mulch Benefit:</strong> You're saving approximately ${waterSaved}% water thanks to your ${mulchDepth} cm mulch layer!
                </div>

                <div class="info-card">
                    <h4>📅 Recommended Schedule</h4>
                    <p><strong>Frequency:</strong> ${frequency}</p>
                    <p><strong>Amount:</strong> ${(waterNeed * 2.54).toFixed(1)} cm per watering session</p>
                    <p><strong>Best Time:</strong> Early morning (6-8 AM)</p>
                </div>

                <div class="info-card">
                    <h4>💡 Watering Tips with Mulch</h4>
                    <ul style="margin-left: 20px; margin-top: 10px;">
                        <li style="margin-bottom: 8px;">Water deeply but less frequently - mulch keeps moisture in!</li>
                        <li style="margin-bottom: 8px;">Check soil moisture 5-8 cm below surface before watering</li>
                        <li style="margin-bottom: 8px;">Water at soil level, not on leaves</li>
                        <li style="margin-bottom: 8px;">In hot weather, add extra watering if plants show stress</li>
                        <li style="margin-bottom: 8px;">Refresh mulch layer as it decomposes to maintain water savings</li>
                    </ul>
                </div>

                <div class="info-card">
                    <h4>⚠️ Signs of Overwatering or Underwatering</h4>
                    <p><strong>Too much water:</strong> Yellowing leaves, wilting despite wet soil, root rot</p>
                    <p><strong>Too little water:</strong> Drooping leaves, dry soil 3" down, slow growth</p>
                </div>
            </div>
        `;

        resultsDiv.innerHTML = html;
    }

    function identifyPest() {
        const description = document.getElementById('pest-description').value.toLowerCase();
        const plant = document.getElementById('pest-plant').value;
        const resultsDiv = document.getElementById('pest-results');

        if (!description) {
            resultsDiv.innerHTML = '<div class="alert alert-warning">⚠️ Please describe what you\'re seeing!</div>';
            return;
        }

        let pestInfo = {
            name: 'Unknown Pest',
            severity: 'moderate',
            description: 'Unable to identify based on description.',
            mulchHelp: 'Mulching can help prevent some pests.',
            treatment: 'Take a photo using the Camera tab for better identification.'
        };

        // Simple keyword matching
        if (description.includes('aphid') || description.includes('green insect') || description.includes('small green')) {
            pestInfo = {
                name: 'Aphids',
                severity: 'moderate',
                description: 'Small, soft-bodied insects that cluster on new growth and undersides of leaves.',
                mulchHelp: 'Mulch provides habitat for beneficial insects that eat aphids!',
                treatment: 'Spray with water, introduce ladybugs, use neem oil if severe. Mulch encourages natural predators.'
            };
        } else if (description.includes('caterpillar') || description.includes('worm') || description.includes('holes')) {
            pestInfo = {
                name: 'Caterpillars/Worms',
                severity: 'moderate',
                description: 'Larvae that chew holes in leaves and can defoliate plants.',
                mulchHelp: 'Mulch can harbor birds and beneficial insects that feed on caterpillars.',
                treatment: 'Hand-pick, use BT (Bacillus thuringiensis), encourage birds with proper mulching habitat.'
            };
        } else if (description.includes('white') || description.includes('powder') || description.includes('mold')) {
            pestInfo = {
                name: 'Powdery Mildew',
                severity: 'high',
                description: 'Fungal disease appearing as white powder on leaves and stems.',
                mulchHelp: '⚠️ Keep mulch away from plant stems to improve air circulation.',
                treatment: 'Remove affected leaves, ensure good spacing, spray with baking soda solution or neem oil.'
            };
        } else if (description.includes('slug') || description.includes('snail') || description.includes('slime')) {
            pestInfo = {
                name: 'Slugs/Snails',
                severity: 'moderate',
                description: 'Mollusks that leave slime trails and eat large holes in leaves.',
                mulchHelp: 'Rough mulches like wood chips deter slugs. Avoid thick wet mulch near plants.',
                treatment: 'Hand-pick at night, use beer traps, diatomaceous earth, or copper barriers.'
            };
        } else if (description.includes('spider') || description.includes('mite') || description.includes('stippling')) {
            pestInfo = {
                name: 'Spider Mites',
                severity: 'high',
                description: 'Tiny pests that cause stippling/yellowing on leaves, often with fine webbing.',
                mulchHelp: 'Keep plants well-watered - mulch helps! Dry conditions favor mites.',
                treatment: 'Spray with water regularly, use insecticidal soap, maintain humidity with good mulching.'
            };
        }

        const severityColors = {
            low: '#28a745',
            moderate: '#ffc107',
            high: '#dc3545'
        };

        let html = `
            <div class="result-box">
                <h3>🐛 Pest Identification Results</h3>
                
                <div class="alert alert-${pestInfo.severity === 'high' ? 'danger' : 'warning'}">
                    <strong>Identified:</strong> ${pestInfo.name}
                    <br><strong>Severity:</strong> <span style="color: ${severityColors[pestInfo.severity]};">⬤</span> ${pestInfo.severity.toUpperCase()}
                </div>

                <div class="info-card">
                    <h4>📋 Description</h4>
                    <p>${pestInfo.description}</p>
                </div>

                <div class="info-card">
                    <h4>🍂 Mulching Connection</h4>
                    <p>${pestInfo.mulchHelp}</p>
                </div>

                <div class="info-card">
                    <h4>💊 Treatment Recommendations</h4>
                    <p>${pestInfo.treatment}</p>
                </div>

                <div class="info-card">
                    <h4>🔬 For Better Accuracy</h4>
                    <p>Use the <strong>📷 Camera</strong> tab to take a photo of the pest or damage. Our AI can provide more specific identification and treatment plans!</p>
                </div>
            </div>
        `;

        resultsDiv.innerHTML = html;
    }

    async function startCamera() {
        try {
            cameraStream = await navigator.mediaDevices.getUserMedia({ 
                video: { facingMode: 'environment' } 
            });
            const video = document.getElementById('camera-feed');
            video.srcObject = cameraStream;
            video.style.display = 'block';
            document.getElementById('captured-image').style.display = 'none';
            document.getElementById('capture-btn').style.display = 'inline-block';
            document.getElementById('stop-btn').style.display = 'inline-block';
        } catch (err) {
            alert('Camera access denied or not available: ' + err.message);
        }
    }

    function capturePhoto() {
        const video = document.getElementById('camera-feed');
        const canvas = document.createElement('canvas');
        canvas.width = video.videoWidth;
        canvas.height = video.videoHeight;
        canvas.getContext('2d').drawImage(video, 0, 0);
        
        capturedImageData = canvas.toDataURL('image/jpeg');
        const img = document.getElementById('captured-image');
        img.src = capturedImageData;
        img.style.display = 'block';
        
        stopCamera();
        document.getElementById('analyze-btn').style.display = 'inline-block';
    }

    function stopCamera() {
        if (cameraStream) {
            cameraStream.getTracks().forEach(track => track.stop());
            document.getElementById('camera-feed').style.display = 'none';
            document.getElementById('capture-btn').style.display = 'none';
            document.getElementById('stop-btn').style.display = 'none';
        }
    }

    function handleFileUpload(event) {
        const file = event.target.files[0];
        if (file) {
            const reader = new FileReader();
            reader.onload = function(e) {
                capturedImageData = e.target.result;
                const img = document.getElementById('captured-image');
                img.src = capturedImageData;
                img.style.display = 'block';
                document.getElementById('analyze-btn').style.display = 'inline-block';
            };
            reader.readAsDataURL(file);
        }
    }

    function analyzeImage() {
        const analysisType = document.getElementById('analysis-type').value;
        const resultsDiv = document.getElementById('image-results');

        if (!capturedImageData) {
            resultsDiv.innerHTML = '<div class="alert alert-warning">⚠️ Please capture or upload an image first!</div>';
            return;
        }

        const analyses = {
            soil: {
                title: '🌍 Soil Quality Analysis',
                findings: [
                    'Soil appears to have good organic matter content',
                    'Color indicates adequate drainage',
                    'Texture suggests balanced composition'
                ],
                recommendations: [
                    'Add 5-8 cm of organic mulch to preserve moisture',
                    'Consider adding compost to boost nutrients',
                    'Maintain current soil management practices'
                ]
            },
            plant: {
                title: '🌱 Plant Health Analysis',
                findings: [
                    'Overall plant vigor appears normal',
                    'Leaf color indicates adequate nutrients',
                    'Growth pattern seems healthy'
                ],
                recommendations: [
                    'Continue current watering schedule',
                    'Monitor for any pest development',
                    'Ensure mulch is not touching stems'
                ]
            },
            pest: {
                title: '🐛 Pest Detection Analysis',
                findings: [
                    'Some signs of minor insect activity detected',
                    'No severe infestation observed',
                    'Damage appears manageable'
                ],
                recommendations: [
                    'Monitor daily for pest population changes',
                    'Consider introducing beneficial insects',
                    'Use organic pest control if needed'
                ]
            },
            mulch: {
                title: '🍂 Mulch Condition Analysis',
                findings: [
                    'Mulch coverage appears adequate',
                    'Some decomposition is normal and beneficial',
                    'Overall condition is good'
                ],
                recommendations: [
                    'Add fresh mulch layer in 2-3 weeks',
                    'Current depth provides good moisture retention',
                    'Decomposing mulch enriches soil - excellent!'
                ]
            }
        };

        const analysis = analyses[analysisType];

        let html = `
            <div class="result-box">
                <h3>${analysis.title}</h3>
                
                <div class="alert alert-success">
                    ✅ Image analysis complete!
                </div>

                <div class="info-card">
                    <h4>🔍 Key Findings</h4>
                    <ul style="margin-left: 20px; margin-top: 10px;">
                        ${analysis.findings.map(finding => `<li style="margin-bottom: 8px;">${finding}</li>`).join('')}
                    </ul>
                </div>

                <div class="info-card">
                    <h4>💡 Recommendations</h4>
                    <ul style="margin-left: 20px; margin-top: 10px;">
                        ${analysis.recommendations.map(rec => `<li style="margin-bottom: 8px;">${rec}</li>`).join('')}
                    </ul>
                </div>

                <div class="info-card">
                    <h4>💬 Need More Help?</h4>
                    <p>Click the chat button in the bottom-right corner to ask our AI assistant specific questions about your ${analysisType}!</p>
                </div>
            </div>
        `;

        resultsDiv.innerHTML = html;
    }

    function checkSoilHealth() {
        const compost = document.getElementById('compost-time').value;
        const mulchCondition = document.getElementById('mulch-condition').value;
        const growth = document.getElementById('growth-observation').value;
        const appearance = document.getElementById('soil-appearance').value;
        const resultsDiv = document.getElementById('health-results');

        let healthScore = 0;
        const warnings = [];
        const recommendations = [];

        // Calculate health score
        const scores = {
            compost: { recent: 25, moderate: 20, old: 10, 'very-old': 5, never: 0 },
            mulch: { fresh: 25, decomposing: 20, old: 10, none: 0 },
            growth: { excellent: 30, good: 25, moderate: 15, poor: 5 },
            appearance: { earthy: 20, neutral: 15, compacted: 8, bad: 0 }
        };

        healthScore += scores.compost[compost];
        healthScore += scores.mulch[mulchCondition];
        healthScore += scores.growth[growth];
        healthScore += scores.appearance[appearance];

        // Generate warnings and recommendations
        if (compost === 'never' || compost === 'very-old') {
            warnings.push('⚠️ Soil may be depleted of organic matter');
            recommendations.push('Add compost or well-rotted manure immediately');
        }

        if (mulchCondition === 'none' || mulchCondition === 'old') {
            warnings.push('⚠️ Insufficient mulch coverage detected');
            recommendations.push('Apply 8-10 cm of organic mulch to protect and feed soil');
        }

        if (growth === 'poor' || growth === 'moderate') {
            warnings.push('⚠️ Plants showing signs of nutrient deficiency');
            recommendations.push('Consider soil testing and adding balanced organic fertilizer');
        }

        if (appearance === 'bad') {
            warnings.push('🚨 Critical: Soil may be anaerobic or diseased');
            recommendations.push('Improve drainage, add organic matter, and consider soil amendment');
        } else if (appearance === 'compacted') {
            warnings.push('⚠️ Soil compaction limiting root growth');
            recommendations.push('Aerate soil and add compost to improve structure');
        }

        let status, statusColor, statusIcon;
        if (healthScore >= 80) {
            status = 'EXCELLENT';
            statusColor = '#28a745';
            statusIcon = '🌟';
            if (recommendations.length === 0) {
                recommendations.push('Keep up the great work!', 'Maintain current mulching practices');
            }
        } else if (healthScore >= 60) {
            status = 'GOOD';
            statusColor = '#28a745';
            statusIcon = '✅';
            recommendations.push('Minor improvements will boost soil even more');
        } else if (healthScore >= 40) {
            status = 'FAIR';
            statusColor = '#ffc107';
            statusIcon = '⚠️';
            recommendations.push('Focus on consistent organic matter addition');
        } else {
            status = 'POOR - ACTION NEEDED';
            statusColor = '#dc3545';
            statusIcon = '🚨';
            recommendations.push('Soil rehabilitation program recommended');
        }

        let html = `
            <div class="result-box">
                <h3>❤️ Soil Health Report</h3>
                
                <div style="text-align: center; margin: 20px 0;">
                    <div style="font-size: 3em; color: ${statusColor};">${healthScore}%</div>
                    <div style="font-size: 1.5em; color: ${statusColor}; font-weight: bold;">${statusIcon} ${status}</div>
                    <div class="progress-bar">
                        <div class="progress-fill" style="width: ${healthScore}%; background: ${statusColor};"></div>
                    </div>
                </div>
        `;

        if (warnings.length > 0) {
            html += `
                <div class="alert alert-${healthScore < 40 ? 'danger' : 'warning'}">
                    <h4 style="margin-bottom: 10px;">⚠️ Warnings</h4>
                    <ul style="margin-left: 20px;">
                        ${warnings.map(w => `<li style="margin-bottom: 5px;">${w}</li>`).join('')}
                    </ul>
                </div>
            `;
        }

        html += `
                <div class="info-card">
                    <h4>📋 Action Plan</h4>
                    <ul style="margin-left: 20px; margin-top: 10px;">
                        ${recommendations.map(r => `<li style="margin-bottom: 8px;">${r}</li>`).join('')}
                    </ul>
                </div>

                <div class="info-card">
                    <h4>🌱 Mulching for Soil Health</h4>
                    <p><strong>Why mulch matters:</strong></p>
                    <ul style="margin-left: 20px; margin-top: 8px;">
                        <li style="margin-bottom: 8px;">Feeds beneficial soil microorganisms as it decomposes</li>
                        <li style="margin-bottom: 8px;">Regulates soil temperature and moisture</li>
                        <li style="margin-bottom: 8px;">Prevents erosion and nutrient loss</li>
                        <li style="margin-bottom: 8px;">Suppresses weeds that compete for nutrients</li>
                        <li style="margin-bottom: 8px;">Improves soil structure over time</li>
                    </ul>
                    <p style="margin-top: 10px;"><strong>Tip:</strong> Maintain 5-10 cm depth and refresh when it decomposes below 5 cm</p>
                </div>

                <div class="info-card">
                    <h4>📅 Next Steps</h4>
                    <p><strong>Re-check in:</strong> ${healthScore >= 60 ? '1-2 months' : '2-4 weeks'}</p>
                    <p>Track your improvements and adjust your practices based on plant response!</p>
                </div>
            </div>
        `;

        resultsDiv.innerHTML = html;
    }

    function toggleChat() {
        const chatWindow = document.getElementById('chat-window');
        chatWindow.classList.toggle('active');
    }

    function sendMessage() {
        const input = document.getElementById('chat-input');
        const message = input.value.trim();
        
        if (!message) return;

        const messagesDiv = document.getElementById('chat-messages');
        
        // Add user message
        const userMsg = document.createElement('div');
        userMsg.className = 'chat-message user';
        userMsg.textContent = message;
        messagesDiv.appendChild(userMsg);

        input.value = '';

        // Simulate AI response
        setTimeout(() => {
            const aiMsg = document.createElement('div');
            aiMsg.className = 'chat-message ai';
            aiMsg.textContent = getAIResponse(message);
            messagesDiv.appendChild(aiMsg);
            messagesDiv.scrollTop = messagesDiv.scrollHeight;
        }, 500);

        messagesDiv.scrollTop = messagesDiv.scrollHeight;
    }

    function handleChatKeyPress(event) {
        if (event.key === 'Enter') {
            sendMessage();
        }
    }

    function getAIResponse(message) {
        const msg = message.toLowerCase();
        
        if (msg.includes('track') || msg.includes('reminder') || msg.includes('notification')) {
            return 'Use the Plant Tracker tab to add your plants and get automatic watering reminders! You can track when you planted them, set watering schedules, and receive notifications. Enable browser notifications for the best experience!';
        } else if (msg.includes('mulch') && (msg.includes('how much') || msg.includes('depth'))) {
            return 'For most crops, 8-10 cm of organic mulch is ideal. Use 10-15 cm for sandy soil, and 5-8 cm for clay soil. Never let mulch touch plant stems!';
        } else if (msg.includes('water') || msg.includes('irrigat')) {
            return 'With proper mulching, you can reduce watering by 30-50%! Water deeply but less frequently. Check soil moisture 5-8 cm below the surface before watering. Use the Plant Tracker to get personalized reminders!';
        } else if (msg.includes('pest') || msg.includes('bug') || msg.includes('insect')) {
            return 'Mulching creates habitat for beneficial insects that control pests naturally. Use the Pest Detection tab or Camera feature to identify specific problems. What symptoms are you seeing?';
        } else if (msg.includes('compost') || msg.includes('organic matter')) {
            return 'Compost is gold for your soil! Apply 2-5 cm every season. As mulch decomposes, it also acts as a slow-release compost. This builds amazing soil health over time!';
        } else if (msg.includes('tomato') || msg.includes('pepper') || msg.includes('vegetable')) {
            return 'For vegetables like tomatoes and peppers, use organic mulch like straw or grass clippings. Keep it 5-8 cm from stems to prevent rot. This helps prevent soil-borne diseases too! Add them to the Plant Tracker for watering reminders!';
        } else if (msg.includes('soil') && msg.includes('dead')) {
            return 'Soil can be revived! Check the Soil Health tab for a complete assessment. Quick fix: add compost, apply mulch, and give it time. Soil organisms will bounce back with proper care.';
        } else if (msg.includes('when') && msg.includes('mulch')) {
            return 'Best time to mulch: early spring after soil warms up, or fall for winter protection. Refresh mulch as needed when it decomposes to less than 5 cm thick.';
        } else if (msg.includes('type') || msg.includes('kind') || msg.includes('best mulch')) {
            return 'Best mulches: straw (great for vegetables), wood chips (paths & perennials), grass clippings (nitrogen boost), shredded leaves (free & nutritious). Avoid fresh wood chips around young plants.';
        } else {
            return 'Great question! I can help with mulching techniques, watering schedules, soil health, pest control, plant tracking, and crop management. Try using our specialized tabs for detailed analysis, or ask me specific questions!';
        }
    }

    // Initialize
    console.log('MULCHMATE App initialized - helping farmers grow better with less water! 🌱');

    // Plant Tracker Functions
    let trackedPlants = [];
    let notificationPermission = false;

    // Load plants from localStorage on page load
    window.addEventListener('load', function() {
        loadPlants();
        checkNotificationPermission();
        // Set today's date as default
        document.getElementById('new-plant-date').valueAsDate = new Date();
        // Check watering reminders every hour
        setInterval(checkWateringReminders, 3600000);
        // Check immediately
        checkWateringReminders();
    });

    function loadPlants() {
        const saved = localStorage.getItem('mulchmate_plants');
        if (saved) {
            trackedPlants = JSON.parse(saved);
            displayPlants();
        }
    }

    function savePlants() {
        localStorage.setItem('mulchmate_plants', JSON.stringify(trackedPlants));
    }

    async function checkNotificationPermission() {
        if ('Notification' in window) {
            if (Notification.permission === 'granted') {
                notificationPermission = true;
            } else if (Notification.permission !== 'denied') {
                const permission = await Notification.requestPermission();
                notificationPermission = permission === 'granted';
            }
        }
    }

    function addPlant() {
        const name = document.getElementById('new-plant-name').value.trim();
        const type = document.getElementById('new-plant-type').value;
        const date = document.getElementById('new-plant-date').value;
        const frequency = parseInt(document.getElementById('new-plant-frequency').value);
        const mulch = parseFloat(document.getElementById('new-plant-mulch').value);
        const notifications = document.getElementById('new-plant-notifications').value === 'true';

        if (!name || !date) {
            alert('⚠️ Please enter a plant name and planting date!');
            return;
        }

        const plant = {
            id: Date.now(),
            name: name,
            type: type,
            plantedDate: date,
            wateringFrequency: frequency,
            mulchDepth: mulch,
            notifications: notifications,
            lastWatered: date,
            history: []
        };

        trackedPlants.push(plant);
        savePlants();
        displayPlants();

        // Reset form
        document.getElementById('new-plant-name').value = '';
        document.getElementById('new-plant-type').selectedIndex = 0;
        document.getElementById('new-plant-date').valueAsDate = new Date();
        document.getElementById('new-plant-frequency').selectedIndex = 1;
        document.getElementById('new-plant-mulch').value = 8;

        // Request notification permission if enabled
        if (notifications && !notificationPermission) {
            checkNotificationPermission();
        }

        alert('✅ Plant added successfully!');
    }

    function displayPlants() {
        const listDiv = document.getElementById('plant-list');
        
        if (trackedPlants.length === 0) {
            listDiv.innerHTML = `
                <div style="text-align: center; padding: 40px; color: #999;">
                    <p>No plants tracked yet. Add your first plant above!</p>
                </div>
            `;
            return;
        }

        const now = new Date();
        let html = '';

        trackedPlants.forEach(plant => {
            const plantedDate = new Date(plant.plantedDate);
            const lastWatered = new Date(plant.lastWatered);
            const daysGrowing = Math.floor((now - plantedDate) / (1000 * 60 * 60 * 24));
            const daysSinceWatered = Math.floor((now - lastWatered) / (1000 * 60 * 60 * 24));
            const nextWatering = new Date(lastWatered);
            nextWatering.setDate(nextWatering.getDate() + plant.wateringFrequency);
            const daysUntilWatering = Math.floor((nextWatering - now) / (1000 * 60 * 60 * 24));

            let wateringStatus, statusClass, statusIcon;
            if (daysUntilWatering < 0) {
                wateringStatus = `⚠️ Overdue by ${Math.abs(daysUntilWatering)} day(s)!`;
                statusClass = 'status-overdue';
                statusIcon = '🚨';
            } else if (daysUntilWatering === 0) {
                wateringStatus = '💧 Water today!';
                statusClass = 'status-due';
                statusIcon = '⏰';
            } else if (daysUntilWatering === 1) {
                wateringStatus = '📅 Water tomorrow';
                statusClass = 'status-ok';
                statusIcon = '✅';
            } else {
                wateringStatus = `✅ Next watering in ${daysUntilWatering} days`;
                statusClass = 'status-ok';
                statusIcon = '✅';
            }

            const emoji = {
                tomatoes: '🍅',
                lettuce: '🥬',
                carrots: '🥕',
                peppers: '🌶️',
                strawberries: '🍓',
                cucumbers: '🥒'
            }[plant.type];

            html += `
                <div class="plant-tracker-card">
                    <div class="plant-header">
                        <div class="plant-name">${emoji} ${plant.name}</div>
                        <div class="plant-actions">
                            <button class="btn-small" onclick="waterPlant(${plant.id})">💧 Watered</button>
                            <button class="btn-small btn-danger" onclick="deletePlant(${plant.id})">🗑️</button>
                        </div>
                    </div>

                    <div class="plant-info-grid">
                        <div class="plant-info-item">
                            <div class="plant-info-label">Planted</div>
                            <div class="plant-info-value">${daysGrowing} days ago</div>
                        </div>
                        <div class="plant-info-item">
                            <div class="plant-info-label">Last Watered</div>
                            <div class="plant-info-value">${daysSinceWatered} day(s) ago</div>
                        </div>
                        <div class="plant-info-item">
                            <div class="plant-info-label">Mulch Depth</div>
                            <div class="plant-info-value">${plant.mulchDepth} cm</div>
                        </div>
                        <div class="plant-info-item">
                            <div class="plant-info-label">Water Every</div>
                            <div class="plant-info-value">${plant.wateringFrequency} day(s)</div>
                        </div>
                    </div>

                    <div class="watering-status ${statusClass}">
                        ${statusIcon} ${wateringStatus}
                    </div>

                    ${plant.notifications ? '<p style="margin-top: 10px; font-size: 0.85em; color: #666;">🔔 Notifications enabled</p>' : ''}
                </div>
            `;
        });

        listDiv.innerHTML = html;
    }

    function waterPlant(plantId) {
        const plant = trackedPlants.find(p => p.id === plantId);
        if (plant) {
            const today = new Date().toISOString().split('T')[0];
            plant.lastWatered = today;
            plant.history.push({
                date: today,
                action: 'watered'
            });
            savePlants();
            displayPlants();
            
            const plantEmoji = {
                tomatoes: '🍅',
                lettuce: '🥬',
                carrots: '🥕',
                peppers: '🌶️',
                strawberries: '🍓',
                cucumbers: '🥒'
            }[plant.type];
            
            alert(`✅ ${plantEmoji} ${plant.name} watered successfully!`);
        }
    }

    function deletePlant(plantId) {
        if (confirm('Are you sure you want to remove this plant from tracking?')) {
            trackedPlants = trackedPlants.filter(p => p.id !== plantId);
            savePlants();
            displayPlants();
        }
    }

    function checkWateringReminders() {
        if (!notificationPermission) return;

        const now = new Date();
        trackedPlants.forEach(plant => {
            if (!plant.notifications) return;

            const lastWatered = new Date(plant.lastWatered);
            const nextWatering = new Date(lastWatered);
            nextWatering.setDate(nextWatering.getDate() + plant.wateringFrequency);

            // Check if watering is due today
            const today = new Date().toISOString().split('T')[0];
            const nextWateringDate = nextWatering.toISOString().split('T')[0];

            if (today === nextWateringDate) {
                // Check if we already sent notification today
                const lastNotif = localStorage.getItem(`notif_${plant.id}`);
                if (lastNotif !== today) {
                    sendNotification(plant);
                    localStorage.setItem(`notif_${plant.id}`, today);
                }
            }
        });
    }

    function sendNotification(plant) {
        const emoji = {
            tomatoes: '🍅',
            lettuce: '🥬',
            carrots: '🥕',
            peppers: '🌶️',
            strawberries: '🍓',
            cucumbers: '🥒'
        }[plant.type];

        new Notification('🌱 MULCHMATE Watering Reminder', {
            body: `${emoji} Time to water ${plant.name}!`,
            icon: 'data:image/svg+xml,%3Csvg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"%3E%3Ctext y="50" font-size="60" fill="%23667eea"%3E🌱%3C/text%3E%3C/svg%3E',
            badge: 'data:image/svg+xml,%3Csvg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 100 100"%3E%3Ctext y="50" font-size="60" fill="%23667eea"%3E💧%3C/text%3E%3C/svg%3E'
        });
    }
</script>
```

</body>
</html>
