# Project-1

<html>
<head>
<title>Quiz</title>
</head>
<meta name="viewport" content="width=device-width, intial-scale=1.0">
<style>
body {
background-color: black;
}
img {
width: 100%;
height: auto;
}
h1 {
text-align: left;
color: white;
font-style: oblique;
font-size: 150px; 
}
#character {
color: white;
font-size: 30px;
}
button {
width: 200px;
}
window.location {
width: 3000px;
}
#results {
position: relative;
right: -900px;
width: 200px;
}
#nextpage {
position: relative;
right: -840px;
bottom: -50px;
width: 200px;
}

</style>

<body>
<img src="http://www.furious7.com/images/main_content_back.jpg">
<h1><center>Fast and Furious</center></h1>

<div id="character"><form>
<blockquote>
	<tr>
	<td>
		<center>Who is your favorite character?<center>
		<br>
		<label><input type="checkbox" name="fastcrew" id="mia" value="mia"> <label for="mia">Mia</label>
		<label><input type="checkbox" name="fastcrew" id="hobbs" value="hobbs"> <label for="hobbs">Hobbs</label>
		<label><input type="checkbox" name="fastcrew" id="letty" value="letty"> <label for="letty">Letty</label>
		<label><input type="checkbox" name="fastcrew" id="brian" value="brian"> <label for="brian">Brian</label>
		<label><input type="checkbox" name="fastcrew" id="dom" value="dom"> <label for ="dom">Dom</label>
	</td>
	</tr>
	</blockquote>
	</div>
	</form>	
<p id='fastcrewParagraph'></p>
<div id="nextpage"><button onclick="window.location='file://net160.net.ucf.edu/userfolders$/ti153451/My%20Documents/quiz%201%20page%202.html'">Let's begin!</button></div>
<div id="results"><input type="button" id="quizButton" value="Click here!"></div>
<script>
var myCrew = ['Mia', 'Hobbs', 'Letty', 'Brian', 'Dom'];
var points = [0,0,0,0,0];

function init() {
var button = document.getElementById('quizButton');
button.onclick = checkQuiz;
}

function checkQuiz() {
var fastcrew;
var inputs = document.getElementsByName('fastcrew');

	fastcrew = findValue(inputs);
	switch(fastcrew) {
		case 'Mia':
			points[0]++;
			break;
		case 'Hobbs':
			points[2]++;
			break;
		case 'Letty':
			points[1]++;
			break;
		case 'Brian':
			points[4]++;
			break;
		case 'Dom':
			points[3]++;
			break;
	}
	maxScore = 0;
	maxIndex = 0;
	
	for (var i = 0; i < points.length; i++) {
		if (points[i] > maxScore) {
		maxIndex = i;
		}
	}
	fastcrew = myCrew[maxIndex];
	displayFastcrew(fastcrew);
}
function findValue(inputs) {
		var checked;
		for (var i=0; i < inputs.length; i++) {
		if (inputs[i].checked) {
		alert(inputs[i].value);
			checked = inputs[i].value;
			return(checked);
		}
	}
	if (!checked) {
		alert('Please choose a value');
	}
	
}

function displayFastcrew(fastcrew) {
	var image = document.createElement('img');
	image.className = 'fastcrew';
	var source = document.getElementById('fastcrewParagraph');
	
	source.appendChild(image);
	source.innerHTML += '<br>' + text;
	
}
	window.onload = init;

</script>
</html>
