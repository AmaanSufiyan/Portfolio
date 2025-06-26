<!DOCTYPE html>
<html lang="en" data-theme="light">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Amaan Ahamed </title>
    <link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.4.0/css/all.min.css">
    <link rel="preconnect" href="https://fonts.googleapis.com">
    <link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
    <link href="https://fonts.googleapis.com/css2?family=Poppins:wght@300;400;500;600;700&family=Roboto:wght@300;400;500;700&display=swap" rel="stylesheet">
    <style>
        :root {
            /* Light Mode Colors */
            --primary-color: #5e60ce;
            --secondary-color: #5390d9;
            --text-color: #2b2d42;
            --light-text: #6c757d;
            --bg-color: #f8f9fa;
            --card-bg: #ffffff;
            --accent: #7400b8;
            --gradient-start: #5e60ce;
            --gradient-end: #64dfdf;
            --header-bg: rgba(255, 255, 255, 0.95);
            --shadow-color: rgba(0, 0, 0, 0.1);
            --shadow-color-strong: rgba(0, 0, 0, 0.2);
            --border-color: #e9ecef;
            --footer-text: #ffffff;
            --toggle-bg: #e9ecef;
            --toggle-circle: #ffffff;
            --transition: all 0.3s ease-in-out;
        }

        [data-theme="dark"] {
            /* Dark Mode Colors */
            --primary-color: #9d4edd;
            --secondary-color: #7b2cbf;
            --text-color: #e6e6e6;
            --light-text: #adb5bd;
            --bg-color: #121212;
            --card-bg: #1e1e1e;
            --accent: #c77dff;
            --gradient-start: #9d4edd;
            --gradient-end: #5390d9;
            --header-bg: rgba(30, 30, 30, 0.95);
            --shadow-color: rgba(0, 0, 0, 0.3);
            --shadow-color-strong: rgba(0, 0, 0, 0.5);
            --border-color: #333333;
            --footer-text: #e6e6e6;
            --toggle-bg: #333333;
            --toggle-circle: #9d4edd;
        }
        
        * {
            margin: 0;
            padding: 0;
            box-sizing: border-box;
        }
        
        html {
            scroll-behavior: smooth;
        }
        
        body {
            font-family: 'Poppins', sans-serif;
            background-color: var(--bg-color);
            color: var(--text-color);
            line-height: 1.6;
            overflow-x: hidden;
            transition: background-color 0.3s ease, color 0.3s ease;
        }
        
        a {
            text-decoration: none;
            color: inherit;
        }
        
        ul {
            list-style: none;
        }
        
        .container {
            max-width: 1200px;
            margin: 0 auto;
            padding: 0 20px;
        }
        
        /* Header & Navigation */
        header {
            position: fixed;
            top: 0;
            left: 0;
            width: 100%;
            background: var(--header-bg);
            box-shadow: 0 2px 10px var(--shadow-color);
            z-index: 1000;
            backdrop-filter: blur(10px);
            transition: var(--transition);
        }
        
        header.scrolled {
            padding: 10px 0;
        }
        
        nav {
            display: flex;
            justify-content: space-between;
            align-items: center;
            padding: 20px 0;
        }
        
        .logo {
            font-size: 1.5rem;
            font-weight: 700;
            background: linear-gradient(to right, var(--gradient-start), var(--gradient-end));
            -webkit-background-clip: text;
            background-clip: text;
            -webkit-text-fill-color: transparent;
            transition: var(--transition);
        }
        
        .logo:hover {
            transform: scale(1.05);
        }
        
        .nav-links {
            display: flex;
            gap: 30px;
        }
        
        .nav-links a {
            font-weight: 500;
            position: relative;
            transition: var(--transition);
        }
        
        .nav-links a::after {
            content: '';
            position: absolute;
            width: 0;
            height: 2px;
            bottom: -5px;
            left: 0;
            background: linear-gradient(to right, var(--gradient-start), var(--gradient-end));
            transition: var(--transition);
        }
        
        .nav-links a:hover {
            color: var(--primary-color);
        }
        
        .nav-links a:hover::after {
            width: 100%;
        }
        
        .theme-toggle {
            position: relative;
            width: 50px;
            height: 24px;
            background-color: var(--toggle-bg);
            border-radius: 30px;
            cursor: pointer;
            display: flex;
            align-items: center;
            justify-content: space-between;
            padding: 0 5px;
            margin-left: 15px;
            transition: var(--transition);
        }
        
        .theme-toggle i {
            font-size: 14px;
            color: var(--text-color);
            z-index: 1;
        }
        
        .theme-toggle::after {
            content: '';
            position: absolute;
            width: 20px;
            height: 20px;
            background-color: var(--toggle-circle);
            border-radius: 50%;
            left: 2px;
            transition: var(--transition);
        }
        
        [data-theme="dark"] .theme-toggle::after {
            transform: translateX(26px);
        }
        
        .hamburger {
            display: none;
            cursor: pointer;
            font-size: 1.5rem;
        }
        
        /* Hero Section */
        .hero {
            min-height: 100vh;
            display: flex;
            align-items: center;
            position: relative;
            overflow: hidden;
            padding: 100px 0;
        }
        
        .hero-content {
            display: flex;
            align-items: center;
            justify-content: space-between;
            width: 100%;
            gap: 30px;
        }
        
        .hero-text {
            flex: 1;
            z-index: 1;
        }
        
        .hero-images {
            flex: 1;
            display: flex;
            justify-content: flex-end;
            position: relative;
            z-index: 1;
        }
        
        .profile-images {
            position: relative;
            width: 100%;
            height: 400px;
            perspective: 1000px;
            margin-bottom: 20px;
        }
        
        .profile-image {
            position: absolute;
            width: 300px;
            height: 300px;
            object-fit: cover;
            border-radius: 20px;
            box-shadow: 0 10px 30px var(--shadow-color);
            transition: transform 0.8s ease-in-out, opacity 0.8s ease-in-out;
            transform-style: preserve-3d;
            backface-visibility: hidden;
            top: 50%;
            left: 50%;
            transform: translate(-50%, -50%);
        }
        
        .profile-formal {
            transform: translate(-50%, -50%) rotateY(0deg);
            z-index: 2;
        }
        
        .profile-casual {
            transform: translate(-50%, -50%) rotateY(180deg);
            z-index: 1;
        }
        
        .profile-images:hover .profile-formal {
            transform: translate(-50%, -50%) rotateY(180deg);
        }
        
        .profile-images:hover .profile-casual {
            transform: translate(-50%, -50%) rotateY(0deg);
        }
        
        .image-indicator {
            position: absolute;
            bottom: 10px;
            left: 50%;
            transform: translateX(-50%);
            font-size: 0.8rem;
            color: var(--light-text);
            background-color: var(--card-bg);
            padding: 5px 15px;
            border-radius: 20px;
            box-shadow: 0 5px 15px var(--shadow-color);
            transition: var(--transition);
            opacity: 0;
        }
        
        .profile-images:hover .image-indicator {
            opacity: 1;
        }
        
        .greeting {
            font-size: 1.2rem;
            color: var(--light-text);
            margin-bottom: 10px;
            animation: fadeUp 1s ease-out forwards;
        }
        
        .hero-name {
            font-size: 3.5rem;
            font-weight: 700;
            margin-bottom: 10px;
            background: linear-gradient(to right, var(--gradient-start), var(--gradient-end));
            -webkit-background-clip: text;
            background-clip: text;
            -webkit-text-fill-color: transparent;
            animation: fadeUp 1s 0.2s ease-out forwards;
            opacity: 0;
            transform: translateY(20px);
        }
        
        .hero-title {
            font-size: 1.8rem;
            font-weight: 500;
            color: var(--secondary-color);
            margin-bottom: 20px;
            animation: fadeUp 1s 0.4s ease-out forwards;
            opacity: 0;
            transform: translateY(20px);
        }
        
        .hero-description {
            font-size: 1.1rem;
            max-width: 600px;
            margin-bottom: 30px;
            animation: fadeUp 1s 0.6s ease-out forwards;
            opacity: 0;
            transform: translateY(20px);
        }
        
        .social-links {
            display: flex;
            gap: 15px;
            margin-top: 30px;
            animation: fadeUp 1s 0.8s ease-out forwards;
            opacity: 0;
            transform: translateY(20px);
        }
        
        .social-links a {
            display: flex;
            align-items: center;
            justify-content: center;
            width: 40px;
            height: 40px;
            border-radius: 50%;
            background: var(--card-bg);
            color: var(--primary-color);
            font-size: 1.2rem;
            box-shadow: 0 5px 15px var(--shadow-color);
            transition: var(--transition);
        }
        
        .social-links a:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px var(--shadow-color-strong);
            background: linear-gradient(to right, var(--gradient-start), var(--gradient-end));
            color: white;
        }
        
        .cta-btn {
            display: inline-block;
            padding: 12px 30px;
            background: linear-gradient(to right, var(--gradient-start), var(--gradient-end));
            color: white;
            font-weight: 500;
            border-radius: 30px;
            box-shadow: 0 5px 15px var(--shadow-color);
            transition: var(--transition);
            animation: fadeUp 1s 1s ease-out forwards;
            opacity: 0;
            transform: translateY(20px);
        }
        
        .cta-btn:hover {
            transform: translateY(-5px);
            box-shadow: 0 10px 20px var(--shadow-color-strong);
        }
        
        .scroll-down {
            position: absolute;
            bottom: 30px;
            left: 50%;
            transform: translateX(-50%);
            animation: bounce 2s infinite;
            color: var(--primary-color);
            font-size: 1.5rem;
            cursor: pointer;
        }
        
        @keyframes bounce {
            0%, 20%, 50%, 80%, 100% {
                transform: translateY(0) translateX(-50%);
            }
            40% {
                transform: translateY(-20px) translateX(-50%);
            }
            60% {
                transform: translateY(-10px) translateX(-50%);
            }
        }
        
        @keyframes fadeUp {
            to {
                opacity: 1;
                transform: translateY(0);
            }
        }
        
        /* Section Styling */
        section {
            padding: 100px 0;
        }
        
        .section-title {
            text-align: center;
            margin-bottom: 60px;
            position: relative;
        }
        
        .section-title h2 {
            font-size: 2.5rem;
            display: inline-block;
            background: linear-gradient(to right, var(--gradient-start), var(--gradient-end));
            -webkit-background-clip: text;
            background-clip: text;
            -webkit-text-fill-color: transparent;
            margin-bottom: 15px;
        }
        
        .section-title p {
            color: var(--light-text);
            max-width: 600px;
            margin: 0 auto;
        }
        
        .section-title::after {
            content: '';
            position: absolute;
            width: 80px;
            height: 3px;
            background: linear-gradient(to right, var(--gradient-start), var(--gradient-end));
            bottom: -15px;
            left: 50%;
            transform: translateX(-50%);
        }
        
        /* About Section */
        .about-content {
            display: flex;
            align-items: center;
            gap: 50px;
        }
        
        .about-image {
            flex: 1;
            position: relative;
        }
        
        .about-image img {
            width: 100%;
            border-radius: 20px;
            box-shadow: 0 10px 30px var(--shadow-color);
            transition: var(--transition);
        }
        
        .about-image::before {
            content: '';
            position: absolute;
            width: 100%;
            height: 100%;
            border: 3px solid var(--primary-color);
            border-radius: 20px;
            top: 15px;
            left: 15px;
            z-index: -1;
        }
        
        .about-text {
            flex: 1;
        }
        
        .about-text p {
            margin-bottom: 20px;
        }
        
        /* Skills Section */
        .skills-container {
            display: flex;
            flex-wrap: wrap;
            gap: 30px;
            justify-content: center;
        }
        
        .skill-category {
            flex: 1;
            min-width: 300px;
            max-width: 500px;
            background: var(--card-bg);
            border-radius: 15px;
            padding: 30px;
            box-shadow: 0 5px 20px var(--shadow-color);
            transition: var(--transition);
        }
        
        .skill-category:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px var(--shadow-color-strong);
        }
        
        .skill-category h3 {
            margin-bottom: 20px;
            font-size: 1.4rem;
            color: var(--primary-color);
            position: relative;
            display: inline-block;
        }
        
        .skill-category h3::after {
            content: '';
            position: absolute;
            width: 50px;
            height: 2px;
            background: linear-gradient(to right, var(--gradient-start), var(--gradient-end));
            bottom: -10px;
            left: 0;
        }
        
        .skill-item {
            margin-bottom: 15px;
        }
        
        .skill-name {
            display: flex;
            justify-content: space-between;
            margin-bottom: 5px;
        }
        
        .skill-bar {
            height: 8px;
            background: var(--border-color);
            border-radius: 10px;
            overflow: hidden;
        }
        
        .skill-progress {
            height: 100%;
            background: linear-gradient(to right, var(--gradient-start), var(--gradient-end));
            border-radius: 10px;
            width: 0;
            transition: width 1.5s ease-out;
        }
        
        /* Experience Section */
        .timeline {
            position: relative;
            max-width: 800px;
            margin: 0 auto;
        }
        
        .timeline::after {
            content: '';
            position: absolute;
            width: 3px;
            background: linear-gradient(to bottom, var(--gradient-start), var(--gradient-end));
            top: 0;
            bottom: 0;
            left: 50%;
            transform: translateX(-50%);
        }
        
        .timeline-item {
            padding: 10px 40px;
            position: relative;
            width: 50%;
            animation: fadeIn 0.5s linear forwards;
            opacity: 0;
        }
        
        .timeline-item:nth-child(odd) {
            left: 0;
        }
        
        .timeline-item:nth-child(even) {
            left: 50%;
        }
        
        .timeline-content {
            background: var(--card-bg);
            padding: 30px;
            border-radius: 15px;
            box-shadow: 0 5px 20px var(--shadow-color);
            transition: var(--transition);
        }
        
        .timeline-content:hover {
            transform: translateY(-5px);
            box-shadow: 0 15px 30px var(--shadow-color-strong);
        }
        
        .timeline-date {
            position: absolute;
            top: 18px;
            font-size: 0.9rem;
            font-weight: 600;
            color: var(--primary-color);
            background: var(--card-bg);
            padding: 5px 15px;
            border-radius: 20px;
            box-shadow: 0 5px 15px var(--shadow-color);
        }
        
        .timeline-item:nth-child(odd) .timeline-date {
            right: -150px;
        }
        
        .timeline-item:nth-child(even) .timeline-date {
            left: -150px;
        }
        
        .timeline-item::after {
            content: '';
            position: absolute;
            width: 25px;
            height: 25px;
            background: linear-gradient(to right, var(--gradient-start), var(--gradient-end));
            border-radius: 50%;
            top: 20px;
            z-index: 1;
        }
        
        .timeline-item:nth-child(odd)::after {
            right: -12px;
        }
        
        .timeline-item:nth-child(even)::after {
            left: -13px;
        }
        
        .timeline-title {
            margin-bottom: 10px;
            font-size: 1.2rem;
            color: var(--primary-color);
        }
        
        .timeline-position {
            font-weight: 500;
            margin-bottom: 15px;
            color: var(--secondary-color);
        }
        
        /* Education Section */
        .education-cards {
            display: flex;
            flex-wrap: wrap;
            gap: 30px;
            justify-content: center;
        }
        
        .education-card {
            flex: 1;
            min-width: 300px;
            max-width: 380px;
            background: var(--card-bg);
            border-radius: 15px;
            padding: 30px;
            box-shadow: 0 5px 20px var(--shadow-color);
            transition: var(--transition);
            position: relative;
            overflow: hidden;
        }
        
        .education-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px var(--shadow-color-strong);
        }
        
        .education-card::before {
            content: '';
            position: absolute;
            width: 100px;
            height: 100px;
            background: linear-gradient(to right, var(--gradient-start), var(--gradient-end));
            border-radius: 50%;
            top: -50px;
            right: -50px;
            opacity: 0.1;
            transition: var(--transition);
        }
        
        .education-card:hover::before {
            transform: scale(1.5);
        }
        
        .education-year {
            display: inline-block;
            padding: 5px 15px;
            background: linear-gradient(to right, var(--gradient-start), var(--gradient-end));
            color: white;
            border-radius: 20px;
            font-size: 0.9rem;
            margin-bottom: 15px;
        }
        
        .education-degree {
            font-size: 1.2rem;
            font-weight: 600;
            margin-bottom: 10px;
            color: var(--primary-color);
        }
        
        .education-school {
            color: var(--secondary-color);
            margin-bottom: 15px;
        }
        
        /* Projects Section */
        .projects-container {
            display: grid;
            grid-template-columns: repeat(auto-fill, minmax(320px, 1fr));
            gap: 30px;
        }
        
        .project-card {
            background: var(--card-bg);
            border-radius: 15px;
            overflow: hidden;
            box-shadow: 0 5px 20px var(--shadow-color);
            transition: var(--transition);
        }
        
        .project-card:hover {
            transform: translateY(-10px);
            box-shadow: 0 15px 30px var(--shadow-color-strong);
        }
        
        .project-image {
            height: 200px;
            background: linear-gradient(to right, var(--gradient-start), var(--gradient-end));
            display: flex;
            align-items: center;
            justify-content: center;
            color: white;
            font-size: 3rem;
        }
        
        .project-content {
            padding: 20px;
        }
        
        .project-title {
            font-size: 1.2rem;
            font-weight: 600;
            margin-bottom: 10px;
            color: var(--primary-color);
        }
        
        .project-tech {
            display: flex;
            gap: 10px;
            margin-bottom: 15px;
            flex-wrap: wrap;
        }
        
        .tech-tag {
            padding: 5px 10px;
            background: var(--border-color);
            border-radius: 5px;
            font-size: 0.8rem;
            color: var(--secondary-color);
        }
        
        /* Contact Section */
        .contact {
            background: linear-gradient(rgba(var(--bg-color-rgb), 0.9), rgba(var(--bg-color-rgb), 0.9)), url('https://public.youware.com/users-website-assets/prod/2e1d3b4f-2f80-4c2f-b2fe-c654203b7bb7/gf428e4b9da47c34e22b6c3f5babc845d58d33de681fd198e3f3342a41a44a933da30c972f5b579324c73a87e8e842ad6b9789dde214b505c20d6c9d95d3db911_640.png');
            background-size: cover;
            background-position: center;
            background-attachment: fixed;
            position: relative;
        }

        .contact::before {
            content: '';
            position: absolute;
            top: 0;
            left: 0;
            width: 100%;
            height: 100%;
            background-color: var(--bg-color);
            opacity: 0.9;
            z-index: 0;
        }
        
        .contact .container {
            position: relative;
            z-index: 1;
        }
        
        .contact-content {
            display: flex;
            flex-wrap: wrap;
            gap: 50px;
        }
        
        .contact-info {
            flex: 1;
            min-width: 300px;
        }
        
        .contact-form {
            flex: 1;
            min-width: 300px;
        }
        
        .contact-info h3, .contact-form h3 {
            font-size: 1.5rem;
            margin-bottom: 30px;
            color: var(--primary-color);
        }
        
        .contact-item {
            display: flex;
            gap: 15px;
            margin-bottom: 25px;
            align-items: flex-start;
        }
        
        .contact-item i {
            width: 40px;
            height: 40px;
            background: linear-gradient(to right, var(--gradient-start), var(--gradient-end));
            color: white;
            display: flex;
            align-items: center;
            justify-content: center;
            border-radius: 50%;
            font-size: 1rem;
        }
        
        .contact-text h4 {
            font-size: 1.1rem;
            margin-bottom: 5px;
        }
        
        .form-group {
            margin-bottom: 20px;
        }
        
        .form-control {
            width: 100%;
            padding: 12px 15px;
            border: 1px solid var(--border-color);
            border-radius: 8px;
            font-family: 'Poppins', sans-serif;
            transition: var(--transition);
            background-color: var(--card-bg);
            color: var(--text-color);
        }
        
        .form-control:focus {
            outline: none;
            border-color: var(--primary-color);
            box-shadow: 0 0 0 3px rgba(94, 96, 206, 0.2);
        }
        
        textarea.form-control {
            resize: vertical;
            min-height: 150px;
        }
        
        /* Footer */
        footer {
            background: linear-gradient(to right, var(--gradient-start), var(--gradient-end));
            color: var(--footer-text);
            padding: 50px 0 20px;
            text-align: center;
        }
        
        .footer-logo {
            font-size: 2rem;
            font-weight: 700;
            margin-bottom: 20px;
        }
        
        .footer-social {
            display: flex;
            justify-content: center;
            gap: 20px;
            margin-bottom: 30px;
        }
        
        .footer-social a {
            width: 40px;
            height: 40px;
            background: rgba(255, 255, 255, 0.1);
            border-radius: 50%;
            display: flex;
            align-items: center;
            justify-content: center;
            transition: var(--transition);
        }
        
        .footer-social a:hover {
            background: rgba(255, 255, 255, 0.2);
            transform: translateY(-5px);
        }
        
        .footer-nav {
            display: flex;
            justify-content: center;
            flex-wrap: wrap;
            gap: 20px;
            margin-bottom: 30px;
        }
        
        .footer-nav a {
            transition: var(--transition);
        }
        
        .footer-nav a:hover {
            color: rgba(255, 255, 255, 0.8);
        }
        
        .copyright {
            font-size: 0.9rem;
            opacity: 0.8;
        }
        
        /* Responsive */
        @media (max-width: 992px) {
            .hero-content {
                flex-direction: column-reverse;
                text-align: center;
                gap: 50px;
            }
            
            .hero-images {
                justify-content: center;
            }
            
            .profile-images {
                height: 300px;
            }
            
            .profile-image {
                width: 250px;
                height: 250px;
            }
            
            .social-links {
                justify-content: center;
            }
            
            .about-content {
                flex-direction: column;
                text-align: center;
            }
            
            .about-image {
                max-width: 500px;
                margin: 0 auto;
            }
            
            .timeline::after {
                left: 31px;
            }
            
            .timeline-item {
                width: 100%;
                padding-left: 70px;
                padding-right: 25px;
            }
            
            .timeline-item:nth-child(even) {
                left: 0;
            }
            
            .timeline-date {
                position: relative;
                right: auto !important;
                left: auto !important;
                top: auto;
                display: inline-block;
                margin-bottom: 15px;
            }
            
            .timeline-item::after {
                left: 18px !important;
            }
        }
        
        @media (max-width: 768px) {
            .nav-links {
                position: fixed;
                top: 0;
                right: -100%;
                width: 70%;
                height: 100vh;
                background: var(--card-bg);
                flex-direction: column;
                align-items: center;
                justify-content: center;
                transition: var(--transition);
                box-shadow: -5px 0 15px var(--shadow-color);
            }
            
            .nav-links.active {
                right: 0;
            }
            
            .hamburger {
                display: block;
                z-index: 1001;
            }
            
            .hero-name {
                font-size: 2.5rem;
            }
            
            .hero-title {
                font-size: 1.5rem;
            }
            
            .section-title h2 {
                font-size: 2rem;
            }
        }
    </style>
