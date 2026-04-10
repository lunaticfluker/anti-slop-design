# Anti-Slop Photo & Image Prompt Rules

Apply these when writing prompts for FLUX 2 Pro, Midjourney, DALL-E, or any AI image generator. These rules produce editorial-quality output that doesn't look AI-generated.

## The AI tells in image prompts (never do these)

### Composition
- **Never say "centered composition"** — AI defaults to centered. Say "off-centre" or "asymmetric."
- **Never say "symmetrical"** — say "nothing symmetrical, nothing perfect."
- **Never say "beautiful" or "stunning"** — these are filler words AI ignores. Be specific about mood.
- **Never say "high quality" or "4K" or "8K"** — these do nothing. Specify the camera and film stock instead.
- **Never say "professional photography"** — say which photographer or publication. "Rich Stapleton (Cereal)" > "professional photography."

### Person/subject
- **Never say "looking at the camera"** — say "unaware of camera" or "eyes on the task."
- **Never say "posing"** — say "mid-gesture" or describe the action naturally.
- **Never say "sharp facial features, visible pores"** — AI interprets too literally, creates uncanny faces. Say "natural skin texture, slight imperfections."
- **Never force "three-quarter angle"** — over-constrains composition. Let the scene determine the angle.
- **Never say "shallow depth of field"** as a standalone instruction — it's too generic. Specify the camera (Hasselblad 80mm f/2.8) and the bokeh will follow.

### Environment
- **Never describe a generic interior** — "bright modern room with white walls" = stock photo. Use specific atmospheric details: "morning light through large windows, flour-dusted oak table."
- **Never hardcode person actions per industry** — "arranging ingredients" for every food brand = identical output. Let per-brand voice descriptors drive the gesture.
- **Never describe the space when a space-type tag already handles it** — don't say "modern showroom" twice.

### Color
- **Never say "the only brand-colored item in frame"** — AI isolates color unnaturally. Say "brand color visible in the product or one worn detail."
- **Never say "shadows carry [color]"** — pushes the entire grade toward a different mood. Keep color as accent, not grade.
- **Never describe brand color as the dominant grade AND as a physical accent** — pick one. Let the film stock handle the mood.

## The anti-slop prompt structure

### For lifestyle/editorial photography:
```
[Color accent: brand color on product/worn detail. Everything else natural.]
[Emotional framing: "Intimate editorial photograph" not "Editorial lifestyle photograph"]
[Brand mood: voice descriptors as comma-separated adjectives]
[Visual direction: AI-generated per-brand, not hardcoded per industry]
[Modern anchor + scene: "Modern, contemporary interior." + industry-specific scene details]
[Person with product: name the specific product + use productPhotoDesc for what they're doing with it]
[Face: "Face visible, eyes on the task, never looking at camera."]
[Gesture: "The gesture feels {voiceDescriptor1} and {voiceDescriptor2}."]
[Texture: "Natural skin texture, slight imperfections."]
[Clothing: "Dressed simply — quality fabrics, understated, fitting the space."]
[Technical: camera format + film stock + lighting + composition from archetype]
[Photographer reference: specific names with campaigns/publications]
[Anti-slop anchors: "Understated, human, grounded."]
[Negative guidance: "Photorealistic — not illustrated, not commercial, not CGI."]
[Constraints: "No text, no logos, no watermarks."]
```

**Key pattern: productPhotoDesc** — Don't describe the product generically ("using the product"). Instead, generate a photographer direction per product that tells the AI what to shoot:
- Physical: "Single whisky bottle on dark marble, side-lit, condensation on glass, wax seal visible"
- Service: "Two people mid-conversation at a glass table, documents between them, natural window light"
- Experience: "Empty dental chair in modern treatment room, warm wood accents, morning light through frosted glass"

The lifestyle prompt uses this to show the person interacting with a specific, described product — not a vague "using a product."

### For product photography:
```
[Color: brand color as product tone, packaging in sub-color, natural background]
[What: product name, brand name, productPhotoDesc (photographer direction, not marketing copy)]
[Visual direction: same as lifestyle — consistency across the brand]
[Tactile: "Every material rendered with tactile precision"]
[Focus: "Shallow depth of field — product razor-sharp, background gradient"]
[Technical: camera + film stock from archetype]
[Lighting: product-specific lighting from archetype]
[Photographer reference]
[Constraints: "Photorealistic. Not a 3D render, not illustrated. No text, no watermarks, no human hands."]
```

**productPhotoDesc vs productDesc:** The product description is marketing copy ("Hand-thrown ceramic mug in ash glaze"). The photo description is photographer direction ("Single ceramic mug on weathered oak board, steam rising, morning side light"). Use the photo description in prompts — it tells the AI what to shoot, not what to sell.

### For architectural/interior photography:
```
[Color: brand color as architectural accent, subtle, not dominant]
[What: interior photograph for brand — category]
[Visual direction: same as other images]
[Modern anchor + scene: "Modern, contemporary interior." + industry-specific space description]
[Architectural details: lighting, composition, spatial depth from archetype]
[Depth: "The space has depth — foreground, midground, background all visible."]
[Technical: camera + film stock]
[Photographer reference]
[Quality benchmark: "Architectural Digest quality"]
[Constraints: "Not a 3D render, not CGI. No people, no text, no signage."]
```

## Key principles

1. **One visual direction drives all images** — not different per image type
2. **Specific camera + film stock > "high quality"** — "Hasselblad 500CM, Kodak Portra 400" tells the model exactly what look to produce
3. **Named photographers > "professional"** — "Juergen Teller (Balenciaga)" is a precise aesthetic reference
4. **Mood words from the brand > generic adjectives** — "honest, unhurried, tactile" > "beautiful, stunning, amazing"
5. **"Modern, contemporary" as an anchor** — prevents the scene from going rustic/traditional even with specific cultural references
6. **Person uniqueness from brand voice, not industry template** — two food brands get different human energy because their voice descriptors differ
7. **Photographer direction > marketing copy** — "Single whisky bottle on dark marble, side-lit" > "Premium aged whisky, crafted with care." Tell the AI what to photograph, not what to advertise.
8. **Name the product in the scene** — "A real person with Omakase Board — charcoal-grilled tasting set" > "A person using the product." Specificity prevents generic output.
