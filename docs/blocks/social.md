---
title: Social Media Configuration
---

The `social` block in the configuration file allows you to define your social media links dynamically. It ensures that your GitHub profile README or any other generated content stays up-to-date with your latest profiles.

---

## Schema

```json
"social": {
    "type": "object",
    "description": "Configuration for social media links.",
    "properties": {
        "links": {
            "type": "array",
            "description": "List of social media platforms with user handles and URLs.",
            "items": {
                "type": "object",
                "properties": {
                    "platform": {
                        "type": "string",
                        "description": "Name of the social media platform (e.g., GitHub, LinkedIn)."
                    },
                    "handle": {
                        "type": "string",
                        "description": "The user's handle or username on the platform."
                    },
                    "url": {
                        "type": "string",
                        "format": "uri",
                        "description": "The URL to the user's profile on the platform."
                    }
                },
                "required": [
                    "platform",
                    "handle",
                    "url"
                ]
            }
        }
    },
    "required": [
        "links"
    ]
}
```

---

## Example Configuration

Here’s how you can define your social media links in `config.yaml`:

```yaml
social:
  links:
  - platform: "GitHub"
    handle: "HYP3R00T"
    url: "https://github.com/HYP3R00T"
    badge: "https://img.shields.io/badge/GitHub-HYP3R00T-24273a?style=for-the-badge"

  - platform: "LinkedIn"
    handle: "rajesh-kumar-das"
    url: "https://www.linkedin.com/in/rajesh-kumar-das/"
    badge: "https://img.shields.io/badge/LinkedIn-rajesh--kumar--das-0A66C2?style=for-the-badge"
```

---

## Template File: `templates/social.md`

To display these links in the final README, the following Jinja2 template is used:

```jinja
## Connect with Me

{% for link in links %}[![{{ link.platform }}]({{ link.badge }})]({{ link.url }})
{% endfor %}
```

This template dynamically generates **Shields.io badges** for each platform and links them to the corresponding profile.

---

## How It Works

1. The **YAML configuration** defines each social media platform with a name, handle, and URL.
2. The **Jinja2 template** processes these values and creates Markdown badges using Shields.io.
3. The final README will include clickable badges that direct visitors to your social media profiles.

This setup allows you to easily manage and update your social links without modifying the actual README file.
