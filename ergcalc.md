<html>
<body><h3>Erg Score Calculator</h3>
<hr>
<form>
<b><i>Split Time</i></b><br>
<input type="TEXT" name="split_min" size="2">
 min <input type="TEXT" name="split_sec" size="6"> sec /500m<br>
<b><i>Distance (m)</i></b><br>
<input type="TEXT" name="distance" size="11"><br>
<b><i>Total Time (mm:ss)</i></b><br>
<input type="TEXT" name="time_hr" size="2">
 hr <input type="TEXT" name="time_min" size="2">
 min <input type="TEXT" name="time_sec" size="4">
 sec<br><br>
<b><i>Calculate:</i></b><br>
<input type="button" value="Time" onclick="ergtime(this.form)">
<input type="button" value="Distance" onclick="ergdistance(this.form)">
<input type="button" value="Split" onclick="ergsplit(this.form)">
<input type="button" value="Clear All Fields" onclick="reset(this.form)">
</form>
<script language="JavaScript">
<!--
function reset(form) {
        form.split_min.value=""
        form.split_sec.value=""
        form.distance.value=""
        form.time_hr.value=""
        form.time_min.value=""
        form.time_sec.value=""
}

function ergdistance(form) {
var th=0, tm=0, ts=0, sm=0, ss=0, dis=0
if (form.time_hr.value.length==0) {
form.time_hr.value = 0
}
if (form.time_min.value.length==0) {
form.time_min.value = 0
}
if (form.time_sec.value.length==0) {
form.time_sec.value = 0
}
if (form.split_min.value.length==0) {
form.split_min.value = 0
}
if (form.split_sec.value.length==0) {
form.split_sec.value = 0
}
if ((form.time_hr.value==0 
&& form.time_min.value==0 
&& form.time_sec.value==0) 
|| (form.split_min.value==0 
&& form.split_sec.value==0)) {
alert("Cannot calculate when the" +
 " Split or Total times are Zero!")
}
else {
th = 1*form.time_hr.value
tm = 1*form.time_min.value
ts = 1*form.time_sec.value
sm = 1*form.split_min.value
ss = 1*form.split_sec.value
if (th>=24 || th<0 || tm>59 
|| tm<0 || ts>59 || ts<0 
|| sm>=60 || sm<0 || ss>=60 
|| ss<0 ) {
alert("Check your Time values: Hours 0-23,"+
" Minutes 0-59, seconds 0-59")
}
else {
ss = ss + (60*sm)
ts = ts + (60*tm) + (60*60*th)
dis = (ts/ss) *500
form.distance.value = dis
}
}
}

function ergsplit(form) {
var ts=0, ss1=0, ss=0, sm=0
if (form.time_hr.value.length==0) {
form.time_hr.value = 0
}
if (form.time_min.value.length==0) {
form.time_min.value = 0
}
if (form.time_sec.value.length==0) {
form.time_sec.value = 0
}
if (form.distance.value.length==0) {
form.distance.value = 0
}
if ((form.time_hr.value==0
 && form.time_min.value==0
 && form.time_sec.value==0)
 || (form.distance.value==0)) {
alert("Cannot calculate when the "+
"Distance or Total time is Zero!")
}
else {
ts = (form.time_hr.value*3600) 
+ (form.time_min.value*60) 
+ 1*form.time_sec.value
ss1 = 500*(ts / form.distance.value)
sm = Math.floor(ss1/60)
ss = ss1 - (60*sm)
form.split_min.value = sm
form.split_sec.value = ss
}
}

function ergtime(form) {
var tm=0, ts=0, th=0, ts1=0, ss=0
if (form.split_min.value.length==0) {
form.split_min.value = 0
}
if (form.split_sec.value.length==0) {
form.split_sec.value = 0
}
if (form.distance.value.length==0) {
form.distance.value = 0
}
if ((form.split_min.value==0 && 
form.split_sec.value==0) 
|| (form.distance.value==0)) {
alert("Cannot calculate when the"
+" Distance or Total time is Zero!")
}
else {
ss = (form.split_min.value*60) 
+ 1*form.split_sec.value
ts1 = ss * ((1*form.distance.value)/500)
th = Math.floor(ts1/3600)
tm = Math.floor((ts1 - 3600*th)/60)
ts = ts1 - (3600*th) - (60*tm)
form.time_hr.value = th
form.time_min.value = tm
form.time_sec.value = ts
}

if (form.distance.value.length==0 
|| form.split_min.value.length==0 
|| form.split_sec.value.length==0) {
alert("Please complete the Split "
+"Time and Total Time fields first.")
}
else {
}
}

<!-- -->
</script>
<hr>
<i>Written by <a href="mailto:ojrg20@bath.ac.uk">OG</a>
 14/01/2022. Procrastinating CM50258.</i>
 <hr>


</i></i></body></center>
</html>
