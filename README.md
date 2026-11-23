# CamEUnet

The website of Cambridge Europe Network CIC, a community interest company in Cambridge. It works on youth exchanges, inclusive sport and digital skills with partners across Europe, and plans to take part in Erasmus+ once the UK rejoins in 2027.

The site is a single static page. `index.html` holds the markup and styles, `hero.jpg` is the photo behind the top section, and `favicon.svg` is the "C" logo. There is no build step and no JavaScript.

## Run it

Open `index.html` in a browser, or serve the folder locally:

```sh
python3 -m http.server 8000
```

Then go to http://localhost:8000.

## Deploy

The live site is https://cameunet.uk, hosted as a Cloudflare Worker with static assets. A GitHub Action deploys every push to `main`. It needs two repository secrets, `CLOUDFLARE_API_TOKEN` and `CLOUDFLARE_ACCOUNT_ID`. To deploy by hand, run `npx wrangler@4 login` once, then:

```sh
npx wrangler@4 deploy
```

Files listed in `.assetsignore` are not published.

## Wiki

Project knowledge (design notes, partners, how the logo and arch are built) lives in the `wiki/` folder.
