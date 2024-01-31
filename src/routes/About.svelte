<script>

</script>

<main>
    <h1>About Islamic Midnight Calculator</h1>
    <div class="about-main">
        <h2>Understanding Islamic Midnight</h2>
        <div class="intro-description">
            In Islamic tradition, the concept of midnight does not necessarily refer to the 
            conventional 12:00 AM. Instead, Islamic midnight is the halfway point between Maghrib
            (sunset) and Fajr (dawn), and it is crucial for accurately observing prayer schedules. 
        </div>
    
        <h2>How We Calculate It</h2>

        <div class="calculation-prewords">The Islamic Midnight Calculator is designed to find this precise time based on the following method:</div>
        <div class="calculation-description">
            <ol>
                <li><b>Input Times</b>: Users input the local Maghrib and Fajr times in a 24-hour format.</li>
                <li><b>Conversion to Minutes</b>: Both times are converted to minutes to facilitate the calculation process.</li>
                <li><b>Order Correction</b>: If the Maghrib time is later than the Fajr time (which can occur during the night), their values are swapped to ensure accuracy.</li>
                <li><b>Determine the Difference</b>: We calculate the total minutes between Fajr and Maghrib.</li>
                <li><b>Find the Midpoint/Third of the night</b>: Divide the difference by two for the midpoint, or split the night into thirds and add two thirds to Maghrib time.</li>
                <li><b>Reconvert to Time Format</b>: The midpoint/last third of the night is then converted back into standard hours and minutes format, providing the exact time for Islamic midnight.</li>
            </ol>
        </div>
    
        <h2>Contact and FeedBack</h2>
        <div class="feedback-description">
            Your feedback is invaluable to us. If you have any suggestions, questions, or comments
            about the Islamic Midnight Calculator, please feel free to contact us. We're dedicated to 
            making this tool as accurate and user-friendly as possible.
            <div class="contact-information">
                <b>Email: imcweb2024@gmail.com</b>
            </div>
        </div>
        
        <h2>Acknowledgements</h2>
        <div class="credits">
            All emojis designed by <a href="https://openmoji.org/">OpenMoji</a> - the open-source emoji and icon project. 
            License: <a href="https://creativecommons.org/licenses/by-sa/4.0/#">CC BY-SA 4.0</a>.
        </div>

        <h2>GitHub Repository</h2>
        <div class="github-container">Link to the <a href="https://github.com/Moneer-Deshly/Islamic-Midnight-Calculator">GitHub Repository</a> for this project.</div>
    </div>
</main>

<style>
.github-container{
    font-size: 1.3rem;
}

a{
    text-decoration: underline;
    font-weight: bold;
}

.credits{
    font-size: 1.3rem;
}

.feedback-description{
    font-size: 1.3rem;
}

.calculation-prewords{
    font-size: 1.3rem;
}

.calculation-description{
    margin-left: 1.4rem;
    font-size: 1.3rem;
}

.intro-description{
    font-size: 1.3rem;
}

h2{
    font-size: 2rem;
}

h1{
    margin-bottom: 0.6rem;
    font-size: 2.5rem;
}

.about-main{
    width: 90%;
    border-radius: 16px;
    background-color: #1C6433;
    padding: 1.5rem;
}

main{
    display: grid;
    place-items: center;
}
</style>