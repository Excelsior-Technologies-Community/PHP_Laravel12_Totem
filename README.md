# PHP_Laravel12_Totem


## Project Description

PHP_Laravel12_Totem is a Laravel 12 based web application that integrates the Totem package to provide a graphical dashboard for managing Laravel scheduled tasks.

Totem allows developers and administrators to create, edit, monitor, and manage scheduled jobs directly from a user-friendly web interface instead of writing all scheduler code manually.

This project demonstrates how to install, configure, and use the Totem scheduler dashboard in Laravel 12 with authentication security.


## Project Purpose

The main purpose of this project is to:

- Provide a web interface to manage Laravel scheduled tasks

- Monitor task execution status

- Create and edit scheduler tasks dynamically

- Improve task management without editing code manually

- Learn integration of third-party packages in Laravel 12


## Features

- Totem Scheduler Dashboard UI
- Create Scheduled Tasks from Web Interface
- Edit and Delete Scheduled Tasks
- Enable / Disable Scheduler Tasks
- View Task Logs and Execution Status
- Authentication using Laravel Breeze
- Secure Access to Totem Dashboard
- No manual scheduler coding required


## What is Totem?

Totem is a Laravel package that provides:

- Web dashboard for scheduler

- Create scheduled tasks

- Edit scheduled tasks

- View task logs

- Enable / Disable tasks

- Monitor task execution


## Technologies Used

- PHP 8.2+

- Laravel 12

- MySQL

- Laravel Totem package

- Laravel Breeze (Authentication)

- Composer

- Node.js & NPM

- Bootstrap / Blade UI



---

#  Laravel 12 + Totem Setup (Final Verified)

---


## STEP 1: Create Laravel 12 Project

### Open terminal / CMD and run:

```
composer create-project laravel/laravel PHP_Laravel12_Totem "12.*"

```

### Go inside project:

```
cd PHP_Laravel12_Totem

```

#### Explanation:

- composer create-project → creates a new Laravel project

- laravel/laravel → official Laravel package

- PHP_Laravel12_Totem → project folder name

- "12.*" → installs Laravel version 12

- Result: A fresh Laravel 12 project is created.




## STEP 2: Database Setup (Required for Totem)


### Open .env and set:

```
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=laravel12_totem
DB_USERNAME=root
DB_PASSWORD=

```

### Create database in MySQL / phpMyAdmin:

```
Database name: laravel12_totem

```




## STEP 3: Studio Laravel Totem package

### Totem is available as studio/laravel‑totem

```
composer require studio/laravel-totem

```

#### Explanation:

This installs Totem package.

Totem is a Laravel scheduler dashboard.




## STEP 4: Publish Totem Files

### Run:

```
php artisan vendor:publish

```

### Select the number for:

```
Studio\Totem\TotemServiceProvider

```

#### Explanation:

This copies Totem files into your project.



## STEP 5: Run Migrations

### Run:

```
php artisan migrate

```

Totem tables will be created (totem_jobs, totem_tasks, etc.) — this is required for the dashboard.



## STEP 6: Protect Totem UI (Optional – Recommended)

To prevent random users from accessing the scheduler dashboard, set authentication.

### Install Laravel Breeze:

```

composer require laravel/breeze --dev

php artisan breeze:install

npm install

npm run dev

php artisan migrate

```

Now you have auth routes (login/register)





## STEP 7: Totem Routes (Automatic)


- Totem routes are automatically registered by the Totem service provider.

- You DO NOT need to add any routes manually.

- Totem dashboard URL:

```
http://127.0.0.1:8000/totem

```

- To protect the dashboard, install Laravel Breeze authentication.





## STEP 8:Run the App

### Start server:

```
php artisan serve

```

### Now open in browser:

```
http://127.0.0.1:8000/totem

```


## STEP 9: Login to Access Totem Dashboard

### Open browser:

```
http://127.0.0.1:8000/login

```
Register a new user or login.

### After login, open:

```
http://127.0.0.1:8000/totem

```



## STEP 10: Run Laravel Scheduler

Totem manages tasks, but Laravel scheduler must be running.

### Run this command:

```
php artisan schedule:work

```

This will execute scheduled tasks automatically.



## So you can see this type Output:

### Register Page:


<img width="1917" height="965" alt="Screenshot 2026-02-16 102439" src="https://github.com/user-attachments/assets/7caa4352-90da-453e-8492-52f8f20a9a90" />


### Login Page:


<img width="1919" height="959" alt="Screenshot 2026-02-16 102521" src="https://github.com/user-attachments/assets/9b5f9e90-f0f1-4965-b74a-5b3add9892b4" />


### Task List:


<img width="1918" height="963" alt="image" src="https://github.com/user-attachments/assets/a6515125-de63-4667-88e1-5e77a2c02ede" />


### Task Create:


<img width="1919" height="966" alt="Screenshot 2026-02-15 114453" src="https://github.com/user-attachments/assets/d69ab5e5-ea46-4c43-9517-80db38f1ecab" />

After create:

<img width="1919" height="966" alt="Screenshot 2026-02-15 114439" src="https://github.com/user-attachments/assets/436336f2-ebaa-4a5a-8cdd-869347b7026f" />


### Task Details:


<img width="1919" height="960" alt="Screenshot 2026-02-15 114632" src="https://github.com/user-attachments/assets/16309506-e233-42b9-8f3c-1c19af1fd086" />


### Task Edit:


<img width="1919" height="964" alt="Screenshot 2026-02-15 114650" src="https://github.com/user-attachments/assets/1e83bb15-263a-4e45-821c-f2b541b81f9a" />

After Edit:

<img width="1919" height="964" alt="Screenshot 2026-02-15 114659" src="https://github.com/user-attachments/assets/b5e037df-6a55-486d-9898-bfccee8f0f35" />


### Artisan Command to view scheduled tasks:


<img width="1470" height="308" alt="Screenshot 2026-02-15 114811" src="https://github.com/user-attachments/assets/430f814d-d139-48a2-b4dd-385fc2f6d6ec" />


---

# Project Folder Structure:

```


PHP_Laravel12_Totem/
│
├── app/
│   ├── Console/
│   ├── Http/
│   └── Models/
│
├── bootstrap/
│
├── config/
│   └── totem.php
│
├── database/
│   ├── migrations/
│   │   ├── create_users_table.php
│   │   ├── create_totem_tasks_table.php
│   │   ├── create_totem_jobs_table.php
│   │   └── create_totem_logs_table.php
│
├── public/
│
├── resources/
│   └── views/
│
├── routes/
│   └── web.php
│
├── vendor/
│   └── studio/
│       └── totem/
│
├── .env
├── artisan
├── composer.json

```
