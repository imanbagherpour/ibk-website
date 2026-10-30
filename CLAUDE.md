# Context

Read this first in every new chat or Claude Code session.

## What we're building
A website for a web design business that builds websites for local businesses in Berlin: cafés and restaurants, shops, studios and trades. These are small, owner-run places that need a clear, good-looking website without hiring a big agency.

## What makes us different
- **Better UX and UI.** Sites that are clear, fast and easy to use on a phone.
- **An easier way for the owner's customers to pay.** Paying should take as few steps as possible.
- **A detailed dashboard for the business owner.** One place to see numbers such as visitors, sales and more.

## Our Git
- Design system: https://github.com/imanbagherpour/ibk-design-system
  Tokens (`assets/tokens.css`), components (`assets/components.css`), the storybook (`storybook.html`), the design skill (`SKILL.md`), and page designs in `prototypes/`.
- Website: https://github.com/imanbagherpour/ibk-website
  The pages Claude Code builds. `main` is the live site, `staging` is the rehearsal, every change goes through a pull request.
- The design system repository is the source of truth. The website only uses what is in it.

## Stack
Plain HTML, CSS and a little JavaScript. No build step. Hosted on Netlify, connected to the website repository. The contact form uses Netlify Forms.

Payments and the owner dashboard (visitors, sales) need services beyond plain HTML, such as a payment provider and an analytics tool. None has been chosen yet. Claude Code must not pick or install one on its own: stop and ask with two or three options, including cost, GDPR impact and where data is stored.

## Pages
`index.html` (home) · `pricing.html` · `about.html` · `contact.html` · `thanks.html` (after the form)

## How we work: the loop
1. Design in Claude chat: prototype the page, try versions, check phone and desktop.
2. Update the design system: anything reused or a rule goes into tokens, components, storybook and SKILL.md. The page goes into `prototypes/`.
3. Push the design system repository to GitHub.
4. Claude Code, in the website repository: get the latest design system, update tokens and components to match, build the page from its prototype, on a new branch.
5. Test on localhost: phone and desktop, every link, Lighthouse. Not OK? The report goes back to Claude chat.
6. Pull request, check the Netlify preview link, merge. The site goes live.

## Rules for Claude Code
- Never make a design decision. Colours, fonts, spacing, layout, copy, motion and imagery are decided in Claude chat and live in the design system or the prototype.
- If something isn't defined there, stop and ask. Offer two or three options with a short reason for each. Don't pick one yourself.
- Use only tokens from `assets/tokens.css` and components from `assets/components.css`. Never hard-code a value.
- Never choose a payment, analytics or dashboard tool without asking first.
- Work on a branch, never directly on `main`.
- After building, run the site locally, test phone and desktop, and report what you built, what you tested and every open question, before opening a pull request.

## Current state
Design system and website repositories exist. Starting kit: Clay. Tokens unchanged so far. Home page designed (split hero, direction 3) and saved as prototypes/home.html; new components hero--split and card--row added. Next: push the design system, then build index.html with Claude Code on a branch called home-page. Open: final copy, German version, payment and dashboard tools.
