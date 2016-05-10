### Miscellaneous Gotchas

- Don't call GetLastError() inside of a variable parameter list like printf(). You can end up hiding the actual error and get 0.
- Related: http://stackoverflow.com/questions/8671483/why-does-getlasterror-return-0-or-2-depending-on-how-it-is-called
