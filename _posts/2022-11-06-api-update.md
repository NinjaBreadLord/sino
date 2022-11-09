---
toc: true
layout: post
title: frontend api update
description: javascript html frontend update
categories: [markdown]
---

<style>
    head {
        font-size: 40px;
        text-align: center;
    }
</style>

<head>
    <label for = "pop">World Population:</label>
    <p id = "pop"> world population </p>
</head>

<script>
const options = {
    method: 'GET',
    headers: {
        'X-RapidAPI-Key': 'befd3aa94cmsh6c15f9448db64f3p194824jsn7727f7079e12',
        'X-RapidAPI-Host': 'get-population.p.rapidapi.com'
    }
};


fetch('https://get-population.p.rapidapi.com/population', options)
    .then(response => response.json())
    .then(response => {
        console.log(response.count);
        document.getElementById("pop").innerHTML = response.count;
    })

    .catch(err => console.error(err));

change();

function change() {
    document.getElementById("pop").innerHTML = parseFloat(document.getElementById("pop").innerHTML) + 3;
}

setInterval(change,1000);        
</script>

