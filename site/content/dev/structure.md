---
title: Structure
resources:
- name: structure
  src: content_structure.png
---

# Structure

*Making with Code* is organized into courses, units, and lessons. Courses are the highest-level container for content. They contain one or more units. Units are clusters of content organized around essential questions, providing materials to orchestrate student learning for 1-2 months. Lessons are the finest level of organization, representing one class meeting. Lessons will be the hardest to adapt to different school schedules, so using lessons is optional. Courses and units are purely organizational structures, while lessons are also themselves a content type.

{{< figure src="images/content_organization.png" title="Organization of content" >}}

## Content types

The following content types are implemented. For each, ensure that `type: contenttype` is in the page's front matter.

- `course`: Introduces a course.
- `unit`: Introduces a unit.
- `labs`: Introduces a lab and includes necessary modules.
- `module`: A chunk of content such as a handout, a homework assignment, a lab,
  or a set of slides.
- `teaching`: A pedagogical overview, introducing the content to a teacher
  preparing to use it. Each course, unit, lesson, and module may have `teaching` content.
- `notes`: Pedagogical details related to a specific implementation of the
  content.

Courses, units, and lessons  are implemented in Hugo as [branch bundles](https://gohugo.io/content-management/page-bundles/#branch-bundles), which means each page is built from `_index.html` and it has access to all the other pages in its directory. Teaching and notes are implemented as pages within branch bundles.

## File structure

Here is an example file structure showing the various content types.

```
content/
├── _index.md
└── courses
    └── cs9
        ├── _index.md
        ├── notes.md
        ├── teaching.md
        └── unit00
            ├── _index.md
            ├── lessons
            │   ├── _index.md
            │   └── lesson00
            │       ├── _index.md
            │       ├── notes.md
            │       └── teaching.md
            ├── modules
            │   ├── _index.md
            │   ├── hw_terminal_practice
            │   │   └── _index.md
            │   └── lab_terminal_adventure
            │       └── _index.md
            ├── notes.md
            └── teaching.md
```
