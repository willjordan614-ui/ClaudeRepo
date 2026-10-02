# ClaudeRepo

A cross-platform mobile app for **iOS and Android**, built with [Expo](https://expo.dev) (React Native, SDK 57) and TypeScript. A single codebase runs on both platforms, plus web.

## Get started

```bash
npm install
npx expo start
```

From the dev server you can open the app in:

- **Expo Go** on your phone: install it from the App Store or Play Store, then scan the QR code. On iOS this works without a Mac.
- an **Android emulator** (press `a`) or an **iOS simulator** (press `i`, macOS only)
- a **web browser** (press `w`)

## Project layout

```
src/
  app/          screens and routes (Expo Router, file-based); _layout.tsx defines navigators
  components/   reusable UI (themed text/views, tab bar, ...)
  constants/    theme colors and fonts
  hooks/        shared hooks (color scheme, theme)
assets/         icons, splash screen, images
app.json        app config: name, bundle IDs, icons, plugins
```

The app supports light and dark mode automatically.

## Scripts

| Command             | What it does                             |
| ------------------- | ---------------------------------------- |
| `npm start`         | Start the Expo dev server                |
| `npm run android`   | Start and open on Android                |
| `npm run ios`       | Start and open on iOS                    |
| `npm run web`       | Start and open in a browser              |
| `npm run lint`      | Run ESLint                               |
| `npm run typecheck` | Run the TypeScript compiler (no emit)    |
| `npm run reset-project` | Move the starter screens to `app-example/` and start from a blank `src/app` |

`npm run typecheck` needs `expo-env.d.ts`, which `npx expo start` generates the first time it runs.

## Building for the stores

Use [EAS Build](https://docs.expo.dev/build/introduction/) to create signed iOS and Android binaries in the cloud. You don't need Xcode or Android Studio installed.

```bash
npx eas-cli@latest login
npx eas-cli@latest build:configure
npx eas-cli@latest build --platform all
```

The bundle identifier and package name are both `com.willjordan614.clauderepo` (set in `app.json`). Change them before your first store submission if you want different ones.
