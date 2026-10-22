# Personal blog

This site uses Jekyll and the [al-folio theme](https://github.com/alshedivat/al-folio). Set `author.name` and the `first_name`, `middle_name`, and `last_name` fields in `_config.yml` to your name before publishing.

## Local setup and preview

On Ubuntu 26.04, install Ruby and the native-gem build tools with:

```sh
sudo apt-get update
sudo apt-get install -y ruby3.3 ruby3.3-dev build-essential zlib1g-dev libssl-dev libyaml-dev
gem install bundler -v 4.0.6
bundle install
```

Then run:

```sh
bundle exec jekyll serve --unpublished --livereload
```

Open <http://localhost:4000/>. `--unpublished` includes the placeholder preview post; it is not published by the deployment workflow.
Use Ruby 3.3.x and Bundler 4.0.6 on other platforms.

Build the published site locally with:

```sh
JEKYLL_ENV=production bundle exec jekyll build
```

## Writing posts

Copy the template to a dated filename, replace its front matter and placeholders, and write your content in the empty sections:

```sh
cp _posts/_TEMPLATE.md _posts/YYYY-MM-DD-your-post-slug.md
```

Use `##` and `###` headings for the generated table of contents. Add tags and categories in the front matter; year, tag, and category archive pages are generated automatically.

### Math

MathJax supports `\( [INLINE MATH] \)` and `$[INLINE MATH]$` inline, plus `\[ [DISPLAY MATH] \]` and `$$ [DISPLAY MATH] $$` for display math. AMS equation numbering, labels, and references are enabled.

### Styled blocks

Use Markdown inside a `div` with `markdown="1"`. The available classes are `theorem-box`, `lemma-box`, `definition-box`, `proof-box`, `remark-box`, `note-box`, and `example-box`.

```html
<div class="theorem-box" markdown="1">
**Theorem.** [STATEMENT]
</div>
```

For a proof, include the QED symbol at the end:

```html
<div class="proof-box" markdown="1">
**Proof.** [PROOF]
<span class="qed" aria-label="Q.E.D.">&#x220E;</span>
</div>
```

### Images and figures

Put image files in `assets/img/`. Use the figure include for a responsive image and caption:

```liquid
{% include figure.liquid path="assets/img/[IMAGE FILE]" alt="[IMAGE DESCRIPTION]" caption="[FIGURE CAPTION]" %}
```

### Interactive widgets

Put a self-contained HTML widget in `assets/widgets/`, then embed it using:

```liquid
{% include widget.liquid src="assets/widgets/[WIDGET FILE].html" title="[WIDGET TITLE]" %}
```

`assets/widgets/example.html` is an empty, commented starting point. The widget is embedded in a sandboxed iframe.

### Code and footnotes

Use fenced Markdown blocks with a language identifier for syntax highlighting and the built-in copy button:

````markdown
```python
# WRITE CODE HERE
```
````

Use Kramdown footnotes with `[^note]` in the text and `[^note]: [FOOTNOTE TEXT]` under the Footnotes heading.

## Publish

1. Replace `[BLOG TITLE]`, `[ONE-LINE TAGLINE]`, and `YOUR-USERNAME`, and set the author name fields in `_config.yml`.
2. Create a GitHub repository named `YOUR-USERNAME.github.io` and select **Settings → Pages → Build and deployment → GitHub Actions**.
3. Add your repository as `origin` and push the `main` branch:

   ```sh
   git remote add origin https://github.com/YOUR-USERNAME/YOUR-USERNAME.github.io.git
   git push -u origin main
   ```

The workflow builds and deploys the site whenever you push to `main`.
