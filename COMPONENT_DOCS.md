# Portfolio Component Documentation

## Overview
This portfolio is built with reusable, customizable components that can now be used as custom HTML tags. Each component is designed to be flexible and maintainable, and can be used either as React components or as custom HTML elements.

## New Custom Element Tags

The portfolio components are now available as custom HTML tags. Use these tags in your markup to render the components:

- `<portfolio-navigation>` - Navigation component
- `<portfolio-hero>` - Hero section component  
- `<portfolio-about>` - About section component
- `<portfolio-projects>` - Projects showcase component
- `<portfolio-skills>` - Skills and expertise component
- `<portfolio-experience>` - Experience timeline component
- `<portfolio-contact>` - Contact form and information component
- `<portfolio-footer>` - Footer component

### Usage Example

```html
<portfolio-hero data-config='{"name": "Your Name", "title": "Full Stack Developer", "subtitle": "Innovative Developer", "description": "I create exceptional digital experiences.", "primaryButtonText": "View Projects", "secondaryButtonText": "Contact Me"}'></portfolio-hero>
```

### Configuration

Each custom element accepts configuration through the `data-config` attribute, which should contain a JSON string with the component's props. If no configuration is provided, the component will use its default settings.

```html
<portfolio-navigation data-config='{"items": [{"href": "#home", "label": "Home"}, {"href": "#about", "label": "About"}]}'></portfolio-navigation>

<portfolio-about data-config='{"title": "About Me", "description": "Custom description here", "colors": {"background": "bg-gray-900", "text": "text-white", "accent": "text-blue-400"}}'></portfolio-about>
```

## Component Props Reference

### Navigation Component
```typescript
interface NavigationProps {
  items?: NavigationItem[];     // Navigation menu items
  className?: string;          // Additional CSS classes
  position?: 'top' | 'floating'; // Position type
}

// Default items:
[
  { href: "#hero", label: "Home" },
  { href: "#about", label: "About" },
  { href: "#projects", label: "Project" },
  { href: "#skills", label: "Skill" },
  { href: "#experience", label: "Experience" },
  { href: "#contact", label: "Contact" }
]
```

### Hero Component
```typescript
interface HeroProps {
  name?: string;              // Your name (default: "Your Name")
  title?: string;             // Main title (default: "Full Stack Developer")
  subtitle?: string;          // Animated subtitle text
  description?: string;       // Description text
  primaryButtonText?: string; // Primary CTA button text
  secondaryButtonText?: string; // Secondary CTA button text
  backgroundGradient?: string; // Background gradient CSS
  textColors?: {
    name: string;            // Name text color
    title: string;           // Title text color
    subtitle: string;        // Subtitle text color
    description: string;     // Description text color
  };
  buttonColors?: {
    primary: string;         // Primary button color
    secondary: string;       // Secondary button color
  };
}

// Default values:
{
  name: "Your Name",
  title: "Full Stack Developer",
  subtitle: "Full Stack Developer",
  description: "I create exceptional digital experiences through clean code and innovative solutions",
  primaryButtonText: "View My Work",
  secondaryButtonText: "Get In Touch",
  backgroundGradient: "from-black via-gray-900 to-black",
  textColors: {
    name: "text-white",
    title: "text-white",
    subtitle: "text-gray-300",
    description: "text-gray-400"
  },
  buttonColors: {
    primary: "bg-white text-black hover:bg-gray-200",
    secondary: "border border-white text-white hover:bg-white hover:text-black"
  }
}
```

### About Component
```typescript
interface AboutProps {
  title?: string;            // Section title (default: "About Me")
  description?: string;      // Main description text
  skills?: Skill[];         // Technical skills array
  tools?: Tool[];           // Tools and technologies
  colors?: {
    background: string;      // Background color
    text: string;           // Text color
    accent: string;         // Accent color
  };
}

// Default skills:
[
  { name: "React/Next.js", level: 95 },
  { name: "TypeScript", level: 90 },
  { name: "Node.js", level: 85 },
  { name: "Python", level: 80 },
  { name: "Database Design", level: 85 },
  { name: "UI/UX Design", level: 75 }
]

// Default tools:
[
  { category: "Frontend", items: ["React", "Next.js", "TypeScript", "Tailwind CSS"] },
  { category: "Backend", items: ["Node.js", "Python", "PostgreSQL", "MongoDB"] },
  { category: "Tools & DevOps", items: ["Git", "Docker", "AWS", "Vercel"] }
]
```

