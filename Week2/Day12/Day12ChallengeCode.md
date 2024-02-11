### index.html
```html
<!DOCTYPE html>
<html>
<head>
    <title>Our Restaurant Menu</title>
    <!-- External CSS Link -->
    <link rel="stylesheet" type="text/css" href="styles.css">
    <!-- Internal CSS -->
    <style>
        body {
            font-family: 'Arial', sans-serif;
            margin: 0;
            padding: 0;
            background-color: #f4f4f4;
        }
        header {
            background-color: #ffebcd;
            padding: 20px;
            text-align: center;
        }
        h2 {
            color: #333;
        }
        .menu-section {
            background-color: #ffffff;
            padding: 15px;
            margin: 15px;
            border-radius: 5px;
        }
        footer {
            background-color: #deb887;
            color: #fff;
            text-align: center;
            padding: 10px;
            position: fixed;
            bottom: 0;
            width: 100%;
        }
    </style>
</head>
<body>
    <header>
        <h1>Welcome to ABC Restaurant</h1>
        <p>Our restaurant, <b>ABC</b> offers a unique blend of traditional and contemporary culinary delights, set in a cozy, inviting atmosphere perfect for any occasion.</p>
    </header>
    <h2>Menu</h2>
    <section class="menu-section"> <!-- Updated class name for consistency -->
        <h3>Appetizers</h3>
        <a href="#appetizers">View Appetizers</a>
        <ul>
            <img src="https://www.budgetbytes.com/wp-content/uploads/2023/08/Garlic-Bread-close.jpg" alt="Garlic Bread"
                width="80" height="80" />
            <li>Garlic Bread</li>
            <img src="https://www.allrecipes.com/thmb/QSsjryxShEx1L6o0HLer1Nn4jwA=/1500x0/filters:no_upscale():max_bytes(150000):strip_icc()/54165-balsamic-bruschetta-DDMFS-4x3-e2b55b5ca39b4c1783e524a2461634ea.jpg"
                alt="Bruschetta" width="80" height="80" />
            <li>Bruschetta</li>
        </ul>
    </section>
    <section class="menu-section"> <!-- Added missing section tag and class for Main Courses -->
        <h3>Main Courses</h3>
        <ol>
            <li>Biryani</li>
            <li>Butter Chicken</li>
            <li>Korma</li>
        </ol>
    </section>
    <section class="menu-section"> <!-- Added section tag and class for Desserts -->
        <h3>Desserts</h3>
        <ol>
            <li style="color: red; font-weight: bold;">Special: Cake</li> <!-- Added "Special" and inline CSS for emphasis -->
            <li>Cookie</li>
            <li>Candy</li>
        </ol>
    </section>
    <h3>Submit your reviews here:</h3>
    <form action="submit-review.php" method="post">
        <input type="text" name="customer_name" placeholder="Your Name">
        <textarea name="review" placeholder="Write your review here..."></textarea>
        <input type="submit" value="Submit Review">
    </form>
    <footer>
        <p>Contact us</p>
    </footer>
</body>
</html>
```
### styles.css
```html
/* External CSS file: styles.css */
ul {
    list-style-type: none;
    padding: 0;
}

li {
    margin-bottom: 5px;
}

img {
    border-radius: 50%;
}
```