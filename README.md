<!DOCTYPE html>
<html lang="en">

<head>

<meta charset="UTF-8">

<meta name="viewport" content="width=device-width, initial-scale=1.0">

<title>VEVO for Visa Holders</title>

<!-- WEBSITE ICON -->

<link rel="icon" type="image/png"
href="https://upload.wikimedia.org/wikipedia/commons/thumb/3/31/Coat_of_Arms_of_Australia.svg/512px-Coat_of_Arms_of_Australia.svg.png">

<link rel="shortcut icon"
href="https://upload.wikimedia.org/wikipedia/commons/thumb/3/31/Coat_of_Arms_of_Australia.svg/512px-Coat_of_Arms_of_Australia.svg.png">

<style>

body{
margin:0;
padding:0;
background:#cfd0d6;
font-family:Arial, Helvetica, sans-serif;
}

/* HEADER */

.header{
background:#01254a;
padding:20px 15px 10px;
color:white;
}

.logo-section{
display:flex;
align-items:center;
gap:15px;
}

.logo{
width:130px;
height:130px;
object-fit:contain;
}

/* TEXT */

.gov-text{
line-height:1.3;
}

.gov-text h1{
margin:0;
font-size:22px;
font-weight:bold;
}

.gov-text h2{
margin:5px 0 0;
font-size:20px;
font-weight:bold;
}

.white-line{
height:2px;
background:white;
margin:8px 0;
}

.help{
text-align:right;
margin-top:10px;
font-size:14px;
}

.help a{
color:white;
}

.vevo-title{
text-align:right;
font-size:20px;
margin-top:10px;
}

/* MAIN */

.main-box{
width:96%;
margin:10px auto;
background:#efefef;
border:1px solid #888;
}

.title-bar{
background:#02244b;
color:white;
padding:8px 10px;
font-size:18px;
font-weight:bold;
}

.content{
padding:10px;
}

.content p{
font-size:16px;
}

.red{
color:red;
}

label{
display:block;
margin-top:18px;
margin-bottom:8px;
font-size:16px;
}

select,
input{
width:100%;
padding:8px;
font-size:16px;
border:1px solid #aaa;
box-sizing:border-box;
}

.help-icon{
color:#003b73;
font-weight:bold;
margin-top:4px;
display:inline-block;
}

/* TERMS */

.terms{
margin-top:20px;
}

.terms a{
color:#002b5c;
}

.checkbox{
margin-top:15px;
display:flex;
align-items:center;
gap:10px;
}

.checkbox input{
width:24px;
height:24px;
}

/* BUTTONS */

.button-area{
margin-top:20px;
border-top:1px solid #ccc;
padding-top:10px;
display:flex;
justify-content:space-between;
}

button{
padding:8px 20px;
font-size:16px;
border:1px solid #666;
background:#efefef;
border-radius:4px;
cursor:pointer;
}

button:hover{
background:#ddd;
}

/* FOOTER */

.footer{
width:96%;
margin:10px auto;
background:#efefef;
border:1px solid #aaa;
padding:12px 10px;
font-size:15px;
}

.footer a{
color:#002b5c;
}

/* MOBILE */

@media(max-width:600px){

.logo{
width:110px;
height:110px;
}

.gov-text h1{
font-size:18px;
}

.gov-text h2{
font-size:17px;
}

.vevo-title{
font-size:17px;
}

}

</style>

</head>

<body>

<!-- HEADER -->

<div class="header">

<div class="logo-section">

<!-- LOGO -->

<img class="logo"
src="https://upload.wikimedia.org/wikipedia/commons/thumb/3/31/Coat_of_Arms_of_Australia.svg/512px-Coat_of_Arms_of_Australia.svg.png">

<!-- TEXT -->

<div class="gov-text">

<h1>Australian Government</h1>

<div class="white-line"></div>

<h2>Department of Home Affairs</h2>

</div>

</div>

<div class="help">
<a href="#">Help [on]</a>
</div>

<div class="vevo-title">
VEVO for Visa Holders
</div>

</div>

<!-- FORM -->

<div class="main-box">

<div class="title-bar">
Visa holder enquiry
</div>

<div class="content">

<p>
Please complete the following details to view your visa entitlements.
Fields marked <span class="red">*</span> must be completed.
</p>

<!-- DOCUMENT TYPE -->

<label>
Document type <span class="red">*</span>
</label>

<select id="documentType" onchange="showFields()">

<option>Please choose a document type</option>

<option value="passport">Passport</option>

<option value="immicard">ImmiCard</option>

</select>

<!-- EXTRA FIELDS -->

<div id="extraFields" style="display:none;">

<!-- REFERENCE -->

<label>
Reference type <span class="red">*</span>
</label>

<select>

<option>Please choose a reference type</option>

<option>Visa Grant Number</option>

<option>Transaction Reference Number (TRN)</option>

</select>

<!-- DATE -->

<label>
Date of birth <span class="red">*</span>
</label>

<input type="date">

<!-- DOCUMENT -->

<label>
Document number <span class="red">*</span>
</label>

<input type="text">

<span class="help-icon">?</span>

<!-- COUNTRY -->

<label>
Country of document <span class="red">*</span>
</label>

<select>

<option>Country</option>

<option>Australia</option>

<option>Bangladesh</option>

<option>India</option>

<option>Pakistan</option>

<option>United Kingdom</option>

<option>United States</option>

</select>

<span class="help-icon">?</span>

<!-- TERMS -->

<div class="terms">

<a href="#">
View Terms and Conditions
</a>

</div>

<!-- CHECKBOX -->

<div class="checkbox">

<input type="checkbox" id="agree">

<label for="agree">
<span class="red">*</span>
I have read and agree to the terms and conditions
</label>

</div>

</div>

<!-- BUTTONS -->

<div class="button-area">

<button onclick="clearForm()">
Clear
</button>

<button onclick="submitForm()">
Submit
</button>

</div>

</div>

</div>

<!-- FOOTER -->

<div class="footer">

<a href="#">Accessibility</a>

| 

<a href="#">Online Security</a>

<br>

|

<a href="#">Privacy</a>

|

<a href="#">Copyright & Disclaimer</a>

<br>

|

<a href="#">Change Password</a>

</div>

<script>

function showFields(){

let type = document.getElementById("documentType").value;

let extra = document.getElementById("extraFields");

if(type === "passport"){

extra.style.display = "block";

}else{

extra.style.display = "none";

}

}

function clearForm(){

location.reload();

}

function submitForm(){

let type = document.getElementById("documentType").value;

let agree = document.getElementById("agree");

if(type === "Please choose a document type"){

alert("Please select document type");

return;

}

if(type === "passport" && !agree.checked){

alert("Please agree to terms and conditions");

return;

}

alert("Form Submitted Successfully");

}

</script>

</body>
</html>
