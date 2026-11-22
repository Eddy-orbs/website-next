# Japanese localization

## Editorial direction

- Use `Orbs` for the brand and `ORBS` for the token. Keep product names (dSPOT, dPERPS, dTWAP, dLIMIT, Orbs Agentic, Orbs Lambda, Orbs VM), code, contract identifiers and published PDF URLs intact.
- Follow the existing Japanese staking, contract and privacy-policy terminology: ステーキング, 流動性, スマートコントラクト, ガーディアン, デリゲータ. Explain new trading concepts in polite Japanese; use concise noun phrases for headings.
- Use 執行 for trade execution, 実行 for computational execution, 指値注文, 成行注文, 損切り, 利確, 無期限先物, ノンカストディアル and 自己管理 consistently.
- Preserve existing English navigation/product labels, as in the Japanese legacy chrome and Korean refresh. Translate descriptions, accessibility controls and forms. Keep the Japanese community blog and existing social destinations; do not copy Korean channel overrides.
- English is the source of current product facts; Korean is a cross-check for structure and meaning, not a reason to copy Korean-only wording. In particular, dSPOT funds stay in the wallet until execution, whereas dPERPS collateral is handled by self-custodial contracts. Do not turn execution conditions into unconditional fill guarantees.

## Coverage and exclusions

The public Japanese refresh includes Home, dSPOT, dPERPS, Agentic, Institutions, Venues, Overview, Execution Services, Ecosystem, Security & Audits, FAQ, Contact, Brand Assets, existing PoS/contract content, the Spot skill guide, the news wrapper and all 28 white-paper title/abstract pages. The detailed dTWAP/dLIMIT FAQ is translated as supporting documentation.

Historic Challenge/NFT/Tetra content and unlinked legacy product/use-case pages are not newly translated or reopened. Existing archive routes and published Japanese copy are retained. Product URLs and the redundant AI Skills index continue to redirect to localized dSPOT/Agentic; translation does not override product consolidation.

Published PDFs and CMS articles are not translated. Japanese news headings and navigation surround English CMS cards explicitly tagged `lang="en"`; news stays a noindex placeholder. Existing privacy-policy Japanese is retained. Source-language legal policies (including the English-only implementation-specific cookie policy and Hebrew accessibility declaration) retain their original language/fallback and indexing policy rather than being declared Japanese translations.

## Integration rules

- dPERPS section eyebrow strings are intentionally empty in Japanese and Korean. The main-branch renderer is retained without locale-specific suppression; English keeps its labels and layout spacing follows main.
- `/jp/` remains the URL prefix; `ja` remains the locale/language code.
- Add reachable translated pages through the shared registry/availability map, not duplicate renderers.
- News, pagination and white-paper interface copy is read from the locale catalogs, not embedded in shared renderers. Explicit locale lookup keeps pages prerenderable.
- Japanese FAQ documents carry explicit `/jp/` destinations for available translated internal pages; external URLs remain unchanged. Regression coverage checks rendered destinations rather than requiring raw URLs to equal English.
- Media webhooks invalidate all available news locales, including paginated routes.
- White-paper sitemap entries follow translated locales. Preserve the historical Japanese grant-paper spelling with an exact same-locale redirect, without a catch-all redirect to English.
- During main integration, retain upstream English/Korean behavior and content plus explicitly requested locale copy changes. Japanese-only copy must not alter global social URLs or CMS behavior.
- Blog exclusion and empty CMS fixtures are for the disposable local preview only and must never enter source commits.

## Validation

Run the Node and Chromium/Storybook suites, formatting, ESLint, route type generation and TypeScript. Verify Japanese public routes, product redirects, footer Media/Blog links, white-paper details and desktop/mobile light/dark rendering in the isolated preview. A fixture-backed preview does not validate live Contentful publishing.

## November main integration preview

- Main revision `ef00130` supplies the shared layouts, product graphics and social metadata. Existing Japanese translations remain including the newly added or semantically changed strings, now translated in the Japanese catalog.
- Newly translated copy covers dPERPS marquee/risk headings, Execution Services function/service descriptions and labels, dSPOT order navigation, and the standardized SDK CTA.
- Japanese Contact subtitle is an empty catalog string. Its contact-type label is restored visibly: blanking it would remove the select's accessible name, and locale-specific hiding code is not retained.
- Japanese/Korean dPERPS eyebrows remain empty strings without custom suppression or spacing code. The Overview section is removed by upstream for all locales, not by a translation override.
