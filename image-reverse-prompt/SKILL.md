# Image Reverse Prompt

Use this skill when the user uploads an image and asks to reverse-engineer its prompt ("反推"). Do not skip classification, and do not return a generic image description instead of a usable prompt.

## Step 1: Classify first

Classify the image into one of seven categories before writing anything else. State the classification in the answer.

1. General — works for any image, use it as the fallback.
2. Font / Logo / text design — typography, logos, and text-led designs.
3. Landscape — natural scenery, city scenery, and scenes.
4. Photography — real people, portraits, products, and documentary photos.
5. Illustration — flat, anime, healing, and hand-drawn styles.
6. 3D — C4D / Blender / 3D renders.
7. IP character — designer toys, chibi, and blind-box characters.

Decision rules:

- If the image is a composite infographic or poster that mixes photos with text blocks, a map, and icons, use General as the main category and name Photography and Font / Logo / text design as auxiliaries. A single category will drop either the photo or the layout.
- If text is the dominant visual element, use Font / Logo / text design.
- If there is one clear subject and one clear style, use that subject's category, not General.
- If you are unsure, say so, use General, and name the closest alternative.

## Step 2: Break the image down by that category's dimensions

Use the dimensions below for the chosen category. Write physical relationships, not adjectives alone. For example, say what a prop aligns to, what sits on what, and what the light does, instead of only saying "beautiful" or "high quality".

- General: subject, style, colour, light and shadow, composition, texture, resolution, and detail.
- Font / Logo / text design: typeface style, stroke and weight, serif or sans-serif, corners, three-dimensional effect, gloss, material (metal, matte, glass), colour scheme, layout proportion, and effects such as outline, glow, gradient, or relief.
- Landscape: environment, weather, time of day, sky, clouds, vegetation, water, colour, atmosphere, composition, and depth of field.
- Photography: light type (natural, hard, soft, backlight), depth of field, focal length, image quality (for example 8K, HD, film), colour (cool, warm, vintage, film look), composition, focus, noise, sharpness, and mood.
- Illustration: drawing method (hand-drawn, digital), flat or thick painting, line weight, colour combination, texture, composition, and atmosphere.
- 3D: render style, material, lighting (for example three-point lighting), reflection, roughness, renderer character, soft edges, and volumetric light.
- IP character: character design, style, facial expression, body proportion, hairstyle, clothing and accessories, pose, material (matte, resin, PVC, ceramic), light, and detail.

## Step 3: Output in a fixed format

Output, in this order, for each image:

1. Classification — the category and one line explaining why.
2. Detailed breakdown — the image's content, broken down by the dimensions in Step 2.
3. Reconstructed original prompt — a copy-ready prompt in Chinese, plus an English keyword list. This must be usable to generate a similar image, not just a description of the uploaded one.
4. Keyword list — style, colour, light, material, composition, and quality keywords.

Rules for the reconstructed prompt:

- State clearly that it is a reconstruction inferred from the image, not the original creator's actual prompt, which cannot be verified from the image alone.
- Keep one character, palette, and composition per series so a set reads as a set. If the user wants a series, fix those elements and only vary the scene or action.
- Correct factual errors instead of copying them into the prompt. For example, a polar bear belongs in the Arctic, not Antarctica; drop leftover elements from a different subject (for example a raccoon or a mossy branch) if the user pasted them by mistake. Tell the user what was corrected.
- If the prompt asks for long Chinese body copy on the image, warn that AI image models often garble Chinese text. Offer the safer route: generate a text-free layout and photo first, then add the exact copy in a design tool.

## Worked pattern: animal science infographic poster

A common composite case is a vertical animal science poster. Its reusable template is: vertical format, cream paper texture, a large distressed title at the top left, one photorealistic animal as the main visual on a diagonal branch or on sea ice, a scenic background at the top, a silhouette band at the bottom, section headers in a dark brushstroke with white text, and circular inset photos, a distribution map, food icons, and a family scene around the edges. To reuse it for another species, swap the animal, the background, the map, and the section content, and keep the title treatment, palette, and section-header style fixed.

## Source and attribution

This skill is an original paraphrase of a general reverse-prompt workflow. It is not a copy of the post that inspired it. Read the original post in full here:

https://x.com/mmmusol/status/2093584457412517905

Author of the original post: Musolsol (@MMMusol), 2026-08-29.
