# When I Die List

One sheet of paper that makes it easy for your friends and family to know what to do in the first 48 hours after you die.

You fill in the form in a browser, or print it blank and use a pen. Then you seal it in an envelope and tell two people where it is.

## What's on the sheet

1. **First:** who to call, who depends on you, who can step in, and a reminder not to cancel your phone plan
2. **Getting in:** device passcodes, where your passwords are, and your safe or lockbox combination
3. **Where things are:** spare keys, mailbox key, safe or lockbox, will and important papers
4. **Who to call next:** boss, doctor, lawyer, accountant
5. **Anything else only you know**

The scope is deliberately limited to what fits on one sheet. This is not an estate planner, and it doesn't replace a will.

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
- **Storage:** the page doesn't save what you type. Closing the tab erases it.
- **Spellcheck:** it's turned off in every field, because some browsers' enhanced spellcheck sends text to a server.

Some risks are outside what the page can control:

- Browser extensions with permission to read pages may be able to see what you type.
- Saving as a PDF creates a file with your passcodes in it, so print on paper instead.
- Printing can leave a copy in a print queue or on some office printers.
- Anyone who opens the envelope can read your passcodes.

On a work or shared computer, leave the passcodes blank and write them in pen after printing.

## Limitations

- Tested in Chrome only, using generated PDFs on US Letter and A4. It hasn't been tested on a physical printer or in Safari or Firefox.
- Nothing is saved, so changing the list means filling it out again.
- Long entries shrink to fit their lines, and each field has a character limit so text doesn't get cut off.

## Editing

There's no build step, so edit `index.html` directly and refresh your browser.

- The fonts are base64-encoded in the second `<style>` block. Those lines are very long, so most edits should avoid them.
- After changing the layout, check the print preview on both Letter and A4. Everything has to stay on one sheet.
- New items have to fit on that sheet too.

## Hosting

The planned home is `whenidielist.com` on Cloudflare Pages. It isn't live yet.

The site needs no build. In Cloudflare Pages, connect this repository, leave the build command empty, and set the output directory to the repository root.

## Credits

Made by [Mike Murphy](https://mikemurphy.ai). The embedded fonts are IBM Plex Mono and IBM Plex Sans, licensed under the [SIL Open Font License](https://openfontlicense.org).
