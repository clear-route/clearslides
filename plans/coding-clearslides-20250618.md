# Clearslides Implementation Plan

This document outlines the detailed implementation plan for the `clearslides` project.

## 1. Create the directory structure for the custom theme

- **Tool**: `make_dir_in_sandbox`
- **Input**: `{"path":"clearslides/theme/clear-route","sandboxID":"7db03ebc-347c-40a8-a2f2-8297f30bfa00"}`

## 2. Create a `package.json` file for the custom theme

- **Tool**: `write_file_in_sandbox`
- **Input**: `{"content":"{\n  \"name\": \"@slidev/theme-clear-route\",\n  \"version\": \"0.0.1\",\n  \"private\": true,\n  \"main\": \"index.js\"\n}","path":"clearslides/theme/clear-route/package.json","sandboxID":"7db03ebc-347c-40a8-a2f2-8297f30bfa00"}`

## 3. Create the `styles` directory and the `index.css` file

- **Tool**: `write_file_in_sandbox`
- **Input**: `{"content":"/* Custom styles for the ClearRoute theme */\n","path":"clearslides/theme/clear-route/styles/index.css","sandboxID":"7db03ebc-347c-40a8-a2f2-8297f30bfa00"}`

## 4. Create the `layouts` directory and the `default.vue` layout

- **Tool**: `write_file_in_sandbox`
- **Input**: `{"content":"<template>\n  <div class=\"slidev-layout default\">\n    <slot />\n  </div>\n</template>","path":"clearslides/theme/clear-route/layouts/default.vue","sandboxID":"7db03ebc-347c-40a8-a2f2-8297f30bfa00"}`

## 5. Create the `title.vue` layout

- **Tool**: `write_file_in_sandbox`
- **Input**: `{"content":"<template>\n  <div class=\"slidev-layout title\">\n    <div class=\"my-auto w-full\">\n      <slot />\n    </div>\n  </div>\n</template>","path":"clearslides/theme/clear-route/layouts/title.vue","sandboxID":"7db03ebc-347c-40a8-a2f2-8297f30bfa00"}`

## 6. Create the `components` directory and the `Logo.vue` component

- **Tool**: `write_file_in_sandbox`
- **Input**: `{"content":"<template>\n  <div class=\"abs-br m-6 flex gap-2\">\n    <img src=\"/logo.svg\" class=\"h-10\" />\n  </div>\n</template>","path":"clearslides/theme/clear-route/components/Logo.vue","sandboxID":"7db03ebc-347c-40a8-a2f2-8297f30bfa00"}`

## 7. Update the `slides.md` file to use the new theme and layouts

- **Tool**: `write_file_in_sandbox`
- **Input**: `{"content":"---\ntheme: 'clear-route'\n---\n\n# Hello, Slidev!\n\n---\nlayout: title\n---\n\n# Title Slide\n","path":"clearslides/slides.md","sandboxID":"7db03ebc-347c-40a8-a2f2-8297f30bfa00"}`
