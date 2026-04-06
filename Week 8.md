# 25 / Mar / 2026

# Week 8 - WordPress: Developing Custom Themes

# Learning Activities & Resources

This week, I learned how to build a custom WordPress theme from scratch using a basic theme, focusing on creating a reusable, dynamic theme rather than modifying an existing one or building a theme for a specific website.

- I watched the week 8 lecture videos (about starter themes and Sass).

- I watched the LinkedIn Learning course: Building a Theme from Scratch (setting up the development environment, the design-to-development process, setting up the basic theme, building the header and menu). (https://www.linkedin.com/learning/wordpress-building-themes-from-scratch-using-underscores-2/style-the-default-header?resume=false&u=2223545)

- I explored the Underscores basic theme locally and looked at and understood its file structure.

- I set up my local development environment (Docker, WSL).

- I reflected on the questions I encountered in this course and wrote a learning experiment report.

```txt
Learning Experiment
Hypothesis
If I take structured notes while watching video tutorials, instead of just watching, I will understand the content more clearly and remember it better.
Reason for this hypothesis:
Over the past few weeks, I've watched many LinkedIn Learning courses, but usually just passively. I think taking organized notes might help me actively process information.
Experiment
To verify this hypothesis, I designed the following experiment:
    1.Select two similar learning resources
        - Resource A: Watch a 20–30-minute PHP tutorial without taking notes.
        - Resource B: Watch another 20–30-minute PHP tutorial of similar difficulty, while actively taking structured notes.
    2.Learning Tasks for Both Resources
    After watching each video:
        - Write a short summary from memory
        - Try to complete a small exercise (e.g., write a simple PHP script or website).
    3.Measurement / Comparison
    I used three criteria to evaluate the results:
        - Accuracy of the summary
        - Number of errors in the exercise task
        - My confidence in the content afterwards.
    4.Results
        - The summary written after taking notes was more complete and organized.
        - Fewer revisions were needed for the exercise task after taking notes.
        - Because I could refer to my notes while practicing, I felt more confident.
Conclusion
The results support the hypothesis—taking structured notes helps me learn better than passively watching videos.
```

# Estimated Hours:

Around 5 hours 22 minutes

# Content Insights

### Understanding the Header Template Structure

The course covered the header.php file in the Underscores theme. I learned that a well-structured header template includes:
- `<!DOCTYPE html>` and `<html>` start tags with the `language_attributes()` attribute
- `<head>` section with the `wp_head()` hook
- `<body>` tag with the `body_class()` function
- Ballpoints to content
- Website branding section
- Navigation menu section

What surprised me was that most of the header content is handled by WordPress functions, rather than hard-coded HTML code. For example, `bloginfo('name')` and `bloginfo('description')` fetch information from a database. The custom logo functionality is handled by the `the_custom_logo()` function, which returns an `<img>` tag if a logo has been uploaded, otherwise nothing. This dynamic approach is key to the theme's reusability.

### Understanding the Difference Between Custom Themes and Child Themes

Previously, I learned about child themes, a safe way to modify an existing theme. This week, I discovered a fundamental difference between custom themes and child themes. Child themes inherit from a parent theme and override specific parts of it, while custom themes define the entire website's look and style from scratch. This difference is crucial for project planning. If a client wants a unique design that differs from any existing theme, then building a custom theme is the right choice. If they like an existing theme but need to make some minor tweaks, then child themes are more efficient.

### Getting Started Theme: No Need to Start from Scratch

I downloaded the Underscores theme and studied its file structure. What impressed me was its apparent simplicity—basic styles and a minimalist layout. But that's precisely its strength. It provides the correct template hierarchy and WordPress integration without imposing any design decisions. The website doesn't need to be designed from scratch.

# Career/Employability/Learning Insights

Looking back, the learning path for this topic is logical: first child themes (modifying existing themes), then custom themes (creating from scratch). Both skills are crucial in practice. Maintaining a project might only require modifying child themes, while building a new website might necessitate customizing the theme to meet specific design requirements.

Using Underscores' approach to getting started with themes perhaps reflects how developers actually work. Nobody wants to start by writing an empty `index.php` file to build a theme. They start with a solid foundation and build step by step.

### PHP Alternative Syntax: Small Changes, Big Impact

The alternative syntax for control structures initially seems insignificant. But after writing some template files, I understood why WordPress uses it. Comparison:

```php
<?php if (have_posts()) { ?>
    <?php while (have_posts()) { ?>
        <?php the_post(); ?>
        <h2><?php the_title(); ?></h2>
    <?php } ?>
<?php } ?>
```

Using the alternative syntax:

```php
<?php if (have_posts()) : ?>
    <?php while (have_posts()) : the_post(); ?>
        <h2><?php the_title(); ?></h2>
    <?php endwhile; ?>
<?php endif; ?>
```

The second version has fewer nested PHP tags and a clearer closing statement. This may seem insignificant, but in teamwork, highly readable code can reduce errors and speed up maintenance.

## Personal Learning Journey Reflection

Looking back on the first week, I gained some understanding of content management systems. Now I can build custom themes. This progress is truly gratifying. The key is shifting from passive to active learning (actually modifying theme files, writing PHP code snippets, identifying problems, and fixing them).

In the ninth week, I plan to build a simple custom theme based on Underscores, just for practice and to learn how to write code. This will also help me better prepare for my current team projects.