# Landing Page Project
A complete landing page built from scratch using HTML and CSS, based on provided design mockups.

## Description
This project involves creating a webpage from design specifications. The goal is to master fundamental HTML structure and CSS styling—specifically layout architecture, positioning, typography, and color theory.

## Project Goals
Through this project, I aim to:
- Translate static visual designs into functional, semantic code
- Strengthen mastery of __Flexbox__ layout techniques
- Practice precise element positioning and box-model spacing
- Implement consistent typography and color palettes
- Establish a professional Git workflow with atomic, meaningful commits

## Technologies Used
- HTML5
- CSS3

## Key Features Implemented
- __Semantic HTML5:__ Used appropriate landmarks for accessibility and SEO
- __Modular Design:__ Implemented a `.btn` component system with primary and secondary modifiers
- __Design Fidelity:__ Matched typography, spacing, and color schemes to the original mockup

## Design System

### Color Palette
- ![#1F2937](https://placehold.co/15x15/1F2937/1F2937.png) `#1F2937` __Primary Dark:__ Header, Hero, and Footer background
- ![#3882F6](https://placehold.co/15x15/3882F6/3882F6.png) `#3882F6` __Action Blue:__ Buttons, image borders, and Call to Action
- ![#F9FAF8](https://placehold.co/15x15/F9FAF8/F9FAF8.png) `#F9FAF8` __Main White:__ Logo and primary Hero text
- ![#E5E7EB](https://placehold.co/15x15/E5E7EB/E5E7EB.png) `#E5E7EB` __Secondary Grey:__ Quote background and Hero subtext

### Typography
- __Primary Font:__ [Roboto](https://fonts.google.com/specimen/Roboto) (Sans-serif)
- __Weights Used:__
    - `300` (Light): Elegant, airy feel for quotes
    - `900` (Black): Strong visual hierarchy for headings and logos
    - `Regular/Italic`: Standard body text and author attributions.

## Challenges & Reflections
> [!NOTE]
> This section will document my learning journey, including what went well, challenges faced, and key insights gained.
>
> It will be updated throughout the project and completed after its completion.

### What Went Well
- __Layout Fidelity__

    Successfully balanced the hero section with information cards to match the design's intent.

- __Semantic Integrity__

    Utilized `<main>`, `<section>`, and `<blockquote>`to ensure readable and accessible code.

- __Style Accuracy__

    Integrated Google Fonts with multiple weights to achieve high-contrast, professional typography.

### Struggles & Solutions

#### __The Box Model__
I faced constant issues with layout consistency where elements would "break" their rows or overflow the screen despite having the "correct" widths assigned in CSS.

I discovered that I was fighting the browser's default `content-box` behavior, where any added padding or borders increased the element's total footprint beyond its defined width, making precise layout math nearly impossible.

##### __Solution:__
Implementing a global CSS reset to switch the project to `box-sizing: border-box`.

This was a turning point in my development process; it forced the browser to include padding and borders _within_ the specified width and height. This allowed me to manage spacing intuitively, ensuring that my element sizes remained predictable and that my Flexbox containers calculated space accurately.

#### __The "Alignment Lane"__
I struggled to maintain a cohesive visual flow across different sections. Diversely sized content—like the logo, hero text, and the call-to-action block—would "drift" to the edges of the screen on wider monitors, breaking the design's professional look.

Furthermore, applying a background color to a centered container would cause the background itself to stop at the container's edge rather than filling the section.

##### Solution
Implementing a global `.container` class with a fixed `max-width` and `margin: 0 auto` to create a consistent vertical "alignment lane."

To solve the background color issue, I learned to separate __Layout__ from __Design__. For the Call-to-Action section, I nested a `.cta-blue-box` _inside_ the container.

This allowed the container to handle the alignment while the inner box handled the blue background and rounded corners, ensuring the content stayed perfectly in the "lane" without the background bleeding incorrectly.

#### __Flexbox Nested Logic__
I needed to position the quote attribution (the author's name) on the far right side of the section, while keeping the quote text itself centered or left aligned.

I initially struggled to move this single element without affecting its siblings or the entire container's alignment. I wanted to avoid "hacky" fixes like excessive negative margins or absolute positioning, which often break responsive layouts.

##### Solution
While researching the relationship between flex containers and individual children, it lead me to the `align-self` property.

By implementing `align-self: flex-end`, I was able to override the parent container's default alignment for just that specific element.

This allowed me to precisely place the attribution along the cross-axis while maintaining a clean, flexible layout that adhered strictly to the design mockup's requirements.

### What I Learned
Throughout the duration of this project, I transitioned from basic HTML/CSS knowledge to a more technical understanding of layout architecture.

Key takeaways include:

- __The Power of Global Resets__

    I learned that implementing a global CSS reset (targeting `*`, `::before`, and `::after`) is vital for eliminating browser default inconsistencies and ensuring that `box-sizing: border-box` is applied project-wide for predictable element sizing.

- __Advanced Flexbox Orchestration__
    
    Beyond simple alignment, I practiced using Flexbox as a layout system.

    This included using `flex-direction: column` for vertical stacking in cards and quotes, and mastering `align-self` to manipulate individual items along the cross-axis without affecting their siblings.

- __Modular Component Design__

    By creating a reusable `.container` class, I learned how to separate "layout" (how wide the content is) from "styling" (colors, fonts, and borders).

    This modular approach made the site much easier to maintain and ensure visual consistency across different sections.

- __Translating Design Specs to Code__

    I improved my ability to read design mockups and spec sheets, accurately translating hex codes, pixel-perfect fonts sizes, and specific spacing requirements into a functional webpage.

- __Linting and Selector Specificity__

    I encountered and resolved `no-descending-specificity` errors by learning how CSS Linters analyze code. I learned to organize my CSS selectors from lowest specificity (Tag-based) to highest specificity (Class-based), ensuring a clean and predictable "Cascade."

### What I Would Do Differently
- __Mobile Responsiveness__

    While the current layout works perfectly on desktop, I would like to implement __Media Queries__ in the future to ensure the "card" section stacks vertically on smaller screens.

- __CSS Variable Usage__

    For a project with this many repeating colors (like the dark blue and the light grey), I would use __CSS Variables__ (e.g., `--main-bg-color`) to make it easier to update the theme in one place.

- __Image Optimization__

    I would explore using local, optimized images instead of external placeholder URLs to improve page load times and ensure the images are always available.

## Image Credits
- Hero Image: [Unsplash.it](https://unsplash.it)
- Card Illustrations: [Unsplash.it](https://unsplash.it)
- Design Mockups: Provided by [The Odin Project](https://www.theodinproject.com)

## Live Demo
[Odin Landing Page](https://l0rdphr3ak.github.io/odin-landing-page/)

## Acknowledgments
This project is part of [The Odin Project](https://www.theodinproject.com/) curriculum.