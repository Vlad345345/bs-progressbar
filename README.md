# Progressbar Overlay

A lightweight, zero-dependency JavaScript utility that displays a full-page overlay progress bar with optional caption, color customization, and a lazy-loaded singleton architecture. Ideal for blocking the UI during long-running tasks like data loading, form submission, or AJAX calls.

---

[Demo page](/example/index.html)

---

## 📦 Features

- ✅ Full-screen overlay to prevent user interaction while loading
- ✅ Lazy-loaded **singleton**: only initializes when first accessed
- ✅ Fully customizable:
  - Duration
  - Caption label
  - Overlay transparency
  - Bootstrap-compatible progress bar color
- ✅ Supports dynamic label updates mid-progress
- ✅ Clean removal of overlay after progress completion
- ✅ Zero dependencies – works in any modern browser

---

## 🌍 Browser Support

| Browser       | Supported |
|---------------|-----------|
| Chrome        | ✅        |
| Firefox       | ✅        |
| Safari        | ✅        |
| Edge          | ✅        |
| Opera         | ✅        |
| IE 11         | ⚠️ *untested, possibly partial* |

---

## 📥 Installation

### 1. Download or Clone

```bash
git clone https://github.com/yesman93/bs-progressbar.git
```

### 2. Include in Your HTML

```html
<script src="bs-progressbar.js"></script>
<link rel="stylesheet" href="bs-progressbar.css">
```

Or load via CDN:

```html
<script src="https://cdn.jsdelivr.net/gh/yesman93/bs-progressbar/bs-progressbar.js"></script>
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/yesman93/bs-progressbar/bs-progressbar.css">
```

---

## 🚀 Quick Start

```html
<script src="bs-bs-progressbar.js"></script>
<script>
  // Start the overlay progress bar
  Progressbar.start(5000, 'Processing...', false, 'bg-primary');

  // Update label after 2 seconds
  setTimeout(() => {
    Progressbar.update_label('Almost done...');
  }, 2000);

  // Stop and remove the progress bar after 4 seconds
  setTimeout(() => {
    Progressbar.stop(() => {
      alert('Complete!');
    });
  }, 4000);
</script>
```

---

## 📚 API Reference

The `Progressbar` is exposed as a **singleton** on the `window` object. Use `Progressbar` or `window.Progressbar` to access its methods. It can be accessed from e.g. inside of `<iframe>` using `parent.Progressbar`.

### `Progressbar.start(duration, label, transparent, color)`

**Description:** Starts the progress bar overlay.

| Parameter    | Type     | Default   | Description                                                                 |
|--------------|----------|-----------|-----------------------------------------------------------------------------|
| `duration`   | Number   | 5000      | Total time in milliseconds to simulate progress from 0% to 100%             |
| `label`      | String   | `""`      | Optional caption text displayed above the progress bar                      |
| `transparent`| Boolean  | `false`   | If true, uses a transparent overlay instead of a dark one                   |
| `color`      | String   | `'bg-dark'` | Bootstrap-compatible class for the progress bar color (e.g., `bg-success`)  |

**Example:**

```javascript
Progressbar.start(3000, 'Loading user data...', true, 'bg-warning');
```

---

### `Progressbar.update_label(label)`

**Description:** Dynamically updates the caption above the progress bar. Creates a label if it doesn’t already exist.

| Parameter | Type   | Description                          |
|-----------|--------|--------------------------------------|
| `label`   | String | New caption to display               |

**Example:**

```javascript
Progressbar.update_label('Validating credentials...');
```

---

### `Progressbar.stop(on_complete)`

**Description:** Stops and removes the progress overlay, optionally running a callback when the animation finishes.

| Parameter       | Type       | Description                                |
|-----------------|------------|--------------------------------------------|
| `on_complete`   | Function   | A callback to run after overlay is removed |

**Example:**

```javascript
Progressbar.stop(() => {
  console.log('Progress completed.');
});
```

---

## 🎨 Styling

The progress bar uses dynamic DOM creation. Add this `bs-progressbar.css` file for styling the backdrop and modal. You can expand or modify it to match your app’s design system.

```css
.progress-backdrop {
    position: fixed;
    top: 0; left: 0;
    width: 100vw; height: 100vh;
    background: rgba(0, 0, 0, 0.5);
    display: flex;
    align-items: center;
    justify-content: center;
    z-index: 9999;
}

.progress-backdrop.is-transparent {
    background: rgba(0, 0, 0, 0.05);
}

.progress-modal {
    background: white;
    width: 300px;
    padding: 1rem;
    border-radius: 0.5rem;
    box-shadow: 0 0 20px rgba(0,0,0,0.2);
}

.progress-caption {
    font-size: 0.85rem;
    font-weight: bold;
    margin-bottom: 0.5rem;
    opacity: 0.75;
    text-align: left;
}

.progress-bar {
    transition: width 0.2s ease;
}
```

📌 You can also use Bootstrap’s default `.progress` and `.progress-bar` styles if Bootstrap is already included in your project.

---

## 💡 Use Cases

- Blocking UI while sending AJAX requests
- Feedback for form submission
- Delayed modal operations
- Simulated loading for demo apps
- Multi-step workflows or onboarding

---

## 🤝 Contributing

Contributions are welcome! If you find a bug or want to add a feature:

1. Fork the repo
2. Create a new branch
3. Make your changes
4. Open a Pull Request

Please follow the existing style and naming conventions. Include doc comments when adding new functionality.

---

## 📄 License

This project is licensed under the [MIT License](LICENSE).

---

## 🙌 Author

Created by **TB**  
2025-05-18

If you use this in your project, consider giving it a ⭐ or sharing it! Feedback and ideas welcome.
