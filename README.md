# theme-bash
A simple bash script I made a while ago to automatically re-theme every
application in an X11 session. Themes are defined using Xresources syntax.

# Usage 
Call the `theme` script with a single argument, that being the name of a theme.
Themes are defined in the `themes` folder, each theme being a different
.Xresources file.

Templates for specific applications can be put in `templates`. Names of
Xresources from your theme file, surrounded by double curly brackets
`{{resource_name}}`, will be replaced with the corresponding resource value. At
the beginning, directives can be specified, by putting them on separate lines
using the following syntax:

`::{directive name}: {value}`

The following directives are supported:

- `destination`: The destination for the file once it has been run through the
  templating engine. Supports shell expansion for paths.
- `post_write`: A command to be ran after the template has been written to its
  destination.
- `namespace`: If specified, resources will be taken from the Xresources theme
  file preferentially if they belong to this class.
- `enabled`: Whether this template is used. If equal to "no", it won't be.

For a better idea of how things work, check the example templates and themes.
