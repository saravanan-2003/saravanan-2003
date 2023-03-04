<!DOCTYPE html>
<html lang="en">

<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <link rel="stylesheet" href="style.css">
  <title>My Portfolio</title>
  <style>
    @import 'https://fonts.googleapis.com/css?family=Montserrat:300, 400, 700&display=swap';
* {
	padding: 0;
	margin: 0;
	box-sizing: border-box;
}
html {
	font-size: 10px;
	font-family: 'Montserrat', sans-serif;
	scroll-behavior: smooth;
}
a {
	text-decoration: none;
}
.container {
	min-height: 100vh;
	width: 100%;
	display: flex;
	align-items: center;
	justify-content: center;
}
img {
	height: 100%;
	width: 100%;
	object-fit: cover;
}
p {
	color: black;
	font-size: 1.4rem;
	margin-top: 5px;
	line-height: 2.5rem;
	font-weight: 300;
	letter-spacing: 0.05rem;
}
.section-title {
	font-size: 4rem;
	font-weight: 300;
	color: black;
	margin-bottom: 10px;
	text-transform: uppercase;
	letter-spacing: 0.2rem;
	text-align: center;
}
.section-title span {
	color: crimson;
}

.cta {
	display: inline-block;
	padding: 10px 30px;
	color: white;
	background-color: transparent;
	border: 2px solid crimson;
	font-size: 2rem;
	text-transform: uppercase;
	letter-spacing: 0.1rem;
	margin-top: 30px;
	transition: 0.3s ease;
	transition-property: background-color, color;
}
.cta:hover {
	color: white;
	background-color: crimson;
}
.brand h1 {
	font-size: 3rem;
	text-transform: uppercase;
	color: white;
}
.brand h1 span {
	color: crimson;
}

/* Header section */
#header {
	position: fixed;
	z-index: 1000;
	left: 0;
	top: 0;
	width: 100vw;
	height: auto;
}
#header .header {
	min-height: 8vh;
	background-color: rgba(31, 30, 30, 0.24);
	transition: 0.3s ease background-color;
}
#header .nav-bar {
	display: flex;
	align-items: center;
	justify-content: space-between;
	width: 100%;
	height: 100%;
	max-width: 1300px;
	padding: 0 10px;
}
#header .nav-list ul {
	list-style: none;
	position: absolute;
	background-color: rgb(31, 30, 30);
	width: 100vw;
	height: 100vh;
	left: 100%;
	top: 0;
	display: flex;
	flex-direction: column;
	justify-content: center;
	align-items: center;
	z-index: 1;
	overflow-x: hidden;
	transition: 0.5s ease left;
}
#header .nav-list ul.active {
	left: 0%;
}
#header .nav-list ul a {
	font-size: 2.5rem;
	font-weight: 500;
	letter-spacing: 0.2rem;
	text-decoration: none;
	color: white;
	text-transform: uppercase;
	padding: 20px;
	display: block;
}
#header .nav-list ul a::after {
	content: attr(data-after);
	position: absolute;
	top: 50%;
	left: 50%;
	transform: translate(-50%, -50%) scale(0);
	color: rgba(240, 248, 255, 0.021);
	font-size: 13rem;
	letter-spacing: 50px;
	z-index: -1;
	transition: 0.3s ease letter-spacing;
}
#header .nav-list ul li:hover a::after {
	transform: translate(-50%, -50%) scale(1);
	letter-spacing: initial;
}
#header .nav-list ul li:hover a {
	color: crimson;
}
#header .hamburger {
	height: 60px;
	width: 60px;
	display: inline-block;
	border: 3px solid white;
	border-radius: 50%;
	position: relative;
	display: flex;
	align-items: center;
	justify-content: center;
	z-index: 100;
	cursor: pointer;
	transform: scale(0.8);
	margin-right: 20px;
}
#header .hamburger:after {
	position: absolute;
	content: '';
	height: 100%;
	width: 100%;
	border-radius: 50%;
	border: 3px solid white;
	animation: hamburger_puls 1s ease infinite;
}
#header .hamburger .bar {
	height: 2px;
	width: 30px;
	position: relative;
	background-color: white;
	z-index: -1;
}
#header .hamburger .bar::after,
#header .hamburger .bar::before {
	content: '';
	position: absolute;
	height: 100%;
	width: 100%;
	left: 0;
	background-color: white;
	transition: 0.3s ease;
	transition-property: top, bottom;
}
#header .hamburger .bar::after {
	top: 8px;
}
#header .hamburger .bar::before {
	bottom: 8px;
}
#header .hamburger.active .bar::before {
	bottom: 0;
}
#header .hamburger.active .bar::after {
	top: 0;
}
/* End Header section */

