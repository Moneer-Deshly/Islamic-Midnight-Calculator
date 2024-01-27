<script>
let maghribTime = "";
let fajrTime = "";
let islamicMidnight = "";
let caluclatedOnce = false;
let invalidInput = false;

function hasFlyingNumbers(time) {
    let parts = String(time).split(":");
    if (parts.length !== 2) {
        return true; 
    }
    let hours = parseInt(parts[0]);
    let minutes = parseInt(parts[1]);

    if (isNaN(hours) || isNaN(minutes)) {
        return true; 
    }

    if (hours < 0 || hours > 24) {
        return true; 
    }
    if (minutes < 0 || minutes > 59) {
        return true;
    }
    return false;
}


function checkInput() {
    invalidInput = false;
    if (islamicMidnight === "NaN:NaN" || hasFlyingNumbers(maghribTime) || hasFlyingNumbers(fajrTime)) {
        invalidInput = true;
    }
}


function calculate(maghribString, fajrString){
    try {
        caluclatedOnce = true;
        let maghribMins = getTotalMinutes(maghribString);
        let fajrMins = getTotalMinutes(fajrString);

        if (maghribMins > fajrMins) {
            let temp = maghribMins;
            maghribMins = fajrMins;
            fajrMins = temp;
        }

        let difference = fajrMins - maghribMins;
        let middle = difference / 2;

        let midnightInMins = maghribMins + middle;

        let middleHour = midnightInMins / 60;
        let middleMinutes = midnightInMins % 60;

        let formattedTime = formatTime(Math.round(middleHour), Math.round(middleMinutes));
        return formattedTime;
    }
    catch (e) {
        if (e.message === "Invalid time format" || invalidInput || hasFlyingNumbers(maghribTime) || hasFlyingNumbers(fajrTime)) {
            invalidInput = true;
        }
    }
    
}

function handleCalculate() {
    islamicMidnight = "";
    checkInput();
    islamicMidnight = calculate(maghribTime, fajrTime);
}

function getTotalMinutes(time) {
    let parts = String(time).split(":");
    let hours = parseInt(parts[0]);
    let minutes = parseInt(parts[1]);

    if (isNaN(hours) || isNaN(minutes)) {
        throw new Error("Invalid time format");
    }

    let totalMinutes = (hours * 60) + minutes;
    return totalMinutes;
}

function formatTime(hours, minutes) {
    let paddedHours = String(hours).padStart(2, '0');
    let paddedMinutes = String(minutes).padStart(2, '0');
    return `${paddedHours}:${paddedMinutes}`;
}


</script>

<main>
    <div class="main">
        <h1 class="main-information">Calculate the exact islamic midnight!</h1>
        <h2 class="sub-information">Click on <a href="/#/about">About</a> to learn how it is calculated</h2>
        <div class="main-container">
            <div class="maghrib">Enter Maghrib time: </div>
            <div class="fajr">Enter Fajr time: </div>
            <input type="text" bind:value={maghribTime} placeholder="Enter local maghrib time in 24-hour time format..."/>
            <input type="text" bind:value={fajrTime} placeholder="Enter local fajr time in 24-hour time format..."/>
        </div>
        <button on:click={handleCalculate}>Calculate</button>
        {#if (caluclatedOnce)}
            {#if (invalidInput)}
                <div class="wrong-input">Wrong input format. Please write in "--:--" format.</div>
                <div class="example">Example: Maghrib = 16:26, Fajr = 06:02</div>
            {:else}
                <div class="result-container">Islamic Midnight: <div class="result">{islamicMidnight}</div></div>
            {/if}
        {/if}
    </div>
</main>



<style>
.wrong-input, .example, .result-container{
    font-size: 2rem;
    grid-column: 1 / -1;
    text-align: center;
}

.result, .example{
    font-weight: bolder;
}

.maghrib{
    font-size: 1.5rem;
}

.fajr{
    font-size: 1.5rem;
}

main{
    display: grid;
    place-items: center;
}

button{
    font-size: 1.5rem;
    padding: 1rem;
    border-radius: 16px;
    margin-bottom: 1rem;
}

input{
    font-size: 2rem;
    border-radius: 8px;
    padding: 1rem;
    margin-bottom: 1rem;
}

input::placeholder {
    font-style: italic;
    opacity: 0.7;
}

a{
    text-decoration: underline;
    font-weight: bold;
}

.main-container{
    display: grid;
    grid-template-columns: repeat(2, 1fr);
    justify-content: center;
    gap: 1rem;
}

.main{
    width: 90%;
    border-radius: 16px;
    background-color: #1C6433;
    padding: 2rem;
}

h2{
    opacity: 90%;
    font-style: italic;
}
</style>