# splitslides

Michael Yoshitaka Erlewine (mitcho), public domain, 2020

splitslides is a LaTeX package for creating simple "slides" from a running document, allowing you to quickly turn a handout into a deck of "slides."

Useful when all your class materials exist in handout form and there's a pandemic and your university switches to online learning and so you want to quickly turn your handouts into "slides" with minimal effort. Just an example.

## Tutorial

It is easiest to explain the package usage by example:

1. Load the package with `\usepackage{splitslides}` in your preamble.
2. Add `\slidestart`, then some `\slidebreak`s, and then `\slideend`; compile and you should see some lines appear in your document.
3. Recompile in "active" mode: `\usepackage[active]{splitslides}`. It should give you a deck of "slides": the content between each adjacent pair of `\slide...` commands will appear on their own page and cropped.
4. Note that the "slides" may all be different sizes, as each page size will varie based on the content. My simple suggestion is to then open the resulting PDF in a PDF viewer and "print" it in a particular paper size and save that result as a PDF. Now you have slides which are all of the same size.
4. To get back your original document without the lines, recompile in "hide" mode: `\usepackage[hide]{splitslides}`.

## How to

- *How to hide something in the slides:* End the slide above with `\slideend`, enter the content that should only be in the full document, and then start the next slide with `\slidestart`. The material in between will not show up in the slides.
- *How to hide something in the full document:* You can wrap some content in `\slideonly{...}` and it will only appear in "active" slide mode.
- *How to do something more complicated, like overlays with Beamer `\pause`:* Please use Beamer.

## Limitations

`\slidestart` / `\slidebreak` / `\slideend` **cannot** be used inside a list (e.g. `itemize`, `enumerate` etc.)! This is the only serious limitation I have run into myself. I have looked into getting around it briefly and think it would be a headache so I don't plan on "fixing" this. If you want `\slidebreak` etc. in a list, my suggestion is to split up the list into multiple lists. If you are writing an enumerated list with `enumerate` and need your numbering to persist across multiple slides, you can use the `enumitem` package to retain numbering across multiple `enumerate` environments (look for the `resume` option in `enumitem` docs).