/* Hero Section */
#hero {
	background-image: url('pic2.jpg');
	background-size: cover;
	background-position: top center;
	position: relative;
	z-index: 1;
}
#hero::after {
	content: '';
	position: absolute;
	left: 0;
	top: 0;
	height: 100%;
	width: 100%;
	background-color: rgba(59, 57, 57, 0.277);
	opacity: 0.7;
	z-index: -1;
}
#hero .hero {
	max-width: 1200px;
	margin: 0 auto;
	padding: 0 50px;
	justify-content: flex-start;
}
#hero h1 {
	display: block;
	width: fit-content;
	font-size: 4rem;
	position: relative;
	color: transparent;
	animation: text_reveal 0.5s ease forwards;
	animation-delay: 1s;
}
#hero h1:nth-child(1) {
	animation-delay: 1s;
}
#hero h1:nth-child(2) {
	animation-delay: 2s;
}
#hero h1:nth-child(3) {
	animation: text_reveal_name 0.5s ease forwards;
	animation-delay: 3s;
}
#hero h1 span {
	position: absolute;
	top: 0;
	left: 0;
	height: 100%;
	width: 0;
	background-color: crimson;
	animation: text_reveal_box 1s ease;
	animation-delay: 0.5s;
}
#hero h1:nth-child(1) span {
	animation-delay: 0.5s;
}
#hero h1:nth-child(2) span {
	animation-delay: 1.5s;
}
#hero h1:nth-child(3) span {
	animation-delay: 2.5s;
}

/* End Hero Section */

/* education Section */
#education .education {
	flex-direction: column;
	text-align: center;
	max-width: 1500px;
	margin: 0 auto;
	padding: 100px 0;
}
#education .service-top {
	max-width: 500px;
	margin: 0 auto;
}
#education .service-bottom {
	display: flex;
	align-items: center;
	justify-content: center;
	flex-wrap: wrap;
	margin-top: 50px;
}
#education .service-item {
	flex-basis: 80%;
	display: flex;
	align-items: flex-start;
	justify-content: center;
	flex-direction: column;
	padding: 30px;
	border-radius: 10px;
	background-image: url(./img/img-1.png);
	background-size: cover;
	margin: 10px 5%;
	position: relative;
	z-index: 1;
	overflow: hidden;
}
#education .service-item::after {
	content: '';
	position: absolute;
	left: 0;
	top: 0;
	height: 100%;
	width: 100%;
	background-image: linear-gradient(60deg, #29323c 0%, #485563 100%);
	opacity: 0.9;
	z-index: -1;
}
#education .service-bottom .icon {
	height: 80px;
	width: 80px;
	margin-bottom: 20px;
}
#education .service-item h2 {
	font-size: 2rem;
	color: white;
	margin-bottom: 10px;
	text-transform: uppercase;
}
#education .service-item p {
	color: white;
	text-align: left;
}
/* End education Section */

