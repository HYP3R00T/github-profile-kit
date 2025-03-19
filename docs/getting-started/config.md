---
title: Configuration
---

The `config.yaml` file consists of multiple blocks that define different sections of your profile. The currently supported blocks are:

- [Social Media Configuration (social)](./../blocks/social.md)
- Featured Projects (projects)
- Latest Blog Posts (blog)
- Latest YouTube Videos (youtube)

### Understanding Block Order in the README Generation

The order of the blocks in `config.yaml` directly affects the structure of the final README because the script processes them sequentially. This means:

1. Blocks are rendered in the order they appear in `config.yaml`  
   - If `social` comes before `projects`, the social badges will be placed at the top.
   - If `blog` appears before `projects`, the latest posts will be displayed earlier.

2. Logical Flow Matters  
   - If you want your "About Me" section first, it should be defined at the start of `config.yaml`.  
   - If your "Connect with Me" block is placed at the end, visitors might miss it if it's a long README file.

3. Dynamic Content Can Push Other Sections Down  
   - If your `blog` or `youtube` section fetches multiple items dynamically, it might push lower sections further down.
   - Keeping dynamic sections near the bottom can help maintain consistency.

### Best Practices for Block Order

- Keep introductory sections (bio, social links) at the top.
- Place static content before dynamic content to avoid layout shifts.
- Ensure call-to-action sections (connect, projects, contributions) are visible early.

By structuring your `config.yaml` carefully, you can control how users navigate your profile and what they notice first!