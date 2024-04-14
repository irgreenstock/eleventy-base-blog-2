---
title: Creating a Tip Calculator with JavaScript
date: 2024-02-25
tags: -IG
---


<div>This shows how JavaScript can be utilised to calculate a tip and provide the final bill. The codepen embed below shows a simple front end which can display the result of the calculation.


``` js
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

```
</div>
<h2>Tip Calculator</h2>
<div>
<p class="codepen" data-height="300" data-default-tab="result" data-slug-hash="JjzmaVo" data-user="Isabelle-Greenstock" data-zoom="0.5" style="height: 300px; box-sizing: border-box; display: flex; align-items: center; justify-content: center; border: 2px solid; margin: 1em 0; padding: 1em;">
  <span>See the Pen <a href="https://codepen.io/Isabelle-Greenstock/pen/JjzmaVo">
  Tip Calculator</a> by Isabelle Greenstock (<a href="https://codepen.io/Isabelle-Greenstock">@Isabelle-Greenstock</a>)
  on <a href="https://codepen.io">CodePen</a>.</span>
</p>
<script async src="https://cpwebassets.codepen.io/assets/embed/ei.js"></script>
</div>