/* Projects section */
#projects .projects {
	flex-direction: column;
	max-width: 1200px;
	margin: 0 auto;
	padding: 100px 0;
}
#projects .projects-header h1 {
	margin-bottom: 50px;
}
#projects .all-projects {
	display: flex;
	align-items: center;
	justify-content: center;
	flex-direction: column;
}
#projects .project-item {
	display: flex;
	align-items: center;
	justify-content: center;
	flex-direction: column;
	width: 80%;
	margin: 20px auto;
	overflow: hidden;
	border-radius: 10px;
}
#projects .project-info {
	padding: 30px;
	flex-basis: 50%;
	height: 100%;
	display: flex;
	align-items: flex-start;
	justify-content: center;
	flex-direction: column;
	background-image: linear-gradient(60deg, #29323c 0%, #485563 100%);
	color: white;
}
#projects .project-info h1 {
	font-size: 4rem;
	font-weight: 500;
}
#projects .project-info h2 {
	font-size: 1.8rem;
	font-weight: 500;
	margin-top: 10px;
}
#projects .project-info p {
	color: white;
}
#projects .project-img {
	flex-basis: 50%;
	height: 300px;
	overflow: hidden;
	position: relative;
}
#projects .project-img:after {
	content: '';
	position: absolute;
	left: 0;
	top: 0;
	height: 100%;
	width: 100%;
	background-image: linear-gradient(60deg, #29323c 0%, #485563 100%);
	opacity: 0.7;
}
#projects .project-img img {
	transition: 0.3s ease transform;
}
#projects .project-item:hover .project-img img {
	transform: scale(1.1);
}
/* End Projects section */

/* About Section */
#about .about {
	flex-direction: column-reverse;
	text-align: center;
	max-width: 1200px;
	margin: 0 auto;
	padding: 100px 20px;
}
#about .col-left {
	width: 250px;
	height: 360px;
}
#about .col-right {
	width: 100%;
}
#about .col-right h2 {
	font-size: 1.8rem;
	font-weight: 500;
	letter-spacing: 0.2rem;
	margin-bottom: 10px;
}
#about .col-right p {
	margin-bottom: 20px;
}
#about .col-right .cta {
	color: black;
	margin-bottom: 50px;
	padding: 10px 20px;
	font-size: 2rem;
}
#about .col-left .about-img {
	height: 100%;
	width: 100%;
	position: relative;
	border: 10px solid white;
}
#about .col-left .about-img::after {
	content: '';
	position: absolute;
	left: -33px;
	top: 19px;
	height: 98%;
	width: 98%;
	border: 7px solid crimson;
	z-index: -1;
}
/* End About Section */

/* contact Section */
#contact .contact {
	flex-direction: column;
	max-width: 1200px;
	margin: 0 auto;
	width: 90%;
}
#contact .contact-items {
	/* max-width: 400px; */
	width: 100%;
}
#contact .contact-item {
	width: 80%;
	padding: 20px;
	text-align: center;
	border-radius: 10px;
	padding: 30px;
	margin: 30px;
	display: flex;
	justify-content: center;
	align-items: center;
	flex-direction: column;
	box-shadow: 0px 0px 18px 0 #0000002c;
	transition: 0.3s ease box-shadow;
}
#contact .contact-item:hover {
	box-shadow: 0px 0px 5px 0 #0000002c;
}
#contact .icon {
	width: 70px;
	margin: 0 auto;
	margin-bottom: 10px;
}
#contact .contact-info h1 {
	font-size: 2.5rem;
	font-weight: 500;
	margin-bottom: 5px;
}
#contact .contact-info h2 {
	font-size: 1.3rem;
	line-height: 2rem;
	font-weight: 500;
}
/*End contact Section */

/* Footer */
#footer {
	background-image: linear-gradient(60deg, #29323c 0%, #485563 100%);
}
#footer .footer {
	min-height: 200px;
	flex-direction: column;
	padding-top: 50px;
	padding-bottom: 10px;
}
#footer h2 {
	color: white;
	font-weight: 500;
	font-size: 1.8rem;
	letter-spacing: 0.1rem;
	margin-top: 10px;
	margin-bottom: 10px;
}
#footer .social-icon {
	display: flex;
	margin-bottom: 30px;
}
#footer .social-item {
	height: 50px;
	width: 50px;
	margin: 0 5px;
}
#footer .social-item img {
	filter: grayscale(1);
	transition: 0.3s ease filter;
}
#footer .social-item:hover img {
	filter: grayscale(0);
}
#footer p {
	color: white;
	font-size: 1.3rem;
}
/* End Footer */

