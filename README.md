1) Where would you fit your automated tests in your Recipe project development pipeline? Select one of the following and explain why.

Automated tests should ideally run **every time code is pushed** (aka: **1. Within a Github action that runs whenever code is pushed**) to catch issues early and to make sure projects remain stable. Integrating these tests into a GitHub Action, or any CI pipeline, will allow developers to detect bugs or features that shouldn't be implemented as soon as new code is added, prevent "bad" code from being merged into the main branch, and ensure tests run consistently across different environments (rather than just running tests locally and relying on individual developers). This practice supports Continuous Integration (CI) and helps maintain code quality throughout the development lifecycle.

2) Would you use an end to end test to check if a function is returning the correct output? (yes/no)

**No**, end to end testing is used to simulate user interaction. It tests application workflow as a user. To check that a function returns the correct output, a unit test (which typically checks logic outputs) would be better than an end to end test.

3) What is the difference between navigation and snapshot mode?

Navigation mode analyzes a page right after it loads, so it is best used/runs when you load or navigate to a new page. Navigation mode also provides an overall performance metric, but it cannot analyze interactions or changes in content. In other words, it simulates a user loading a page from scratch and measures performance, execution, and structure, to understand site performance on the first load.

Snapshot mode, on the other hand, analyzes a page in its current state, so it takes a "snapshot" of the current page state, as we see it. Snapshot mode is best used for finding accessibility issues but it cannot analyze JS performance or changes to DOM tree. In other words, it measures accessibility issues, SEO structure, and visual and structural HTML/CSS problems, to audit static elements.

4) Name three things we could do to improve the CSE 110 shop site based on the Lighthouse results.

Here are three things we could do to improve the CSE 110 shop site based on the Lighthouse results...
1. Add a `<meta name="viewport">` tag (Red triangle mark)
    - Lighthouse flagged that the site does not have a `<meta name="viewport">` tag
    - Without the tag the mobile responsiveness is affected negatively specifically on smaller screens. Lighthouse report states "A <meta name="viewport"> not only optimizes your app for mobile screen sizes, but also prevents a 300 millisecond delay to user input."
    - Fix: add `<meta name="viewport" content="width=device-width, initial-scale=1">` in the html `<head>`
2. Reduce unused JS (Orange square mark)
    - Lighthouse flagged that we could be saving 1,213 KiB by reducing the amount of unused JavaScript
    - This affects performance (more load time)
    - Fix: As Lighouse report states "Reduce unused JavaScript and defer loading scripts until they are required to decrease bytes consumed by network activity." Lighthouse also lists AI Grammar Checker & Paraphraser – LanguageTool , chrome-extension://kbfnbcaeplbcioakkpcpgfkobkghlhen/src/js/Grammarly-check.js, and Adobe Acrobat: PDF edit, convert, sign tools as the three unused JS contents that could save 1,213 KiB
3. Properly Size images (Red triangle mark)
    - Lighthouse flagged that images could be properly sized in order to save 798 KiB
    - This affects performance and Speed Index. Lighthouse states "Serve images that are appropriately-sized to save cellular data and improve load time." and highlights each image used as a potential issue.
    - Fix: Resize larger images to appropiate dimensions, convert images to WebP or AVIF, use the `<img>` tag to control sizes of images



