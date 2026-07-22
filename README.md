# EcoSnap

Winner of the Sustainability Track in the WiCS HopperHacks 2026 hackathon!

## Inspiration

Only 21% of waste gets recycled in the US. Despite an overall recycling rate of around 32%, plastic recycling is even lower, and most waste still ends up in landfills. The root cause isn't indifference. More than half of Americans are unsure what can actually be recycled, recycling feels like extra effort, and most ends up in landfills. The problem isn't a lack of care; it's a lack of clarity and incentive. The consequences of higher carbon emissions, plastic pollution, and wasted resources make it vital to educate on proper recycling practices.

## What it does

Make recycling simple and fun with EcoSnap! In EcoSnap, recycling is gamified and users can upload pictures of their trash for instant feedback on how to recycle or reuse their trash, depending on its material. By uploading and recycling trash, users gain points that they can use to cultivate their digital cherry blossom forest. As you recycle more, you can watch your trees grow from sprouts to full blossom, as well as plant new species of trees!

## How we built it

We built EcoSnap as a web application using React and Vite. For the 3D sakura forest that users grow with their points, we used Three.js through React Three Fiber, which let us create an interactive UI in the browser. We integrated Gemini API to analyze the image and return recycling advice. User data like points, recycling stats, and forest progress are stored locally through login.