### Projects Component
```typescript
interface ProjectsProps {
  title?: string;            // Section title (default: "Featured Projects")
  projects?: Project[];     // Array of projects
  colors?: {
    background: string;      // Background color
    text: string;           // Text color
    accent: string;         // Accent color
  };
}

// Default projects:
[
  {
    title: "E-Commerce Platform",
    description: "A full-stack e-commerce solution with real-time inventory management, secure payments, and admin dashboard.",
    technologies: ["Next.js", "TypeScript", "Stripe", "PostgreSQL", "Tailwind CSS"],
    github: "https://github.com",
    live: "https://example.com"
  }
]
```

### Skills Component
```typescript
interface SkillsProps {
  title?: string;            // Section title (default: "Skills & Expertise")
  skills?: Skill[];         // Technical skills array
  tools?: Tool[];           // Tools and technologies
  colors?: {
    background: string;      // Background color
    text: string;           // Text color
    accent: string;         // Accent color
  };
}
```

### Experience Component
```typescript
interface ExperienceProps {
  title?: string;            // Section title (default: "Experience")
  workExperience?: TimelineItem[]; // Work experience items
  education?: TimelineItem[]; // Education items
  colors?: {
    background: string;      // Background color
    text: string;           // Text color
    accent: string;         // Accent color
  };
}

// TimelineItem structure:
{
  title: string;           // Bold title (work/education title)
  description: string;     // Semibold description
  year: string;            // Date/year
  isAbove?: boolean;       // Position above/below timeline
}
```

### Contact Component
```typescript
interface ContactProps {
  title?: string;            // Section title (default: "Get In Touch")
  email?: string;           // Contact email
  location?: string;        // Location text
  socialLinks?: SocialLink[]; // Social media links
  colors?: {
    background: string;      // Background color
    text: string;           // Text color
    accent: string;         // Accent color
  };
}

// Default social links:
[
  { name: "GitHub", url: "https://github.com" },
  { name: "LinkedIn", url: "https://linkedin.com" },
  { name: "Twitter", url: "https://twitter.com" }
]
```

### Footer Component
```typescript
interface FooterProps {
  text?: string;            // Footer text
  socialLinks?: SocialLink[]; // Social media links
  colors?: {
    background: string;      // Background color
    text: string;           // Text color
    accent: string;         // Accent color
  };
}
```

## Usage Examples

### Basic Usage
```typescript
// In page.tsx
import Hero from '@/components/hero';

<Hero 
  name="John Doe"
  title="Senior Developer"
  description="Building amazing web experiences"
/>
```

### Full Customization
```typescript
<Hero
  name="Your Name"
  title="Full Stack Developer"
  description="Creating exceptional digital experiences"
  primaryButtonText="View Portfolio"
  secondaryButtonText="Contact Me"
  backgroundGradient="from-purple-900 via-blue-900 to-indigo-900"
  textColors={{
    name: "text-yellow-400",
    title: "text-white",
    subtitle: "text-gray-300",
    description: "text-gray-400"
  }}
  buttonColors={{
    primary: "bg-yellow-400 text-black hover:bg-yellow-300",
    secondary: "border border-yellow-400 text-yellow-400 hover:bg-yellow-400 hover:text-black"
  }}
/>
```

### Custom Projects
```typescript
<Projects
  title="My Work"
  projects={[
    {
      title: "My Custom Project",
      description: "Custom project description",
      technologies: ["React", "Node.js", "MongoDB"],
      github: "https://github.com/username/project",
      live: "https://myproject.com"
    }
  ]}
  colors={{
    background: "bg-gray-900",
    text: "text-white",
    accent: "text-blue-400"
  }}
/>
```

## Color Customization
All components support color customization through the `colors` prop:

- **background**: Component background color
- **text**: Primary text color
- **accent**: Accent/highlight color

## Responsive Design
All components are fully responsive and work on all screen sizes.

## TypeScript Support
Full TypeScript support with proper interfaces and type safety.
