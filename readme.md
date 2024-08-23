# Full Statement Syntax Highlighting for PowerShell

This extension extends the basic PowerShell capabilities of VSCode to include complete full statement syntax highlighting for PowerShell files.  It is based on the basic language grammar VSCode derived from the PowerShell/EditorSyntax repository, but improved in many ways.

If you are using a theme with semantic token highlighting enabled, and you have a recent PowerShell extension, you must disable semantic token highlighting, in order to insure the this tmLangauge grammar is used to the fullest.

The primary improvement in the syntax highlighting is regarding using a full statement syntax approach, which better discerns the difference between keywords, commands, operators, parameter designators and parameter values.  This makes it possible for your theme to better highlight your code!

I have made significant changes, based on PowerShell/EditorSyntax commit 472c944:
- Improved `${}` handling, including fixes to `${drive:variable}` and multiline names.
- Added meta.embedded scope to interpolation inside double quoted strings, most themes will revert back to base color for the interpolated text, plus it adds support for full intellisense inside the embedded expression.
- Fixed most of the issues with '#' inside object names and file paths.
- improved matching of `$^` `$$` and `$?`.
- Improved `class` and `function` support and with `enum` support.
- Consistent 'accessor'(`::`, `.`, `?.`) (member/method/property/index) scoping behavior.
- Full statement syntax'ing approach, which limits keywords from scoping where they are not available.
- In many places, invalid text will be so marked, including useless escapes.
- Command arguments and switch match arguments among others now scope as bare-word (unquoted) strings.

For more information, reference [PowerShell/EditorSyntax PR #156](https://github.com/PowerShell/EditorSyntax/pull/156).

This extension is meant as a preview of what PowerShell syntax highlighting could be.

## Contributing

I encourage all to contribute to the PowerShell/EditorSyntax repository at this time.