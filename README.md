# Trippyy

The website for "Trippy Animations" has been created. Now, let's implement the functionality to make the button trigger random animations.

### Steps to Add Functionality

1. **HTML**:
   - Create a page with a red button and a container for the animations.

2. **CSS**:
   - Style the button and animation container.

3. **JavaScript**:
   - Add a script to play random animations on button click.

### Implementation Code

Here's a more detailed code snippet to get your site up and running:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Trippy Animations</title>
    <style>
        body {
            display: flex;
            flex-direction: column;
            justify-content: center;
            align-items: center;
            height: 100vh;
            background-color: #000;
            margin: 0;
            color: #fff;
        }
        #trippy-button {
            background-color: red;
            border: none;
            color: white;
            padding: 15px 32px;
            text-align: center;
            font-size: 16px;
            cursor: pointer;
            margin-bottom: 20px;
        }
        #animation-container {
            width: 100px;
            height: 100px;
            display: none;
        }
        /* Sample animations */
        .animation1 {
            animation: spin 2s linear infinite;
        }
        .animation2 {
            animation: pulse 2s ease infinite;
        }
        @keyframes spin {
            0% { transform: rotate(0deg); }
            100% { transform: rotate(360deg); }
        }
        @keyframes pulse {
            0%, 100% { transform: scale(1); }
            50% { transform: scale(1.5); }
        }
    </style>
</head>
<body>

<button id="trippy-button">Push Me</button>
<div id="animation-container"></div>

<script>
    const animations = ['animation1', 'animation2'];

    document.getElementById('trippy-button').addEventListener('click', () => {
        const randomAnimation = animations[Math.floor(Math.random() * animations.length)];
        const animationContainer = document.getElementById('animation-container');

        // Set and show animation
        animationContainer.className = randomAnimation;
        animationContainer.style.display = 'block';

        // Remove animation after 20 seconds
        setTimeout(() => {
            animationContainer.style.display = 'none';
        }, 20000);
    });
</script>

</body>
</html>
```

### Hosting

You can host your website using platforms like GitHub Pages, Netlify, or Vercel for free. If you need assistance with deployment or further customization, let me know!
