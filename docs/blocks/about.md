---
title: About Block Configuration
---

This block displays personal information and a brief bio on your GitHub profile README. It supports two input methods: loading content from an external Markdown file or using inline Markdown content.

## Schema

The block follows this JSON schema:

```json
"about": {
  "type": "object",
  "description": "Section for displaying personal information and a brief bio. Provide either a 'path' to an external Markdown file or inline 'content'. At least one is required.",
  "properties": {
    "path": {
      "type": "string",
      "description": "Path to an external Markdown file whose content will be inserted."
    },
    "content": {
      "type": "string",
      "description": "Inline Markdown content to be inserted."
    }
  },
  "anyOf": [
    { "required": ["path"] },
    { "required": ["content"] }
  ],
  "additionalProperties": false
}
```

## Example Configuration

Below is an example YAML configuration that uses the external file option. It is recommended to store your Markdown files at `/blocks/about.md`:

```yaml
about:
  path: "./blocks/about.md"
```

## Template File

The following template handles the rendering for the about block. (For documentation consistency, you can reference this file as `templates/about.md`.)

```jinja
{% if path %}
{{ read_custom_file(path) }}
{% elif content %}
{{ content }}
{% else %}
<!-- No custom content provided -->
{% endif %}
```

## Behavior

- External File (`path`):  
  If the configuration includes a `path`, the system will load and render the Markdown content from the specified file. This is ideal for maintaining content separately.

- Inline Content (`content`):  
  If no `path` is provided but `content` is defined, the inline Markdown content will be rendered directly.

- Fallback:  
  If neither a `path` nor `content` is provided, the block outputs an HTML comment indicating that no custom content is available.

## Notes

- Organization:  
  It is recommended to store external Markdown files under the `/blocks/` directory (e.g., `/blocks/about.md`) for better project organization.

- Flexibility:  
  Use the `content` property for quick changes or static content that doesn’t require external file management.

- Validation:  
  The schema enforces that at least one of `path` or `content` is provided. No additional properties are allowed.

- Customization:  
  You can customize the rendering behavior by modifying the template file if needed, ensuring it fits your profile's style and requirements.
