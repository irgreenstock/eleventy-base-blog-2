---
layout: layouts/base.njk
title: Contact
eleventyNavigation:
  key: Projects
  order: 5
---

<head><title>Tip Calculator</title>
   <link rel="stylesheet" href="https://maxcdn.bootstrapcdn.com/bootstrap/4.0.0-beta.2/css/bootstrap.min.css" integrity="sha384-PsH8R72JQ3SOdhVi3uxftmaW6Vc51MKb0q5P2rRUpPvrszuE4W1povHYgTpBfshb" crossorigin="anonymous">
</head>
<body>
  <div><h1>Tip Calculator</h1>
    <div class="container border border-info rounded w-50 mx-auto p-4 m-4">
    <form id="calculator">
      <div class="form-group p-2">
        <div class="row g-3"><label for="Bill">How much was your bill? £
         </label><div><input type="text" id="Bill" name="Bill"></input></div></div></div>
      <div class="form-group p-2"><div class="row g-3"><label for="tip amount" class="col-form-label">How much do you want to tip?</label><select id="tip" name="tip">
  <option value="0.10">10%</option>
  <option value="0.15">15%</option>
        <option value="0.20">20%</option></select></div></div>
         <div class="form-group p-2 text-center"><button type="submit" id="calculate" class="btn btn-info mx-auto">Submit</button></div> 
    </form>
    <hr>
    <div id="results"><p class="tipAmount"></p>
      <p class="displayBill"></p>
    <div> 
     </div></div>
<script>
function calculateTip() {
    //define bill amount
    let preTip = document.querySelector('#Bill').value;
    //define tip amount
    let tip = document.querySelector('#tip').value;
    //calculate tip
      tip = preTip*tip;
    //Calculate total bill
    let totalBill = parseFloat(tip)+parseFloat(preTip);
      
    //Document final bill in a string
       
    document.querySelector('.displayBill').innerHTML=
     `Your total bill, including a tip of £${tip.toFixed(2)}, is £${totalBill.toFixed(2)}` ;
    //display div with results text 
      document.querySelector("#results").style = "display: block"; 
      
    console.log(`Your total bill, including a tip of £${parseFloat(tip).toFixed(2)}, is £${parseFloat(totalBill).toFixed(2)}`);
    };
    
     
    //run calculator when Submit button is clicked
    document.getElementById("calculate").onclick = function() {
      calculateTip();
      };
    //prevent reload
    document.addEventListener('submit', (e) => e.preventDefault());
</script>