/* Keyframes */
@keyframes hamburger_puls {
	0% {
		opacity: 1;
		transform: scale(1);
	}
	100% {
		opacity: 0;
		transform: scale(1.4);
	}
}
@keyframes text_reveal_box {
	50% {
		width: 100%;
		left: 0;
	}
	100% {
		width: 0;
		left: 100%;
	}
}
@keyframes text_reveal {
	100% {
		color: white;
	}
}
@keyframes text_reveal_name {
	100% {
		color: crimson;
		font-weight: 500;
	}
}
/* End Keyframes */

/* Media Query For Tablet */
@media only screen and (min-width: 768px) {
	.cta {
		font-size: 2.5rem;
		padding: 20px 60px;
	}
	h1.section-title {
		font-size: 6rem;
	}

	/* Hero */
	#hero h1 {
		font-size: 7rem;
	}
	/* End Hero */

	/* education Section */
	#education .service-bottom .service-item {
		flex-basis: 45%;
		margin: 2.5%;
	}
	/* End education Section */

	/* Project */
	#projects .project-item {
		flex-direction: row;
	}
	#projects .project-item:nth-child(even) {
		flex-direction: row-reverse;
	}
	#projects .project-item {
		height: 400px;
		margin: 0;
		width: 100%;
		border-radius: 0;
	}
	#projects .all-projects .project-info {
		height: 100%;
	}
	#projects .all-projects .project-img {
		height: 100%;
	}
	/* End Project */

	/* About */
	#about .about {
		flex-direction: row;
	}
	#about .col-left {
		width: 600px;
		height: 400px;
		padding-left: 60px;
	}
	#about .about .col-left .about-img::after {
		left: -45px;
		top: 34px;
		height: 98%;
		width: 98%;
		border: 10px solid crimson;
	}
	#about .col-right {
		text-align: left;
		padding: 30px;
	}
	#about .col-right h1 {
		text-align: left;
	}
	/* End About */

	/* contact  */
	#contact .contact {
		flex-direction: column;
		padding: 100px 0;
		align-items: center;
		justify-content: center;
		min-width: 20vh;
	}
	#contact .contact-items {
		width: 100%;
		display: flex;
		flex-direction: row;
		justify-content: space-evenly;
		margin: 0;
	}
	#contact .contact-item {
		width: 30%;
		margin: 0;
		flex-direction: row;
	}
	#contact .contact-item .icon {
		height: 100px;
		width: 100px;
	}
	#contact .contact-item .icon img {
		object-fit: contain;
	}
	#contact .contact-item .contact-info {
		width: 100%;
		text-align: left;
		padding-left: 20px;
	}
	/* End contact  */
}
/* End Media Query For Tablet */

/* Media Query For Desktop */
@media only screen and (min-width: 1200px) {
	/* header */
	#header .hamburger {
		display: none;
	}
	#header .nav-list ul {
		position: initial;
		display: block;
		height: auto;
		width: fit-content;
		background-color: transparent;
	}
	#header .nav-list ul li {
		display: inline-block;
	}
	#header .nav-list ul li a {
		font-size: 1.8rem;
	}
	#header .nav-list ul a:after {
		display: none;
	}
	/* End header */

	#education .service-bottom .service-item {
		flex-basis: 22%;
		margin: 1.5%;
	}
}
/* End  Media Query For Desktop */
  </style>
</head>

