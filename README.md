# 🍽️ Collaborative Recipe Management Portal

Welcome to the **Collaborative Recipe Management Portal** — a dynamic web application where users can create, share, and explore recipes with rich features like authentication, file uploads, social interactions, and robust authorization. Perfect for food enthusiasts, coding learners, and .NET developers alike!

---

## 📖 Table of Contents

1. [Project Overview](#project-overview)
2. [Features](#features)
3. [Data Model & Entities](#data-model--entities)
4. [User Flows](#user-flows)
5. [Entity Relationships](#entity-relationships)
6. [Tech Stack & Setup](#tech-stack--setup)
7. [Run Instructions](#run-instructions)

---

## 📚 Project Overview

The portal serves as an online hub for cooking lovers, enabling:
- **Recipe creation and sharing**
- **User registration and role-based access**
- **Engaging social features** like comments and ratings
- **File uploads** for recipe images and guides
- **Exporting organized shopping lists and reports**

Designed for learning real-world .NET Core, Entity Framework, and modern web design.

---

## ✨ Features

- **🔐 Authentication & Authorization**  
  Register, login, and manage roles (User, Moderator, Admin). Policy-based access ensures users can only edit their own recipes; moderators/admins can moderate everything.

- **📝 Recipe Management**  
  - Add, edit, delete, browse, and search recipes
  - Advanced rich-text instructions [ Optional ]
  
- **👥 User Profiles**  
  - Manage avatar, bio, and view other users' recipes
  
- **🥕 Ingredients & Categories**  
  - Dynamic ingredients with quantities/units
  - Recipes sorted into categories for easy browsing

- **📂 File Uploads**  
  - Attach multiple images or PDFs per recipe with validation

- **💬 Social Features**  
  - Comment and rate recipes
  - Bookmark favorite recipes

- **🔍 Discovery & Search**  
  - Filter by title, category, or ingredient
  - View trending and new recipes

- **📤 Report Downloads**  
  - Download individual ingredient lists or meal plans (.csv/.xls)

- **🛡️ Moderation Tools**  
  - Admin/moderator dashboards for content control  [ Future Scope ]

---

## 🗃️ Data Model & Entities

| Entity         | Fields (Sample)                       | Description                               |
|----------------|--------------------------------------|-------------------------------------------|
| Users          | Id, UserName, Email, PasswordHash     | Registered users                          |
| UserProfiles   | Id, UserId (FK), Avatar, Bio         | Profile info, one-to-one with Users       |
| Roles          | Id, Name                             | User roles (User, Moderator, Admin)       |
| Recipes        | Id, Title, Instructions, UserId, CategoryId | Recipes, each with a creator and category |
| RecipeImages   | Id, RecipeId, ImagePath              | Images or guides linked to recipes        |
| Ingredients    | Id, Name                             | Ingredient catalog                        |
| RecipeIngredients | RecipeId, IngredientId, Quantity, Unit | Relationship (with qty/unit info)       |
| Categories     | Id, Name                             | Recipe categories                         |
| Comments       | Id, RecipeId, UserId, Rating, Text   | Comments and ratings                      |
| Bookmarks      | Id, UserId, RecipeId                 | Track recipe bookmarks                    |

---

## 🧭 User Flows

**Registration/Login**
- Sign up and create a profile 👤  
- Assign default role (`User`), with elevated roles by admin

**Recipe Creation**
1. Click “Add Recipe”
2. Enter details, select category, add ingredients (with quantities/units)
3. Upload images or guides
4. Save and publish 🎉

**Browsing & Bookmarking**
- Search/filter recipes by category, ingredient, or title
- Bookmark your favorites ⭐

**Commenting & Rating**
- Leave feedback and rate each recipe  
- View all comments and average rating

**File Upload/Download**
- Upload multiple images/PDFs per recipe
- Download a recipe’s ingredients list as CSV/XLS 🗂️

**Moderation**
- Admins/Moderators can edit/delete any recipe/comment, manage flagged content  
  
---

## 🔗 Entity Relationships

- **1:1** — User ⇄ UserProfile
- **1:N** — User ⇄ Recipes, Category ⇄ Recipes, Recipe ⇄ RecipeImages, Recipe ⇄ Comments
- **N:N** — Recipe ⇄ Ingredients (via RecipeIngredients), User ⇄ Bookmarks

Diagram (textual):  
- *Users* ↔ *UserProfiles*  
- *Users* → *Recipes*  
- *Categories* → *Recipes*  
- *Recipes* → *RecipeImages*, *Comments*  
- *Recipes* ⇄ *Ingredients* (via RecipeIngredients)  
- *Users* ⇄ *Bookmarks*

---

## 🛠️ Tech Stack & Setup

- **Back End:** ASP.NET Core MVC / Razor Pages
- **ORM:** Entity Framework Core (Code First)
- **Authentication:** ASP.NET Core Identity
- **Front End:** Razor Views (with Bootstrap/Tailwind CSS)
- **File Storage:** Local initially; optional cloud for scale
- **Reporting:** CsvHelper or EPPlus for exports
- **Database:** SQL Server Express/LocalDB (dev)
- **Testing:** xUnit or NUnit  [ Future Scope ]
- **Deployment:** Easily containerized or deployed to Azure [Future Scope ]

---

## 🏁 Run Instructions

TODO : 💻

---

## 🎁 Nuget libraries 

TODO : Keep adding the packages here ⏬
---

> **Enjoy cooking, coding, and collaborating! 🍲🖥️**


