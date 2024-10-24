# DHRIFT Institute Template

This repository provides a template for setting up and managing digital humanities workshops using DHRIFT, a platform that integrates interactive content and tools for technical teaching. This template can be used by institutions to create custom workshop events with ease.

[See a Demonstration](https://app.dhrift.org/inst?instUser=GC-DRI&instRepo=GCDRI24Schedule)

## Features

- **Customizable Workshop Events**: Configure your events, instructors, and helpers easily using YAML configurations.
- **Interactive Learning Tools**: DHRIFT supports in-browser code editors, interactive challenges, and more through WebAssembly.

## Configuration

To customize your instance, edit the `config.yml` file in the root of this repository. Key fields include:

- **Organizer Name**: `Lisa Rhody`
- **Institution**: `CUNY Graduate Center`
- **Event Title**: `Learn with DHRIFT`
- **Event Description**: "DHRIFT workshops have been used and tested across over twenty institutions. This template helps instructors organize and deploy their own sessions."
- **Hero Description**: "DHRIFT offers customization for your educational needs."
- **Registration Link**
- **Instructors**: `Steve Zweibel`, `Leanne Fan`
- **Helpers**: `Zachary Lloyd`

### Workshop Sessions Example

The sessions you configure in the `config.yml` link to workshops in the DHRIFT curriculum. Here's an example of how to set up a session:

```yaml
sessions:
  - date: 2024-01-01
    time: 09:00
    title: "Introduction to Git"
    description: "Learn the basics of version control using Git and GitHub."
    workshop: "git"  # Automatically links to workshops/git.md
    location: "The Graduate Center, CUNY"
    instructors: ["Steve Zweibel"]
```

The `workshop` field uses the filename (e.g., `git`) from the core [DHRIFT workshops repository](https://github.com/DHRI-Curriculum/workshops) and links it to the appropriate markdown file dynamically, so you don’t need to specify the full path or extension.

## Getting Started

1. **Fork this Repository**: Start by forking this template for your institute's DHRIFT workshops.
2. **Configure**: Update the `config.yml` with your institution’s details, event specifics, and list of instructors.
3. **Deploy**: Use the DHRIFT platform to view your new Institute or event.

## How DHRIFT Works
When you deploy DHRIFT, it dynamically pulls content from a GitHub repository specified in the URL query. DHRIFT reads the config.yml file from the specified repository to gather metadata (e.g., site title, description) and locate the workshops repository.

For example, if your repository URL is:

https://app.dhrift.org/inst?instUser=dhri-curriculum&instRepo=dhrift-site-template
DHRIFT will pull the config.yml from https://github.com/DHRI-Curriculum/dhrift-site-template:

# Example config.yml
title: "DHRI Curriculum"
description: "A site for DHRI workshops"
workshopsuser: dhri-curriculum
workshopsrepo: workshops 
The workshopsuser and workshopsrepo keys point to the repository containing the Markdown workshop files.

## Contributing

We welcome contributions that can expand the DHRIFT curriculum. Feel free to open issues or submit pull requests.

## License

This repository is licensed under the MIT License.
```

This draft addresses how workshop filenames are linked automatically from the main DHRIFT curriculum repository using a bit of “magic” (no need to specify `.md` extensions) and offers clear instructions for setting up and deploying events.
