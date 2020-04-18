<html lang="en">
<head>
<title>Bootstrap Example</title>
<meta charset="utf-8">
<meta name="viewport" content="width=device-width, initial-scale=1">
<!-- Latest compiled and minified CSS -->
<link rel="stylesheet"
href="https://maxcdn.bootstrapcdn.com/bootstrap/4.4.1/css/bootstrap.min.css">
<!-- jQuery library -->
<script src="https://ajax.googleapis.com/ajax/libs/jquery/3.4.1/jquery.min.js"></script>
<!-- Popper JS -->
<script
src="https://cdnjs.cloudflare.com/ajax/libs/popper.js/1.16.0/umd/popper.min.js"></script>
<!-- Latest compiled JavaScript -->
<script src="https://maxcdn.bootstrapcdn.com/bootstrap/4.4.1/js/bootstrap.min.js"></script>


<style>
body {
  font-family: sans-serif;
  display: grid;
  height: 100vh;
  place-items: center;
}

.base-timer {
  position: relative;
  width: 300px;
  height: 400px;
}

.base-timer__svg {
  transform: scaleX(-1);
}

.base-timer__circle {
  fill: none;
  stroke: none;
}

.base-timer__path-elapsed {
  stroke-width: 7px;
  stroke: grey;
}

.base-timer__path-remaining {
  stroke-width: 7px;
  stroke-linecap: round;
  transform: rotate(90deg);
  transform-origin: center;
  transition: 1s linear all;
  fill-rule: nonzero;
  stroke: currentColor;
}

.base-timer__path-remaining.green {
  color: rgb(40,167,69);
}

.base-timer__path-remaining.orange {
  color: orange;
}

.base-timer__path-remaining.red {
  color: red;
}

.base-timer__path-remaining.grey {
  color: rgb(128,128,128)
}

.base-timer__label {
  position: absolute;
  width: 300px;
  height: 300px;
  top: 0;
  display: flex;
  align-items: center;
  justify-content: center;
  font-size: 48px;
}

</style>







</head>
<body>
<!-- copy this file as your starting point -->






<!-- code start!!~~-->
<div class="container-fluid bg-white text-secondary">
	<div class="row">
    	<BR>
    </div>
	<div class="row">
    	<div class="col-12 text-center">
        	<h3> <span id="title" class="text"> </span></h3>
        </div>
    </div>
 
<!-- blank row -->
<div class="item html">
  <div class="row">
    <BR> <BR> <BR> <BR> <BR>
  </div>
</div>

    <!-- people row-->
    <div class="row">
    	<div class="col-3 text-center">
        	<h3>Person A </h3>
            <h4>Person A</h4>
      </div>
		  <div class="col-6 text-center">
        <!-- timer -->
          <center> <h1><span id="countdown" class="timer"></span></h1> </center>
      </div>
      <div class="col-3 text-center">
        <h3>Person B</h3>
        <h4>Person B</h4>
      </div>
    </div>
    

    <!-- blank row -->
    <div class="row">
        <BR>           
    </div>
    
    <!-- button row-->
    <div class="row">
    	<div class="col-3">
        	<!-- Blank Column-->
            <BR> <BR> 
        </div>
        <div class= "col-12 text-center">
            <button type="button" class="btn btn-outline-dark btn-lg" id= "preButton" onclick="stepDown();"> < </button>
			<button type="button" class="btn btn-success btn-lg" id="commandButton" onclick="startCount();"> Start </button>
            <!-- <button type="button" class="btn btn-warning btn-lg" id="pauseButton" onclick="pauseCount();"> Pause </button> -->
            <button type="button" class="btn btn-danger btn-lg" id="resetButton" onclick="resetTime();"> Reset </button>
            <button type="button" class="btn btn-outline-dark btn-lg" id="nextButton" onclick="stepUp();"> > </button>
            
            
        </div>
        <div class= "col-3">
        	<!-- Blank Column-->
        </div>
    </div>
</div>

</body>




<script>

var step = 1
var countdown_enable=false;
var totalSeconds = 300
var timeProcessed = 0;
const warningThreshold = 10;
var overtime = false; 
var bFlashing = false;
const FULL_DASH_ARRAY = 283;
const WARNING_THRESHOLD = 10;
const ALERT_THRESHOLD = 0;
let sectionTime= [300, 480, 120, 600]

function initButtons(){
    document.getElementById('title').innerHTML = "Round 1 Room A – Step 1: Present Proposal (5 mins)";
    document.getElementById('resetButton').disabled = true;
    document.getElementById('preButton').disabled = true;
}
var init=initButtons();




const COLOR_CODES = {
  info: {
    color: "green",
  },
  warning: {
    color: "orange",
    threshold: WARNING_THRESHOLD
  },
  alert: {
    color: "red",
    threshold: ALERT_THRESHOLD
  },
  base:{
    color: "grey",
  }

};

let remainingPathColor = COLOR_CODES.info.color;


