# Mingjing (Marcus) Xu - Academic Resume

`awesome-cv.tex` builds the current one-page A4 resume, `awesome-cv.pdf`.
The document uses the local `awesome-source-cv.cls`, the bundled Source Sans Pro
fonts in `fonts/`, and `PP2.jpg` in the upper-right corner.

## Build

Run from this directory with LuaLaTeX through `latexmk`:

```sh
latexmk -lualatex -interaction=nonstopmode -halt-on-error -file-line-error awesome-cv.tex
```

The source was verified with LuaHBTeX 1.24.0 (TeX Live 2026) and latexmk 4.88.
A full TeX Live or MacTeX installation provides the required LaTeX packages.
Use the LaTeX engine `lualatex`, not the plain-TeX command `luatex` or `pdflatex`.
The class uses the local `fontawesome.sty`, which also needs the FontAwesome font.

To remove build intermediates while keeping the PDF:

```sh
latexmk -c awesome-cv.tex
```

## Content and layout

The active section files, in display order, are:

1. `section_headline.tex`: research interests and conference reviewing service.
2. `section_education.tex`: five institutions, each using exactly two lines.
3. `section_publications.tex`: five linked publications, with author order and
   equal-contribution markers preserved; each entry ends with a linked venue ranking.
4. `section_skills.tex`: combined programming/tools, ML, English scores, and training.
5. `section_experience_short.tex`: the embedded AI project and four areas of Jabil
   responsibility: firmware/drivers, embedded applications, hardware integration,
   and FPGA tools/validation.
6. `section_awards.tex`: honors, prizes, and scholarships.

Research Experience and Academic Service are no longer standalone sections.
Reviewing venues are listed in the headline; the ICML Gold Reviewer Award remains
under Honors and Awards. Temple and RIT show the dates, assistantship roles, and
GPAs supplied by the author. Their entries make no completed-degree claim.
Swansea is identified as ongoing Ph.D. study; the doctoral subject is not inferred.
The ambiguous undergraduate rank is omitted, with a note in the education source.

The design uses 10 pt body text, 9 pt secondary details and awards, 12 pt section headings,
navy accents, gray dates, and light section rules. Bold and italic weights provide
hierarchy within one font family. Publications and contact details retain their
links. The photograph is included at its original aspect ratio.

Edit the header and section order in `awesome-cv.tex`. The `\educationentry`
command takes an institution, dates, and a single detail line. Keep that detail
line short: the full-width table cell does not wrap automatically. The class
controls fonts, margins, colors, section spacing, and bullet styling. There is no
forced page break or page number in the current one-page layout.

After content changes, rebuild and inspect the PDF, including its page count,
education line lengths, section breaks, and compiler warnings. All current text
is selectable. Other `section_*.tex` files and photographs remain unused template
assets and do not affect the build.

## Venue rankings

The labels use the 2026 ranking editions, checked on 15 September 2026. The year
in the Publications heading refers to the ranking edition. These are venue-level
classifications; publication years and author contribution markers are separate.

| Venue | Label in the CV | Ranking source |
| --- | --- | --- |
| ICLR | ICORE A* | [ICORE2026 record](https://portal.core.edu.au/conf-ranks/2273/) |
| AAAI (both papers) | ICORE A* | [ICORE2026 record](https://portal.core.edu.au/conf-ranks/1629/) |
| ACM MobiCom | ICORE A* | [ICORE2026 record](https://portal.core.edu.au/conf-ranks/27/) |
| Automation in Construction | JCR Q1 | [Editor-in-Chief's announcement](https://www.linkedin.com/posts/daniel-castro-lacouture-8a5a787_automationinconstruction-researchimpact-activity-7473811382401142784-mJgY) |

[CORE is now named ICORE](https://portal.core.edu.au/conf-ranks/?by=all).
For Automation in Construction, the editor confirms Q1 in both Engineering,
Civil and Construction & Building Technology. The edition is JCR 2026, using
2025 data, following [Clarivate's release announcement](https://clarivate.com/news/clarivate-releases-journal-citation-reports-2026/).
The journal's Q1 status was confirmed through the editor's announcement; the
official JCR record could not be accessed directly during this review.

The `\venuerank` command in `awesome-cv.tex` controls the compact linked labels.
Update the values, source links, and heading year together when changing editions.

## Style references

The compact publication lists, restrained color, and right-aligned dates were
informed by these public ML Ph.D. resumes/CVs:

- [Benjamin V. Rozonoyer - one-page ML resume](https://brozonoyer.github.io/assets/pdf/resume-onepage.pdf)
- [Feiyang Wu - ML Ph.D. CV](https://feiyangwu.com/CV/04-26.pdf)

Publication metadata and contribution markers were checked against the linked
proceedings. Education and employment details are author-supplied.

## Template attribution

Based on [Huajh Awesome LaTeX CV](https://github.com/huajh/awesome-latex-cv),
itself based on Christophe Roger's Awesome Source CV. The local class has been
adapted for this English academic resume. Original license and copyright notices
are retained; see `LICENSE` and the source headers.
