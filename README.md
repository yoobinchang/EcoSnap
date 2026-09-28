# 🌱 EcoSnap

**Snap your waste. Learn to recycle. Grow your forest.**

EcoSnap is an AI-powered recycling app that turns photos of everyday waste into recycling and reuse guidance. Users earn points by confirming recycling actions and spend those points to grow an interactive 3D cherry blossom forest.

🏆 **Winner of the Sustainability Track at WiCS HopperHacks 2026**

## Inspiration

Recycling can be confusing. Knowing what an item is made of—and how to dispose of it—is not always straightforward.

We built EcoSnap to make learning about recycling more approachable and rewarding. By connecting recycling guidance with a growing virtual forest, the app gives users a visual way to track their participation.

## Features

- **AI image analysis:** Identify an item's materials and receive recycling instructions and reuse ideas through the Gemini API.
- **Multiple-image uploads:** Submit multiple photos and review each item's analysis.
- **Recycling rewards:** Earn points after confirming that an eligible item was recycled.
- **Interactive tree growth:** Spend points to water trees and advance them through four stages, from sprout to full blossom.
- **Forest customization:** Unlock additional planting when all existing trees are fully grown, choose blossom colors, and place new trees in the 3D scene.
- **Progress tracking:** Track lifetime points, available points, and recycling activity by material category.
- **Duplicate detection:** Use file-content hashes to prevent previously rewarded uploads from earning points again.

## How It Works

1. **Upload** a photo of a waste item.
2. **Analyze** the image to receive material information and disposal guidance.
3. **Confirm** that you recycled the item to earn points when eligible.
4. **Grow** your forest by spending points on watering and advancing your trees.

## Built With

| Technology | Role |
|---|---|
| React | UI components and application state |
| Vite | Development server and production builds |
| Three.js / React Three Fiber | 3D trees, animations, and scene interactions |
| Gemini API | Image analysis and recycling guidance |
| Web Crypto API | SHA-256 hashes for duplicate-file detection |
| localStorage | Browser-local profiles and saved progress |
| CSS | Application styling and layout |

## Implementation Highlights

### Tree Growth and Point Management

Lifetime points and spendable points are tracked separately, allowing users to grow their forest without reducing their recorded recycling achievements. Each tree maintains its own growth stage, blossom palette, and position.

Watering interactions connect point spending with a delayed growth-stage update and a corresponding change to the rendered 3D tree.

### Interactive 3D Planting

Raycasting translates clicks on the scene into positions on the ground plane. New trees are placed within a bounded area and tracked individually.

### Image Processing

Images are sent to Gemini for structured analysis. Multiple analysis requests run concurrently, with individual errors handled separately so that one failed request does not discard other results.

SHA-256 hashes identify identical uploaded files without retaining the full images for duplicate checks.
Demo fallback: If Gemini returns a quota or rate-limit error, the app uses sample results to keep the demo running. These results are not based on the uploaded image.

## Getting Started

### Prerequisites

- **Node.js 22.12 or later**
- **npm**
- A **Gemini API key** for image analysis

### 1. Clone the Repository

```bash
git clone https://github.com/yoobinchang/EcoSnap.git
cd EcoSnap/EcoSnap
```

The application lives in the nested `EcoSnap` folder containing `package.json`.

### 2. Install Dependencies

```bash
npm ci
```

### 3. Configure Environment Variables

Create a `.env.local` file alongside `package.json`:

```env
VITE_GEMINI_API_KEY=your_gemini_api_key
```

The application can start without a key, but image analysis requires one. Restart the development server after updating environment variables.

Local development: The app calls Gemini directly from the browser, so the API key is accessible in client code. For public deployment, move API calls and key storage to a backend.

### 4. Run the Application

```bash
npm run dev
```

Open the URL displayed in the terminal, typically `http://localhost:5173`.

## Available Commands

| Command | Description |
|---|---|
| `npm run dev` | Start the development server |
| `npm run build` | Create a production build in `dist` |
| `npm run preview` | Preview the production build locally |
| `npm run lint` | Run ESLint |
