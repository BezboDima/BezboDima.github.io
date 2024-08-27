---
title: "Auction"
description: "Website build on Django framework for Auction"
dateString: Jan 2022
draft: false
tags: ["Python","Django", "CSS", "SQL"]
weight: 202
cover:
    image: "/projects/auction/auction.jpg"
---

<style>
        /* Container to maintain aspect ratio */
        .video-container {
            position: relative;
            width: 100%;
            padding-bottom: 56.25%; /* 16:9 aspect ratio */
            height: 0;
            overflow: hidden;
            background: #000; /* Optional: adds a black background if the video doesn't load */
        }

        /* Iframe to fill the container */
        .video-container iframe {
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
        }
</style>

This is the Auction Website. The website allows the person to create an account and then create new listings and make bids on the existing ones. The user needs to specify the title, description and the starting bid. User may also optionaly chose the category or upload a picture. The main page shows all of the listing created by the user Users may bid on the items and leave comments. When the creator of the auction is closing the auction, the winner is able to see if they have won the bid. Also, by using the admin webpage the administrator may interact with the data. They can edit add and delete comments, bids, users, or auctions

This project uses django as a web framework. The backend connect to the database using django Migrations, which are then can be easily accesed by from django administration page. This project taught me a lot about django framework and improved my OOP skills in python.

GitHub link: - [Online Auction Website](https://github.com/BezboDima/Auction)

Below is the video Demonstration of the user process:
<div class="video-container">
    <iframe src="https://www.youtube.com/embed/watch?v=NbaTm5DC8f4" 
            title="YouTube video player" 
            frameborder="0" 
            allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture" 
            allowfullscreen>
    </iframe>
</div>