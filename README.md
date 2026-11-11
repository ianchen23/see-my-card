# See My Card

**Live page: https://ianchen23.github.io/see-my-card/**

A single web page that lets Google Chrome autofill one of your saved cards, so you can see its full details. It's useful when a checkout page won't autofill, or when you need your card number in person and don't have your wallet.

It works with cards saved in Google Chrome, including Google Pay cards, in Chrome on computers, Android and iPhone. Chrome still asks for whatever confirmation it normally does (security code, fingerprint, face or device PIN).

## Why you can trust it

- **It's one file:** [`index.html`](index.html). There's no build step, so what you see here is exactly what GitHub Pages serves.
- **It has no JavaScript.** The page contains no code that runs, only text, styling and input boxes.
- **Its security policy** (the `Content-Security-Policy` tag at the top of the file) blocks scripts, network connections and form submissions.
- **The input boxes have no `name` attributes.** Browsers never send unnamed fields anywhere.
- **Spellcheck is turned off on the boxes.** Chrome's enhanced spellcheck can send typed text to Google, so this keeps your card details out of it.

You can check this yourself: open the page, right-click → **View page source**, and compare it with `index.html` here.

## Host your own copy

If you'd rather not trust anyone else's site, host your own copy. It takes a couple of minutes and is free:

1. Sign in to GitHub and click **Fork** at the top of this page. Alternatively, create a new public repository and upload `index.html` to it.
2. In your repository, go to **Settings → Pages**.
3. Under **Build and deployment**, choose **Deploy from a branch**, pick `main` and `/ (root)`, then click **Save**.
4. After a minute, your copy is live at `https://<your-username>.github.io/<repo-name>/`.

Chrome only autofills cards on secure (`https://`) pages, which GitHub Pages provides automatically.

## Editing the styles

The security policy only allows the exact inline stylesheet currently in the file, identified by its SHA-256 hash. If you change anything between `<style>` and `</style>`, recompute the hash and update the `style-src` value in the policy tag. You can print the new hash with:

```sh
python3 -c "import re,hashlib,base64;s=open('index.html').read();c=re.search(r'<style>(.*?)</style>',s,re.S).group(1);print('sha256-'+base64.b64encode(hashlib.sha256(c.encode()).digest()).decode())"
```

If the hash doesn't match, the browser ignores the styles. The page still works, just unstyled.

## License

MIT. Not affiliated with Google.
