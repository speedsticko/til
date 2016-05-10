### Miscellaneous Gotchas

- Don't call GetLastError() inside of a variable parameter list like printf(). You can end up hiding the actual error and get 0.
