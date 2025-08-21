Personal Portfolio Website

This is a personal portfolio website designed to showcase projects, skills, and provide a point of contact. It features a clean, responsive design, a dynamic typing animation, a theme switcher for changing colors and toggling between light and dark modes, and a functional contact form powered by PHPMailer.

Features

Responsive Design: The layout adapts to different screen sizes, from mobile devices to desktops.

Multiple Sections: Includes Home, About, Portfolio, and Contact sections for comprehensive information.

Typing Animation: A dynamic typing effect in the home section to display different professions or titles.

Style Switcher: Allows users to change the primary color theme and switch between light and dark modes.

Contact Form: A working PHP-based contact form that uses PHPMailer to send emails via SMTP.

Composer Integration: Manages the PHPMailer dependency using Composer.

File Structure
code
Code
download
content_copy
expand_less

├── .vscode
│   └── settings.json
├── composer.json
├── composer.lock
├── css
│   ├── skins
│   │   ├── color-1.css
│   │   ├── color-2.css
│   │   ├── color-3.css
│   │   ├── color-4.css
│   │   └── color-5.css
│   ├── style-switcher.css
│   └── style.css
├── cv
│   └── new_cv.pdf
├── images
│   ├── aeroplane.png
│   ├── food_donate.png
│   ├── icons8-portfolio-64.png
│   ├── king_space.png
│   └── portfolio
│       └── image.png
├── index.html
├── js
│   ├── script.js
│   └── style-switcher.js
├── send_email.php
└── vendor
    └── ... (Composer packages)
Setup and Installation

To get this project up and running on your local machine or web server, follow these steps.

Prerequisites

A web server that supports PHP (e.g., Apache, Nginx).

Composer installed for managing PHP dependencies.

An SMTP account (e.g., a Gmail account) to send emails from the contact form.

Installation Steps

Clone the repository:

code
Bash
download
content_copy
expand_less
IGNORE_WHEN_COPYING_START
IGNORE_WHEN_COPYING_END
git clone <repository-url>

Install dependencies:
Navigate to the project's root directory and run Composer to install PHPMailer.

code
Bash
download
content_copy
expand_less
IGNORE_WHEN_COPYING_START
IGNORE_WHEN_COPYING_END
composer install

Configure the email script:
Open the send_email.php file and update the SMTP server settings with your own credentials.

code
PHP
download
content_copy
expand_less
IGNORE_WHEN_COPYING_START
IGNORE_WHEN_COPYING_END
// Server settings
$mail->isSMTP();
$mail->Host       = 'smtp.gmail.com'; // Your SMTP server
$mail->SMTPAuth   = true;
$mail->Username   = 'your_email@gmail.com'; // Your SMTP username
$mail->Password   = 'your_gmail_app_password'; // Your Gmail App Password
$mail->SMTPSecure = 'tls';
$mail->Port       = 587;

//Recipients
$mail->setFrom($_POST['from_email'], $_POST['from_name']);
$mail->addAddress('your_email@gmail.com'); // The email address that will receive the messages

Important: For Gmail, you will need to generate an "App Password" to use here instead of your regular password. You can find instructions on how to do that in Google's help center.

Usage

After setting up the project on your web server, you can access it through your browser.

Navigation: Use the navigation links on the left-hand side to switch between the Home, About, Portfolio, and Contact sections.

Style Switcher: Click on the gear icon to open the style switcher. From there, you can select a different color theme or toggle the light/dark mode.

Contact Form: Fill out the form in the "Contact" section and click "Send Message" to send an email.

Code Overview

index.html: The main HTML file containing the structure of the entire single-page portfolio.

css/style.css: The primary stylesheet that defines the layout, responsive design, and base theme colors.

css/skins/: Contains different CSS files for the alternate color schemes available in the style switcher.

js/script.js: Handles the core interactivity, including the navigation logic for showing and hiding sections and the typing animation on the home page.

js/style-switcher.js: Manages the functionality of the style switcher, allowing for real-time theme and color changes.

send_email.php: The backend PHP script that processes the contact form data and uses the PHPMailer library to send the email.

composer.json: Defines the project's PHP dependencies (in this case, PHPMailer).

Dependencie

PHPMailer: A full-featured email creation and transfer class for PHP.

The typing animation is based on a library like Typed.js, which is included in js/script.js.
