# Slidev Presentation Guide: Clear Route Theme

This guide provides comprehensive context for agents to create rich and detailed slideshows using the pre-defined templates and components within the `clear-route` Slidev theme. The goal is to enable the automatic generation of presentations that adhere to the established visual and structural guidelines.

## Theme Overview

The `clear-route` theme is designed for modern, visually appealing presentations with a focus on clear communication. It leverages Vue.js components and Tailwind CSS for flexible and consistent styling.

## Available Layout Templates

The theme provides several pre-built layout templates, each designed for a specific presentation purpose. When creating a new slide, always specify the `layout` in the frontmatter.

### 1. `title.vue`
*   **Purpose**: The main title slide for the presentation.
*   **Slots**:
    *   `heading`: Main title of the presentation. Supports multiline headings with per-line coloring using `<span>` tags and Tailwind CSS color classes (e.g., `<span class="text-clear-route-white block">`).
    *   `subheading`: A subtitle or tagline for the presentation.
    *   `date`: The date of the presentation.
*   **Example Usage**:
    ```markdown
    ---
    layout: title
    ---

    <template v-slot:heading>
    <span class="text-clear-route-white block">Your Main</span>
    <span class="text-clear-route-green block">Presentation Title</span>
    </template>
    <template v-slot:subheading>A compelling subtitle</template>
    <template v-slot:date>June 2025</template>
    ```

### 2. `section-title.vue`
*   **Purpose**: Used for introducing new sections or phases of the presentation. Features an image and customizable primary color.
*   **Slots**:
    *   `phase`: A short text indicating the phase or section number (e.g., "PHASE 1").
    *   `main-heading`: The main heading for the section.
    *   `sub-heading`: A subheading providing more detail.
    *   Default slot: For additional body content below the headings.
*   **Props**:
    *   `imageSrc` (String): Path to an SVG icon or image (e.g., `'/icons/Discover.svg'`). Icons are typically located in `public/icons/`.
    *   `backgroundGradient` (String): CSS variable for the background gradient (e.g., `'var(--gradient-dark-to-green)'`).
    *   `primaryColor` (String): CSS variable for the primary color used in the layout (e.g., `'var(--clear-route-green-light)'`).
*   **Example Usage**:
    ```markdown
    ---
    layout: section-title
    imageSrc: '/icons/Discover.svg'
    backgroundGradient: 'var(--gradient-dark-to-green)'
    primaryColor: 'var(--clear-route-green-light)'
    ---

    <template v-slot:phase>PHASE 1</template>
    <template v-slot:main-heading>DISCOVERY</template>
    <template v-slot:sub-heading>HOLISTIC END TO END REVIEW:</template>

    Your detailed section content goes here.
    ```

### 3. `generic-header.vue`
*   **Purpose**: A versatile layout with a prominent heading and a flexible body section for various content types.
*   **Slots**:
    *   `heading`: Main heading for the slide. Supports multiline headings with per-line coloring.
    *   `body`: A flexible slot where you can insert any content, including plain text, HTML, or other Vue components.
*   **Props**:
    *   `backgroundGradient` (String): CSS variable for the background gradient.
    *   `bodyColor` (String): CSS variable for the text color within the body slot (e.g., `'var(--clear-route-white)'`).
*   **Example Usage**:
    ```markdown
    ---
    layout: generic-header
    backgroundGradient: 'var(--gradient-dark-to-purple)'
    bodyColor: 'var(--clear-route-white)'
    ---

    <template v-slot:heading>
      <span class="text-clear-route-purple block">Your Custom</span>
      <span class="text-clear-route-white block">Headline Here</span>
    </template>

    <template v-slot:body>
      <p>This is where your main content goes. You can use paragraphs, lists, or even embed other components.</p>
      <ul>
        <li>Item 1</li>
        <li>Item 2</li>
      </ul>
    </template>
    ```

### 4. `empty.vue`
*   **Purpose**: Provides a blank canvas with a customizable background, ideal for highly custom slides or embedding large media.
*   **Slots**:
    *   `body`: A flexible slot for any content.
*   **Props**:
    *   `backgroundGradient` (String): CSS variable for the background gradient.
*   **Example Usage**:
    ```markdown
    ---
    layout: empty
    backgroundGradient: 'var(--gradient-dark-to-orange)'
    ---

    <template v-slot:body>
      <h2 class="text-clear-route-white">Completely Custom Content</h2>
      <img src="/path/to/your/image.png" alt="Custom Image" />
    </template>
    ```

### 5. `section-overview.vue`
*   **Purpose**: Designed for an overview or case study slide, featuring an image on the right, a multiline heading, and a body slot.
*   **Slots**:
    *   `caption`: A small caption above the main heading (e.g., "Case Study").
    *   `heading`: Main heading for the slide. Supports multiline headings with per-line coloring.
    *   `body`: A flexible slot for detailed content.
*   **Props**:
    *   `imageSrc` (String): Path to an SVG icon or image (e.g., `'/icons/Vertical.svg'`).
    *   `gradient` (String): CSS variable for the background gradient (e.g., `'var(--gradient-dark-to-purple)'`).
