# Agents Guide for Online CV Jekyll Site

This document provides guidance for AI coding agents working on this Jekyll-based online CV project.

## 🚀 Quick Start Commands

### Development Server
```bash
# Install dependencies
bundle install

# Start development server (with live reload)
bundle exec jekyll serve

# Start server on different host/port
bundle exec jekyll serve --host 0.0.0.0 --port 4001

# Force regeneration (useful after config changes)
bundle exec jekyll serve --force_polling
```

### Build Commands
```bash
# Build for production
bundle exec jekyll build

# Build with verbose output
bundle exec jekyll build --verbose

# Clean build artifacts
bundle exec jekyll clean
```

### Testing & Validation
```bash
# Validate HTML/links (if htmlproofer is added)
bundle exec jekyll build && bundle exec htmlproofer ./_site

# Check Jekyll configuration
bundle exec jekyll doctor

# Validate YAML data files
bundle exec ruby -e "require 'yaml'; YAML.load_file('_data/data.yml')"
```

## 📁 Project Structure

```
online-cv/
├── _config.yml           # Jekyll configuration
├── _data/
│   └── data.yml         # All CV content (personal info, experience, skills)
├── _includes/           # Reusable HTML components
│   ├── sidebar.html     # Personal info sidebar
│   ├── experiences.html # Work experience section
│   ├── education.html   # Education section
│   └── *.html          # Other CV sections
├── _layouts/
│   └── default.html     # Main page layout
├── _sass/              # SCSS stylesheets
│   ├── _base.scss      # Base styles
│   ├── _responsive.scss # Mobile responsiveness
│   └── skins/          # 6 color theme variants
├── assets/
│   ├── css/main.scss   # Main stylesheet entry
│   ├── images/         # Profile pictures and assets
│   └── plugins/        # Third-party libraries
└── _site/              # Generated output (don't edit)
```

## ✨ Code Style Guidelines

### YAML Data Files (_data/data.yml)
- Use 2-space indentation consistently
- Boolean values: `True`/`False` (capitalized)
- Comments start with `#` for section headers
- Keep personal data organized in logical sections:
  ```yaml
  sidebar:
      about: True
      education: True
      name: Full Name
      tagline: Professional Title
  ```

### HTML Templates (_includes/, _layouts/)
- Use semantic HTML5 elements
- Maintain proper indentation (2 spaces)
- Liquid template syntax:
  ```liquid
  {% if condition %}
    {% include component.html %}
  {% endif %}
  ```
- Comment HTML sections:
  ```html
  <div class="section-wrapper">
    <!-- Content goes here -->
  </div><!--//section-wrapper-->
  ```

### SCSS Stylesheets (_sass/)
- Use BEM-like naming conventions for classes
- Maintain color scheme variables in skin files
- Responsive design with mobile-first approach
- Use Sass mixins for repeated patterns:
  ```scss
  .class-name {
      @include box-shadow(0px 2px 4px rgba(0,0,0,0.1));
      color: $theme-color;
  }
  ```

### Jekyll Configuration
- Keep `_config.yml` organized by purpose (Site Settings, Build settings, etc.)
- Use descriptive comments for configuration options
- Environment-specific settings go in appropriate sections

## 🎨 Theme Management

### Color Themes
Available themes in `_sass/skins/`:
- `blue` (default)
- `turquoise` 
- `green`
- `berry`
- `orange` 
- `ceramic`

To change theme:
1. Update `theme_skin` in `_config.yml`
2. Restart Jekyll server
3. Colors auto-update via Sass variables

### Adding New Themes
1. Create new skin file: `_sass/skins/_newtheme.scss`
2. Define `$theme-color` variable
3. Add theme name to `_config.yml` options

## 🔧 Data Management

### Content Updates
All content is centralized in `_data/data.yml`:

```yaml
sidebar:
    # Personal information
experiences:
    - role: Job Title
      time: 2020 - Present
      company: Company Name
      details: |
        Bullet points of achievements
        - Achievement 1
        - Achievement 2
```

### Best Practices
- Keep descriptions concise but informative
- Use markdown formatting in `details` fields
- Maintain consistent date formats
- Validate YAML syntax before committing

## 📱 Responsive Design

- Mobile-first CSS approach
- Breakpoints defined in `_responsive.scss`
- Test on multiple screen sizes
- Print-friendly styles in `_print.scss`

## 🚀 Deployment

### GitHub Pages
- Automatic deployment from main branch
- Uses `github-pages` gem for compatibility
- Custom domain configured in `_config.yml`

### Manual Deployment
1. Run `bundle exec jekyll build`
2. Upload `_site/` contents to web server
3. Ensure proper file permissions

## ⚠️ Common Issues & Troubleshooting

### Build Errors
- **YAML syntax errors**: Validate `_data/data.yml` syntax
- **Liquid template errors**: Check include file paths and variable names
- **Sass compilation errors**: Verify import paths and variable definitions

### Development Issues
- **Changes not reflecting**: Hard refresh browser or restart Jekyll server
- **Port conflicts**: Use different port with `--port` flag
- **Permission errors**: Check file permissions and Ruby gem installation

### Content Issues
- **Missing profile image**: Ensure file exists in `assets/images/`
- **Broken links**: Verify external URLs and internal paths
- **Formatting issues**: Check markdown syntax in YAML content

## 🔍 File Locations Reference

- **Personal info**: `_data/data.yml` → `sidebar` section
- **Work experience**: `_data/data.yml` → `experiences` section  
- **Skills**: `_data/data.yml` → `skills` section
- **Education**: `_data/data.yml` → `education` section
- **Profile image**: `assets/images/` (referenced in `sidebar.avatar`)
- **Site metadata**: `_config.yml`
- **Color themes**: `_sass/skins/`
- **Custom styles**: `assets/css/main.scss`

## 🎯 Agent Instructions

When working on this codebase:
1. **Always validate YAML**: Check `_data/data.yml` syntax after edits
2. **Test theme changes**: Restart Jekyll server after modifying `_config.yml`
3. **Responsive testing**: Verify mobile compatibility for layout changes
4. **Content integrity**: Maintain professional tone and formatting
5. **Version control**: Use meaningful commit messages for content updates
6. **Performance**: Keep image files optimized and reasonably sized

Remember: This is a personal CV site - maintain professional standards and ensure all changes enhance the presentation of professional information.