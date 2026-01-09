# Design System Extractor

## Skill Overview
**Purpose**: Extract comprehensive design patterns from a reference page and generate a reusable DESIGN_SYSTEM.md specification  
**When to Use**: After creating your first well-crafted page to maintain consistency across all future pages  
**Output**: A structured markdown file documenting all design decisions and patterns

---

## User Prompt

```
Analyze the page/component code we just created and generate a comprehensive 
DESIGN_SYSTEM.md file that documents all design patterns, styles, and 
specifications for reuse across the entire project.
```

---

## Claude's Task

Extract and document every design pattern, styling decision, and technical specification from the provided code to create a comprehensive design system reference.

### Extraction Checklist

#### 1. Typography System
Extract and document:
- [ ] All font families (primary, secondary, monospace)
- [ ] Complete font size scale (h1-h6, body, small, etc.)
- [ ] Font weights used throughout
- [ ] Line heights for each text type
- [ ] Letter spacing values
- [ ] Text color variations and usage

**Output Format:**
```markdown
## Typography System

### Font Families
- **Primary**: [Font name], [fallbacks] - Used for: [usage context]
- **Headings**: [Font name], [fallbacks] - Used for: [usage context]
- **Code**: [Font name], [fallbacks] - Used for: [usage context]

### Font Size Scale
| Element | Size | Line Height | Weight | Usage Context |
|---------|------|-------------|--------|---------------|
| h1 | Xpx (Xrem) | X.X | XXX | [where used] |
| h2 | Xpx (Xrem) | X.X | XXX | [where used] |

### Implementation Example
```html
<h1 class="[classes]">Main Heading</h1>
<p class="[classes]">Body text example</p>
```
```

#### 2. Color Palette
Extract and document:
- [ ] All colors used (hex/RGB codes)
- [ ] Color categories (primary, secondary, neutral, semantic)
- [ ] Usage context for each color
- [ ] Opacity/transparency variations
- [ ] Light/dark mode variants if applicable

**Output Format:**
```markdown
## Color Palette

### Primary Colors
| Color Name | Hex Code | RGB | Usage |
|------------|----------|-----|-------|
| Primary | #XXXXXX | rgb(X,X,X) | Buttons, links, CTAs |
| Primary Hover | #XXXXXX | rgb(X,X,X) | Interactive states |

### Semantic Colors
| Purpose | Color | Hex | Usage |
|---------|-------|-----|-------|
| Success | Green | #XXXXXX | Success messages, checkmarks |
| Error | Red | #XXXXXX | Error states, validation |

### Implementation Example
```css
/* Primary action */
background: #XXXXXX;

/* Success state */
color: #XXXXXX;
```
```

#### 3. Spacing System
Extract and document:
- [ ] Base spacing unit
- [ ] Spacing scale (xs, sm, md, lg, xl, etc.)
- [ ] Common padding patterns
- [ ] Common margin patterns
- [ ] Gap values for flex/grid layouts
- [ ] Section spacing patterns

**Output Format:**
```markdown
## Spacing System

### Base Unit
- **Base**: Xpx (all spacing is a multiple of this)

### Spacing Scale
| Name | Value | Usage |
|------|-------|-------|
| xs | Xpx | Tight spacing |
| sm | Xpx | Compact elements |
| md | Xpx | Default spacing |

### Common Patterns
- **Card Padding**: `padding: Xpx Xpx`
- **Section Spacing**: `margin-bottom: Xpx`
- **Button Padding**: `padding: Xpx Xpx`
```

#### 4. Layout Patterns
Extract and document:
- [ ] Container max-widths
- [ ] Grid systems (columns, gaps)
- [ ] Common section structures
- [ ] Content width constraints
- [ ] Flex/grid patterns

**Output Format:**
```markdown
## Layout Patterns

### Containers
- **Max Width**: XXXXpx
- **Padding**: Xpx (mobile), Xpx (desktop)

### Grid Systems
- **Columns**: 12-column grid
- **Gap**: Xpx
- **Common Layouts**: 2-column (md:), 3-column (lg:), 4-column (xl:)

### Section Structure
```html
<section class="[classes]">
  <div class="[container-classes]">
    <!-- content -->
  </div>
