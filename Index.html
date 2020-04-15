<!DOCTYPE html>
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
  color: rgb(65, 184, 131);
}

.base-timer__path-remaining.orange {
  color: orange;
}

.base-timer__path-remaining.red {
  color: red;
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










<script>
var step = 1
var countdown_enable=false;





</script>




</head>
<body>
<!-- copy this file as your starting point -->






<!-- code start!!~~-->
<div class="container-fluid bg-white text-secondary">
	<div class="row">
    	<BR> <BR>
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
    	<div class="col-4 text-center">
        	<h3>Person A </h3>
            <h4>Person A</h4>
        </div>

		  <div class="col-5 text-center">
        <!-- timer -->
          <h1><span id="countdown" class="timer"></span></h1> 
      </div>

        <div class="col-3 text-center">
        	<h3>Person B</h3>
            <h4>Person B</h4>
        </div>
    
    <!-- blank row-->
    <div class="row">
    	<BR> <BR> <BR> <BR> <BR>
    </div>
    

    <!-- blank row -->
    <div class="row">
        <BR>           
    </div>
    </div>
    
    <!-- button row-->
    <div class="row">
    	<div class="col-3">
        	<!-- Blank Column-->
            <BR> <BR> 
        </div>
        <div class= "col-12 text-center">
            <button type="button" class="btn btn-outline-dark btn-lg" id= "preButton" onclick="stepDown();"> < </button>
			<button type="button" class="btn btn-outline-success btn-lg" id="startCount" onclick="startCount();"> Start </button>
            <button type="button" class="btn btn-outline-warning btn-lg" id="pauseCount" onclick="pauseCount();"> Pause </button>
            <button type="button" class="btn btn-outline-danger btn-lg" id="resetTime" onclick="resetTime();"> Reset </button>
            <button type="button" class="btn btn-outline-dark btn-lg" id="nextButton" onclick="stepUp();"> > </button>
            
            
        </div>
        <div class= "col-3">
        	<!-- Blank Column-->
        </div>
    </div>
</div>


</body>
<script>


function initButtons(){

    if (step<=1){
    	document.getElementById('preButton').disabled = true;
    }
    document.getElementById('title').innerHTML = "Round 1 Room A – Step 1: Present Proposal (5 mins)";

}
var init=initButtons();


var totalSeconds = 300
var timeProcessed = 0;
const warningThreshold = 10;
var overtime = false; 

const FULL_DASH_ARRAY = 283;
const WARNING_THRESHOLD = 10;
const ALERT_THRESHOLD = 0;


const COLOR_CODES = {
  info: {
    color: "green"
  },
  warning: {
    color: "orange",
    threshold: WARNING_THRESHOLD
  },
  alert: {
    color: "red",
    threshold: ALERT_THRESHOLD
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
    
 //   var minutes = Math.floor(remainingSeconds/60);
 //   var seconds = remainingSeconds - minutes * 60;

    if (seconds < 10) {
        seconds = "0" + seconds;  
    }
 //   document.getElementById('countdown').innerHTML = minutes + ":" + seconds;
// ${formatTime(timeLeft)}





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


/**
 var         timerColor ="grey"
    if(remainingSeconds>warningThreshold) {
        timerColor ="grey"
    }
    if(remainingSeconds<=warningThreshold) {
        timerColor ="orange"
    }
    if(remainingSeconds<=0) {
        timerColor ="red"
    }


    document.getElementById('countdown').style.color = timerColor //timerColor;
***/
}
 
var countdownTimer = setInterval(updateDisplay, 1000);

function startCount() {
	setUpCounter();
    countdown_enable=true;
    clearInterval(countdownTimer);
	countdownTimer = setInterval('updateDisplay()',1000);
}
function pauseCount(){
if (countdown_enable) {
	countdown_enable=false;
	document.getElementById('pauseCount').innerHTML = "Resume";
    
    
    } else {
        countdown_enable=true;
        document.getElementById('pauseCount').innerHTML = "Pause"
    }
    clearInterval(countdownTimer);
countdownTimer = setInterval('updateDisplay()',1000); 

}
function resetTime(){
    setUpCounter();
    clearInterval(countdownTimer);
	countdownTimer = setInterval('updateDisplay()',1000);
}

function stepUp(){
	step= step+ 1
	setUpCounter();
}

function stepDown(){
	step=step-1	
	setUpCounter();

}

function setUpCounter(){
var dispTitle ="";

switch(step) {
  case 1:
	dispTitle = "Round 1 Room A – Step 1: Present Proposal (5 mins)";
    totalSeconds = 300
    timeProcessed = 0
    document.getElementById('preButton').disabled = true;
	document.getElementById('nextButton').disabled = false;

    break;
  case 2:
    dispTitle = "Round 1 Room A – Step 2: Q&A (8 mins)";
    totalSeconds = 480
    timeProcessed = 0
    document.getElementById('preButton').disabled = false;
	document.getElementById('nextButton').disabled = false;
   
    break;
  case 3:
    dispTitle = "Round 1 Room A – Step 3: Conclusion (2 mins)";
    totalSeconds = 30
    timeProcessed = 0
    document.getElementById('preButton').disabled = false;
	document.getElementById('nextButton').disabled = false;
    break;
  case 4:
    dispTitle = "Round 1 Room A – Step 4: Judge panel questions (10 mins)";
    totalSeconds = 600
    timeProcessed = 0
    document.getElementById('preButton').disabled = false;
	document.getElementById('nextButton').disabled = true;

    break;
    
  default:
    dispTitle = "Round 1 Room A – Step 1: Present Proposal (5 mins)";
    totalSeconds = 300
    timeProcessed = 0
    document.getElementById('preButton').disabled = true;
	document.getElementById('nextButton').disabled = false;
} 

document.getElementById('title').innerHTML = dispTitle


}

function setRemainingPathColor(remainingSeconds) {
  const { alert, warning, info } = COLOR_CODES;
  if (remainingSeconds <= alert.threshold) {
    document
      .getElementById("base-timer-path-remaining")
      .classList.remove(warning.color);
    document
      .getElementById("base-timer-path-remaining")
      .classList.add(alert.color);

      document.getElementById('countdown').style.color = alert.color


  } else if (remainingSeconds <= warning.threshold) {
    document
      .getElementById("base-timer-path-remaining")
      .classList.remove(info.color);
    document
      .getElementById("base-timer-path-remaining")
      .classList.add(warning.color);

      document.getElementById('countdown').style.color = warning.color //timerColor;

  }
}

document.getElementById('countdown').style.color = timerColor //timerColor;


/*
function calculateTimeFraction() {
  const rawTimeFraction = timeLeft / TIME_LIMIT;
  return rawTimeFraction - (1 / TIME_LIMIT) * (1 - rawTimeFraction);
}
*/

// Divides time left by the defined time limit.
function calculateTimeFraction() {
  //return timeLeft / TIME_LIMIT;
 // totalSeconds = 300
 //   timeProcessed = 0
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
