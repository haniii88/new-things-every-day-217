```javascript
function dailyLog217() {
  const pages = [
    {
      url: "/home",
      title: "My Website",
      description: "Welcome to my website",
      hasH1: true,
      hasImageAlt: tru,
    },
    {
      url: "/about",
      title: "",
      description: "Learn more about us",
      hasH1: true,
      hasImageAlt: false,
    },
    {
      url: "/blog",
      title: "Our Blog",
      description: "",
      hasH1: false,
      hasImageAlt: true,
    },
    {
      url: "/contact",
      title: "Contact Us",
      description: "Get in touch with our team",
      hasH1: true,
      hasImageAlt: true,
    },
  ];

  const issues = [];

  pages.forEach(page => {
    const missing = [];

    if (!page.title.trim()) missing.push("Missing title");
    if (!page.description.trim()) missing.push("Missing description");
    if (!page.hasH1) missing.push("Missing H1 heading");
    if (!page.hasImageAlt) missing.push("Missing image alt text");

    if (missing.length > 0) {
      issues.push({ url: page.url, missing });
    }
  });

  console.log("=== SEO Analysis Report ===");
  console.log(`Pages Analyzed: ${pages.length}`);
  console.log(`Pages With Issues: ${issues.length}`);

  issues.forEach(issue => {
    console.log(`\n⚠️ ${issue.url}`);

    issue.missing.forEach(item => {
      console.log(`  - ${item}`);
    });
  });

  console.log(
    `\nSEO Health: ${
      ((pages.length - issues.length) / pages.length * 100).toFixed(0)
    }%`
  );
}

dailyLog217();
```
