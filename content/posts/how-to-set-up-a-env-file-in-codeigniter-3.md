+++
title = "How to Set up a .env file in Codeigniter 3"
date = 2022-10-20T12:31:39+07:00
draft = false
tags = ["codeigniter3", "env"]
categories = ["Codeigniter"]
meta = true
+++

# Why .env?

Basically, a .env file is an easy way to load custom configuration variables that your application needs without having to modify .htaccess files or Apache/nginx virtual hosts. This means you won't have to edit any files outside the project, and all the environment variables are always set no matter how you run your project - Apache, Nginx, CLI, and even PHP's built-in webserver. It's WAY easier than all the other ways you know of to set environment variables, and you're going to love it!

# Installation

You will need to install the vlucas/phpdotenv package to use the .env file in CodeIgniter. You can install it using Composer by running the following command:

    composer require vlucas/phpdotenv

Create a .env file in the root directory of your CodeIgniter application

In the .env file, define your environment variables in the following format: VARIABLE_NAME=value. For example:

    DB_HOST=localhost
    DB_USERNAME=root
    DB_PASSWORD=password

Load the .env file in your CodeIgniter application by adding the following line to the top of your index.php file:

    $dotenv = \Dotenv\Dotenv::createImmutable(FCPATH);
    $dotenv->safeLoad();

# Usage

You can now access the environment variables in your CodeIgniter application like this:

    $host = $_ENV['DB_HOST'];
    $username = $_ENV['DB_USERNAME'];
    $password = $_ENV['DB_PASSWORD'];