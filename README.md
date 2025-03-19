<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Red Thread - Enter the Sequence</title>
    <link rel="stylesheet" href="styles.css">
</head>
<body>
    <div class="container">
        <h1 class="glitch-text" data-text="We are but echoes in the loop.">We are but echoes in the loop.</h1>
        <input type="text" id="sequenceInput" placeholder="Enter the sequence">
        <p id="errorMessage">ACCESS DENIED. TRY AGAIN.</p>
    </div>

    <script>
        document.addEventListener("DOMContentLoaded", function() {
            const inputField = document.getElementById("sequenceInput");
            const errorMessage = document.getElementById("errorMessage");

            inputField.addEventListener("keypress", function(event) {
                if (event.key === "Enter") {
                    checkSequence();
                }
            });
        });

        function checkSequence() {
            const input = document.getElementById("sequenceInput").value.trim();
            const errorMessage = document.getElementById("errorMessage");

            if (input === "033") {  // Replace "033" with the real secret passphrase
                document.body.style.animation = "glitch-screen 0.5s infinite";
                setTimeout(() => {
                    window.location.href = "inside.html"; // Redirect to the hidden page
                }, 2000);
            } else {
                errorMessage.style.visibility = "visible";
                errorMessage.textContent = "ACCESS DENIED. TRY AGAIN.";
            }
        }
    </script>
</body>
</html>