</section>
```
```

#### 5. Component Specifications
For each component type found (buttons, cards, inputs, navigation, etc.):
- [ ] Base styling
- [ ] All variants (primary, secondary, outline, ghost, etc.)
- [ ] All states (default, hover, active, focus, disabled)
- [ ] Size variations (sm, md, lg)
- [ ] Border radius values
- [ ] Shadow specifications

**Output Format:**
```markdown
## Component: Button

### Variants
**Primary Button**
- Background: [color]
- Text: [color]
- Padding: [value]
- Border Radius: [value]
- Font Size: [value]
- Font Weight: [value]

**States:**
- Hover: [changes]
- Active: [changes]
- Disabled: [changes]

### Implementation
```html
<!-- Primary -->
<button class="[classes]">Click Me</button>

<!-- Secondary -->
<button class="[classes]">Cancel</button>
```
```

#### 6. Responsive Design
Extract and document:
- [ ] All breakpoints used
- [ ] Layout changes at each breakpoint
- [ ] Mobile-first or desktop-first approach
- [ ] Components that hide/show at breakpoints
- [ ] Typography scaling across breakpoints

**Output Format:**
```markdown
## Responsive Breakpoints

### Breakpoint System
| Name | Min Width | Typical Device | Layout Changes |
|------|-----------|----------------|----------------|
| sm | 640px | Mobile landscape | Stack to single column |
| md | 768px | Tablet | 2-column layouts |
| lg | 1024px | Desktop | 3-column layouts |

### Common Responsive Patterns
- **Navigation**: Hamburger menu (< md), Full nav (>= md)
- **Grid**: 1 col (mobile), 2 col (md), 3 col (lg), 4 col (xl)
- **Typography**: Scale up by 1.2x on desktop

### Implementation
```html
<div class="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-3">
```
```

#### 7. Effects & Interactions
Extract and document:
- [ ] Border radius scale
- [ ] Shadow scale
- [ ] Transition durations and easing
- [ ] Hover effects patterns
- [ ] Animation specifications
- [ ] Transform effects

**Output Format:**
```markdown
## Effects & Interactions

### Border Radius
- **Small**: Xpx - Cards, buttons
- **Medium**: Xpx - Modals, images
- **Large**: Xpx - Hero sections
- **Full**: 9999px - Pills, badges

### Shadows
| Name | Value | Usage |
|------|-------|-------|
| sm | box-shadow: [...] | Subtle elevation |
| md | box-shadow: [...] | Cards, dropdowns |
| lg | box-shadow: [...] | Modals, popovers |

### Transitions
- **Duration**: Xms (fast), Xms (normal), Xms (slow)
- **Easing**: ease-in-out, cubic-bezier(...)
- **Properties**: transform, opacity, colors

### Common Hover Effects
```css
/* Button hover */
.button:hover {
  transform: translateY(-2px);
  box-shadow: [...];
}
```
```

#### 8. Assets & File Paths
Extract and document:
- [ ] Logo file paths and variations
- [ ] Image paths and naming conventions
- [ ] Icon library being used
- [ ] Icon sizes and usage patterns
- [ ] Asset organization structure
- [ ] CDN links or external resources
- [ ] Font file paths

**Output Format:**
```markdown
## Assets & Resources

### Logo Files
- **Main Logo**: `/path/to/logo.svg` (Header, Xpx × Xpx)
- **Logo Icon**: `/path/to/icon.svg` (Mobile, Xpx × Xpx)
- **Logo White**: `/path/to/logo-white.svg` (Dark backgrounds)
- **Favicon**: `/path/to/favicon.ico`

### Image Conventions
- **Path Structure**: `/assets/images/{category}/{name}.{ext}`
- **Naming Pattern**: `{type}-{descriptor}-{variant}.{ext}`
- **Example**: `hero-homepage-mobile.jpg`

### Icon System
- **Library**: [Lucide React / Font Awesome / Custom SVG]
- **Version**: vX.X.X
- **Default Size**: Xpx (w-X h-X)
- **Common Icons**: 
  - Navigation: Menu, X, ChevronDown
  - Actions: Plus, Edit, Trash, Download
  - Status: Check, AlertCircle, Info

### External Resources
- **Font CDN**: https://fonts.googleapis.com/...
- **Icon CDN**: https://cdnjs.cloudflare.com/...
```