*   **Example Usage**:
    ```markdown
    ---
    layout: section-overview
    imageSrc: '/icons/Vertical.svg'
    gradient: 'var(--gradient-dark-to-purple)'
    ---

    <template v-slot:caption>Our Vision</template>
    <template v-slot:heading>
      <span class="text-clear-route-white block">Why We</span>
      <span class="text-clear-route-green block">Are Here...</span>
    </template>

    <template v-slot:body>
      <p class="text-clear-route-white">This section provides an overview of our mission and goals.</p>
    </template>
    ```

### 6. `three-column.vue`
*   **Purpose**: A layout for presenting content in three distinct columns.
*   **Slots**:
    *   `heading`: Main heading for the slide.
    *   `left`: Content for the leftmost column.
    *   `center`: Content for the middle column.
    *   `right`: Content for the rightmost column.
*   **Props**:
    *   `backgroundGradient` (String): CSS variable for the background gradient.
    *   `verticalAlign` (String): Controls vertical alignment of content within columns. Accepts `'top'`, `'center'`, or `'bottom'`.
*   **Example Usage**:
    ```markdown
    ---
    layout: three-column
    backgroundGradient: 'var(--clear-route-grey-dark)'
    verticalAlign: 'center'
    ---

    <template v-slot:heading>
      <span class="text-clear-route-orange block">Our</span>
      <span class="text-clear-route-white block">Approach</span>
    </template>

    <template v-slot:left>
      <h3 class="text-clear-route-white mb-4">Column 1 Title</h3>
      <p>Content for the first column.</p>
    </template>

    <template v-slot:center>
      <h3 class="text-clear-route-white mb-4">Column 2 Title</h3>
      <p>Content for the second column.</p>
    </template>

    <template v-slot:right>
      <h3 class="text-clear-route-white mb-4">Column 3 Title</h3>
      <p>Content for the third column.</p>
    </template>
    ```

### 7. `two-column.vue`
*   **Purpose**: A layout for presenting content in two distinct columns.
*   **Slots**:
    *   `heading`: Main heading for the slide.
    *   `left`: Content for the leftmost column.
    *   `right`: Content for the rightmost column.
*   **Props**:
    *   `backgroundGradient` (String): CSS variable for the background gradient.
    *   `verticalAlign` (String): Controls vertical alignment of content within columns. Accepts `'top'`, `'center'`, or `'bottom'`.
*   **Example Usage**:
    ```markdown
    ---
    layout: two-column
    backgroundGradient: 'var(--clear-route-grey-dark)'
    verticalAlign: 'center'
    ---

    <template v-slot:heading>
      <span class="text-clear-route-orange block">Key</span>
      <span class="text-clear-route-white block">Insights</span>
    </template>

    <template v-slot:left>
      <h3 class="text-clear-route-white mb-4">Insight 1</h3>
      <p>Detailed explanation of the first insight.</p>
    </template>

    <template v-slot:right>
      <h3 class="text-clear-route-white mb-4">Insight 2</h3>
      <p>Detailed explanation of the second insight.</p>
    </template>
    ```

## Available Components

These are reusable Vue components that can be embedded within the slots of your layout templates.

### 1. `Logo.vue`
*   **Purpose**: Displays a logo image.
*   **Props**:
    *   `name` (String): The base name of the logo file (e.g., `'logo-landscape'`). The theme will automatically resolve the full path (e.g., `public/logos/logo-landscape.png`).
    *   `height` (String): A Tailwind CSS height utility class (e.g., `'h-15'`).
*   **Example Usage**:
    ```html
    <Logo name="logo-landscape" height="h-15" />
    ```

### 2. `IconItem.vue`
*   **Purpose**: Displays an SVG icon next to a line of text, useful for lists or key points.
*   **Props**:
    *   `icon` (String): Path to an SVG icon (e.g., `'/icons/Trust.svg'`). Icons are typically located in `public/icons/`.
    *   `text` (String): The text content to display next to the icon.
*   **Example Usage**:
    ```html
    <IconItem icon="/icons/Trust.svg" text="Goal: Achieve decarbonised electricity by 2035" />
    ```

## Content Creation Guidelines

When creating your presentation content, please adhere to the following guidelines to ensure consistency and maintainability:

1.  **Prioritize Templates and Components**: Always try to use the provided layout templates and reusable components first. They are designed to maintain the theme's aesthetic and functionality.
2.  **Utilize Slots**: Pass your content into the appropriate slots defined by each layout. This keeps your Markdown clean and separates content from presentation logic.
3.  **Styling within Slots**: For text and basic elements within slots, leverage Tailwind CSS utility classes directly in your Markdown. This is especially useful for per-line coloring in headings (e.g., `<span class="text-clear-route-green block">`).
4.  **Inline HTML/Vue as a Last Resort**: If a specific visual or interactive element cannot be achieved using the existing templates or components, you may write custom HTML or Vue code directly within a slot. However, this should be considered a last resort to avoid cluttering the Markdown and making it harder to maintain.
5.  **Icon Paths**: When referencing icons, use absolute paths starting from the `public` directory (e.g., `/icons/Discover.svg`).

## Example Slideshow

For a practical demonstration of how to use these templates and components, please refer to the `example.md` file at the root of this project. It contains various slides showcasing different layouts and component usages.

---