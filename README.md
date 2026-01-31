https://github.com/ejcacciatore/mcrae-pathfinder.git

# 🛰️ Pathfinder Mission Control: McRae's Launch Control

An interactive career and academic pathway exploration tool designed for students navigating major decisions, particularly those with unique learning profiles who are passionate about space, technology, and big ideas.

![Mission Status](https://img.shields.io/badge/Mission-Active-00ff88?style=for-the-badge)
![Built With](https://img.shields.io/badge/Built_With-React-00d4ff?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-ffd700?style=for-the-badge)

---

## 🚀 Overview

**Pathfinder Mission Control** helps students discover optimal academic majors and career pathways by analyzing their unique strengths, interests, learning styles, and priorities. Originally designed for a student transitioning from Aerospace Engineering at the University of Alabama, this tool provides personalized recommendations based on a comprehensive slider-based profile system.

### Key Features

- **22 Interactive Sliders** across 6 categories to build a complete learner profile
- **Tier-Ranked Results** (S/A/B/C) for majors and careers with match percentages
- **Caution Flags** that warn about potential challenges based on your profile
- **Radar Chart Visualization** to see your profile at a glance
- **Dynamic Next Steps** that update based on your selections
- **Profile Management** — save multiple scenarios and compare paths
- **Shareable URLs** — send your exact configuration to advisors or family
- **Mobile-First Design** with enhanced desktop layout
- **Space-Themed UI** with NASA-inspired aesthetics

---

## 📊 How It Works

### 1. Build Your Profile

Adjust sliders across six categories:

| Category | What It Measures |
|----------|------------------|
| **Learning & Cognitive Style** | Conceptual vs procedural thinking, comfort with ambiguity, verbal vs math strength |
| **Work Environment & Motivation** | Need for structure, project preferences, feedback needs, mentor importance |
| **Interests & Passions** | Space, defense, philosophy, technology, business, writing interests |
| **Executive Function** | Tolerance for repetitive tasks, multi-step comfort, novelty needs |
| **Social & Communication** | Team vs independent work, public speaking, persuasion interest |
| **Career & Life Priorities** | Stability vs risk, salary vs passion, impact goals, location flexibility |

### 2. View Recommendations

Results are organized into tiers:

- **Tier S (75%+)** — Optimal Fit
- **Tier A (60-74%)** — Strong Fit  
- **Tier B (45-59%)** — Moderate Fit
- **Tier C (Below 45%)** — Lower Fit

Each recommendation includes:
- Match percentage
- Description and key points
- Suggested minor pairings (for majors)
- Salary ranges (for careers)
- 🔒 Clearance bonus indicator (for defense careers)
- ⚠️ Caution flags when your profile suggests potential challenges

### 3. Explore & Compare

- Save different profile configurations ("Entrepreneurial Path," "Maximum Stability")
- Generate shareable URLs to send to advisors
- View your profile as a radar chart
- Get personalized next steps based on your settings

---

## 🎓 Included Majors (University of Alabama)

| Major | Best For |
|-------|----------|
| New College Interdisciplinary Studies | Self-directed conceptual thinkers who want custom curricula |
| Philosophy (Mind-Brain) | Deep thinkers interested in ethics, consciousness, and reasoning |
| Communication Studies | Those who love persuasion, public speaking, and influence |
| English (Professional Writing) | Strong writers interested in technical or science communication |
| Political Science | Policy-minded students interested in government and advocacy |
| Psychology | Those curious about human behavior and cognition |
| Economics | Analytically-minded students interested in markets and strategy |
| Marketing | Creative communicators interested in brand and storytelling |
| Management | Future leaders interested in organizations and project management |
| Aerospace Engineering | (Reference) Traditional engineering path for comparison |

---

## 💼 Included Career Pathways

| Career | Salary Range | Clearance Bonus |
|--------|--------------|-----------------|
| Space Policy Analyst | $80K - $150K | ✓ |
| Head of Government Affairs | $160K - $225K | ✓ |
| Aerospace Technical Writer | $98K - $182K | ✓ |
| Science Communicator / Space Journalist | $60K - $120K | |
| Content Producer (Space Company) | $80K - $100K | |
| Program Manager (Aerospace) | $140K - $270K | ✓ |
| Mission Architect / Concept Developer | $100K - $180K | ✓ |
| Aerospace Consultant | $56K - $150K+ | ✓ |
| Space Venture Capital Analyst | $80K - $200K+ | |
| Space Tech Startup Founder | Variable | |
| NASA Public Affairs Specialist | $79K - $160K | |
| Space Advocacy / Nonprofit | $50K - $120K | |
| Graduate School: Space Policy | Investment | |
| Graduate School: Space Law | Investment | |

---

## 🛠️ Installation & Deployment

### Option 1: GitHub Pages (Recommended)

1. **Fork or clone this repository**
   ```bash
   git clone https://github.com/yourusername/pathfinder-mission-control.git
   ```

2. **Rename the HTML file** (if needed)
   ```bash
   mv pathfinder-mission-control.html index.html
   ```

3. **Push to GitHub**
   ```bash
   git add .
   git commit -m "Initial commit"
   git push origin main
   ```

4. **Enable GitHub Pages**
   - Go to repository Settings
   - Navigate to Pages
   - Select "Deploy from a branch"
   - Choose `main` branch, `/ (root)` folder
   - Click Save

5. **Access your tool** at `https://yourusername.github.io/pathfinder-mission-control/`

### Option 2: Local Use

Simply open `pathfinder-mission-control.html` in any modern web browser. No server required.

### Option 3: Any Static Host

Upload the HTML file to Netlify, Vercel, or any static hosting service.

---

## 🔗 Sharing Profiles

The tool generates shareable URLs that encode all slider settings. Example:

```
https://yourusername.github.io/pathfinder-mission-control/?profile=eyJjb25jZXB0dWFsX3ZzX3Byb2NlZHVyYWwiOjl9...
```

Share these URLs with:
- Academic advisors
- UA-ACTS support staff
- Family members
- Career counselors

---

## 📱 Responsive Design

- **Mobile (< 640px)**: Single-column layout, thumb-friendly sliders, collapsible sections
- **Tablet (640px - 1024px)**: Optimized spacing, larger touch targets
- **Desktop (> 1024px)**: Side-by-side panels, sticky results section, enhanced radar chart

---

## ⚙️ Customization

### Adding New Majors

In the `MAJORS` array, add an object:

```javascript
{
    id: 'unique_id',
    name: 'Major Name',
    type: 'Major',
    description: 'Description paragraph...',
    bullets: [
        'Key point 1',
        'Key point 2'
    ],
    weights: {
        conceptual_vs_procedural: 1.5,  // Positive = higher score when slider is high
        verbal_vs_math: -1.0            // Negative = higher score when slider is low
    },
    cautionFactors: [
        { factor: 'slider_id', threshold: 7, message: 'Warning message...' }
    ],
    minors: ['minor_id_1', 'minor_id_2']
}
```

### Adding New Careers

In the `CAREERS` array, add an object:

```javascript
{
    id: 'unique_id',
    name: 'Career Name',
    type: 'Career',
    salary: '$XX,XXX - $XXX,XXX',
    clearanceBonus: true,  // Shows 🔒 badge
    description: 'Description...',
    bullets: ['Point 1', 'Point 2'],
    weights: {
        // Same format as majors
    }
}
```

### Adjusting Slider Defaults

In `SLIDER_GROUPS`, modify the `default` value for any slider to change the pre-populated baseline.

---

## 🧠 Scoring Algorithm

Each major and career has weighted factors. The algorithm:

1. Starts with a base score of 50
2. For each weight factor:
   - Normalizes the slider value to -1 to +1 range
   - Multiplies by the weight and adds to score
3. Clamps final score between 0 and 100
4. Assigns tier based on score threshold

```
Score = 50 + Σ((sliderValue - 5) / 5 × weight × 10)
```

---

## 🎨 Design Philosophy

The space-themed interface is intentional:

- **Dark background with stars**: Creates immersive atmosphere
- **NASA blue and electric cyan accents**: Connects to aerospace passion
- **Orbitron font for headers**: Evokes mission control aesthetics
- **Tier system**: Gamifies exploration without overwhelming
- **Caution flags**: Provides honest guidance without discouragement

---

## 📄 License

MIT License — free to use, modify, and distribute.

---

## 🙏 Acknowledgments

Built with:
- [React](https://reactjs.org/) — UI framework
- [Chart.js](https://www.chartjs.org/) — Radar chart visualization
- [Google Fonts](https://fonts.google.com/) — Orbitron, Rajdhani, Share Tech Mono

Inspired by:
- The journey of finding the right academic path
- UA-ACTS autism support program
- The space industry's need for diverse talent beyond engineering

---

## 🚀 Mission Statement

> "You don't need to be an engineer to shape humanity's future in space. Policy analysts, communicators, strategists, and visionaries are equally essential to the mission."

This tool exists to help students discover pathways that leverage their unique strengths while staying connected to their passions.

---

**Ad Astra** ✨
