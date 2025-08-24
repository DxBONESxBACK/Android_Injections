# Android_Injections
R U 1 of those people who cant seem 2 get away from those pesky bright LED's coming from  your cellphones, headphones, charging stations as well as their cords &amp; there not limited 2 portable devices. Your smart TV's  &amp; pretty much everything that has a current running through it. What if you had the ability 2 have full control of your devices LED?

<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>LED Simulator</title>
    <script src="https://cdn.tailwindcss.com"></script>
    <style>
        body {
            font-family: 'Inter', sans-serif;
        }
    </style>
</head>
<body class="bg-gray-900 text-white min-h-screen flex flex-col items-center justify-center p-4">
    <div class="bg-gray-800 p-8 rounded-xl shadow-lg text-center max-w-sm w-full">
        <!-- Main title for the app -->
        <h1 class="text-3xl font-bold mb-6">LED Simulator</h1>

        <!-- The "LED" element, initially off -->
        <div id="led" class="w-32 h-32 mx-auto mb-8 rounded-full bg-gray-600 transition-colors duration-300 shadow-inner"></div>

        <!-- The button to toggle the LED -->
        <button id="toggleButton" class="w-full px-6 py-3 bg-blue-600 text-white font-semibold rounded-lg shadow-md hover:bg-blue-700 transition-colors duration-200 focus:outline-none focus:ring-2 focus:ring-blue-500 focus:ring-opacity-50">
            Turn On
        </button>
    </div>

    <script>
        // Get the LED element and the button element from the DOM
        const led = document.getElementById('led');
        const toggleButton = document.getElementById('toggleButton');

        // A variable to track the current state of the LED (false = off, true = on)
        let isOn = false;

        // Function to toggle the state of the LED
        function toggleLed() {
            // Change the state
            isOn = !isOn;

            if (isOn) {
                // If it's on, change the background color to yellow and the button text
                led.classList.remove('bg-gray-600');
                led.classList.add('bg-yellow-400', 'shadow-yellow-300');
                led.style.boxShadow = '0 0 40px 10px #fde047';
                toggleButton.textContent = 'Turn Off';
                toggleButton.classList.remove('bg-blue-600', 'hover:bg-blue-700');
                toggleButton.classList.add('bg-red-600', 'hover:bg-red-700');
            } else {
                // If it's off, change the background color back to gray and the button text
                led.classList.remove('bg-yellow-400', 'shadow-yellow-300');
                led.classList.add('bg-gray-600');
                led.style.boxShadow = 'none';
                toggleButton.textContent = 'Turn On';
                toggleButton.classList.remove('bg-red-600', 'hover:bg-red-700');
                toggleButton.classList.add('bg-blue-600', 'hover:bg-blue-700');
            }
        }

        // Add a click event listener to the button
        toggleButton.addEventListener('click', toggleLed);

    </script>
</body>
</html>
