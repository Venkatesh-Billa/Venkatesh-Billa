<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>AI HEALTH-CARE SYSTEM</title>
    <style>
        body {
            font-family: 'Arial', sans-serif; 
            background-color: #F4F4F4;
            margin: 0;
            padding: 0;
        }
        .header {
            background-color: #002147;
            color: white;
            padding: 20px;
            text-align: center;
            font-size: 24px;
            font-weight: bold;
        }
        .scrolling-bar {
            background-color: #FFD700;
            color: black;
            padding: 10px;
            text-align: center;
            font-weight: bold;
            white-space: nowrap;
            overflow: hidden;
            box-shadow: 0 2px 5px rgba(0, 0, 0, 0.2);
        }
        .navbar {
            background-color: #004080;
            overflow: hidden;
            display: flex;
            justify-content: center;
            padding: 15px;
        }
        .navbar a {
            color: white;
            text-decoration: none;
            padding: 14px 20px;
            font-size: 18px;
            cursor: pointer;
        }
        .navbar a:hover {
            background-color: #0056b3;
            border-radius: 5px;
        }
        .container {
            width: 80%;
            margin: auto;
            background: white;
            padding: 20px;
            border-radius: 10px;
            box-shadow: 0 0 10px rgba(0, 0, 0, 0.1);
            margin-top: 20px;
        }
        h2 {
            color: #002147;
            text-align: center;
        }
        .form-group {
            margin: 15px 0;
        }
        .form-group input, .form-group button {
            width: 100%;
            padding: 10px;
            margin-top: 5px;
            border-radius: 5px;
            border: 1px solid #ccc;
        }
        .form-group button {
            background-color: #DAA520;
            color: white;
            cursor: pointer;
            font-weight: bold;
        }
        .form-group button:hover {
            background-color: #B8860B;
        }
        .output {
            background: #e9ecef;
            padding: 10px;
            margin-top: 15px;
            border-radius: 5px;
            border-left: 5px solid #800000;
        }
        .back-button {
            display: block;
            margin: 20px auto;
            padding: 10px 15px;
            background-color: #800000;
            color: white;
            border: none;
            border-radius: 5px;
            cursor: pointer;
            text-align: center;
            font-size: 16px;
        }
        .back-button:hover {
            background-color: #600000;
        }
        .footer {
            background-color: #002147;
            color: white;
            text-align: center;
            padding: 15px;
            position: fixed;
            bottom: 0;
            width: 100%;
        }
    </style>
</head>
<body>
    <div class="header">AI Health-Care System</div>
    <p style="text-align: center; font-size: 18px;">Combining "Heal" with "Mind" for a Better Tomorrow</p>
    <div class="scrolling-bar">
        <marquee behavior="scroll" direction="left">AI Health-Care System - Your Virtual Health Assistant!</marquee>
    </div>
    <div class="navbar">
        <a href="Home.html">Home</a>
        <a href="healthprofile.html">Health Profile</a>
        <a href="fitnessPlan.html">Fitness Plan</a>
        <a href="nutritionplan.html">Nutrition Plan</a>
        <a href="notifications.js">Notifications&Alerts</a>
        <a href="healthtips.html">Health Tips</a>
        <a href="contactUs.html">Contact Us</a>
    </div>

    <!-- Health Profile Section -->
    <div class="container" id="healthProfile-section" style="display:none;">
        <h2>Health Profile</h2>
        <p>Enter your medical history to receive personalized medicine reminders and check-up alerts.</p>

        <!-- Health Profile Form -->
        <div class="card card-blue">
            <h3>Medical History</h3>
            <div class="form-group">
                <input type="text" id="medicalHistory" placeholder="Enter your medical history">
                <button onclick="saveMedicalHistory()">Save Medical History</button>
            </div>
            <div class="output" id="reminderOutput"></div>
            <button class="back-button" onclick="openSection('home')">Back to Home</button>
        </div>
    </div>

    <!-- Footer -->
    <footer class="footer">
        <p>&copy; 2025 AI Health-Care System. All Rights Reserved.</p>
    </footer>

    <script>
        function openSection(section) {
            localStorage.setItem("lastVisitedSection", section);
            document.querySelectorAll('.container').forEach(el => el.style.display = 'none');
            document.getElementById(`${section}-section`).style.display = 'block';
        }

        function saveMedicalHistory() {
            let history = document.getElementById("medicalHistory").value;
            if (history) {
                localStorage.setItem("medicalHistory", history);
                document.getElementById("reminderOutput").innerHTML = `<strong>Reminders Set:</strong> Your medicine and check-up reminders have been scheduled based on your medical history.`;
                scheduleReminders();
            }
        }

        function scheduleReminders() {
            alert("Medicine and check-up reminders have been scheduled based on your medical history.");
        }
    </script>
</body>
</html>