function updateDisplay() {
    var minutes = 0;
    var seconds = 0;
 
    if (countdown_enable) {
        timeProcessed += 1
    }

    var remainingSeconds = totalSeconds-timeProcessed;
    if (remainingSeconds >0) {
        overtime=false
        minutes = Math.floor(remainingSeconds/60);
        seconds = remainingSeconds - minutes * 60;
    } else{
        overtime=true
        minutes = Math.floor((timeProcessed-totalSeconds)/60);
        seconds = timeProcessed-totalSeconds - minutes * 60;
    }
    

    if (seconds < 10) {
        seconds = "0" + seconds;  
    }

    document.getElementById("countdown").innerHTML = `
<div class="base-timer">
  <svg class="base-timer__svg" viewBox="0 0 100 100" xmlns="http://www.w3.org/2000/svg">
    <g class="base-timer__circle">
      <circle class="base-timer__path-elapsed" cx="50" cy="50" r="45" />
      <path
        id="base-timer-path-remaining"
        stroke-dasharray="283"
        class="base-timer__path-remaining ${remainingPathColor}"
        d="
          M 50, 50
          m -45, 0
          a 45,45 0 1,0 90,0
          a 45,45 0 1,0 -90,0
        "
      ></path>
    </g>
  </svg>
  <span id="base-timer-label" class="base-timer__label">
    ${minutes + ":" + seconds}
  </span>
</div>
`;


setCircleDasharray();
setRemainingPathColor(remainingSeconds);
}
 
var countdownTimer = setInterval(updateDisplay, 1000);

function startCount() {
  clearInterval(countdownTimer);
  countdownTimer = setInterval('updateDisplay()',1000);

	if (!countdown_enable){
    countdown_enable=true;
    document.getElementById('commandButton').innerHTML = "Pause"
    document.getElementById('commandButton').style.background = COLOR_CODES.warning.color;
    document.getElementById('resetButton').disabled = false
  } else {
    countdown_enable=false;
    document.getElementById('commandButton').innerHTML = "Resume"
    document.getElementById('commandButton').style.background = "#87CEEB"; 
  } 


}

function resetTime(){
  document.getElementById('resetButton').disabled = true;
  setUpCounter();
  countdown_enable=false;
  clearInterval(countdownTimer);
	countdownTimer = setInterval('updateDisplay()',1000);
  document.getElementById('commandButton').innerHTML = "Start"
  document.getElementById('commandButton').style.background = "#28a745";

  document.getElementById('countdown').style.color = COLOR_CODES.base.color;
  remainingPathColor = COLOR_CODES.info.color;
}

function stepUp(){
	step= step+ 1
	setUpCounter();
  countdown_enable=false
  document.getElementById('commandButton').innerHTML = "Start"
  document.getElementById('commandButton').style.background = "#28a745";
  document.getElementById('resetButton').disabled = true
  document.getElementById('countdown').style.color = COLOR_CODES.base.color;
  remainingPathColor = COLOR_CODES.info.color;
}

function stepDown(){
	step=step-1	
	setUpCounter();
  countdown_enable=false
  document.getElementById('commandButton').innerHTML = "Start"
  document.getElementById('commandButton').style.background = "#009900";
  document.getElementById('resetButton').disabled = true
  document.getElementById('countdown').style.color = COLOR_CODES.base.color;
  remainingPathColor = COLOR_CODES.info.color;
}

function setUpCounter(){
  var dispTitle ="";
  totalSeconds = sectionTime[step-1];
  timeProcessed = 0;
  switch(step) {
    case 1:
    
	  dispTitle = "Round 1 Room A – Step 1: Present Proposal (5 mins)";
      document.getElementById('preButton').disabled = true;
	  document.getElementById('nextButton').disabled = false;

      break;
    case 2:
      dispTitle = "Round 1 Room A – Step 2: Q&A (8 mins)";
      document.getElementById('preButton').disabled = false;
	  document.getElementById('nextButton').disabled = false;
   
      break;
    case 3:
      dispTitle = "Round 1 Room A – Step 3: Conclusion (2 mins)";
      document.getElementById('preButton').disabled = false;
	  document.getElementById('nextButton').disabled = false;
      break;
    case 4:
      dispTitle = "Round 1 Room A – Step 4: Judge panel questions (10 mins)";
      document.getElementById('preButton').disabled = false;
	  document.getElementById('nextButton').disabled = true;

      break;
    
    default:
      dispTitle = "Round 1 Room A – Step 1: Present Proposal (5 mins)";
      document.getElementById('preButton').disabled = true;
	  document.getElementById('nextButton').disabled = false;
  } 

  document.getElementById('title').innerHTML = dispTitle

}



function setRemainingPathColor(remainingSeconds) {
  const { alert, warning, info, base } = COLOR_CODES;
  if (remainingSeconds <= alert.threshold) {
    remainingPathColor = COLOR_CODES.alert.color
    bFlashing = ~bFlashing;
      if (bFlashing){
        document
          .getElementById("base-timer-path-remaining")
          .classList.remove(alert.color);
        document
          .getElementById("base-timer-path-remaining")
          .classList.add(base.color);
        document
          .getElementById("base-timer-path-remaining")
          .classList.add(alert.color);
        document.getElementById('countdown').style.color = alert.color
      }

  } else if (remainingSeconds <= warning.threshold) {
    document
      .getElementById("base-timer-path-remaining")
      .classList.remove(info.color);
    document
      .getElementById("base-timer-path-remaining")
      .classList.add(warning.color);
      
      document.getElementById('countdown').style.color = warning.color;

  }
}



// Divides time left by the defined time limit.
function calculateTimeFraction() {
    return (totalSeconds-timeProcessed)/totalSeconds;
}
   // calculateTimeFraction() * FULL_DASH_ARRAY 
// Update the dasharray value as time passes, starting with 283
function setCircleDasharray() {
  const circleDasharray = `${(
    calculateTimeFraction() * FULL_DASH_ARRAY
  ).toFixed(0)} 283`;
  document
    .getElementById("base-timer-path-remaining")
    .setAttribute("stroke-dasharray", circleDasharray);
}


</script>
</html>
