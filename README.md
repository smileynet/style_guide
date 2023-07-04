# smiley.net's coding style guide
An opinionated (mostly) documentation repository on coding styles and conventions I follow in my projects.

## Major Conventions
[Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) - Provides clear standards for informative commit messages, enforced via commitlint (see below)

[Keep a Changelog](https://keepachangelog.com/en/1.1.0/) - Machine generated commitlogs are useful for developers, but are not user centric. A manual CHANGELOG.md is kept to write user oriented descriptions of major changes, and the machine generated log for commits is instead named COMMITLOG.md.

[Semantic Versioning](https://semver.org/) - "Versioning without sentimentality", a system that gives clear meaning to version changes.

Logging - Use console.log as temporary logging while building a feature. Avoid committing code to main that still contains console.log (ideally a branch filter is in place to prevent this. Instead use the appropriate client or server side logging library in use in the project (as of this writing [Logger](https://github.com/jonnyreeves/js-logger) and [Winston](https://github.com/winstonjs/winston) respectively are what I commmonly use).

Group files by feature - For projects of anything beyond a small hanful of files, prefer to group files by feature first, then function (i.e. crafting/types, movement/systems, etc). This helps illustrate logical boundaries between features, which helps in keeping features decoupled as much as possible. There are some exceptions, such a Next.js that use an oppinionated folder structure for parts of the application. In these cases I prefer to follow convention so that folks familiar with NextJS won't be confused by a custom structure (which would also reduce future-proofing).

Code as comments - Prefer to use descriptive variable and function names, such as getNextEnemy() or currentHealth, avoiding abbreviation/ truncation where possible as well as "old" style type oriented naming (i.e. iInterface, _private). If a block of code is not self explanatory, move it to a descriptive function name in lieu of comments, even if it is only a few lines long. "Code never lies, comments sometimes do." - Ron Jeffries

Keep files short - If a file runs longer than 200-300 lines of code, it is usually an invitation to refactor and break out some code to another helper function/ class. This is doubly useful in GenAI based programming reducing the number of tokens consumed in adding a given class/function to a prompt.

