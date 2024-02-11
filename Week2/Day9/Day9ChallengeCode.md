```html
<!DOCTYPE html>
<html>
<head>
    <title>Our Restaurant Menu</title>
</head>
<body>
    <h1>Welcome to ABC Restaurant</h1> <!--h1 Heading tag-->
    <p>Our restaurant, <b>ABC</b> offers a unique blend of traditional and contemporary culinary delights, set in a cozy, inviting atmosphere perfect for any occasion.</p>
    <h2>Menu</h2> <!--h2 Heading tag-->
    <h3>Appetizers</h3> <!--h3 Heading tag ; Observe the difference in the tags-->
    <a href="#appetizers">View Appetizers</a>
    <ul> <!--Unordered list-->
        <img src="https://www.budgetbytes.com/wp-content/uploads/2023/08/Garlic-Bread-close.jpg" alt="Garlic Bread"  width="80" height="80"/>
        <li>Garlic Bread</li>
        <img src="https://www.allrecipes.com/thmb/QSsjryxShEx1L6o0HLer1Nn4jwA=/1500x0/filters:no_upscale():max_bytes(150000):strip_icc()/54165-balsamic-bruschetta-DDMFS-4x3-e2b55b5ca39b4c1783e524a2461634ea.jpg" alt="Bruschetta"  width="80" height="80"/>
        <li>Bruschetta</li>
        <img src="https://www.twopeasandtheirpod.com/wp-content/uploads/2020/12/Stuffed-Mushrooms-1.jpg" alt="Stuffed Mushrooms"  width="80" height="80"/>
        <li>Stuffed Mushrooms</li>
    </ul>
    <hr>
    <h3>Main Courses</h3>
    <ol>
        <li>Biryani</li>
        <li>Butter Chicken</li>
        <li>Korma</li>
    </ol>
    <hr>
    <h3>Desserts</h3>
    <ol>
        <li>Cake</li>
        <li>Cookie</li>
        <li>Candy</li>
    </ol>
    <h3>Submit your reviews here:</h3>
    <form action="submit-review.php" method="post">
        <input type="text" name="customer_name" placeholder="Your Name">
        <textarea name="review" placeholder="Write your review here..."></textarea>
        <input type="submit" value="Submit Review">
      </form>
</body>
</html>
```