<body>
  <!-- Header -->
  <section id="header">
    <div class="header container">
      <div class="nav-bar">
        <div class="brand">
          <a href="#hero">
            <!-- <h1><span>S</span>aravanan <span>T</span></h1> -->
            <img src="pic3.png" alt="" style="height:9%; width: 9%;background-color: rgba(123, 85, 123, 0.434);">
          </a>
        </div>
        <div class="nav-list">
          <div class="hamburger">
            <div class="bar"></div>
          </div>
          <ul>
            <li><a href="#hero" data-after="Home">Home</a></li>
            <!-- <li><a href="#education" data-after="Service">Education</a></li> -->
            <li><a href="#projects" data-after="Projects">Projects</a></li>
            <li><a href="#about" data-after="About">About</a></li>
            <li><a href="#contact" data-after="Contact">Contact</a></li>
          </ul>
        </div>
      </div>
    </div>
  </section>

  <section id="hero">
    <div class="hero container">
      <div>
        <h1>Hello, <span></span></h1>
        <h1>My Name is <span></span></h1>
        <h1>Saravanan <span></span></h1>
        <!-- <a href="#projects" type="button" class="cta">Portfolio</a> -->
      </div>
    </div>
  </section>

  <!-- <section id="education">
    <div class="education container">
      <div class="service-top">
        <h1 class="section-title">EDUCATION</h1>
      </div>
      <div class="service-bottom">
        <div class="service-item">
          <div class="icon"><img src="https://www.bitsathy.ac.in/assets/images/favicons/meta-logo.png" style="border-radius: 20%;"/></div>
          <h2>BANNARI AMMAN INSTITUTE OF TECHNOLOGY</h2>
          <p></p>
        </div>
        <div class="service-item">
          <div class="icon"><img src="https://www.static-contents.youth4work.com/university/Documents/Colleges/collegeLogo/20191121143649.png?v=20191121143649" style="border-radius: 20%;"/></div>
          <h2>ADHARSH HIGHER SECONDARY SCHOOL</h2>
          <p></p>
        </div>
        
        <div class="service-item">
          <div class="icon"><img src="data:image/jpeg;base64,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" style="border-radius: 20%;"/></div>
          <h2>Little Flower Matric School</h2>
          <p></p>
        </div>
      </div>
    </div>
  </section> -->
 
  <section id="projects">
    <div class="projects container">
      <div class="projects-header">
        <h1 class="section-title">Recent <span>Projects</span></h1>
      </div>
      <div class="all-projects">
        <div class="project-item">
          <div class="project-info">
            <h1>Project 1</h1>
            <h2>Todo app with React</h2>
            <p>Done an app with using react will be clone of other Todo apps in play store . which i have done for learning CRUD Operation with connection of backend using MongoDB</p>
          </div>
          <div class="project-img">
            <img src="https://i0.wp.com/blog.lulu.com/wp-content/uploads/2020/07/072120-ToDoList-Blog.png?fit=1200%2C675&ssl=1" alt="img">
          </div>
        </div>
        <div class="project-item">
          <div class="project-info">
            <h1>Project 2</h1>
            <h2>Resume Template for freshers</h2>
            <p>Done my own resume as a template which will be used for fresher students to learn , how to make a resume for professional interview  </p>
          </div>
          <div class="project-img">
            <img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcQLHxDSju19zIpaXoYMh-oIfQfdIytvnZ5HHA&usqp=CAU" alt="img">
          </div>
        </div>
        <div class="project-item">
          <div class="project-info">
            <h1>Project 3</h1>
            <h2>Learn with Java JDBC </h2>
            <p>Done a small CRUD Operation with MySQL server for ATM based system . Done some functions like Credit,Debit,Transactions ...</p>
          </div>
          <div class="project-img">
            <img src="https://miro.medium.com/max/1400/1*vSkjUc3d4YLKQWsPTND5-A.jpeg" alt="img">
          </div>
        </div>
        <div class="project-item">
          <div class="project-info">
            <h1>Project 4</h1>
            <h2>CLONE for Amazon Prime page,Googel Login Templates</h2>
            <p>To learn the function of HTML and CSS , I Have done a clone webpage for Amazon Prime user page and Google Login , Sign up, Forget Page....</p>
          </div>
          <div class="project-img">
            <img src="https://codersera.com/blog/wp-content/uploads/2021/10/web-flow-.jpeg" alt="img">
          </div>
        </div>
        <!-- <div class="project-item">
          <div class="project-info">
            <h1>Project 5</h1>
            <h2>Coding</h2>
            <p>Lorem, ipsum dolor sit amet consectetur adipisicing elit. Ad, iusto cupiditate voluptatum impedit unde
              rem ipsa distinctio illum quae mollitia ut, accusantium eius odio ducimus illo neque atque libero non sunt
              harum? Ipsum repellat animi, fugit architecto voluptatum odit et!</p>
          </div>
          <div class="project-img">
            <img src="./img/img-1.png" alt="img">
          </div>
        </div> -->
      </div>
    </div>
  </section>
  
  <section id="about">
    <div class="about container">
      <div class="col-left">
        <div class="about-img">
          <img src="pic1.jpg" alt="img">
        </div>
      </div>
      <div class="col-right">
        <h1 class="section-title">About <span>me</span></h1>
        <h2>Front End Developer</h2>
        <p>As a web developer, my objective is to create user-friendly and efficient websites that are visually appealing and easy 
            to navigate. I utilize my skills in HTML, CSS, JavaScript, and PHP to develop websites that meet all the requirements of 
            the client.I am confident that I can apply these skills to a Web Developer Role, and would like the opportunity to work 
            with more complex codebases.</p>
        <a href="#" class="cta" download>Download Resume</a>
      </div>
    </div>
  </section>
  
  <section id="contact">
    <div class="contact container">
      <div>
        <h1 class="section-title">Contact <span>info</span></h1>
      </div>
      <div class="contact-items">
        <div class="contact-item">
          <div class="icon"><img src="https://png.pngtree.com/png-vector/20191011/ourmid/pngtree-phone-icon-png-image_1817554.jpg" /></div>
          <div class="contact-info">
            <h1>Phone</h1>
            <h2>+91 6383513778</h2>
            <h2>+04324 636382</h2>
          </div>
        </div>
        <div class="contact-item">
          <div class="icon"><img src="https://encrypted-tbn0.gstatic.com/images?q=tbn:ANd9GcS5awb6UW4Z7e6h4zz_DZdw4_QxJjyH083VUL_BuB_riA_9YguwPL2tFU6rJiB8CC5ulEM&usqp=CAU" /></div>
          <div class="contact-info">
            <h1>Email</h1>
            <h2>stsaravanan2003@gmail.com</h2>
            <h2>saravanan.it20@bitsathy.ac.in</h2>
          </div>
        </div>
        <div class="contact-item">
          <div class="icon"><img src="https://static.thenounproject.com/png/2481156-200.png" /></div>
          <div class="contact-info">
            <h1>Address</h1>
            <h2>141/1,Gandhi Nagar,Udayampalayam,Karur-638 005</h2>
          </div>
        </div>
      </div>
    </div>
  </section>

  <section id="footer">
    <div class="footer container">
      
      
      <div class="social-icon">
        <div class="social-item">
          <a href="https://www.instagram.com/"><img src="https://cdn3.iconfinder.com/data/icons/2018-social-media-logotypes/1000/2018_social_media_popular_app_logo_instagram-1024.png" style="border-radius: 20%;"/></a>
        </div>
        <div class="social-item">
          <a href="https://twitter.com/"><img src="https://cdn3.iconfinder.com/data/icons/2018-social-media-logotypes/1000/2018_social_media_popular_app_logo_twitter-1024.png" /></a>
        </div>
        <div class="social-item">
          <a href="https://github.com/saravanan-2003"><img src="https://cdn3.iconfinder.com/data/icons/social-rounded-2/72/GitHub-512.png" style="border-radius: 20%;"/></a>
        </div>
        <div class="social-item">
          <a href="https://www.linkedin.com/in/saravanan2003/"><img src="https://cdn4.iconfinder.com/data/icons/social-media-logos-6/512/56-linkedin-512.png" style="border-radius: 20%;"/></a>
        </div>
        <div class="social-item">
          <a href="https://leetcode.com/"><img src="https://user-images.githubusercontent.com/36547915/97088991-45da5d00-1652-11eb-900f-80d106540f4f.png" style="border-radius: 20%;"/></a>
        </div>
        <div class="social-item">
          <a href="https://www.hackerrank.com/"><img src="https://cdn4.iconfinder.com/data/icons/logos-and-brands/512/160_Hackerrank_logo_logos-512.png" style="border-radius: 20%;"/></a>
        </div>
        <div class="social-item">
          <a href=" https://wa.me/6383513778"><img src="https://cdn2.iconfinder.com/data/icons/social-media-2285/512/1_Whatsapp2_colored_svg-512.png" style="border-radius: 20%;"/></a>
        </div>
      </div>
    </div>
  </section>

