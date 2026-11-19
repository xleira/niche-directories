# Reference: 15 open-source UI/design kit (seeconvm)

Source: https://x.com/seeconvm/status/2123038573066637425 (read via mirror https://teapawt.org/seeconvm/status/2123038573066637425; text only, images/video not seen)
Saved: 2026-11-19. User note: "might be useful for us later". Banked as a reference, not a build request.

## What it is
A text-only list from @seeconvm: 15 open-source repos meant to make agent-built UI look less AI-generated ("no purple gradients, no generic cards"). Workflow claimed: paste the list into the model and rebuild a landing page. The post ends by promoting the author's paid-looking course article on motion design (not fetched). The "nobody can tell it's AI" claim is unverified. One reply notes the real tell is identical section heights. Repo contents and licenses were NOT opened or verified; descriptions below are the author's.

## The 15 (github.com/...)
Build base
- shadcn-ui/ui: components you own as code
- tailwindlabs/tailwindcss: utility-first styling
- magicuidesign/magicui: animated copy-paste components
- lucide-icons/lucide: consistent icons
Taste / anti-slop guidance for agents
- anthropics/skills (frontend-design): UI that doesn't look AI-generated
- anthropics/skills (theme-factory): 10 themes for slides, docs, landing pages
- nextlevelbuilder/ui-ux-pro-max-skill: 80 styles, palettes, font pairings
- google-labs-code/design.md: format describing visual identity to agents
- meta/astryx: design system built for agents
- google-labs-code/stitch-skills: prompt to UI screens
Color
- adobe/leonardo: palettes from contrast ratios
Design-to-agent and canvas
- GLips/Figma-Context-MCP: Figma layouts into an agent
- excalidraw/excalidraw: hand-drawn diagrams, wireframes
- tldraw/tldraw: infinite canvas SDK
Utility
- danielgatis/rembg: background removal

## Where it could slot in
- niche-directories: write a DESIGN.md from the approved editorial design (Fraunces serif, spec strip, numbered entries, ruled layout, no scroll animation) so the nightly caretaker and any future pages keep one identity. Optional: Lucide icons, Leonardo for contrast checks. Magic UI/shadcn do not apply to the static Jinja generator.
- Other web builds: Magic UI + shadcn for React/Tailwind work; check against the user's taste (smooth, calm, depth, few flashes).
- Cinematic pieces: little direct use; Excalidraw/tldraw for storyboards, rembg for cutting out references.

## Next step if used
Open frontend-design and ui-ux-pro-max first, verify licenses, then draft DESIGN.md.
