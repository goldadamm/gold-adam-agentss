# Gold Adam Agent Opportunity (static site)

A one-page, mobile-friendly recruiting page. It is plain HTML and CSS. There is no JavaScript, no build step, no backend, and no database.

## Folder structure

```
index.html              The page (GitHub Pages serves this file at the site address)
css/styles.css          All styling. Brand colors and fonts are variables at the top.
images/seal.png         The Gold Adam seal used on the page
images/favicon-32.png   Browser tab icon
images/apple-touch-icon.png   Icon for phone home screens
.nojekyll               Tells GitHub Pages to publish the files exactly as they are
README.md               This file
```

All file paths are relative, so the site works at the top of a domain (`https://name.github.io/`), in a project folder (`https://name.github.io/repo-name/`), or on a custom domain.

## Deploy on GitHub Pages

1. Create a GitHub account if you do not have one, then create a **new repository** (for example `agent-opportunity`).
2. Upload the **contents** of this folder to the repository (drag the files and the `css` and `images` folders into the upload page). `index.html` must sit at the top level of the repository, not inside another folder.
3. In the repository, open **Settings, then Pages**.
4. Under **Build and deployment**, set **Source** to **Deploy from a branch**, choose the **main** branch and the **/ (root)** folder, and click **Save**.
5. Wait one to two minutes. GitHub shows the live address at the top of the Pages screen, usually `https://YOUR-USERNAME.github.io/REPO-NAME/`.
6. Open that address in a private window and click every "Sign NDA" button to confirm the Adobe form opens.

Note: GitHub Pages on a **public** repository is free. Publishing from a **private** repository requires a paid GitHub plan. The files contain no secrets, so a public repository is fine.

### Optional: use a goldadam.com address

1. In **Settings, then Pages**, enter your address (for example `join.goldadam.com`) under **Custom domain**.
2. Ask whoever manages your DNS to add a **CNAME** record for that name that points to `YOUR-USERNAME.github.io`.
3. When GitHub finishes checking it, turn on **Enforce HTTPS**.

## What the site depends on

| Item | Where it is used | Needed before launch |
|---|---|---|
| Adobe Acrobat Sign web form (the NDA link) | The three "Sign NDA" buttons in `index.html` | The form must stay published and reachable. It is hosted and managed by Adobe, not by this site. |
| Google Fonts (Barlow, Barlow Condensed, Source Serif 4) | One `<link>` in the `<head>` of `index.html` | Optional. If it cannot load, the page falls back to standard fonts and stays usable, with wider headlines. |

## Backend, database, and environment variables

- **Backend or server code:** none.
- **Database connection:** none.
- **Environment variables, API keys, or secrets:** none.
- **Signed NDAs:** the page itself collects nothing. Signatures are handled entirely by the Adobe form. Routing completed NDAs to a spreadsheet is configured in Adobe Acrobat Sign (for example through an integration such as Zapier or Power Automate), not in this site.

## Common changes

- **Change the NDA link:** open `index.html` in a text editor, search for `na3.documents.adobe.com`, and replace the whole address in all three places.
- **Change wording:** edit the text between the tags in `index.html`.
- **Change colors or fonts:** edit the variables at the top of `css/styles.css`.
- **Let search engines list the page:** delete the line `<meta name="robots" content="noindex, nofollow">` in `index.html`. It is there because the page is meant for recruits, not for public search.
- **Link previews with an image:** add `<meta property="og:image" content="https://YOUR-ADDRESS/images/seal.png">` to the `<head>` once you know the final web address. It must be the full address.
- **Host the fonts yourself (fully independent of Google):** download Barlow, Barlow Condensed, and Source Serif 4 from fonts.google.com, add them to a `fonts` folder, declare them with `@font-face` in `css/styles.css`, and remove the Google Fonts `<link>` from `index.html`.

## Test on your own computer

Double-click `index.html` to open it in a browser. Everything works from the folder because all paths are relative.
