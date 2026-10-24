# Image Reverse Prompt

A reusable agent skill for reverse-engineering image prompts. When the user uploads an image and asks for its prompt, the agent first classifies the image, then breaks it down by that category's dimensions, then outputs a copy-ready reconstructed prompt.

## The seven categories

- General (fallback for any image)
- Font / Logo / text design
- Landscape
- Photography
- Illustration
- 3D
- IP character

Composite posters and infographics that mix photos with text, maps, and icons use General as the main category, with Photography and Font / Logo / text design as auxiliaries.

## Output format

1. Classification, with a reason
2. Detailed breakdown by the category's dimensions
3. Reconstructed original prompt in Chinese, plus an English keyword list
4. Keyword list

The reconstructed prompt is an inference from the image, not the original creator's actual prompt. Factual errors in a pasted prompt (for example, placing a polar bear in Antarctica) are corrected and the correction is stated.

## Source and attribution

This skill is an original paraphrase of a general reverse-prompt workflow. It is not a copy of the post that inspired it. Read the original post in full here:

https://x.com/mmmusol/status/2093584457412517905

Author of the original post: Musolsol (@MMMusol), 2026-08-29.
