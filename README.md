# FindStringsByRegex.py

This Ghidra script prompts the user to enter a regular expression, then scans all defined data strings in either the current program (if no code is selected) or just the active selection. It filters data items whose type name contains "unicode" or "string", extracts each one's default value representation, and tests it against the provided regex using `re.match`. Every matching string is printed to the console, and at the end the total count of matches is displayed.

Key behaviors:
- Uses `askString` to collect the regex from the user.
- Respects a current selection via `currentSelection`, otherwise processes the entire program.
- Only considers data types classified as string/unicode.
- Prints each matching string value individually, then reports the final total.