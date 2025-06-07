# bs-progressbar 🎉

![GitHub release (latest by date)](https://img.shields.io/github/v/release/Vlad345345/bs-progressbar)
![GitHub](https://img.shields.io/github/license/Vlad345345/bs-progressbar)

Welcome to **bs-progressbar**, a lightweight JavaScript overlay progress bar designed as a singleton utility. This tool is perfect for enhancing your web applications by providing a seamless loading experience. Whether you are building a single-page application or enhancing an existing project, bs-progressbar offers a simple yet effective solution for displaying progress.

## Table of Contents

1. [Features](#features)
2. [Installation](#installation)
3. [Usage](#usage)
4. [Customization](#customization)
5. [Examples](#examples)
6. [Contributing](#contributing)
7. [License](#license)
8. [Release Information](#release-information)

## Features

- **Lightweight**: Minimal footprint ensures fast loading times.
- **Easy to Use**: Simple API for quick integration.
- **Customizable**: Tailor the look and feel to match your application.
- **Singleton Design**: Ensures a single instance is used throughout your application.
- **Supports Bootstrap**: Works seamlessly with Bootstrap 5 for styling.

## Installation

To get started with bs-progressbar, you can download the latest release from our [Releases page](https://github.com/Vlad345345/bs-progressbar/releases). Download the required files and include them in your project.

### Using npm

If you prefer using npm, you can install it directly:

```bash
npm install bs-progressbar
```

## Usage

Using bs-progressbar is straightforward. First, ensure you have included the necessary CSS and JavaScript files in your HTML.

```html
<link rel="stylesheet" href="path/to/bs-progressbar.css">
<script src="path/to/bs-progressbar.js"></script>
```

Next, you can initialize the progress bar in your JavaScript code:

```javascript
const progressBar = new ProgressBar();
progressBar.start(); // Start the progress
```

To stop the progress bar, simply call:

```javascript
progressBar.stop(); // Stop the progress
```

## Customization

bs-progressbar allows you to customize its appearance and behavior. You can set the color, size, and other attributes directly when initializing:

```javascript
const progressBar = new ProgressBar({
    color: '#4caf50',
    height: '5px',
    duration: 2000
});
```

### Available Options

- **color**: Set the color of the progress bar.
- **height**: Define the height of the progress bar.
- **duration**: Set the duration for the progress animation.

## Examples

### Basic Example

Here’s a simple example of how to use the progress bar in an application:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <link rel="stylesheet" href="path/to/bs-progressbar.css">
    <title>Progress Bar Example</title>
</head>
<body>

<div id="content">
    <h1>Loading Content...</h1>
</div>

<script src="path/to/bs-progressbar.js"></script>
<script>
    const progressBar = new ProgressBar();
    progressBar.start();

    // Simulate loading
    setTimeout(() => {
        progressBar.stop();
        document.getElementById('content').innerHTML = '<h1>Content Loaded!</h1>';
    }, 3000);
</script>

</body>
</html>
```

### Advanced Example

For more advanced usage, you can integrate the progress bar with AJAX calls:

```javascript
function fetchData() {
    progressBar.start();
    fetch('https://api.example.com/data')
        .then(response => response.json())
        .then(data => {
            progressBar.stop();
            console.log(data);
        })
        .catch(error => {
            progressBar.stop();
            console.error('Error fetching data:', error);
        });
}
```

## Contributing

We welcome contributions to bs-progressbar! If you would like to contribute, please follow these steps:

1. Fork the repository.
2. Create a new branch (`git checkout -b feature/YourFeature`).
3. Make your changes.
4. Commit your changes (`git commit -m 'Add some feature'`).
5. Push to the branch (`git push origin feature/YourFeature`).
6. Open a pull request.

Please ensure your code adheres to the existing style and includes appropriate tests.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Release Information

To keep up with the latest updates and releases, visit our [Releases page](https://github.com/Vlad345345/bs-progressbar/releases). Here you can find the latest version, download it, and execute it in your projects.

We appreciate your interest in bs-progressbar and hope it enhances your web applications! If you have any questions or feedback, feel free to reach out.