# Playwright - Flashcards

## Qu'est-ce que Playwright ?
Framework de test end-to-end moderne développé par Microsoft pour tester les applications web sur Chromium, Firefox et Safari.

## Comment installer Playwright ?
```bash
npm init playwright@latest
```

## Quelle est la particularité de l'auto-wait dans Playwright ?
Playwright attend automatiquement que les éléments soient prêts avant d'interagir avec eux, éliminant le besoin d'attentes explicites dans la plupart des cas.

## Comment sélectionner un élément par texte dans Playwright ?
```javascript
await page.getByText('Texte à rechercher').click();
```

## Quelle est la différence entre page.locator() et page.$() ?
- `page.locator()` : Sélecteur moderne recommandé avec auto-wait
- `page.$()` : Sélecteur legacy sans auto-wait automatique

## Comment prendre une capture d'écran avec Playwright ?
```javascript
await page.screenshot({ path: 'screenshot.png' });
```

## Comment exécuter des tests en mode headless ?
Par défaut, Playwright s'exécute en mode headless. Pour voir le navigateur :
```bash
npx playwright test --headed
```

## Comment déboguer un test Playwright ?
```bash
npx playwright test --debug
```
Ou utiliser `await page.pause()` dans le code.

---
*Compatible avec l'extension "Anki for VSCode"* 