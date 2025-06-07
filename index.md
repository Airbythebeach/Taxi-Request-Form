<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Artemis Taxi Service | Beach House Transport</title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <style>
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
            font-family: 'Segoe UI', Tahoma, Geneva, Verdana, sans-serif;
        }
        
        body {
            background: linear-gradient(135deg, #005b96, #1e5799, #005b96);
            color: #333;
            min-height: 100vh;
            padding: 20px;
            display: flex;
            justify-content: center;
            align-items: center;
            background-image: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" width="100" height="100" viewBox="0 0 100 100"><path d="M0,0 L100,0 L100,100 L0,100 Z" fill="none" stroke="rgba(255,255,255,0.1)" stroke-width="1"/><path d="M0,0 L50,50 M100,0 L50,50 M0,100 L50,50 M100,100 L50,50" stroke="rgba(255,255,255,0.15)" stroke-width="1"/></svg>');
        }
        
        .container {
            max-width: 900px;
            width: 100;
            background: rgba(255, 255, 255, 0.95);
            border-radius: 20px;
            overflow: hidden;
            box-shadow: 0 15px 50px rgba(0, 0, 0, 0.3);
        }
        
        header {
            background: linear-gradient(to right, #1e5799, #005b96);
            color: white;
            padding: 25px 30px;
            text-align: center;
            position: relative;
            border-bottom: 5px solid #f8b400;
        }
        
        .logo-container {
            display: flex;
            justify-content: center;
            align-items: center;
            gap: 20px;
            margin-bottom: 15px;
        }
        
        .logo {
            background: #fff;
            border-radius: 50%;
            padding: 15px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.2);
        }
        
        .logo i {
            font-size: 2.5rem;
            color: #1e5799;
        }
        
        .header-content {
            text-align: center;
        }
        
        .header-content h1 {
            font-size: 2.2rem;
            font-weight: 700;
            margin-bottom: 5px;
            letter-spacing: 1px;
        }
        
        .header-content p {
            font-size: 1.1rem;
            opacity: 0.9;
            max-width: 600px;
            margin: 0 auto;
        }
        
        .greek-pattern {
            height: 20px;
            background: url('data:image/svg+xml;utf8,<svg xmlns="http://www.w3.org/2000/svg" width="100" height="20" viewBox="0 0 100 20"><rect width="100" height="20" fill="%23f8b400"/><path d="M0,10 L100,10" stroke="%231e5799" stroke-width="2" stroke-dasharray="10,10"/></svg>');
            margin-top: 15px;
        }
        
        .form-container {
            padding: 30px;
        }
        
        .form-section {
            margin-bottom: 30px;
            padding: 20px;
            background: #f8f9ff;
            border-radius: 15px;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.05);
            border: 1px solid #e0e7ff;
        }
        
        .section-title {
            font-size: 1.5rem;
            color: #1e5799;
            margin-bottom: 20px;
            padding-bottom: 10px;
            border-bottom: 2px solid #e0e7ff;
            display: flex;
            align-items: center;
            gap: 10px;
        }
        
        .section-title i {
            color: #f8b400;
        }
        
        .form-row {
            display: flex;
            flex-wrap: wrap;
            gap: 20px;
            margin-bottom: 20px;
        }
        
        .form-group {
            flex: 1;
            min-width: 250px;
            margin-bottom: 15px;
        }
        
        label {
            display: block;
            margin-bottom: 8px;
            font-weight: 600;
            color: #1e5799;
        }
        
        input, select {
            width: 100%;
            padding: 14px 15px;
            border: 2px solid #d1dcff;
            border-radius: 10px;
            font-size: 16px;
            transition: all 0.3s;
            background: #fff;
        }
        
        input:focus, select:focus {
            border-color: #1e5799;
            outline: none;
            box-shadow: 0 0 0 3px rgba(30, 87, 153, 0.2);
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
        
        .time-toggle {
            display: flex;
            gap: 10px;
            margin-top: 10px;
        }
        
        .time-option {
            flex: 1;
            text-align: center;
            padding: 12px;
            border: 2px solid #d1dcff;
            border-radius: 10px;
            cursor: pointer;
            transition: all 0.3s;
            font-weight: 600;
        }
        
        .time-option.active {
            background: #1e5799;
            color: white;
            border-color: #1e5799;
        }
        
        .price-display {
            background: linear-gradient(to right, #e8f4ff, #d1e6ff);
            border-radius: 10px;
            padding: 20px;
            margin: 25px 0;
            text-align: center;
            font-size: 1.6rem;
            font-weight: 700;
            color: #1e5799;
            border: 2px solid #a3c6ff;
            box-shadow: 0 5px 15px rgba(0, 0, 0, 0.08);
        }
        
        .price-label {
            font-size: 1rem;
            color: #5a7db0;
            display: block;
            margin-bottom: 5px;
        }
        
        .price-details {
            font-size: 0.9rem;
            color: #5a7db0;
            margin-top: 10px;
        }
        
        .note {
            background: #fff8e1;
            border-left: 4px solid #f8b400;
            padding: 15px;
            margin: 20px 0;
            border-radius: 0 8px 8px 0;
            font-size: 0.95rem;
            color: #5a3d02;
        }
        
        .btn-container {
            display: flex;
            justify-content: center;
            margin-top: 20px;
        }
        
        .whatsapp-btn {
            background: linear-gradient(to right, #25D366, #128C7E);
            color: white;
            border: none;
            padding: 18px 45px;
            font-size: 1.3rem;
            border-radius: 50px;
            cursor: pointer;
            display: flex;
            align-items: center;
            gap: 15px;
            transition: all 0.3s;
            font-weight: 600;
            box-shadow: 0 5px 20px rgba(37, 211, 102, 0.4);
        }
        
        .whatsapp-btn:hover {
            transform: translateY(-3px);
            box-shadow: 0 8px 25px rgba(37, 211, 102, 0.6);
        }
        
        .whatsapp-btn:active {
            transform: translateY(-1px);
        }
        
        footer {
            text-align: center;
            padding: 25px;
            background: linear-gradient(to right, #1e5799, #005b96);
            color: rgba(255, 255, 255, 0.8);
            font-size: 1rem;
        }
        
        .footer-content {
            max-width: 600px;
            margin: 0 auto;
        }
        
        .footer-links {
            display: flex;
            justify-content: center;
            gap: 25px;
            margin-top: 15px;
            flex-wrap: wrap;
        }
        
        .footer-links a {
            color: white;
            text-decoration: none;
            display: flex;
            align-items: center;
            gap: 8px;
        }
        
        .footer-links a:hover {
            text-decoration: underline;
        }
        
        .copyright {
            margin-top: 20px;
            font-size: 0.9rem;
            opacity: 0.7;
        }
        
        @keyframes fadeIn {
            from { opacity: 0; transform: translateY(10px); }
            to { opacity: 1; transform: translateY(0); }
        }
        
        .van-required {
            display: none;
            background: #fff3f3;
            border-left: 4px solid #e74c3c;
            padding: 12px;
            border-radius: 0 8px 8px 0;
            margin-top: 10px;
            font-size: 0.95rem;
        }
        
        .option-grid {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(200px, 1fr));
            gap: 15px;
            margin-top: 10px;
        }
        
        .vehicle-option {
            border: 2px solid #d1dcff;
            border-radius: 10px;
            padding: 15px;
            cursor: pointer;
            transition: all 0.3s;
            text-align: center;
        }
        
        .vehicle-option:hover {
            border-color: #1e5799;
            background: #f0f5ff;
        }
        
        .vehicle-option.selected {
            background: #1e5799;
            color: white;
            border-color: #1e5799;
        }
        
        .vehicle-icon {
            font-size: 2rem;
            margin-bottom: 10px;
            color: #1e5799;
        }
        
        .vehicle-option.selected .vehicle-icon {
            color: white;
        }
        
        .vehicle-title {
            font-weight: 600;
            margin-bottom: 5px;
        }
        
        .vehicle-desc {
            font-size: 0.85rem;
            opacity: 0.8;
        }
        
        @media (max-width: 768px) {
            .form-row {
                flex-direction: column;
                gap: 15px;
            }
            
            .option-grid {
                grid-template-columns: 1fr;
            }
            
            .header-content h1 {
                font-size: 1.8rem;
            }
            
            .whatsapp-btn {
                padding: 16px 35px;
                font-size: 1.2rem;
            }
        }
        
        .time-info {
            font-size: 0.9rem;
            color: #5a7db0;
            margin-top: 5px;
        }
    </style>
</head>
<body>
    <div class="container">
        <header>
            <div class="logo-container">
                <div class="logo">
                    <i class="fas fa-taxi"></i>
                </div>
                <div class="header-content">
                    <h1>Artemis Taxi Service</h1>
                    <p>Reliable transportation for your Greek getaway</p>
                </div>
                <div class="logo">
                    <i class="fas fa-umbrella-beach"></i>
                </div>
            </div>
            <div class="greek-pattern"></div>
        </header>
        
        <div class="form-container">
            <form id="taxiForm">
                <!-- Guest Information Section -->
                <div class="form-section">
                    <h2 class="section-title"><i class="fas fa-user"></i> Guest Information</h2>
                    <div class="form-row">
                        <div class="form-group">
                            <label for="guestName" class="required">Your Name</label>
                            <input type="text" id="guestName" placeholder="Enter your full name" required>
                        </div>
                        <div class="form-group">
                            <label for="phone" class="required">Phone Number</label>
                            <input type="tel" id="phone" placeholder="Enter your phone number" required>
                        </div>
                    </div>
                </div>
                
                <!-- Journey Details Section -->
                <div class="form-section">
                    <h2 class="section-title"><i class="fas fa-route"></i> Journey Details</h2>
                    <div class="form-row">
                        <div class="form-group">
                            <label for="fromLocation" class="required">Pickup From</label>
                            <select id="fromLocation" required>
                                <option value="">Select pickup location</option>
                                <option value="Niriidwn 12 Artemis (Family Beach House)">Niriidwn 12 Artemis (Family Beach House)</option>
                                <option value="Athens International Airport">Athens International Airport</option>
                                <option value="Artemis Port">Artemis Port</option>
                                <option value="Lavrio Port">Lavrio Port</option>
                                <option value="Sounio">Sounio</option>
                                <option value="Athens City Center">Athens City Center</option>
                                <option value="Rafina Port">Rafina Port</option>
                                <option value="Other">Other location</option>
                            </select>
                        </div>
                        
                        <div class="form-group">
                            <label for="toLocation" class="required">Destination To</label>
                            <select id="toLocation" required>
                                <option value="">Select destination</option>
                                <option value="Niriidwn 12 Artemis (Family Beach House)">Niriidwn 12 Artemis (Family Beach House)</option>
                                <option value="Athens International Airport">Athens International Airport</option>
                                <option value="Artemis Port">Artemis Port</option>
                                <option value="Lavrio Port">Lavrio Port</option>
                                <option value="Sounio">Sounio</option>
                                <option value="Athens City Center">Athens City Center</option>
                                <option value="Rafina Port">Rafina Port</option>
                                <option value="Other">Other destination</option>
                            </select>
                        </div>
                    </div>
                    
                    <div id="fromAddressGroup" class="address-group">
                        <div class="form-group">
                            <label for="fromAddress" class="required">Specific Pick