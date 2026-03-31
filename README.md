# EcoKnow Map Editor

A browser-based grid map editor for ecosystem modeling. Paint zone types onto a grid and assign entity populations to cells — no installation, no dependencies.

## Getting Started

Open `index.html` in any modern browser. No server or build step required.

On launch, the welcome screen guides you through two steps:

1. **Load a matrices CSV** — defines the entity types (species, machines, etc.) and their interaction matrix
2. **Load an existing map CSV** or **create a new map** by specifying grid dimensions

Sample files are provided in the `References/` directory.

## Features

- **Zone painting** — define zone types with custom names and colors, then paint them onto the grid
- **Entity populations** — assign per-cell population counts for each entity type
- **Select & inspect** — click cells to view and edit their zone and population data
- **Pan & zoom** — scroll to zoom, hold Space to pan (works in any tool mode)
- **Undo** — stroke-based undo with Ctrl+Z
- **Import/Export** — save and load maps as CSV files

## Drawing Tools

| Tool | Shortcut | Description |
|------|----------|-------------|
| Zone Brush | Z | Paint zone types onto cells (select a zone, or use eraser) |
| Entity | E | Set population values for the selected entity type |
| Select | S | Click a cell to inspect/edit its properties |
| Pan | Space (hold) | Drag to pan the viewport |

## CSV Formats

### Matrices CSV

First row contains entity names. Subsequent rows form the interaction matrix.

```
Benguet Pine Tree,Vetiver Grass,Bamboo (saplings),...
1,2,3,...
1,2,3,...
```

### Map CSV

Header lines define zones and entities, followed by grid data where each cell is a zone ID optionally followed by population counts in brackets. `-1` represents empty cells.

```
#zones:0=Habitable Land:#2d8a4e,1=Laterite Soil:#c45a2c,...
#entities:Benguet Pine Tree,Vetiver Grass,...
-1,-1,0[2,0,0,1,0,0],1[0,1,0,0,0,0],-1
```

## Architecture

The entire application is a single `index.html` file — all CSS, HTML, and JavaScript included. No frameworks, no bundler, no external dependencies beyond Google Fonts.
