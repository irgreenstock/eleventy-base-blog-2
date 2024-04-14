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
{% include "js/tip.js" %}
</script>