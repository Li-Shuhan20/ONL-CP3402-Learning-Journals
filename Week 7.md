# 18 / Mar / 2026

# Week 7 - PHP Programming

# Learning Activities & Resources

This week, I studied the basics of PHP programming and how PHP can be combined with WordPress and content management system development.

- Watched the LinkedIn Learning course (What is PHP, basic knowledge, control structures.) (<https://www.linkedin.com/learning/php-for-wordpress-24300129/what-is-php-for-wordpress?u=2223545>).
- Watched the weekly lecture video and file.
- Constructing the content outline for the team project website.
- The effect of attempting PHP programming in VSCode

# Estimated Hours

 Around 2 hours 45 minutes

# Content Insights

### Server-side features of PHP

PHP is a language that runs entirely on the server side. Any content before being delivered to the browser will be processed on the server. This might seem obvious in theory, but when I wrote a simple script, I saw its practical significance:

```PHP
<?php echo "<p>Hello World</p>"; ? >
```

 When I viewed the page source code through the browser, all I saw was <p>Hello World</p>  The PHP code had completely disappeared. This means that users will never be able to see my PHP logic, which is extremely important for security.

### The embedded feature of PHP
What amazed me the most was the seamless integration of PHP and HTML. A single.php file can both contain HTML tags and can be used with "<?" php ...” Switch to the PHP mode after the sentence. ? Then switch back to the HTML format. For instance, I created a page that displays different greetings based on different times of the day:

```PHP
<h1>Welcome</h1>
<? PHP
$hour = date('H');
if (hour < 12) {
echo "<p>Good morning!</p>";
} else {
echo "<p>Good afternoon!</p>";
}
? >
<footer>Contact Us</footer>
```

This approach of combining logic with presentation is different from those frameworks I have built before.

### Variables and the $ symbol

I found it took some time to get used to the \$ symbol before a variable. In JavaScript and other code learning, \$ is just a character that can be used in variable names, but in PHP it must be included. I initially forgot to add it a few times, causing errors. This reminded me of the experience of learning any new language - every subtle syntax difference in each code is important, and I need to practice enough to make using \$ a natural behavior rather than something that requires thinking.

# Career/Employability/Learning Insights

### Connect these points: from WordPress users to WordPress developers
Previously, my understanding of WordPress was limited to the user level - I could install themes, create content and configure settings. But PHP knowledge serves as the bridge between being a WordPress user and a developer. Now when I look at a theme file like header.php, I can see the HTML structure contained within and PHP functions like bloginfo('name') that can dynamically retrieve content from the database. This shift in perspective is of great significance. I can now envision myself not only choosing a theme, but also modifying it to add custom functionality.
### Custom Sidebar Issue
During my previous learning, I wanted to add a custom sidebar to a WordPress website. This sidebar would display different content based on the current user's login status. I searched for plugins and found one that could roughly achieve this, but still couldn't get it completely right. Now I understand that I can solve this problem using PHP:

```php
<?php if (is_user_logged_in()) : ?>
    <div class="member-sidebar">
        <h3>Member Content</h3>
        <?php echo get_user_meta(get_current_user_id(), 'special_content', true); ?>
    </div>
<?php else : ?>
    <div class="guest-sidebar">
        <h3>Login to See More</h3>
        <a href="<?php echo wp_login_url(); ?>">Login</a>
    </div>
<?php endif; ?>
```

This is a simple example, but it represents the kind of custom functionality that plugins usually don't provide. Having the ability to write such code makes me more independent and valuable, especially for employers who need customized solutions.

### Security thinking mode
The `htmlspecialchars()` function and its role in preventing XSS attacks have made me realize the need for a certain security thinking mode. When I first started learning web development, I only focused on making things work properly. Now I understand that making things work properly is only half of the task - the other half is to ensure its security. In professional environments, security vulnerabilities can have serious consequences.
### Determine my next learning direction
After this week's study, I have realized that I have some deficiencies that need to be addressed. I have gained a general understanding of PHP's syntax and related concepts, but I haven't been able to build anything substantial with it yet. My plan is to create a small custom WordPress plugin - perhaps a simple contact form that stores submitted content in a custom database table. This project will combine form processing, database operations, security considerations, and the unique features of WordPress. By building such a specific thing, these concepts will become more solid, and it will also provide me with a resume piece that can be shown to potential employers.
