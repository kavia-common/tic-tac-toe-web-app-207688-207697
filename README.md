# Tic Tac Toe Web App (React)

This repository contains the frontend for a web-based Tic Tac Toe application.

At the moment, the frontend container is a Create React App (CRA) project that renders a simple page with a light/dark theme toggle. If you are expecting a full Tic Tac Toe game board, that game UI has not been implemented yet in the current codebase.

## Repository structure

The React frontend lives here:

- `tic-tac-toe-web-app-207688-207697/tic_tac_toe_frontend/` – React app (CRA)

## Prerequisites

You need:

- Node.js (an LTS version is recommended)
- npm (ships with Node.js)

## Run the frontend (development)

1. Open a terminal and go to the frontend directory:

   ```bash
   cd tic-tac-toe-web-app-207688-207697/tic_tac_toe_frontend
   ```

2. Install dependencies:

   ```bash
   npm install
   ```

3. Start the dev server:

   ```bash
   npm start
   ```

4. Open the app in your browser:

   - CRA default: http://localhost:3000

If your environment already provides a preview URL (for example via a hosted dev environment), use that URL instead of localhost.

## Use the app (current behavior)

The current UI is a simple page that includes:

- A button in the top-right corner to toggle between light and dark theme.
- A React logo and a “Learn React” link.

Theme state is stored in React component state and applied to the document by setting `data-theme` on the `<html>` element.

## Environment variables

This project is a frontend-only React app. If your environment provides a `.env` file, it may include variables like the following:

- `REACT_APP_API_BASE`
- `REACT_APP_BACKEND_URL`
- `REACT_APP_FRONTEND_URL`
- `REACT_APP_WS_URL`
- `REACT_APP_NODE_ENV`
- `REACT_APP_NEXT_TELEMETRY_DISABLED`
- `REACT_APP_ENABLE_SOURCE_MAPS`
- `REACT_APP_PORT`
- `REACT_APP_TRUST_PROXY`
- `REACT_APP_LOG_LEVEL`
- `REACT_APP_HEALTHCHECK_PATH`
- `REACT_APP_FEATURE_FLAGS`
- `REACT_APP_EXPERIMENTS_ENABLED`

Notes:

- In Create React App, only variables prefixed with `REACT_APP_` are exposed to the browser bundle.
- The current code in `src/App.js` does not read any environment variables yet; they are available for future API integration and configuration.

## Build for production

From `tic_tac_toe_frontend/`:

```bash
npm run build
```

This creates a production build in the `build/` directory.

## Run tests

From `tic_tac_toe_frontend/`:

```bash
npm test
```

This project includes the default CRA test scaffolding (see `src/App.test.js`).

## Develop and customize

### Main entry points

- `tic_tac_toe_frontend/src/index.js` mounts the React app.
- `tic_tac_toe_frontend/src/App.js` contains the main `App` component (currently the theme toggle UI).
- `tic_tac_toe_frontend/src/App.css` defines theme variables and styling.

### How theming works

`App.js` updates the DOM attribute:

- Light mode: no special attribute values besides `data-theme="light"`.
- Dark mode: `data-theme="dark"`.

`App.css` provides two sets of CSS variables:

- `:root { ... }` for light theme variables
- `[data-theme="dark"] { ... }` for dark theme overrides

To adjust the look and feel, update the CSS variables and component styles in `src/App.css`.

### Implementing the Tic Tac Toe game

To implement the intended Tic Tac Toe experience described in the work item, you will typically:

1. Replace the current template UI in `src/App.js` with:
   - A 3x3 game board
   - Player turn indicator
   - Status message for win/draw
   - Reset/new game button

2. Add local state for:
   - Board cells (9 values)
   - Current player (X/O)
   - Game status (in-progress/winner/draw)

3. Style the board and UI in `src/App.css`.

## Troubleshooting

### Port already in use

If port 3000 is already in use, CRA will typically offer a different port when run interactively. In CI or constrained environments, stop the other process using the port or configure the port via your environment tooling.

### Clean install

If dependencies get into a bad state:

```bash
rm -rf node_modules package-lock.json
npm install
```

## Learn more

- React docs: https://reactjs.org/
- Create React App docs: https://create-react-app.dev/
