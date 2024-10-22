# Oksilyum UI Kit

![Version](https://img.shields.io/npm/v/oksilyum)
![License](https://img.shields.io/npm/l/oksilyum)

## Table of Contents
- [Key Features](#key-features)
- [Installation](#installation)
- [Usage](#usage)
  - [Grid System Documentation](#grid-system-documentation)
  - [Breakpoint Documentation](#breakpoints-documentation)
  - [Component Classes](#component-classes)
- [API Documentation](#api-documentation)
- [Contributing](#contributing)
- [License](#license)

## Key Features

- **Dynamic Layout Management**: Automatically adjusts element dimensions based on their content, ensuring a polished and uniform appearance throughout your application.
- **Responsive Design Support**: Built with responsive design principles in mind, making it easy to create layouts that adapt seamlessly to different devices and screen sizes.
- **Ease of Use**: With a straightforward API and easy integration, developers can quickly implement the Oksilyum UI Kit into their projects without extensive setup.
- **Framework Agnostic**: Designed to work independently of any specific framework, allowing developers to leverage its features in various web development environments.


## Installation

To install Oksilyum, you can use npm or yarn:

```bash
npm install oksilyum
```
OR
```bash 
yarn add oksilyum
```

## Usage

## Grid System Documentation

### Basic Setup

#### First Step
```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/onurcanalpp/oksilyum-ui-kit/src/layout/grid.css">
```

### HTML Structure of grids and usage 
The grid system in the `Oksilyum` provides a flexible and responsive layout framework designed to simplify the process of creating complex layouts. It is built on a 12-column grid structure, allowing for precise control over how content is displayed across various screen sizes.
### Preview
![Grid System Col Preview](https://www.onurcanalp.com.tr/readme/oksilyum/col-num-usage.png)
```html
<div class="container">
    <div class="row header-wrapper">
        <div class="col-4">
            Header Content Logo
        </div>
        <div class="col-8">
            Header Menu
        </div>
    </div>
    <div class="row product-wrapper">
        <div class="col-3 col-xl-4 col-lg-6 col-md-12">
            Product 1
        </div>
        <div class="col-3 col-xl-4 col-lg-6 col-md-12">
            Product 2
        </div>
        <div class="col-3 col-xl-4 col-lg-6 col-md-12">
            Product 3
        </div>
        <div class="col-3 col-xl-4 col-lg-6 col-md-12">
            Product 4
        </div>
    </div>
</div>
```

## Extra col usage
In the example below, three columns will automatically adjust their widths to occupy equal space within the row:
### Preview
![Grid System Col Preview](https://www.onurcanalp.com.tr/readme/oksilyum/col-usage.png)
```html
<div class="container">
    <div class="row">
        <div class="col">product-1</div>
        <div class="col">product-2</div>
        <div class="col">product-3</div>
        <div class="col">product-4</div>
    </div>
</div>
```

## Breakpoints Documentation

### Basic Setup

#### First Step
```scss
@import 'oksilyum/layout/_breakpoints.scss';

// Default Breakpoints values coming from import (_breakpoints.scss) don't copy this I just want to let u know current breakpoints. :)
$breakpoints: (
    'xxl': 1599.99px, 
    'xl': 1199.99px,  
    'lg': 991.99px,   
    'md': 767.99px,   
    'sm': 575.99px    
) !default;
```
### Second Step (Optional)  If you need or want to override breakpoints:
```scss
$breakpoints: map-merge($breakpoints, (
    'xl': 1620px
));
```
### SCSS Structure 
We have lots of mixins(methods) for breakpoints I will shou you the how can you use these methods in your scss code
```scss
.product-item {
    flex: 50%;
    font-size: 24px;
    background-color: red;

    // The 'lg-down' mixin applies styles for screen sizes below the lg breakpoint.
    @include lg-down {
        flex: 25%;
        font-size: 20px;
        background: yellow; // Changes background color for smaller screens
    }

    // The 'between-md-sm' mixin allows you to define styles specifically for screens
    // that fall between the large and medium breakpoints.
    @include between-md-sm {
        flex: 40%; // Adjusts flex size for screens between lg and md
        font-size: 22px; // Sets a different font size for this range
        background: blue; // Changes background color for this range
    }
}

```

## API Documentation Breakpoints

### SCSS Breakpoint Mixins

The SCSS breakpoints provide a set of mixins that allow developers to create responsive styles based on different screen sizes. These mixins enable you to define styles that adapt to a variety of devices, ensuring a consistent and user-friendly experience across different platforms.

- The `xxl-down`, `xl-down`, `lg-down`, `md-down`, and `sm-down` mixins are used to apply styles for devices with maximum widths, allowing you to tailor your design for larger screens down to smaller devices. This is particularly useful for managing layouts, font sizes, and element visibility as screens shrink.

- Conversely, the `xxl-up`, `xl-up`, `lg-up`, `md-up`, and `sm-up` mixins target devices with minimum widths, ensuring that your styles expand appropriately for larger screens. This helps maintain design integrity on larger devices, enhancing the user experience.

- Additionally, the `between` mixins allow you to apply styles for devices within specific width ranges, providing greater control over how elements are styled during transitions between different screen sizes. This is particularly helpful for fine-tuning layouts and ensuring that your design looks great across all devices.

By utilizing these mixins, developers can create fluid and responsive designs that automatically adjust to the user's device, making it easier to maintain a consistent look and feel throughout the application.

**Usage:**

```scss
.product-item {
    flex: 50%;
    // Extra extra large devices (up to 1599.99px)
    @include xxl-down { ... }
    // Extra large devices (up to 1199.99px)
    @include xl-down { ... }
    // Large devices (up to 991.99px)
    @include lg-down { ... }
    // Medium devices (up to 767.99px)
    @include md-down { ... }
    // Small devices (up to 575.99px)
    @include sm-down { ... }
    // Extra extra large devices (from 1599.99px and up)
    @include xxl-up { ... }
    // Extra large devices (from 1199.99px and up)
    @include xl-up { ... }
    // Large devices (from 991.99px and up)
    @include lg-up { ... }
    // Medium devices (from 767.99px and up)
    @include md-up { ... }
    // Small devices (from 575.99px and up)
    @include sm-up { ... }
    // Devices between extra large and extra extra large
    @include between-xxl-xl { ... }
    // Devices between large and extra large
    @include between-xl-lg { ... }
    // Devices between medium and large
    @include between-lg-md { ... }
    // Devices between small and medium
    @include between-md-sm { ... }
    // Devices smaller than small
    @include between-sm-xs { ... }
}

```

## Examples


## Contributing

We welcome contributions to SizerJS! To ensure a smooth process, please follow these guidelines:

### How to Contribute

1. **Fork the Repository**
   - Click on the "Fork" button at the top right of the repository page to create a copy of this repository under your GitHub account.

2. **Clone Your Fork**
   - Clone your forked repository to your local machine using the following command:
   ```bash
   git clone https://github.com/your-username/oksilyum-ui-kit.git
   ```

3. **Create a New Branch**
    - Clone your forked repository to your local machine using the following command:
    ```bash
    git checkout -b feature/YourFeatureName
    ```

4. **Make Your Changes**
    - Implement your changes and ensure that they align with the project's coding style. Consider adding tests if applicable.
    
5. **Test Your Changes**
    - Run the existing tests to make sure everything is working as expected. If you've added new features, please include tests for them.

6. **Create a New Branch**
    - Commit your changes with a descriptive message:

    ```bash
    git commit -m "Add a brief description of your changes"
    ``` 
7. **Push to Your Branch**
    - Push your changes to your forked repository:

    ```bash
    git push origin feature/YourFeatureName
    ``` 
8. **Create a Pull Request**
    - Navigate to the original repository where you want to propose your changes. Click on the "Pull Requests" tab, then click on "New Pull Request."
    - Select your branch from the "compare" dropdown and click "Create Pull Request."
    - Provide a detailed description of your changes and why they should be merged.
