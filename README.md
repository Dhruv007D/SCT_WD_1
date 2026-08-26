# SCT_WD_1
Create an interactive navigation
menu that changes color or style
when scrolled or when hovering
over a menu item. 

The navigation menu should
have a fixed position and be
visible on all pages.


<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <meta name="viewport" content="width=device-width, initial-scale=1.0">
  <title>Interactive Navigation Menu</title>
  <style>
    body {
      margin: 0;
      font-family: Arial, sans-serif;
      height: 2000px; /* just to enable scrolling */
    }

    /* Base navigation styling */
    nav {
      position: fixed;
      top: 0;
      width: 100%;
      background: transparent;
      padding: 15px 30px;
      transition: background 0.3s, box-shadow 0.3s;
      z-index: 1000;
    }

    nav.scrolled {
      background: #333;
      box-shadow: 0 2px 5px rgba(0,0,0,0.3);
    }

    nav ul {
      list-style: none;
      margin: 0;
      padding: 0;
      display: flex;
      justify-content: flex-end;
    }

    nav ul li {
      margin-left: 20px;
    }

    nav ul li a {
      text-decoration: none;
      color: #000;
      font-weight: bold;
      transition: color 0.3s, border-bottom 0.3s;
    }

    nav.scrolled ul li a {
      color: #fff;
    }

    nav ul li a:hover {
      color: #ff6600;
      border-bottom: 2px solid #ff6600;
    }
  </style>
</head>
<body>

  <nav id="navbar">
    <ul>
      <li><a href="#home">Home</a></li>
      <li><a href="#about">About</a></li>
      <li><a href="#services">Services</a></li>
      <li><a href="#contact">Contact</a></li>
    </ul>
  </nav>

  <script>
    const navbar = document.getElementById('navbar');
    window.addEventListener('scroll', () => {
      if (window.scrollY > 50) {
        navbar.classList.add('scrolled');
      } else {
        navbar.classList.remove('scrolled');
      }
    });
  </script>

</body>
</html>
