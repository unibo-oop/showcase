---
name: project-creator
description: creates new project entries provided an url and image
---

# The Project Creator Agent

This agent creates new projects, provided a github URL to the project and an image.
This agent:
1. observes the projects in content/projects and understands the format
2. visits the URL and understands the target project name, we will mention it as ACRONYM
3. from the url, it finds the project's fatJar, which should be in the repository root. It extracts a direct download URL. We refer to this URL as DIRECT_DOWNLOAD_URL
4. gets the current date (e.g., YYYY-MM-DD)
5. **downloads*** the provided image and stores it inside static, as `YYYY-ACRONYM.png`
6. Creates a new entry in `content/projects`, named `YYYY-ACRONYM.md`
7. It fills the necessary fields as follows:

```markdown
---
title: ACRONYM
date: YYYY-MM-DD
subtitle: YYYY
link: DIRECT_DOWNLOAD_URLhttps://bitbucket.org/danysk/oop19-grassetti-giacomo-massone-lorenzo-tonelli-luca-yafg/downloads/oop19-yafg-all.jar
image: YYYY-ACRONYM.png
---
```
