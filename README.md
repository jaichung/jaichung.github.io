# jaichung.github.io

Personal academic website of Jaichung Lee, built with Jekyll and served by GitHub Pages.

## Where things live

| To change | Edit |
|---|---|
| Bio, subtitle, fields, JMP label | `index.md` (front matter at the top, bio below it) |
| Papers, abstracts, figures, links | `_data/papers.yml` |
| References | `_data/references.yml` |
| Teaching entries | `teaching.md` |
| CV | replace `assets/CV_Jaichung_Lee.pdf` (keep the file name) |
| Email, LinkedIn, menu | `_config.yml` |
| Colors, fonts, spacing | `assets/css/style.css` (color tokens are at the top) |

## Common tasks

**Add a figure to a paper.** Put the image in `assets/img/papers/` (PNG, around 1600px wide, white background works best), then set `image` for that paper in `_data/papers.yml`, for example `image: /assets/img/papers/fertility-crunch.png`. The same image is used as the large figure on the home page and as the thumbnail on the research page. Leave `image` empty to show the neutral placeholder box.

**Change which paper is the JMP.** Set `status: jmp` on the new paper and change the old one to `status: working`. The home page picks up the paper marked `jmp` automatically.

**Add a paper.** Copy an existing block in `_data/papers.yml` and edit it. Order within each section follows the order in the file.

**Update a PDF.** Upload the new file to `assets/papers/` with the same name as the old one.
