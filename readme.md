# Design System Specimen - Developer Portfolio

Repository URL: https://github.com/tanori-rider/Design System Specimen
Published URL: https://github.com/tanori-rider

----------------------------------------------------------------------

# Test Record

----------------------------------------------------------------------

## Test 1: Responsive Viewports (320px, 768px, 1280px)

Condition: Viewport widths set to 320px (mobile), 768px (tablet), and 1280px (desktop).

Expected Result: Content fits without horizontal overflow or text clipping; grid layouts adjust fluidly.

Observed Result: Card grid converts to a single column on mobile (320px) and expands to multi-column on tablet/desktop.

Outcome: At 320px, horizontal scrolling was not enabled.

----------------------------------------------------------------------

## Test 2: Browser Zoom

Condition: Browser display zoomed to 200% at 1280px screen width.

Expected Result: Text scales proportionally without overlapping, text clipping, or broken containers.

Observed Result: Relative rem units allow text and container padding to expand vertically and cleanly without horizontal scrollbars.

Outcome: Clear legibility at 200% zoom with the vertical expansion maintained.

----------------------------------------------------------------------

## Test 3: Keyboard Navigation & Focus

Condition: Navigated through all links, buttons, inputs, selects, checkboxes, and radios using the Tab key.

Expected Result: Clear, visible outline focus ring on every interactive control for keyboard-only users.

Observed Result: Accent focus outline --color-accent appears on all focused form controls and action buttons.

Outcome: Fully accessible for keyboard-only users.

----------------------------------------------------------------------

## Test 4: Contrast & Alternate Themes

Condition: Evaluated text and interactive controls in both Default Light Theme and Scoped Dark Theme [data-theme="dark"].

Expected Result: Essential text, buttons, and borders maintain WCAG AA contrast (≥ 4.5:1 ratio) in both themes.

Observed Result: Light theme and dark theme surface color tokens swap seamlessly while maintaining high contrast.

Outcome: Contrast standards met in both modes.

----------------------------------------------------------------------

## Test 5: Font Fallback Simulation

Condition: Temporarily blocked the link to Roboto on Google Fonts to force the fallback fonts.

Expected Result: Text renders legibly using the fallback font stack.

Observed Result: Browser fell back to system sans-serif and triggered a revision at the end of Section 3.

Outcome: Revision in Section 3 triggered.

----------------------------------------------------------------------

## Test 6: HTML & CSS Validation

Condition: Ran index.html through the W3C HTML Validator and styles.css through W3C CSS Validator.

Expected Result: Zero syntax errors or invalid declarations.

Observed Result: Zero errors across both files.

Outcome: Valid HTML and CSS

----------------------------------------------------------------------

## Test 7: Publication

Condition: Loaded live GitHub Pages URL in an incognito/signed-out browser session.

Expected Result: External Google Fonts, stylesheet, and component states load identically to local environment.

Observed Result: Page renders with complete token styling and zero missing resource errors.

Outcome: Page is published and verified.

----------------------------------------------------------------------

### Evidence-Based Revision

Finding: During the Font Fallback test (Test 5), blocking "Roboto" caused custom properties --font-body and --font-display to fail in CSS because of a missing comma in the initial stack syntax 'Roboto system-ui' This caused the browser to ignore the variable and drop back to the default serif font (Times New Roman).

Revision: Corrected the typo in the font stack properties.

Retest Result: Re-testing with "Roboto" disabled rendered the page cleanly in system sans-serif.

----------------------------------------------------------------------

### Code Defense

Selective Reset: Using a selective reset rather than a broad reset established a predictable baseline for box model and body margin, while preserving accessibility cues.
----------------------------------------------------------------------

### AI Disclosure & Verification Record

Statement: Generative AI was used to assist in identifying HTML syntax errors. Minimal suggestions were implemented to resolve syntax errors and formatting of CSS tokens. Any modification adhered to MDN Documentation and was validated in Visual Studio Code, as well as browser DevTools. 

----------------------------------------------------------------------