</body>

</html>




<!-- <!DOCTYPE html>
<html>
<body>
    
<h3 align="center">I practice what I post.:-)</h3>
<h2>Hey there , I’m saravanan (❁´◡`❁)</h2>
    <p align="left"> <img src="https://komarev.com/ghpvc/?username=saravanan-2003&label=Profile%20views&color=0e75b6&style=flat" alt="saravanan-2003" /> </p>
<h3>👩‍💻About Me</h3>
<ul>
    <li>
        🤔 Exploring new Technologies.
    </li>
    <li>
        🏫 Studying Information Technology at Bannari Amman Institute of Technology.
    </li>
    <li>
        📑 Learning more about Machine Learning, Deep Learning.
    </li>
    <li>
        ✍️ Pursuing coding as Hobby.
    </li>
</ul>



<h3 align="left">Connect with me:</h3>
<p align="left">
<a href="https://www.linkedin.com/in/saravanan-t-124388200/" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/linked-in-alt.svg" alt="https://www.linkedin.com/in/saravanan-t-124388200/" height="30" width="40" /></a>
<a href="https://www.codechef.com/users/saravanan213" target="blank"><img align="center" src="https://cdn.jsdelivr.net/npm/simple-icons@3.1.0/icons/codechef.svg" alt="saravanan-2003" height="30" width="40" /></a>
<a href="https://www.hackerrank.com/saravanan_it20" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/hackerrank.svg" alt="saravanan-2003" height="30" width="40" /></a>
<a href="https://auth.geeksforgeeks.org/user/saravananit20" target="blank"><img align="center" src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/geeks-for-geeks.svg" alt="saravananit20" height="30" width="40" /></a>
</p>

<h3 align="left">Languages and Tools:</h3>
<p align="left"> 
<a href="https://www.python.org" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/python/python-original.svg" alt="python" width="40" height="40"/> </a>
<a href="https://www.cprogramming.com/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/c/c-original.svg" alt="c" width="40" height="40"/> </a> <a href="https://www.w3schools.com/css/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/css3/css3-original-wordmark.svg" alt="css3" width="40" height="40"/> </a> <a href="https://www.w3.org/html/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/html5/html5-original-wordmark.svg" alt="html5" width="40" height="40"/> </a> <a href="https://www.mysql.com/" target="_blank" rel="noreferrer"> <img src="https://raw.githubusercontent.com/devicons/devicon/master/icons/mysql/mysql-original-wordmark.svg" alt="mysql" width="40" height="40"/> </a>  </p>
<div align="center">
<img src="https://github-readme-stats.vercel.app/api/top-langs/?username=saravanan-2003&theme=highcontrast&hide_border=true"></br>
<img src="https://github-readme-stats.vercel.app/api?username=saravanan-2003&show_icons=true&theme=highcontrast&hide_border=true&hide=stars,prs,issues,contribs"></br>
<img src="https://github-readme-streak-stats.herokuapp.com?user=saravanan-2003&theme=highcontrast&hide_border=true&date_format=j%20M%5B%20Y%5D">
</div>
</body>
</html>

 -->
