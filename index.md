<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Taxi Booking - Artemis Family Beach House</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #1a2a6c, #b21f1f, #1a2a6c);
            color: #333;
            min-height: 100vh;
            padding: 20px;
            display: flex;
            justify-content: center;
            align-items: center;
        }
        
        .container {
            max-width: 800px;
            width: 100%;
            background: rgba(255, 255, 255, 0.95);
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 15px 50px rgba(0, 0, 0, 0.3);
        }
        
        header {
            background: #25D366;
            color: white;
            padding: 25px 30px;
            text-align: center;
            position: relative;
        }
        
        .logo {
            display: flex;
            align-items: center;
            justify-content: center;
            gap: 15px;
            margin-bottom: 15px;
        }
        
        .logo i {
            font-size: 2.5rem;
        }
        
        .logo h1 {
            font-size: 2rem;
            font-weight: 700;
        }
        
        .subtitle {
            font-size: 1.1rem;
            opacity: 0.9;
        }
        
        .form-container {
            padding: 30px;
        }
        
        .form-section {
            margin-bottom: 30px;
        }
        
        .section-title {
            font-size: 1.4rem;
            color: #25D366;
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 2px solid #eee;
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
            color: #444;
        }
        
        input, select {
            width: 100%;
            padding: 14px;
            border: 2px solid #ddd;
            border-radius: 10px;
            font-size: 16px;
            transition: all 0.3s;
        }
        
        input:focus, select:focus {
            border-color: #25D366;
            outline: none;
            box-shadow: 0 0 0 3px rgba(37, 211, 102, 0.2);
        }
        
        .required::after {
            content: " *";
            color: #e74c3c;
        }
        
        .address-group {
            display: none;
            margin-top: 10px;
            animation: fadeIn 0.5s;
        }
        
        .price-display {
            background: #e8f5e9;
            border-radius: 10px;
            padding: 15px;
            margin: 20px 0;
            text-align: center;
            font-size: 1.4rem;
            font-weight: 700;
            color: #2e7d32;
            border: 2px dashed #4caf50;
        }
        
        .price-label {
            font-size: 1rem;
            color: #666;
            display: block;
            margin-bottom: 5px;
        }
        
        .note {
            background: #fff8e1;
            border-left: 4px solid #ffc107;
            padding: 12px 15px;
            margin: 15px 0;
            border-radius: 0 8px 8px 0;
            font-size: 0.9rem;
        }
        
        .btn-container {
            display: flex;
            justify-content: center;
            margin-top: 20px;
        }
        
        .whatsapp-btn {
            background: #25D366;
            color: white;
            border: none;
            padding: 16px 40px;
            font-size: 1.2rem;
            border-radius: 50px;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 12px;
            transition: all 0.3s;
            font-weight: 600;
            box-shadow: 0 4px 15px rgba(37, 211, 102, 0.4);
        }
        
        .whatsapp-btn:hover {
            background: #128C7E;
            transform: translateY(-3px);
            box-shadow: 0 7px 20px rgba(37, 211, 102, 0.6);
        }
        
        .whatsapp-btn:active {
            transform: translateY(-1px);
        }
        
        footer {
            text-align: center;
            padding: 20px;
            background: #f5f5f5;
            color: #666;
            font-size: 0.9rem;
        }
        
        .footer-links {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-top: 10px;
        }
        
        .footer-links a {
            color: #25D366;
            text-decoration: none;
        }
        
        .footer-links a:hover {
            text-decoration: underline;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .info-bubble {
            display: inline-block;
            width: 20px;
            height: 20px;
            background: #25D366;
            color: white;
            border-radius: 50%;
            text-align: center;
            line-height: 20px;
            font-size: 0.8rem;
            margin-left: 5px;
            cursor: help;
        }
        
        .error-message {
            color: #e74c3c;
            font-size: 0.9rem;
            margin-top: 5px;
            display: none;
        }
        
        .van-required {
            display: none;
            background: #ffebee;
            border-left: 4px solid #f44336;
            padding: 10px;
            border-radius: 0 8px 8px 0;
            margin-top: 10px;
            font-size: 0.9rem;
        }
        
        @media (max-width: 600px) {
            body {
                padding: 10px;
            }
            
            .container {
                border-radius: 15px;
            }
            
            header {
                padding: 20px 15px;
            }
            
            .logo h1 {
                font-size: 1.6rem;
            }
            
            .form-container {
                padding: 20px;
            }
            
            .whatsapp-btn {
                padding: 14px 30px;
                font-size: 1.1rem;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <div class="logo">
                <i class="fas fa-taxi"></i>
                <h1>Artemis Taxi Service</h1>
            </div>
            <p class="subtitle">Quick and reliable transportation for our guests</p>
        </header>
        
        <div class="form-container">
            <form id="taxiForm">
                <div class="form-section">
                    <h2 class="section-title"><i class="fas fa-user"></i> Guest Information</h2>
                    <div class="form-group">
                        <label for="guestName" class="required">Your Name</label>
                        <input type="text" id="guestName" placeholder="Enter your full name" required>
                    </div>
                </div>
                
                <div class="form-section">
                    <h2 class="section-title"><i class="fas fa-map-marker-alt"></i> Journey Details</h2>
                    <div class="form-group">
                        <label for="fromLocation" class="required">Pickup From</label>
                        <select id="fromLocation" required>
                            <option value="">Select pickup location</option>
                            <option value="Niriidwn 12 Artemis (Family Beach House)">Niriidwn 12 Artemis (Family Beach House)</option>
                            <option value="Athens International Airport">Athens International Airport</option>
                            <option value="Other">Other location</option>
                        </select>
                    </div>
                    
                    <div id="fromAddressGroup" class="address-group">
                        <div class="form-group">
                            <label for="fromAddress" class="required">Specific Pickup Address</label>
                            <input type="text" id="fromAddress" placeholder="Enter full address with landmarks">
                        </div>
                    </div>
                    
                    <div class="form-group">
                        <label for="toLocation" class="required">Destination To</label>
                        <select id="toLocation" required>
                            <option value="">Select destination</option>
                            <option value="Niriidwn 12 Artemis (Family Beach House)">Niriidwn 12 Artemis (Family Beach House)</option>
                            <option value="Athens International Airport">Athens International Airport</option>
                            <option value="Other">Other destination</option>
                        </select>
                    </div>
                    
                    <div id="toAddressGroup" class="address-group">
                        <div class="form-group">
                            <label for="toAddress" class="required">Specific Destination Address</label>
                            <input type="text" id="toAddress" placeholder="Enter full address with landmarks">
                        </div>
                    </div>
                    
                    <div class="form-group">
                        <label for="pickupTime" class="required">Pickup Time</label>
                        <input type="text" id="pickupTime" placeholder="Now or specific time (e.g., 15:30)" required>
                    </div>
                </div>
                
                <div class="form-section">
                    <h2 class="section-title"><i class="fas fa-users"></i> Vehicle Selection</h2>
                    <div class="form-group">
                        <label for="passengers" class="required">Number of Passengers</label>
                        <select id="passengers" required>
                            <option value="">Select number of passengers</option>
                            <option value="1">1 passenger</option>
                            <option value="2">2 passengers</option>
                            <option value="3">3 passengers</option>
                            <option value="4">4 passengers</option>
                            <option value="5">5 passengers</option>
                            <option value="6">6 passengers</option>
                            <option value="7">7 passengers</option>
                            <option value="8">8 passengers</option>
                            <option value="9+">9+ passengers</option>
                        </select>
                    </div>
                    
                    <div id="vanRequired" class="van-required">
                        <i class="fas fa-exclamation-circle"></i> For 5+ passengers, please select a Taxi Van or VIP Van
                    </div>
                    
                    <div class="form-group">
                        <label for="vehicleType" class="required">Vehicle Type</label>
                        <select id="vehicleType" required>
                            <option value="">Select vehicle type</option>
                            <option value="Standard Taxi">Standard Taxi (max 4 passengers)</option>
                            <option value="Taxi Van">Taxi Van (max 8 passengers)</option>
                            <option value="VIP Van">VIP Van (max 8 passengers)</option>
                        </select>
                    </div>
                    
                    <div class="price-display">
                        <span class="price-label">Estimated Price:</span>
                        <span id="priceAmount">-</span>
                    </div>
                    
                    <div class="note">
                        <i class="fas fa-info-circle"></i> Prices include all taxes and service fees. For other destinations, price will be confirmed by driver.
                    </div>
                </div>
                
                <div class="btn-container">
                    <button type="button" id="sendWhatsApp" class="whatsapp-btn">
                        <i class="fab fa-whatsapp"></i> Send via WhatsApp
                    </button>
                </div>
            </form>
        </div>
        
        <footer>
            <p>Need assistance? Contact your host</p>
            <div class="footer-links">
                <a href="#"><i class="fas fa-phone-alt"></i> +30 698 470 1856</a>
                <a href="#"><i class="fas fa-question-circle"></i> Help Center</a>
            </div>
        </footer>
    </div>

    <script>
        // Phone numbers
        const taxiProviderNumber = "306984001013";
        const hostNumbers = ["97337560499", "306984701856"];
        
        // Pricing structure
        const basePrices = {
            "Niriidwn 12 Artemis (Family Beach House)": {
                "Athens International Airport": 45,
                "Niriidwn 12 Artemis (Family Beach House)": 0,
                "Other": null
            },
            "Athens International Airport": {
                "Niriidwn 12 Artemis (Family Beach House)": 45,
                "Athens International Airport": 0,
                "Other": null
            },
            "Other": {
                "Other": null
            }
        };
        
        // DOM elements
        const fromLocation = document.getElementById('fromLocation');
        const toLocation = document.getElementById('toLocation');
        const fromAddressGroup = document.getElementById('fromAddressGroup');
        const toAddressGroup = document.getElementById('toAddressGroup');
        const passengers = document.getElementById('passengers');
        const vehicleType = document.getElementById('vehicleType');
        const priceDisplay = document.getElementById('priceAmount');
        const vanRequired = document.getElementById('vanRequired');
        const sendButton = document.getElementById('sendWhatsApp');
        
        // Show address field when "Other" is selected
        fromLocation.addEventListener('change', function() {
            if (this.value === 'Other') {
                fromAddressGroup.style.display = 'block';
            } else {
                fromAddressGroup.style.display = 'none';
            }
            calculatePrice();
        });
        
        toLocation.addEventListener('change', function() {
            if (this.value === 'Other') {
                toAddressGroup.style.display = 'block';
            } else {
                toAddressGroup.style.display = 'none';
            }
            calculatePrice();
        });
        
        // Validate vehicle type based on passengers
        passengers.addEventListener('change', function() {
            const passengerCount = parseInt(this.value);
            if (passengerCount > 4) {
                vanRequired.style.display = 'block';
                
                // Reset to van if standard taxi is selected
                if (vehicleType.value === 'Standard Taxi') {
                    vehicleType.value = '';
                }
            } else {
                vanRequired.style.display = 'none';
            }
            calculatePrice();
        });
        
        vehicleType.addEventListener('change', calculatePrice);
        
        // Price calculation function
        function calculatePrice() {
            const from = fromLocation.value;
            const to = toLocation.value;
            const vehicle = vehicleType.value;
            
            // Reset price display
            priceDisplay.textContent = '-';
            
            // Validate selections
            if (!from || !to || !vehicle) return;
            
            // Get base price for route
            let basePrice = null;
            if (basePrices[from] && basePrices[from][to] !== undefined) {
                basePrice = basePrices[from][to];
            }
            
            // Handle unknown routes
            if (basePrice === null) {
                priceDisplay.textContent = 'Price on request';
                return;
            }
            
            // Handle same location
            if (basePrice === 0) {
                priceDisplay.textContent = 'Select different locations';
                return;
            }
            
            // Apply vehicle multipliers and commissions
            let finalPrice = basePrice;
            
            if (vehicle === 'Standard Taxi') {
                finalPrice += 5; // Commission
            } 
            else if (vehicle === 'Taxi Van') {
                finalPrice = basePrice * 2; // Van base price
                finalPrice += 10; // Commission
            } 
            else if (vehicle === 'VIP Van') {
                // Special pricing for airport route
                if (to.includes('Airport') || from.includes('Airport')) {
                    finalPrice = 95; // Fixed price including commission
                } else {
                    finalPrice = basePrice * 2; // Van base price
                    finalPrice += 10; // Commission
                }
            }
            
            priceDisplay.textContent = `${finalPrice}€`;
        }
        
        // Send via WhatsApp
        sendButton.addEventListener('click', function() {
            // Get form values
            const guestName = document.getElementById('guestName').value;
            const from = fromLocation.value === 'Other' ? 
                `Other: ${document.getElementById('fromAddress').value}` : 
                fromLocation.value;
                
            const to = toLocation.value === 'Other' ? 
                `Other: ${document.getElementById('toAddress').value}` : 
                toLocation.value;
                
            const pickupTime = document.getElementById('pickupTime').value;
            const passengerCount = passengers.value;
            const vehicle = vehicleType.value;
            const price = priceDisplay.textContent;
            
            // Validate required fields
            if (!guestName || !from || !to || !pickupTime || !passengerCount || !vehicle) {
                alert('Please fill all required fields');
                return;
            }
            
            // Validate passenger count vs vehicle type
            if (parseInt(passengerCount) > 4 && 
                !['Taxi Van', 'VIP Van'].includes(vehicle)) {
                alert('For 5+ passengers, please select a Taxi Van or VIP Van');
                return;
            }
            
            // Create message template
            const message = `🚕 *Taxi Request from Artemis Beach House* 🏖️\n\n` +
                           `• *Guest Name:* ${guestName}\n` +
                           `• *From:* ${from}\n` +
                           `• *To:* ${to}\n` +
                           `• *Pickup Time:* ${pickupTime}\n` +
                           `• *Passengers:* ${passengerCount}\n` +
                           `• *Vehicle Type:* ${vehicle}\n` +
                           `• *Estimated Price:* ${price}\n\n` +
                           `_This request was sent via the property's taxi booking system_`;
            
            // Encode for URL
            const encodedMessage = encodeURIComponent(message);
            
            // Send to taxi provider
            const taxiLink = `https://wa.me/${taxiProviderNumber}?text=${encodedMessage}`;
            window.open(taxiLink, '_blank');
            
            // Send to host numbers
            hostNumbers.forEach(number => {
                const hostLink = `https://wa.me/${number}?text=${encodedMessage}`;
                window.open(hostLink, '_blank');
            });
            
            // Show confirmation
            alert('Your request has been sent via WhatsApp! Please check your WhatsApp app to confirm sending.');
        });
        
        // Initialize form
        calculatePrice();
    </script>
</body>
</html>