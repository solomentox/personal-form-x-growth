# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a **static HTML form application** for collecting client personal brand information. It's a single-page application with no build process, dependencies, or framework - just pure HTML, CSS, and vanilla JavaScript.

## Architecture

The entire application consists of only two files:
- `index.html` - Complete form interface with embedded styles and Web3Forms integration
- `form.js` - Handles form submission logic and user feedback

Key characteristics:
- **No package.json or npm scripts** - This is intentionally a zero-dependency project
- **No build process** - Files are served directly, no compilation needed
- **Web3Forms API** - Form submissions are handled by Web3Forms (API key embedded in HTML)
- **Dark theme UI** - Styled with shadcn/ui-inspired CSS variables

## Development Approach

Since this is a static site with no build process:
- Edit files directly - changes are immediately reflected when refreshing the browser
- No commands to run for development, testing, or building
- To test locally, simply open `index.html` in a browser or use any static file server

## Important Implementation Details

1. **Form Validation**: All form fields are marked as required in the HTML. The JavaScript adds enhanced UX but the form maintains basic functionality without it.

2. **API Integration**: The Web3Forms access key is embedded directly in the HTML (`dfde76ce-726c-42ce-8408-df1a7eb77917`). This is intentional as Web3Forms keys are designed to be public.

3. **Submission Flow**:
   - Form data is collected and converted to JSON in `form.js`
   - Submitted via fetch to Web3Forms API
   - Success/error messages displayed with auto-hide after 5 seconds
   - Form auto-resets on successful submission

4. **Mobile Responsive**: The design uses CSS Grid and Flexbox with mobile breakpoints at 600px. Any UI changes should maintain mobile responsiveness.

5. **CSS Architecture**: Uses CSS custom properties (variables) for theming. Color scheme variables follow the shadcn/ui convention (--background, --foreground, --primary, etc.)

## Common Tasks

- **Add new form field**: Add the HTML in `index.html` within a `.form-group` div. All fields are automatically included in the submission.
- **Modify styles**: Edit the `<style>` section in `index.html`. Maintain the CSS variable system for consistency.
- **Change form behavior**: Modify `form.js` for submission logic changes.
- **Update API endpoint**: Change the Web3Forms access key in the hidden input field in `index.html`.