---
section: Implementing accessibility
title: Automated testing and auditing tools
status: wip
---

It’s impossible to test for accessibility compliance using automated methods alone. Many of the WCAG guidelines require human judgement in order to ascertain if they are met or not. For example, a computer cannot easily determine whether an image’s alt text accurately describes the image, or if a label is associated with the correct input. Those tests require human interpretation.

Automated tests can still be useful for finding other issues however. Tools that can assist in accessibility testing include [WAVE](http://wave.webaim.org/) and the [Lighthouse accessibility audit](https://developers.google.com/web/tools/lighthouse/). 

- Automated tests don't cover all areas of accessibility compliance, but they help find common mistakes.
- WAVE
- Lighthouse
  - Maintained by Google
  - Can be integrated into automated testing suites (like Jest/Puppeteer)
- Browser devtools
  - Safari auditor
  - Colour contrast checkers
