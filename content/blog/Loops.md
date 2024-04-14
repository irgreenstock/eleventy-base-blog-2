---
title: Exploring Loops, Arrays and Objects Part 1
date: 2024-04-14
tags: -IG -JavaScript
---

<hr>
<div>

Looking at different uses for loops, arrays and objects in JavaScript. First up, a shopping cart. We can find cart totals, apply discount and filter items by price. 

<br><h3>We can list shopping cart items in an array...</h3><br>

``` js
const cartItems =[
 { name: "loaf of bread", type: "food", quantity: 1, price: 0.85 },
        { name: "multipack beans", type: "food", quantity: 1, price: 1 },
        { name: "mushrooms", type: "food", quantity: 10, price: 0.1 },
        { name: "can of beer", type: "alcohol", quantity: 4, price: 1.1 },
        { name: "prosecco", type: "alcohol", quantity: 1, price: 8.99 },
        { name: "steak", type: "food", quantity: 2, price: 3.99 },
        { name: "blue cheese", type: "food", quantity: 1, price: 2.99 },
        { name: "candles", type: "home", quantity: 3, price: 1.99 },
        { name: "cheesecake", type: "food", quantity: 1, price: 4.99 },
        { name: "onions", type: "food", quantity: 3, price: 0.4 }
      ];
```
<br><h3>Find the total cost of the cart...</h3><br>

``` js
//Find the cart total
getTotal = (cart) => {
   let totalPrice = 0;
   for (let i=0; i < cart.length; i++) {
     totalPrice += cart[i].quantity * cart[i].price;   
 }
  return 'the total price is £' + totalPrice.toFixed(2); 
}

console.log(getTotal(cartItems));
```
<br><h3>Apply discounts by item type or on all the cart...</h3><br>

``` js
//Apply a discount on one type of item
const foodDiscount = 20;

getTotal = (cart) => {
   let totalPrice = 0;
   for (let i=0; i < cart.length; i++) {
     let itemPrice = cart[i].quantity * cart[i].price;   
     
     if (cart[i].type === 'food') {
       const discount = itemPrice * foodDiscount/100; 
       itemPrice-= discount;
     }
     totalPrice += itemPrice;
 }
  return 'The total price including a 20% discount on food is £' +totalPrice.toFixed(2); 
}

console.log(getTotal(cartItems));

//Discount all items of any type

getTotal = (cart, discountAmount, type) => {
   let totalPrice = 0;
  
   for (let i=0; i < cart.length; i++) {
     let itemPrice = cart[i].quantity * cart[i].price;   
     
     if (type === 'any' || type === cart[i].type) {
       const discount = itemPrice * discountAmount/100; 
       itemPrice-= discount;
     }
     totalPrice += itemPrice;
 }
  return 'the total price including a 20% discount is £' +totalPrice.toFixed(2); 
}

console.log(getTotal(cartItems, 15, 'any'));
 ```
<br><h3> Or find items in a price range! </h3><br>

 ``` js 
//Find items between two prices
const arrItems = []; 
priceRange = (cart,lowPrice, highPrice) => {
       for (let i = 0; i < cart.length; i++) {
          if (cart[i].price >= lowPrice && cart[i].price <= highPrice) {
          arrItems.push(cart[i]);
          }     
          }
};
priceRange(cartItems,5,10);
console.log(arrItems);


//Find items between two prices, taking quantity of items in to account

const arrItems2 = []; 
priceRange = (cart,lowPrice, highPrice, quantity) => {
       for (let i = 0; i < cart.length; i++) {
          let itemTotal = cart[i].price*cart[i].quantity;
          if (quantity && itemTotal >= lowPrice && itemTotal <= highPrice) {
          arrItems2.push(cart[i]);
          }     
          }
};
priceRange(cartItems,5,10,true);
console.log(arrItems2);

```
</div>