# 🍽️ Meal Flow

A lightweight, single-file web app for planning your weekly meals. Import AI-generated menus via CSV, drag and drop dishes across the week, and keep a reserve list for meals you want to save for later.

## Features

- **Weekly meal grid** — plan lunch and dinner for every day of the week
- **CSV import** — paste or upload a CSV to populate the entire week at once
- **Drag & drop** — rearrange meals freely across days and slots
- **Reservas** — a sidebar holding area to save meals for future weeks
- **Persistent storage** — your plan is saved automatically in the browser via localStorage
- **Responsive design** — works on both desktop and mobile

## How It Works

The intended workflow is to use an LLM (like ChatGPT or Claude) to generate a personalized weekly menu in the required CSV format, then import it directly into the app.

### Prompt example for your LLM

> Give me a weekly meal plan for 7 days (lunch and dinner) in the following CSV format:
> `day,meal_type,dish`
> Use these values: days as `lun`, `mar`, `mié`, `jue`, `vie`, `sáb`, `dom` and meal type as `comida` (lunch) or `cena` (dinner).

### CSV Format

The app expects a simple 3-column CSV with no header row:

```
day,meal_type,dish
```

| Column | Accepted values |
|--------|----------------|
| `day` | `lun`, `mar`, `mié` (or `mie`), `jue`, `vie`, `sáb` (or `sab`), `dom` |
| `meal_type` | `comida` (lunch ☀️) or `cena` (dinner 🌙) |
| `dish` | Any text |

**Example:**

```csv
lun,comida,Pasta al pesto
lun,cena,Ensalada César
mar,comida,Arroz con pollo
mar,cena,Crema de verduras
```

To add a meal directly to the **Reservas** sidebar, use `pantry` or `reserva` as the day value:

```csv
reserva,comida,Lasaña casera
```

## Tech Stack

- Vanilla HTML/CSS/JavaScript — no frameworks, no dependencies
- Font Awesome 6.4.0 (icons)
- Native HTML5 drag & drop with DragDropTouch polyfill (mobile support)
- Browser localStorage for persistence

## Usage

Just open `index.html` in any browser — no server or installation needed.
