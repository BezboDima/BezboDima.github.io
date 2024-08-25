---
title: "IngredientLens"
description: "Application for food recognision and recepie generation"
dateString: April 2024
draft: false
tags: ["AWS", "Python", "Hosting", "GitHub Action", "Docker", "Bash", "TypeScript", "Next.JS"]
weight: 201
cover:
    image: "/projects/ingredient-lens/IngredientLens-thumbnail.png"
---

## Intro
Ingredientlens was my final project, which concluded my undergratuate degree at Monmouth University. With the team of 4 people, we wanted to see if it would be possible to create application that recognizes the dish and its ingredients, which then generates the reciepe to follow in order to cook that dish, while still taking into account for user's preferences and allergies.

![](/projects/ingredient-lens/IngredientLens.png)

So, if you want to try the app for yourself, you can check [**IngredientLens**](https://ingredientlens.net) and create your account ot chose to be incognito and just update your own picture of food or try one of the available dishes. Once the picture is uploaded you can click on **Generate Labels**. Which will give you the labels to chose from. After your choice, click **Generate Recepie**. Then a step by step recepie will be provided.

This project is not perfect, and still requires revisions. However, me and my team are proud of the progress that we were able to achive in a small period of time. We are looking forward on improving it and potentially work on own our revised CNN to recognize more ingredients.


![](/projects/ingredient-lens/IngredientLens-diagram.png)

## Working
In this project workflow, several components are crucial for its operation. The Frontend encompasses the UI/UX design and web server functionality, powered by AWS Amplify for hosting React applications. Amplify integrates with GitHub for seamless CI/CD, allowing automatic updates to the website upon code changes. For the Mobile Frontend, React Native and Expo enable cross-platform app development, leveraging React code from the web frontend while accommodating platform-specific functionalities and testing with Expo Go.

APIs play a pivotal role in connecting the frontend with backend services. AWS API Gateway facilitates HTTP calls to Lambda functions, handling tasks like DynamoDB operations for user data and S3 uploads. The OpenAI API supplements this with advanced language models for recipe generation. Storage Units include DynamoDB for user profiles and recipe histories, and S3 for storing user-uploaded images, facilitating efficient data access across Lambda functions. Side Packages, managed through Docker containers and Lambda layers, streamline dependencies and environment setup, enhancing functionality across Lambda functions.

CI/CD processes ensure rapid updates and bug fixes through automated checks and approvals, supported by GitHub Actions for tasks like Lambda function deployment and UI updates. This comprehensive setup ensures efficient development and maintenance of the project, optimizing for scalability and performance in handling user interactions and data management.

## Final thoughts
Working on the IngredientLens project with my team has been an immensely rewarding experience. Collaborating closely with talented individuals who share a passion for innovation and problem-solving has enriched my understanding of both technology and teamwork. Throughout our journey, I've learned invaluable skills in project management, software development, and effective communication. I am grateful for the opportunity to have worked on IngredientLens, as it not only expanded my technical knowledge but also deepened my appreciation for collaborative teamwork in achieving ambitious goals.

![](/projects/ingredient-lens/IngredientLens-team.png)


## Resources
- [Final Report](/projects/ingredient-lens/final-report.pdf)
- [Ingredient Lens GitHub](https://github.com/BezboDima/IngredientLens)