# When I Die List

One sheet of paper that makes it easy for your friends and family to know what to do in the first 48 hours after you die.

You fill in the form in a browser, or print it blank and use a pen. Then you seal it in an envelope and tell two people where it is.

If you only want the paper version, print one of the blank PDFs: [US Letter](when-i-die-list-letter.pdf) or [A4](when-i-die-list-a4.pdf).

## What's on the sheet

1. **First:** who to call, who depends on you, who can step in, and a reminder not to cancel your phone plan
2. **Getting in:** device passcodes, where your passwords are, and your safe or lockbox combination
3. **Where things are:** spare keys, mailbox key, safe or lockbox, will and important papers
4. **Who to call next:** boss, doctor, lawyer, accountant
5. **Anything else only you know**

The scope is deliberately limited to what fits on one sheet. This is not an estate planner. It isn't a will, and it doesn't give anyone legal authority to access devices or accounts or to make medical or financial decisions.

## Use it

You need a browser and a printer. There's nothing to install and no account to create.

1. Download or clone this repository.
2. Open `index.html` in your browser. Double-clicking the file works.
3. Fill in what you know and skip the rest.
4. Choose **Print what I filled in** or **Print blank form**.
5. Seal the printout in an envelope and tell two people where it is.

To confirm it's working, open your browser's print preview. You should see one sheet, without the instructions or buttons.

## Privacy

The list is one self-contained HTML file. It has no server, accounts, analytics, or outside scripts, and its fonts are embedded in the file.

- **Network:** a Content Security Policy in the file blocks the page from making network requests.
- **Storage:** the page doesn't save what you type. It has no form submission and uses no cookies or browser storage.
- **Spellcheck:** it's turned off in every field, because some browsers' enhanced spellcheck sends text to a server.
- **Blank printing:** **Print blank form** empties the fields while printing and restores them afterward, so typed text can't hide inside a saved PDF.

Writing passcodes in pen after printing is the recommended option on any computer.

Some risks are outside what the page can control:

- Your browser could keep typed text, for example through session restore after a crash.
- Browser extensions with permission to read pages may be able to see what you type.
- Saving as a PDF creates a file with your passcodes in it, so print on paper instead.
- Printing can leave a copy in a print queue or on some office printers.
- Anyone who opens the envelope can read your passcodes.

Never type passcodes on a work or shared computer.

When the site is hosted, Cloudflare processes ordinary visit data, including IP addresses. That's separate from what you type, which the site never receives.

## Limitations

- Tested in Chrome, plus Playwright's Firefox and WebKit builds. Letter and A4 PDFs were generated in Chrome with margins up to 1 inch, and fit was measured in the other two. Printing from a phone has been checked by hand and stays on one sheet. Other phones and browsers may behave differently.
- The legal wording has had an AI review but not a lawyer's review.
- Nothing is saved, so changing the list means filling it out again.
- Long entries shrink to fit their lines, and each field has a character limit so text doesn't get cut off.
- The "Written" date comes from the device's clock when the page loads, and it can be edited.

## Editing

There's no build step, so edit `index.html` directly and refresh your browser.

- The fonts are base64-encoded in the second `<style>` block. Those lines are very long, so most edits should avoid them.
- After changing the layout, check the print preview on both Letter and A4. Everything has to stay on one sheet.
- New items have to fit on that sheet too.
- If you change the printed sheet, replace the blank PDFs. Open a clean copy of the form, choose **Print blank form**, and save as PDF on each paper size, using the existing file names.
- If you change the Content Security Policy, change it in both `index.html` and `_headers`.

## Hosting

The site is live at [whenidielist.com](https://whenidielist.com), hosted as a static-assets Cloudflare Worker named `when-i-die`. Pushing to `main` deploys it. There's no build command.

Cloudflare applies the security headers in `_headers` automatically. The `no-transform` value in `Cache-Control` tells Cloudflare not to alter the page, including adding its analytics script.

Leave Web Analytics and Rocket Loader off for this site, and keep Always Use HTTPS on.

## License

To the extent the law allows, this project is dedicated to the public domain under [CC0 1.0](LICENSE). You can copy, change, translate, reprint, or sell it without asking and without giving credit. It comes with no warranty.

The one exception is the fonts. They're derived from IBM Plex and remain under the [SIL Open Font License](fonts-license/OFL.txt). They're renamed WIDL Mono and WIDL Sans because that license reserves the name "Plex" for unmodified copies. The fonts can still be reused freely under that license.

CC0 doesn't cover trademarks, and it doesn't give permission to use anyone's name to imply they endorse a copy.

Made by [Mike Murphy](https://mikemurphy.ai).
