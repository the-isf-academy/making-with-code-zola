---
Title: Config
---

# Configuration

## Configuration Files

Multiple configuration files are provided to build 
*Making with Code* for various audiences:

- dev (default)
- teachers
- students

To build for a particular audience, use the `environment` flag:

```
hugo --environment teachers
```

## Configuration Params

The following params are defined. *Making with Code* extends the 
[Book theme](https://github.com/alex-shpak/hugo-book), so those params are
defined as well. You should not need to modify these directly. Instead, use the
`environment` flag.

### `ShowTeaching`
Show teaching content on courses, units, lessons, and modules.

### `ShowNotes`
Show teaching notes (only if `ShowTeaching` is also set).

### `ShowDev`
Shows the development documentation and content within the `dev_note`
shortcode.

### `BookLogo` 
Points to the site logo, by default `"fablearn.png"`.

### `CustomCSS`
A list of custom CSS files to inject into the header.

### `ExcludeTypesFromMenu`
Certain types are only intended to be included in larger blocks of content,
not on their own. Defaults to `["teaching", "notes"]`

### `Teacher` 
The name which should be used when referring to the teacher. (See the 
[teacher shortcode]({{< ref "dev/syntax.md#teacher" >}}).)

### `BookSection`
This param from the [Book theme](https://github.com/alex-shpak/hugo-book) is
ignored.


