<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Artemis Taxi Service | Premium Transportation</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        :root {
            --greek-blue: #0d5eaf;
            --greek-blue-light: #1e7fd5;
            --greek-blue-dark: #0a4a8a;
            --greek-white: #ffffff;
            --greek-sand: #f5f0e6;
            --greek-olive: #6b8e23;
            --greek-sun: #ffb400;
        }
        
        body {
            background: linear-gradient(135deg, #f5f7fa, #e4e9f2);
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
            background: var(--greek-white);
            border-radius: 16px;
            overflow: hidden;
            box-shadow: 0 10px 30px rgba(0, 0, 0, 0.08);
        }
        
        header {
            background: var(--greek-blue);
            color: var(--greek-white);
            padding: 30px;
            text-align: center;
            position: relative;
        }
        
        .logo {
            display: flex;
            flex-direction: column;
            align-items: center;
            gap: 15px;
            margin-bottom: 10px;
        }
        
        .logo-icon {
            font-size: 2.8rem;
            color: var(--greek-sun);
        }
        
        .logo h1 {
            font-size: 1.8rem;
            font-weight: 600;
            letter-spacing: 0.5px;
        }
        
        .subtitle {
            font-size: 1.1rem;
            opacity: 0.9;
            max-width: 500px;
            margin: 0 auto;
            line-height: 1.6;
        }
        
        .form-container {
            padding: 30px;
        }
        
        .form-section {
            margin-bottom: 30px;
        }
        
        .section-title {
            font-size: 1.3rem;
            color: var(--greek-blue-dark);
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 1px solid rgba(13, 94, 175, 0.1);
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .form-row {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
            margin-bottom: 15px;
        }
        
        .form-group {
            flex: 1 1 300px;
            margin-bottom: 20px;
        }
        
        label {
            display: block;
            margin-bottom: 8px;
            font-weight: 500;
            color: var(--greek-blue-dark);
            font-size: 0.95rem;
        }
        
        input, select {
            width: 100%;
            padding: 14px 16px;
            border: 1px solid #ddd;
            border-radius: 8px;
            font-size: 16px;
            transition: all 0.3s;
            background: #f9f9f9;
        }
        
        input:focus, select:focus {
            border-color: var(--greek-blue-light);
            outline: none;
            box-shadow: 0 0 0 3px rgba(30, 127, 213, 0.1);
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
            background: #f0f8ff;
            border-radius: 8px;
            padding: 18px;
            margin: 25px 0;
            text-align: center;
            font-size: 1.6rem;
            font-weight: 600;
            color: var(--greek-blue-dark);
            border: 1px solid rgba(13, 94, 175, 0.2);
        }
        
        .price-label {
            font-size: 1rem;
            color: #666;
            display: block;
            margin-bottom: 5px;
        }
        
        .note {
            background: #f9f9f9;
            padding: 15px;
            margin: 20px 0;
            border-radius: 8px;
            font-size: 0.9rem;
            line-height: 1.6;
            color: #555;
            border-left: 3px solid var(--greek-blue-light);
        }
        
        .btn-container {
            display: flex;
            justify-content: center;
            margin-top: 20px;
        }
        
        .whatsapp-btn {
            background: var(--greek-blue);
            color: white;
            border: none;
            padding: 16px 40px;
            font-size: 1.1rem;
            border-radius: 8px;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 12px;
            transition: all 0.3s;
            font-weight: 500;
        }
        
        .whatsapp-btn:hover {
            background: var(--greek-blue-dark);
            transform: translateY(-2px);
        }
        
        footer {
            text-align: center;
            padding: 25px;
            background: #f5f7fa;
            color: #555;
            font-size: 0.95rem;
            border-top: 1px solid rgba(0,0,0,0.05);
        }
        
        .footer-links {
            display: flex;
            justify-content: center;
            gap: 25px;
            margin-top: 15px;
            flex-wrap: wrap;
        }
        
        .footer-links a {
            color: var(--greek-blue);
            text-decoration: none;
            font-weight: 500;
            display: flex;
            align-items: center;
            gap: 8px;
        }
        
        .footer-links a:hover {
            color: var(--greek-blue-dark);
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .van-required {
            display: none;
            background: #ffebee;
            padding: 12px;
            border-radius: 8px;
            margin-top: 10px;
            font-size: 0.9rem;
            color: #d32f2f;
        }
        
        .flight-group {
            display: none;
        }
        
        @media (max-width: 768px) {
            body {
                padding: 10px;
            }
            
            header {
                padding: 25px 20px;
            }
            
            .form-container {
                padding: 25px 20px;
            }
            
            .whatsapp-btn {
                width: 100%;
                justify-content: center;
            }
            
            .form-row {
                gap: 10px;
            }
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <div class="logo">
                <div class="logo-icon">
                    <i class="fas fa-taxi"></i>
                </div>
                <h1>Artemis Taxi Service</h1>
            </div>
            <p class="subtitle">Premium transportation with Greek hospitality</p>
        </header>
        
        <div class="form-container">
            <form id="taxiForm">
                <!-- Guest Information Section -->
                <div class="form-section">
                    <h2 class="section-title"><i class="fas fa-user"></i> Guest Information</h2>
                    <div class="form-row">
                        <div class="form-group">
                            <label for="guestName" class="required">Full Name</label>
                            <input type="text" id="guestName" placeholder="Your full name" required>
                        </div>
                        <div class="form-group">
                            <label for="phone" class="required">Phone Number</label>
                            <input type="tel" id="phone" placeholder="Your contact number" required>
                        </div>
                    </div>
                </div>
                
                <!-- Journey Details Section -->
                <div class="form-section">
                    <h2 class="section-title"><i class="fas fa-route"></i> Journey Details</h2>
                    <div class="form-row">
                        <div class="form-group">
                            <label for="date" class="required">Date</label>
                            <input type="date" id="date" required>
                        </div>
                        <div class="form-group">
                            <label for="time" class="required">Time</label>
                            <input type="time" id="time" required>
                        </div>
                    </div>
                    
                    <div class="form-row">
                        <div class="form-group">
                            <label for="fromLocation" class="required">Pickup Location</label>
                            <select id="fromLocation" required>
                                <option value="">Select pickup location</option>
                                <option value="Niriidwn 12 Artemis (Family Beach House)">Niriidwn 12 Artemis (Family Beach House)</option>
                                <option value="Athens International Airport">Athens International Airport</option>
                                <option value="Athens City Center">Athens City Center</option>
                                <option value="Piraeus Port">Piraeus Port</option>
                                <option value="Rafina Port">Rafina Port</option>
                                <option value="Lavrio Port">Lavrio Port</option>
                                <option value="Sounio">Sounio</option>
                                <option value="Vravrona">Vravrona</option>
                                <option value="Loutsa">Loutsa</option>
                                <option value="Artemida Center">Artemida Center</option>
                                <option value="Marathonas">Marathonas</option>
                                <option value="Other">Other location</option>
                            </select>
                        </div>
                        
                        <div class="form-group">
                            <label for="toLocation" class="required">Destination</label>
                            <select id="toLocation" required>
                                <option value="">Select destination</option>
                                <option value="Niriidwn 12 Artemis (Family Beach House)">Niriidwn 12 Artemis (Family Beach House)</option>
                                <option value="Athens International Airport">Athens International Airport</option>
                                <option value="Athens City Center">Athens City Center</option>
                                <option value="Piraeus Port">Piraeus Port</option>
                                <option value="Rafina Port">Rafina Port</option>
                                <option value="Lavrio Port">Lavrio Port</option>
                                <option value="Sounio">Sounio</option>
                                <option value="Vravrona">Vravrona</option>
                                <option value="Loutsa">Loutsa</option>
                                <option value="Artemida Center">Artemida Center</option>
                                <option value="Marathonas">Marathonas</option>
                                <option value="Other">Other destination</option>
                            </select>
                        </div>
                    </div>
                    
                    <div id="fromAddressGroup" class="address-group">
                        <div class="form-group">
                            <label for="fromAddress" class="required">Specific Pickup Address</label>
                            <input type="text" id="fromAddress" placeholder="Enter full address with landmarks">
                        </div>
                    </div>
                    
                    <div id="toAddressGroup" class="address-group">
                        <div class="form-group">
                            <label for="toAddress" class="required">Specific Destination Address</label>
                            <input type="text" id="toAddress" placeholder="Enter full address with landmarks">
                        </div>
                    </div>
                    
                    <div id="flightGroup" class="flight-group">
                        <div class="form-group">
                            <label for="flightNumber">Flight Number</label>
                            <input type="text" id="flightNumber" placeholder="Enter your flight number">
                        </div>
                    </div>
                </div>
                
                <!-- Luggage Section -->
                <div class="form-section">
                    <h2 class="section-title"><i class="fas fa-suitcase"></i> Luggage Information</h2>
                    <div class="form-row">
                        <div class="form-group">
                            <label for="checkedLuggage">Checked Luggage</label>
                            <select id="checkedLuggage">
                                <option value="0">0 pieces</option>
                                <option value="1">1 piece</option>
                                <option value="2">2 pieces</option>
                                <option value="3">3 pieces</option>
                                <option value="4">4 pieces</option>
                                <option value="5+">5+ pieces</option>
                            </select>
                        </div>
                        <div class="form-group">
                            <label for="cabinLuggage">Cabin Luggage</label>
                            <select id="cabinLuggage">
                                <option value="0">0 pieces</option>
                                <option value="1">1 piece</option>
                                <option value="2">2 pieces</option>
                                <option value="3">3 pieces</option>
                                <option value="4">4 pieces</option>
                                <option value="5+">5+ pieces</option>
                            </select>
                        </div>
                    </div>
                </div>
                
                <!-- Vehicle Selection Section -->
                <div class="form-section">
                    <h2 class="section-title"><i class="fas fa-car"></i> Vehicle Selection</h2>
                    <div class="form-row">
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
                        
                        <div class="form-group">
                            <label for="vehicleType" class="required">Vehicle Type</label>
                            <select id="vehicleType" required>
                                <option value="">Select vehicle type</option>
                                <option value="Standard Taxi">Standard Taxi (max 4 passengers)</option>
                                <option value="Taxi Van">Taxi Van (max 8 passengers)</option>
                                <option value="VIP Van">VIP Van (max 8 passengers)</option>
                                <option value="Two Taxis">Two Taxis (for 5-8 passengers)</option>
                            </select>
                        </div>
                    </div>
                    
                    <div id="vanRequired" class="van-required">
                        <i class="fas fa-exclamation-circle"></i> For 5+ passengers, please select a Taxi Van, VIP Van or Two Taxis
                    </div>
                    
                    <div class="price-display">
                        <span class="price-label">Estimated Price:</span>
                        <span id="priceAmount">-</span>
                    </div>
                    
                    <div class="note">
                        <i class="fas fa-info-circle"></i> 
                        <strong>Pricing Information:</strong> 
                        Day rates (05:00-24:00) and Night rates (00:00-04:59) apply. 
                        All prices include taxes and service fees.
                    </div>
                </div>
                
                <div class="btn-container">
                    <button type="button" id="sendWhatsApp" class="whatsapp-btn">
                        <i class="fab fa-whatsapp"></i> Send Booking Request
                    </button>
                </div>
            </form>
        </div>
        
        <footer>
            <p>Artemis Taxi Service &copy; 2023</p>
            <div class="footer-links">
                <a href="tel:+306984701856"><i class="fas fa-phone"></i> +30 698 470 1856</a>
                <a href="tel:+97337560499"><i class="fas fa-phone"></i> +973 37560499</a>
            </div>
        </footer>
    </div>

    <script>
        // Phone numbers
        const taxiProviderNumber = "306984001013";
        const hostNumbers = ["97337560499", "306984701856"];
        
        // Pricing structure - Day and Night rates
        const basePricesDay = {
            "Niriidwn 12 Artemis (Family Beach House)": {
                "Athens International Airport": 25,
                "Athens City Center": 25,
                "Piraeus Port": 25,
                "Rafina Port": 25,
                "Lavrio Port": 25,
                "Sounio": 25,
                "Vravrona": 25,
                "Loutsa": 25,
                "Artemida Center": 25,
                "Marathonas": 25,
                "Other": null
            },
            "Athens International Airport": {
                "Niriidwn 12 Artemis (Family Beach House)": 25,
                "Athens City Center": 30,
                "Piraeus Port": 35,
                "Rafina Port": 45,
                "Lavrio Port": 60,
                "Sounio": 65,
                "Vravrona": 45,
                "Loutsa": 40,
                "Artemida Center": 38,
                "Marathonas": 50,
                "Other": null
            },
            // Add other origin points as needed
        };
        
        const basePricesNight = {
            "Niriidwn 12 Artemis (Family Beach House)": {
                "Athens International Airport": 30,
                "Athens City Center": 30,
                "Piraeus Port": 30,
                "Rafina Port": 30,
                "Lavrio Port": 30,
                "Sounio": 30,
                "Vravrona": 30,
                "Loutsa": 30,
                "Artemida Center": 30,
                "Marathonas": 30,
                "Other": null
            },
            "Athens International Airport": {
                "Niriidwn 12 Artemis (Family Beach House)": 30,
                "Athens City Center": 35,
                "Piraeus Port": 40,
                "Rafina Port": 50,
                "Lavrio Port": 65,
                "Sounio": 70,
                "Vravrona": 50,
                "Loutsa": 45,
                "Artemida Center": 43,
                "Marathonas": 55,
                "Other": null
            },
            // Add other origin points as needed
        };
        
        // DOM elements
        const fromLocation = document.getElementById('fromLocation');
        const toLocation = document.getElementById('toLocation');
        const fromAddressGroup = document.getElementById('fromAddressGroup');
        const toAddressGroup = document.getElementById('toAddressGroup');
        const flightGroup = document.getElementById('flightGroup');
        const passengers = document.getElementById('passengers');
        const vehicleType = document.getElementById('vehicleType');
        const priceDisplay = document.getElementById('priceAmount');
        const vanRequired = document.getElementById('vanRequired');
        const sendButton = document.getElementById('sendWhatsApp');
        const dateInput = document.getElementById('date');
        const timeInput = document.getElementById('time');
        
        // Set default date to tomorrow
        const tomorrow = new Date();
        tomorrow.setDate(tomorrow.getDate() + 1);
        dateInput.valueAsDate = tomorrow;
        
        // Set default time to current time + 1 hour
        const now = new Date();
        now.setHours(now.getHours() + 1);
        timeInput.value = `${now.getHours().toString().padStart(2, '0')}:${now.getMinutes().toString().padStart(2, '0')}`;
        
        // Show address field when "Other" is selected
        fromLocation.addEventListener('change', function() {
            if (this.value === 'Other') {
                fromAddressGroup.style.display = 'block';
            } else {
                fromAddressGroup.style.display = 'none';
            }
            checkFlightField();
            calculatePrice();
        });
        
        toLocation.addEventListener('change', function() {
            if (this.value === 'Other') {
                toAddressGroup.style.display = 'block';
            } else {
                toAddressGroup.style.display = 'none';
            }
            checkFlightField();
            calculatePrice();
        });
        
        // Check if we should show flight number field
        function checkFlightField() {
            if (fromLocation.value.includes('Airport') || toLocation.value.includes('Airport')) {
                flightGroup.style.display = 'block';
            } else {
                flightGroup.style.display = 'none';
            }
        }
        
        // Validate vehicle type based on passengers
        passengers.addEventListener('change', function() {
            const passengerCount = parseInt(this.value);
            if (passengerCount > 4) {
                vanRequired.style.display = 'block';
                
                // Reset if standard taxi is selected
                if (vehicleType.value === 'Standard Taxi') {
                    vehicleType.value = '';
                }
            } else {
                vanRequired.style.display = 'none';
            }
            calculatePrice();
        });
        
        vehicleType.addEventListener('change', calculatePrice);
        dateInput.addEventListener('change', calculatePrice);
        timeInput.addEventListener('change', calculatePrice);
        
        // Price calculation function
        function calculatePrice() {
            const from = fromLocation.value;
            const to = toLocation.value;
            const vehicle = vehicleType.value;
            
            // Get time and determine day/night rate
            const time = timeInput.value;
            const [hours] = time.split(':').map(Number);
            const isNightTime = hours >= 0 && hours < 5; // 00:00-04:59
            const basePrices = isNightTime ? basePricesNight : basePricesDay;
            
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
            if (from === to) {
                priceDisplay.textContent = 'Select different locations';
                return;
            }
            
            // Apply vehicle multipliers
            let finalPrice = basePrice;
            
            if (vehicle === 'Taxi Van') {
                finalPrice = basePrice * 2;
            } 
            else if (vehicle === 'VIP Van') {
                // Special pricing for airport route
                if (to.includes('Airport') || from.includes('Airport')) {
                    finalPrice = 95;
                } else {
                    finalPrice = basePrice * 2;
                }
            }
            else if (vehicle === 'Two Taxis') {
                finalPrice = basePrice * 2;
            }
            
            priceDisplay.textContent = `${finalPrice}€`;
        }
        
        // Send via WhatsApp
        sendButton.addEventListener('click', function() {
            // Get form values
            const guestName = document.getElementById('guestName').value;
            const phone = document.getElementById('phone').value;
            const date = dateInput.value;
            const time = timeInput.value;
            
            const from = fromLocation.value === 'Other' ? 
                `Other: ${document.getElementById('fromAddress').value}` : 
                fromLocation.value;
                
            const to = toLocation.value === 'Other' ? 
                `Other: ${document.getElementById('toAddress').value}` : 
                toLocation.value;
                
            const flightNumber = document.getElementById('flightNumber').value;
            const passengerCount = passengers.value;
            const vehicle = vehicleType.value;
            const checkedLuggage = document.getElementById('checkedLuggage').value;
            const cabinLuggage = document.getElementById('cabinLuggage').value;
            const price = priceDisplay.textContent;
            
            // Validate required fields
            if (!guestName || !phone || !from || !to || !date || !time || !passengerCount || !vehicle) {
                alert('Please fill all required fields');
                return;
            }
            
            // Validate passenger count vs vehicle type
            if (parseInt(passengerCount) > 4 && 
                !['Taxi Van', 'VIP Van', 'Two Taxis'].includes(vehicle)) {
                alert('For 5+ passengers, please select a Taxi Van, VIP Van or Two Taxis');
                return;
            }
            
            // Create message template
            let message = `This is a taxi reservation request from a guest of "Family Beach House" at Niriidwn 12.\n\n`;
            message += `• *Guest Name:* ${guestName}\n`;
            message += `• *Phone:* ${phone}\n`;
            message += `• *Date:* ${date}\n`;
            message += `• *Time:* ${time}\n`;
            message += `• *From:* ${from}\n`;
            message += `• *To:* ${to}\n`;
            
            if (flightNumber) {
                message += `• *Flight Number:* ${flightNumber}\n`;
            }
            
            message += `• *Passengers:* ${passengerCount}\n`;
            message += `• *Checked Luggage:* ${checkedLuggage} pieces\n`;
            message += `• *Cabin Luggage:* ${cabinLuggage} pieces\n`;
            message += `• *Vehicle Type:* ${vehicle}\n`;
            message += `• *Estimated Price:* ${price} (includes all taxes and fees)\n\n`;
            message += `_This request was sent via the property's booking system_`;
            
            // Encode for URL
            const encodedMessage = encodeURIComponent(message);
            
            // Create WhatsApp links
            const taxiLink = `https://wa.me/${taxiProviderNumber}?text=${encodedMessage}`;
            const hostLink1 = `https://wa.me/${hostNumbers[0]}?text=${encodedMessage}`;
            const hostLink2 = `https://wa.me/${hostNumbers[1]}?text=${encodedMessage}`;
            
            // Open WhatsApp links in new tabs
            window.open(taxiLink, '_blank');
            window.open(hostLink1, '_blank');
            window.open(hostLink2, '_blank');
            
            // Show confirmation
            alert('Your request has been sent via WhatsApp! Please check your WhatsApp app to confirm sending.');
        });
        
        // Initialize form
        calculatePrice();
    </script>
</body>
</html>