</head>
<body>
    <!-- Header & Navigation -->
    <header id="header">
        <div class="container">
            <nav>
                <a href="#" class="logo">Amaan.dev</a>
                <div class="nav-links">
                    <a href="#about">About</a>
                    <a href="#skills">Skills</a>
                    <a href="#experience">Experience</a>
                    <a href="#education">Education</a>
                    <a href="#projects">Projects</a>
                    <a href="#contact">Contact</a>
                </div>
                <div class="theme-toggle" id="theme-toggle">
                    <i class="fas fa-sun"></i>
                    <i class="fas fa-moon"></i>
                </div>
                <div class="hamburger">
                    <i class="fas fa-bars"></i>
                </div>
            </nav>
        </div>
    </header>

    <!-- Hero Section -->
    <section class="hero" id="home">
        <div class="container">
            <div class="hero-content">
                <div class="hero-text">
                    <div class="greeting">Hello, I'm</div>
                    <h1 class="hero-name">Amaan Ahamed</h1>
                    <h2 class="hero-title">Web Developer & UI/UX Designer</h2>
                    <p class="hero-description">
                        A highly motivated and detail-oriented software engineering student with a passion for web development and strong foundation in front-end and UI/UX technologies.
                    </p>
                    <a href="#contact" class="cta-btn">Get In Touch</a>
                    <div class="social-links">
                        <a href="https://github.com/AmaanSufiyan" target="_blank"><i class="fab fa-github"></i></a>
                        <a href="https://www.linkedin.com/in/amaan-ahamed-1ab9b5243/" target="_blank"><i class="fab fa-linkedin-in"></i></a>
                        <a href="mailto:ahamed.amaan@outlook.com"><i class="fas fa-envelope"></i></a>
                        <a href="tel:+94755357739"><i class="fas fa-phone"></i></a>
                    </div>
                </div>
                <div class="hero-images">
                    <div class="profile-images">
                        <img src="IMG_0988.JPG" alt="Amaan Ahamed Formal" class="profile-image profile-formal">
                        <img src="DSC_4001.JPG" alt="Amaan Ahamed Casual" class="profile-image profile-casual">
                        <div class="image-indicator">Hover to see more</div>
                    </div>
                </div>
            </div>
        </div>
        <a href="#about" class="scroll-down">
            <i class="fas fa-chevron-down"></i>
        </a>
    </section>

    <!-- About Section -->
    <section id="about" class="about">
        <div class="container">
            <div class="section-title">
                <h2>About Me</h2>
                <p>Get to know me better</p>
            </div>
            <div class="about-content">
                <div class="about-image">
                    <img src="img0087.jpeg" alt="About Amaan">
                </div>
                <div class="about-text">
                    <p>
                        I am a passionate web developer and UI/UX designer currently pursuing a degree in Software Engineering. With a strong foundation in front-end technologies and a keen eye for design, I create intuitive and engaging digital experiences.
                    </p>
                    <p>
                        My journey in technology began with a curiosity about how websites work, which led me to explore various programming languages and design principles. Today, I combine technical skills with creative thinking to build solutions that are both functional and aesthetically pleasing.
                    </p>
                    <p>
                        I'm constantly learning and exploring new technologies to stay at the forefront of web development trends. Currently, I'm seeking an internship opportunity to apply and enhance my skills in a dynamic and innovative environment.
                    </p>
                    <a href="#contact" class="cta-btn">Let's Connect</a>
                </div>
            </div>
        </div>
    </section>

    <!-- Skills Section -->
    <section id="skills" class="skills">
        <div class="container">
            <div class="section-title">
                <h2>My Skills</h2>
                <p>What I bring to the table</p>
            </div>
            <div class="skills-container">
                <div class="skill-category">
                    <h3>Technical Skills</h3>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>HTML/CSS</span>
                            <span>90%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 90%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>JavaScript</span>
                            <span>75%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 75%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>Figma</span>
                            <span>85%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 85%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>Android Studio</span>
                            <span>70%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 70%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>React</span>
                            <span>75%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 75%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>Java</span>
                            <span>80%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 80%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>Spring Boot</span>
                            <span>75%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 75%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>MySQL</span>
                            <span>80%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 80%"></div>
                        </div>
                    </div>
                </div>
                <div class="skill-category">
                    <h3>Soft Skills</h3>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>Team Work</span>
                            <span>95%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 95%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>Leadership</span>
                            <span>85%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 85%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>Communication</span>
                            <span>90%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 90%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>Problem Solving</span>
                            <span>92%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 92%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>Time Management</span>
                            <span>88%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 88%"></div>
                        </div>
                    </div>
                </div>
                <div class="skill-category">
                    <h3>Languages</h3>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>English</span>
                            <span>95%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 95%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>Tamil</span>
                            <span>98%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 98%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>Sinhala</span>
                            <span>90%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 90%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>Arabic</span>
                            <span>60%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 60%"></div>
                        </div>
                    </div>
                    <div class="skill-item">
                        <div class="skill-name">
                            <span>Japanese</span>
                            <span>45%</span>
                        </div>
                        <div class="skill-bar">
                            <div class="skill-progress" style="width: 45%"></div>
                        </div>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Experience Section -->
    <section id="experience" class="experience">
        <div class="container">
            <div class="section-title">
                <h2>Experience</h2>
                <p>My professional journey</p>
            </div>
            <div class="timeline">
                <div class="timeline-item">
                    <div class="timeline-date">2024</div>
                    <div class="timeline-content">
                        <h3 class="timeline-title">Karaama Trading Company</h3>
                        <div class="timeline-position">Products Detailing & Quality Checker</div>
                        <p>
                            Managed product detailing and quality control processes, ensuring all products met company standards before distribution.
                        </p>
                    </div>
                </div>
                <div class="timeline-item">
                    <div class="timeline-date">2023 - Present</div>
                    <div class="timeline-content">
                        <h3 class="timeline-title">Freelancer</h3>
                        <div class="timeline-position">Web Developer & Designer</div>
                        <p>
                            Providing graphic design services including logo design and advertisement creation on Fiverr. Writing professional CVs, cover letters, and resumes. Managing e-commerce operations on eBay and completing micro tasks on various platforms.
                        </p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Education Section -->
    <section id="education" class="education">
        <div class="container">
            <div class="section-title">
                <h2>Education</h2>
                <p>My academic background</p>
            </div>
            <div class="education-cards">
                <div class="education-card">
                    <div class="education-year">2022 - Present</div>
                    <h3 class="education-degree">Higher National Diploma in Information Technology</h3>
                    <div class="education-school">Sliit City Uni - Kollupitiya</div>
                    <p>
                        Currently pursuing a degree focused on software engineering, web development, and information systems.
                    </p>
                </div>
                <div class="education-card">
                    <div class="education-year">2018 - 2021</div>
                    <h3 class="education-degree">G.C.E Advanced Level</h3>
                    <div class="education-school">Madina National College - Madawala</div>
                    <p>
                        Completed secondary education with focus on mathematics and science subjects.
                    </p>
                </div>
                <div class="education-card">
                    <div class="education-year">2017</div>
                    <h3 class="education-degree">G.C.E Ordinary Level</h3>
                    <div class="education-school">Madina National College - Madawala</div>
                    <p>
                        Completed primary education with strong academic performance across all subjects.
                    </p>
                </div>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section id="projects" class="projects">
        <div class="container">
            <div class="section-title">
                <h2>Projects</h2>
                <p>Some of my recent work</p>
            </div>
            <div class="projects-container">
                <div class="project-card">
                    <div class="project-image">
                        <i class="fas fa-mobile-alt"></i>
                    </div>
                    <div class="project-content">
                        <h3 class="project-title">MyShare Advertisement App</h3>
                        <div class="project-tech">
                            <span class="tech-tag">Java</span>
                            <span class="tech-tag">Android</span>
                        </div>
                        <p>
                            A mobile application for sharing and managing advertisements, built with Java for Android platforms.
                        </p>
                    </div>
                </div>
                <div class="project-card">
                    <div class="project-image">
                        <i class="fas fa-shopping-cart"></i>
                    </div>
                    <div class="project-content">
                        <h3 class="project-title">E-Commerce Website</h3>
                        <div class="project-tech">
                            <span class="tech-tag">HTML</span>
                            <span class="tech-tag">CSS</span>
                            <span class="tech-tag">JavaScript</span>
                        </div>
                        <p>
                            A responsive e-commerce platform with product listings, shopping cart, and checkout functionality.
                        </p>
                    </div>
                </div>
                <div class="project-card">
                    <div class="project-image">
                        <i class="fas fa-store"></i>
                    </div>
                    <div class="project-content">
                        <h3 class="project-title">Super Market Website</h3>
                        <div class="project-tech">
                            <span class="tech-tag">HTML</span>
                            <span class="tech-tag">CSS</span>
                            <span class="tech-tag">JavaScript</span>
                        </div>
                        <p>
                            An online supermarket interface with inventory management and ordering system.
                        </p>
                    </div>
                </div>
                <div class="project-card">
                    <div class="project-image">
                        <i class="fas fa-music"></i>
                    </div>
                    <div class="project-content">
                        <h3 class="project-title">Music Class System</h3>
                        <div class="project-tech">
                            <span class="tech-tag">Spring Boot</span>
                            <span class="tech-tag">MySQL</span>
                            <span class="tech-tag">React</span>
                        </div>
                        <p>
                            A comprehensive management system for music schools to handle students, classes, and scheduling.
                        </p>
                    </div>
                </div>
                <div class="project-card">
                    <div class="project-image">
                        <i class="fas fa-mobile-alt"></i>
                    </div>
                    <div class="project-content">
                        <h3 class="project-title">Android Application</h3>
                        <div class="project-tech">
                            <span class="tech-tag">Android Studio</span>
                            <span class="tech-tag">Java</span>
                        </div>
                        <p>
                            A custom Android application developed using Android Studio and Java.
                        </p>
                    </div>
                </div>
                <div class="project-card">
                    <div class="project-image">
                        <i class="fas fa-book"></i>
                    </div>
                    <div class="project-content">
                        <h3 class="project-title">Bookshop Website Redesign</h3>
                        <div class="project-tech">
                            <span class="tech-tag">Figma</span>
                            <span class="tech-tag">UI/UX</span>
                        </div>
                        <p>
                            Redesigned the user interface for an online bookstore to improve user experience and conversion rates.
                        </p>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="contact">
        <div class="container">
            <div class="section-title">
                <h2>Contact Me</h2>
                <p>Let's get in touch</p>
            </div>
            <div class="contact-content">
                <div class="contact-info">
                    <h3>Contact Information</h3>
                    <div class="contact-item">
                        <i class="fas fa-map-marker-alt"></i>
                        <div class="contact-text">
                            <h4>Location</h4>
                            <p>91/5A, Mosque Road, Madawala, Sri Lanka</p>
                        </div>
                    </div>
                    <div class="contact-item">
                        <i class="fas fa-envelope"></i>
                        <div class="contact-text">
                            <h4>Email</h4>
                            <p>ahamed.amaan@outlook.com</p>
                        </div>
                    </div>
                    <div class="contact-item">
                        <i class="fas fa-phone"></i>
                        <div class="contact-text">
                            <h4>Phone</h4>
                            <p>+94 75 535 7739</p>
                        </div>
                    </div>
                    <div class="contact-item">
                        <i class="fab fa-linkedin-in"></i>
                        <div class="contact-text">
                            <h4>LinkedIn</h4>
                            <p>linkedin.com/in/amaan-ahamed-1ab9b5243</p>
                        </div>
                    </div>
                    <div class="social-links">
                        <a href="https://github.com/AmaanSufiyan" target="_blank"><i class="fab fa-github"></i></a>
                        <a href="https://www.linkedin.com/in/amaan-ahamed-1ab9b5243/" target="_blank"><i class="fab fa-linkedin-in"></i></a>
                        <a href="mailto:ahamed.amaan@outlook.com"><i class="fas fa-envelope"></i></a>
                        <a href="tel:+94755357739"><i class="fas fa-phone"></i></a>
                    </div>
                </div>
                <div class="contact-form">
                    <h3>Send Me a Message</h3>
                    <form>
                        <div class="form-group">
                            <input type="text" class="form-control" placeholder="Your Name">
                        </div>
                        <div class="form-group">
                            <input type="email" class="form-control" placeholder="Your Email">
                        </div>
                        <div class="form-group">
                            <input type="text" class="form-control" placeholder="Subject">
                        </div>
                        <div class="form-group">
                            <textarea class="form-control" placeholder="Your Message"></textarea>
                        </div>
                        <button type="submit" class="cta-btn">Send Message</button>
                    </form>
                </div>
            </div>
        </div>
    </section>

    <!-- Footer -->
    <footer>
        <div class="container">
            <div class="footer-logo">Amaan Ahamed</div>
            <div class="footer-social">
                <a href="https://github.com/AmaanSufiyan" target="_blank"><i class="fab fa-github"></i></a>
                <a href="https://www.linkedin.com/in/amaan-ahamed-1ab9b5243/" target="_blank"><i class="fab fa-linkedin-in"></i></a>
                <a href="mailto:ahamed.amaan@outlook.com"><i class="fas fa-envelope"></i></a>
                <a href="tel:+94755357739"><i class="fas fa-phone"></i></a>
            </div>
            <div class="footer-nav">
                <a href="#home">Home</a>
                <a href="#about">About</a>
                <a href="#skills">Skills</a>
                <a href="#experience">Experience</a>
                <a href="#education">Education</a>
                <a href="#projects">Projects</a>
                <a href="#contact">Contact</a>
            </div>
            <div class="copyright">
                &copy; 2025 Amaan Ahamed. All rights reserved.
            </div>
        </div>
    </footer>

    <script>
        // Theme toggle functionality
        const themeToggle = document.getElementById('theme-toggle');
        const htmlElement = document.documentElement;
        
        // Check for saved theme preference or respect OS preference
        const prefersDarkMode = window.matchMedia('(prefers-color-scheme: dark)').matches;
        const savedTheme = localStorage.getItem('theme');
        
        if (savedTheme === 'dark' || (!savedTheme && prefersDarkMode)) {
            htmlElement.setAttribute('data-theme', 'dark');
        }
        
        themeToggle.addEventListener('click', function() {
            const currentTheme = htmlElement.getAttribute('data-theme');
            const newTheme = currentTheme === 'light' ? 'dark' : 'light';
            
            htmlElement.setAttribute('data-theme', newTheme);
            localStorage.setItem('theme', newTheme);
        });
        
        // Navigation scroll effect
        window.addEventListener('scroll', function() {
            const header = document.getElementById('header');
            if (window.scrollY > 50) {
                header.classList.add('scrolled');
            } else {
                header.classList.remove('scrolled');
            }
        });
        
        // Mobile menu toggle
        const hamburger = document.querySelector('.hamburger');
        const navLinks = document.querySelector('.nav-links');
        
        hamburger.addEventListener('click', function() {
            navLinks.classList.toggle('active');
            
            // Toggle hamburger icon
            const icon = this.querySelector('i');
            if (icon.classList.contains('fa-bars')) {
                icon.classList.remove('fa-bars');
                icon.classList.add('fa-times');
            } else {
                icon.classList.remove('fa-times');
                icon.classList.add('fa-bars');
            }
        });
        
        // Close mobile menu when clicking on links
        document.querySelectorAll('.nav-links a').forEach(link => {
            link.addEventListener('click', () => {
                navLinks.classList.remove('active');
                const icon = hamburger.querySelector('i');
                icon.classList.remove('fa-times');
                icon.classList.add('fa-bars');
            });
        });
        
        // Animate skill bars on scroll
        const skillBars = document.querySelectorAll('.skill-progress');
        
        function animateSkills() {
            skillBars.forEach(bar => {
                const targetWidth = bar.style.width;
                bar.style.width = '0';
                setTimeout(() => {
                    bar.style.width = targetWidth;
                }, 100);
            });
        }
        
        // Animate timeline items on scroll
        const timelineItems = document.querySelectorAll('.timeline-item');
        
        function animateTimeline() {
            timelineItems.forEach((item, index) => {
                setTimeout(() => {
                    item.style.opacity = '1';
                }, 300 * index);
            });
        }
        
        // Intersection Observer for skills section
        const skillsSection = document.querySelector('#skills');
        const experienceSection = document.querySelector('#experience');
        
        const observerOptions = {
            threshold: 0.3
        };
        
        const skillsObserver = new IntersectionObserver(function(entries) {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    animateSkills();
                    skillsObserver.unobserve(entry.target);
                }
            });
        }, observerOptions);
        
        const timelineObserver = new IntersectionObserver(function(entries) {
            entries.forEach(entry => {
                if (entry.isIntersecting) {
                    animateTimeline();
                    timelineObserver.unobserve(entry.target);
                }
            });
        }, observerOptions);
        
        skillsObserver.observe(skillsSection);
        timelineObserver.observe(experienceSection);
    </script>
</body>
</html>
