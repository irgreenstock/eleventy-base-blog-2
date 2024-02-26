---
layout: layouts/base.njk
title: Contact
eleventyNavigation:
  key: Contact
  order: 4
---

<div class="container border border-light-subtle rounded mx-auto p-4 m-4">
  <form name="contact" action="POST" data-netlify="true">
  <div class="form-group p-2"><div class="row">
    <div class="col"><label for="First Name">First Name</label><input name="first name" id="First Name" type="text" class="form-control" placeholder="First Name" aria-label="First Name"></div>
    <div class="col">
    <label for="Last Name">Last Name</label><input name="last name" id="Last Name" type="text" class="form-control" placeholder="Last Name" aria-label="Last Name"></div>
    </div></div>
  <div class="form-group p-2">
    <label for="Email address">Email Address</label>
    <input name="email" id="Email address" type="email" class="form-control" placeholder="example@example.com" required>
   </div>
  <div class="form-group p-2">
    <label for="text-area">Write me a message!</label>
    <textarea name="message" id="text-area" class="form-control" rows="3" placeholder="Anything to say?"></textarea>
  </div>
      <div class="form-check">
        <br>
        <label for="checkbox" class="form-check-label">Click here to agree to the T&Cs</label>
        <input name="check" id="checkbox" type="checkbox" class="form-check-input" required>       
        </div>
    <br>
  <button type="submit" class="btn btn-info">Submit</button>
  </form>
  </div>