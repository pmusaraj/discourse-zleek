# zleek refactor plan

1. Rename theme metadata from "LangChain inspired" to "zleek" and rename the local repo directory to `discourse-zleek`.
2. Refactor `common/common.scss` to reduce rounded corners and card-like borders:
   - flatten radius tokens to zero by default, preserving avatar circles only
   - remove broad `border: 1px solid ...` surface treatments where possible
   - keep subtle border-color variables for existing/core borders
3. Buttons and dropdowns:
   - default transparent borders for `.btn`, `.btn-default`, `.btn-flat`, `.btn-primary`, select-kit/dropdown headers
   - light/subtle border colors on hover, focus, active, or selected states
4. Preserve existing guardrails:
   - no `.sidebar-container` styling
   - no `.d-header-icons` styling
   - no direct welcome-banner search internals
   - no `.user-card` / `.group-card` outer wrapper effects
   - no `overflow:` declarations
5. Compile SCSS, run `git diff --check`, import as `zleek` into local Discourse, and verify imported SCSS/style hash.
