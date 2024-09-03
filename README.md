# ThemeToggle Component

## Overview

The `ThemeToggle` component is a React-based toggle switch that allows users to switch between light and dark themes on a website. This component is built with DaisyUI and Tailwind CSS, ensuring it is highly customizable and easy to integrate into any project that utilizes these frameworks.

The theme is persisted using `localStorage`, so users' theme preferences will be remembered on subsequent visits. Additionally, it checks the user's system preferences for light or dark mode if no theme is stored in `localStorage`.

## Features

- **Persistent Theme:** The user's selected theme is saved in `localStorage` and automatically applied on future visits.
- **System Preference Detection:** If no theme is saved, the component will check the user's system preference for light or dark mode and apply it accordingly.
- **Responsive Design:** The component is fully responsive, utilizing Tailwind CSS and DaisyUI for styling.
- **SVG Icons:** The toggle switch includes SVG icons for sun and moon, representing light and dark themes, respectively.

## Usage

### Installation

Ensure you have the required dependencies installed:

```bash
npm install react tailwindcss daisyui
```

After installing the dependencies, you need to initialize Tailwind CSS in your project:

```bash
npx tailwindcss init
```

This command will generate a `tailwind.config.js` file in your project’s root directory, which you can then modify to include DaisyUI and customize your Tailwind CSS setup.

### Tailwind CSS Configuration

In your `tailwind.config.js` file, ensure that DaisyUI is included in the plugins array, and the themes are enabled or customized as needed:

```javascript
module.exports = {
  // Other Tailwind CSS configuration...

  plugins: [
    require('daisyui'), // Add DaisyUI here
  ],
  daisyui: {
    themes: ["light", "dark"], // Enable themes or customize them
  },
};
```

### Implementation

Import the `ThemeToggle` component and include it in your application:

```javascript
import React from 'react';
import ThemeToggle from './ThemeToggle';

function App() {
    return (
        <div className="App">
            <ThemeToggle className="my-4" />
            {/* Other components */}
        </div>
    );
}

export default App;
```

### Component Props

- **className** (optional): A string of class names to apply custom styles to the theme toggle container.

## How It Works

1. **Theme Initialization:** When the component mounts, it first checks `localStorage` for a saved theme. If no saved theme is found, it checks the user's system preferences using `window.matchMedia`. If no preferences are detected, it defaults to the light theme.

2. **Theme Persistence:** When the user toggles the theme switch, the new theme is saved in `localStorage` and immediately applied to the document root (`<html>` tag) via the `data-theme` attribute.

3. **SVG Icons:** The toggle switch is accompanied by SVG icons representing the current theme, providing a visual cue to users about the theme state.

## Customization

- **Themes:** Customize the available themes in the `tailwind.config.js` file under the `daisyui` key.
- **Styling:** Use Tailwind CSS classes to style the toggle switch and its container. You can pass additional class names through the `className` prop.

## Example

```javascript
import React from 'react';
import ThemeToggle from './ThemeToggle';

function ExampleComponent() {
    return (
        <div className="example-component">
            <h1>Welcome to the Theme Toggle Example</h1>
            <ThemeToggle className="mt-4" />
        </div>
    );
}

export default ExampleComponent;
```

This component will display a header and the theme toggle switch. When the switch is toggled, the theme will change between light and dark modes, with the preference stored in `localStorage`.

## Conclusion

The `ThemeToggle` component is an easy-to-use solution for adding theme toggling functionality to your website or application. By leveraging Tailwind CSS and DaisyUI, it offers both flexibility and ease of customization. Whether you're building a simple site or a complex application, this component will help enhance the user experience by providing a seamless way to switch between light and dark modes.

### GDPR Compliance

The `ThemeToggle` component uses cookies solely to store site settings, such as the user's theme preference (light or dark mode). These cookies do not contain or process any personal data and are considered "necessary" cookies under the GDPR.

Since the cookies used do not involve personal information, explicit user consent is not required. However, it is recommended to inform users about the usage of these cookies through your site's privacy policy or a brief notice, ensuring transparency and compliance with GDPR principles.