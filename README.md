<div align="center">

# ◈ ANTIFITNA

### Le tableau de bord de votre rivalité.

**Suivre les parties. Comparer les scores. Garder une trace des excuses.**

`100 % STATIQUE` · `SANS COMPTE` · `SANS SERVEUR` · `COMPATIBLE GITHUB PAGES`

**[Jouer en ligne →](https://feuille2cedric.github.io/antifitna/)**

</div>

---

## Le concept

**antifitna** est un petit QG pour les parties web jouées entre amis. Le nom est un clin d’œil au palindrome : l’interface reprend cette idée de symétrie entre deux joueurs, deux scores et deux issues possibles — win ou loss.

Le dashboard rassemble :

- le nombre de parties jouées et le taux de victoire ;
- la forme récente sur les sept derniers jours ;
- le classement général entre joueurs ;
- les meilleurs scores par jeu ;
- l’historique des dernières parties ;
- un formulaire pour ajouter rapidement un match.

## Lancer le site

La version publiée est disponible sur **https://feuille2cedric.github.io/antifitna/**.

Ouvre [`dist/index.html`](./dist/index.html) dans un navigateur récent. Aucune installation n’est nécessaire.

Pour le servir en local :

```bash
python -m http.server 8000 --directory dist
```

Puis ouvre <http://localhost:8000>.

## Données et confidentialité

Le projet n’utilise aucun backend. Les parties ajoutées sont sauvegardées dans le `localStorage` du navigateur. Elles restent donc propres à chaque navigateur et à chaque appareil.

## Déployer sur GitHub Pages

Le workflow [`pages.yml`](./.github/workflows/pages.yml) publie automatiquement le dossier `dist` après chaque push sur `main`.

1. Crée un dépôt public nommé `antifitna` sur GitHub.
2. Depuis ce dossier, ajoute le dépôt distant :

   ```bash
   git remote add origin https://github.com/TON-COMPTE/antifitna.git
   git push -u origin main
   ```

3. Dans **Settings → Pages**, choisis **GitHub Actions**.
4. Le site sera ensuite disponible à `https://TON-COMPTE.github.io/antifitna/`.

## Structure

```text
.
├── .github/workflows/pages.yml  # Publication GitHub Pages
├── .openai/hosting.json         # Métadonnées d’hébergement
├── dist/index.html              # Interface, styles et logique du dashboard
└── README.md                    # Documentation
```

Le CSS et le JavaScript sont regroupés dans `dist/index.html` pour garder une version sans build ni dépendances. Ils pourront être séparés en `styles.css` et `app.js` si le projet grossit.

---

<div align="center">

**Les scores mentent parfois. Les historiques, beaucoup moins.**

</div>
