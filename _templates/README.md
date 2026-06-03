# Post templates

Two templates for new posts on The Doctor's Dialectic.

`short_post.qmd` is for 300 to 700 word posts. One sharp claim, one figure or pull-quote, designed to be screenshot-shareable.

`long_post.qmd` is for 2,000 to 5,000 word posts. Methodological depth, citations, optional code. The anchor pieces.

## Workflow

1. Decide whether the piece is short or long.
2. Create the draft under `_local_drafts/YYYY-MM-DD-slug-name/`. `_local_drafts/` is ignored by Git, so drafts and ideas stay off GitHub.
3. Copy the appropriate template into the new folder, renaming it `index.qmd`.
4. Fill in the frontmatter. The required fields are `title`, `date`, `categories`, `image`, and `description`. The `subtitle` is optional.
5. Write the post body with `draft: true` set.
6. Generate three hero image candidates with the image generation script. From the project root:

   ```bash
   python scripts/generate_image.py \
     "one-sentence visual concept for the post" \
     tdd_site-current/_local_drafts/YYYY-MM-DD-slug-name/hero.png
   ```

   This produces `hero_minimalist.png`, `hero_impressionist.png`, and `hero_vangogh.png` in the draft folder. Pick the one that fits, rename it to `hero.png`, delete the other two.
7. When ready to publish, move the folder into `docs/posts/`, set `draft: false`, and render the site.
8. After publish, copy the `social-x` and `social-li` text into the relevant platforms.

## Category values

Use one or two of: `Methods and Models`, `AI in Practice`, `Lab Notebook`, `Epistemology of Clinical AI`, `Global Health` (legacy), `Miscellaneous`.

## Notes

`draft: true` keeps the post out of the blog listing during writing.

The `image:` field is used for both the post hero image and the Open Graph card. Keep it at 1200x630 pixels for clean rendering across X, LinkedIn, and Slack.

The `social-x` and `social-li` fields are private; they live in the YAML frontmatter for your own reference and are not rendered to readers.

Templates and this folder are excluded from rendering because Quarto skips directories whose names begin with an underscore.
