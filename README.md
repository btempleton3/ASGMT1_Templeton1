# ASGMT1_Templeton1
<html>
<head>
<title>Quiz</title>
<style>
.thing {
	position:absolute; 
	left: 0px;
	top: 0px; 
	border: 2px;
	border-style: double;
	background-color: cyan; 
	margin: 5px;
	padding: 5px; 
}
</style>
<script type="text/javascript">
		var facts = [
			["Clemson","Tiger",false],
			["Lincoln","Cornhusker",false],
			["Gainesville","Gator",false],
			["Los Angeles","Bruin",false],
			["Seattle","Husky",false],
			["Lexington","Wildcat",false],
			["Fort Collins","Ram",false],
			["Honolulu","Rainbow Warrior",false]
			];
		var thingelem;
		var nq = 4;
		var elementinmotion;
		var makingmove = false;
		var inbetween = 300;
		var col1 = 20;
		var row1 = 200;
		var rowsize = 50;
		var slots = new Array(nq);
function init() {
	setupgame();
		}
function setupgame() {
	var i;
	var c;
	var s;
	var mx = col1;
	var my = row1;
	var d;
	var uniqueid;
	for (i=0;i<facts.length;i++) {
			facts[i][2] = false;
		}
		for (i=0;i<nq;i++) {
			slots[i] = -100;
		}
		for(i=0;i<nq;i++) {
			do {c = Math.floor(Math.random()*facts.length);}
		while (facts[c][2]==true)
		facts[c][2]=true;
		uniqueid = "c"+String(c);
		d =
document.createElement
('country');
	d.innerHTML = ("<div class='thing'id='"+uniqueid+"'>placeholder</div>");
document.body.appendChild(d);
		thingelem =
document.getElementById(uniqueid);
		thingelem.textContent=
fact[c][0];
		thingelem.style.top =
String(my)+"px";
		thingelem.style.left =
String(mx)+"px";
thingelem.addEventListener('click',pickelement,false);
		uniqueid = "p"+String(c);
		d =
document.createElement('cap');
		d.innerHTML = (
			"<div class='thing'
id='"+uniqueid+"'>placeholder</div>");
document.body.appendChild(d);
		thingelem =
document.getElementById(uniqueid);
thingelem.textContent=facts[c][1];
		do {s = Math.floor(Math.random()*nq);}
		while (slots[s]>=0)
		slots[s]=c;
thingelem.style.top = String
(row1+s*rowsize)+"px";
thingelem.style.left = String
(col1+inbetween)+"px";
thingelem.addEventListener('click',
pickelement,false);
		my +=rowsize;
	}
		document.f.score.value = "0";
		return false;
	}
	function pickelement(ev) {
		var thisx;
		var thisxn;
		if (makingmove) {
			thisx= this.style.left;
thisx = thisx.substring
(0,thisx.length-2);
		thisxn =
Number(thisx) + 110;
elementinmotion.style.left =
String(thisxn)+"px";
elementinmotion.style.top
	this.style.top;
		makingmove = false;
if (this.id.substring(1)==
elementinmotion.id.substring(1)) {
elementinmotion.style.
backgroundColor = "green";
this.style.backgroundColor = "green";
document.f.out.value = "RIGHT";
document.f.score.value = String
(1+Number(document.f.score.value));
		}
	else {
	document.f.out.value = "WRONG";}
	}
	else {
		makingmove = true;
		elementinmotion = this;
	}
}
</script>
</head>
<body onLoad="init();">
<h1>Mascot Matching</h1><br/>Click on a football team's mascot or a city and then click on corresponding
city or mascot.<p>Reload for new game.<form name="f" >Action:<input name="out" type=
"text" value="RIGHT OR WRONG"/>Score: <input name="score" type=
"text" value="0"/></form>
</p>
</body>
</html>
