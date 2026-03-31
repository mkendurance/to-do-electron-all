# 📝 Todo Electron App

A Todo desktop application built with **Electron** and tested with **Playwright**.

## Structure

```
to-do-electron/
├── todo-electron/          # The Electron app
└── todo-electron-tests/    # Playwright E2E tests
```

## Quick Start

### Run the App
```bash
cd todo-electron
npm install
npm start
```

### Run the Tests
```bash
cd todo-electron-tests
npm install
npm test
```

> See **PROJECT_REPORT.txt** for full documentation including build instructions, test architecture details, and troubleshooting.

## Technologies
- **Electron** — Desktop app framework
- **HTML / CSS / JavaScript** — App UI (no framework)
- **Playwright** — E2E testing with Electron support
- **electron-builder** — Cross-platform packaging

## Key Design: Single App Instance for All Tests

All 20 test cases run against **one shared Electron window** (launched in `beforeAll`, closed in `afterAll`). State is reset between tests via `beforeEach`. This is faster, more stable, and the recommended pattern for Playwright + Electron.