#### 9. Code Conventions
Extract and document:
- [ ] Class naming patterns
- [ ] Common utility class combinations
- [ ] Reusable class groups
- [ ] CSS methodology (BEM, utility-first, etc.)
- [ ] Custom class naming conventions

**Output Format:**
```markdown
## Code Conventions

### Methodology
- **Approach**: Utility-first with Tailwind CSS
- **Custom Classes**: Only for complex repeated patterns

### Common Utility Combinations
```html
<!-- Card pattern -->
<div class="bg-white rounded-lg shadow-md p-6 hover:shadow-lg transition-shadow">

<!-- Section pattern -->
<section class="py-16 px-4 max-w-7xl mx-auto">

<!-- Button pattern -->
<button class="px-6 py-3 bg-blue-600 text-white rounded-lg hover:bg-blue-700">
```

### Naming Conventions
- **Components**: PascalCase (`ProductCard`, `HeroSection`)
- **Utilities**: kebab-case (`btn-primary`, `card-elevated`)
- **Files**: kebab-case (`user-profile.jsx`, `hero-section.jsx`)
```

---

## Output Structure

Generate a complete markdown file with the following structure:

```markdown
# [Project Name] Design System

**Version**: 1.0  
**Last Updated**: [Date]  
**Created From**: [Page/Component Name]

---

## Table of Contents
1. Typography System
2. Color Palette
3. Spacing System
4. Layout Patterns
5. Components
   - Buttons
   - Cards
   - Forms
   - Navigation
   - [etc.]
6. Responsive Design
7. Effects & Interactions
8. Assets & Resources
9. Code Conventions

---

[All extracted sections following the formats above]

---

## Usage Guide

### Creating New Pages
When creating new pages, reference this design system by:
1. Using the exact color codes specified
2. Following the typography scale
3. Applying the spacing system consistently
4. Replicating component patterns
5. Maintaining responsive breakpoint behavior

### Prompt Template for New Pages
```
Create a [page type] following the design system specifications 
in DESIGN_SYSTEM.md. The page should include [requirements].
```

## Quick Reference

### Most Common Patterns
- **Primary Button**: `[exact classes]`
- **Card**: `[exact classes]`
- **Section Container**: `[exact classes]`
- **Heading 1**: `[exact classes]`
- **Body Text**: `[exact classes]`
```

---

## Quality Checklist

Before finalizing the DESIGN_SYSTEM.md, ensure:

- [ ] All colors used are documented with hex codes
- [ ] All font sizes include pixel and rem values
- [ ] All spacing values are documented
- [ ] Every component has implementation examples
- [ ] Responsive breakpoints are clearly defined
- [ ] Asset paths are accurate and complete
- [ ] Code examples are copy-paste ready
- [ ] Organization is logical and easy to navigate
- [ ] Tables are used for easy scanning
- [ ] Usage context is provided for each pattern

---

## Success Criteria

The generated DESIGN_SYSTEM.md should enable someone to:
1. ✅ Create a new page that looks identical in style
2. ✅ Use consistent colors without guessing
3. ✅ Apply proper spacing without measuring
4. ✅ Implement components without referencing original code
5. ✅ Maintain responsive behavior across all breakpoints
6. ✅ Reference correct asset paths without errors

---

## Example Completion

After analysis, respond with:

"I've created a comprehensive DESIGN_SYSTEM.md file documenting:
- X typography styles
- X colors in the palette  
- X spacing values
- X component specifications
- X responsive breakpoints
- All asset paths and conventions

This design system can now be referenced for all future pages to maintain perfect consistency. Would you like me to create a new page using this design system to test it?"
