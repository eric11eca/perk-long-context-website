# PERK Website Migration to Astro

This document describes the migration from the monolithic `default.html` file to a modular Astro-based website.

## Project Structure

```
src/
├── layouts/
│   └── Base.astro              # Main HTML layout with head, scripts, and body structure
├── components/
│   ├── Navbar.astro            # Navigation bar component
│   ├── HeroHeadline.astro      # Main title and publication links
│   ├── HeroTeaser.astro        # Main figure and description
│   ├── SectionSummary.astro    # Abstract and overview section
│   ├── SectionPublications.astro # Publication details with BibTeX
│   ├── SectionMethod.astro     # PERK method description
│   ├── SectionLongContextEval.astro # Long-context evaluation results
│   ├── SectionLengthExtrapolation.astro # Length extrapolation results
│   └── Footer.astro            # Acknowledgements and footer
└── pages/
    └── index.astro             # Main page that composes all components
```

## Migration Benefits

1. **Modularity**: Each section is now a separate component, making it easy to:
   - Edit individual sections without affecting others
   - Reuse components across different pages
   - Test and debug specific sections in isolation

2. **Maintainability**:
   - Clear separation of concerns
   - Easier to locate and modify specific content
   - Better code organization

3. **Development Experience**:
   - Hot reload for faster development
   - TypeScript support for better tooling
   - Component-based architecture

4. **Performance**:
   - Astro's static site generation
   - Optimized asset handling
   - Minimal client-side JavaScript

## Key Components

### Base Layout (`src/layouts/Base.astro`)
- Contains all the `<head>` metadata, stylesheets, and scripts
- Provides the main HTML structure
- Uses `<slot />` to inject page content

### Navigation (`src/components/Navbar.astro`)
- Responsive navigation bar
- Dropdown menus for different sections
- Maintains all original navigation functionality

### Hero Sections
- **HeroHeadline**: Main title, tagline, and publication links
- **HeroTeaser**: Main figure with explanation

### Content Sections
- **SectionSummary**: Abstract and overview tiles
- **SectionPublications**: Paper details with BibTeX modals
- **SectionMethod**: PERK algorithm explanation
- **SectionLongContextEval**: Evaluation results and figures
- **SectionLengthExtrapolation**: Test-time generalization results

## Running the Site

```bash
# Development server
npm run dev

# Build for production
npm run build

# Preview production build
npm run preview
```

## Static Assets

All static assets (images, CSS, JS) are located in `public/static/` and are served directly by Astro.

## Future Enhancements

With this modular structure, you can easily:

1. **Add new sections**: Create new components and import them in `index.astro`
2. **Create multiple pages**: Add new pages in `src/pages/`
3. **Implement dynamic content**: Use Astro's data fetching capabilities
4. **Add interactivity**: Include framework components (React, Vue, etc.) as needed
5. **Optimize performance**: Leverage Astro's partial hydration features

## Original File

The original `default.html` file (1597 lines) has been preserved for reference and can be safely removed once the migration is complete and tested.