---
title: Banner Configuration
---

The `banner` block is used to display a banner image at the top or a designated section of the GitHub profile README. This block allows you to specify an image along with alternative text for accessibility.

## Schema

```json
"banner": {
    "type": "object",
    "description": "Section for displaying a banner image.",
    "properties": {
        "image": {
            "type": "string",
            "description": "Path or URL to the banner image."
        },
        "alt": {
            "type": "string",
            "description": "Alternative text for the banner image."
        }
    },
    "required": [
        "image",
        "alt"
    ],
    "additionalProperties": false
}
```

## Example Configuration

```yaml
banner:
  image: "https://example.com/banner.png"
  alt: "My custom banner image"
```

## Template File: `templates/banner.md`

```html
<img src="{{ image }}" alt="{{ alt }}" style="width: 100vw"/>
```

## Behavior

- The `image` field should contain a valid URL or path to the banner image.
- The `alt` field provides descriptive text for screen readers and improves accessibility.
- The banner will be displayed across the full width of the profile section.

## Notes

- Ensure the image URL is publicly accessible.
- The `alt` text should be meaningful and describe the image content concisely.
- The styling can be adjusted in the template file if necessary.

This block helps enhance the visual appeal of your profile by adding a personalized banner.
