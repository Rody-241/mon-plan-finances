# Mon Plan Finances

Application web installable (PWA) pour gérer son argent :

- **Portefeuille** : épargne totale, variation du mois, courbe, positions.
- **Alertes** : versements et engagements en retard.
- **Répartir** : le revenu découpé en enveloppes selon le profil (étudiant, salarié, commerçant, sans emploi, retraité).
- **Objectif** : combien mettre de côté par mois, par semaine, par jour pour atteindre un montant (ex. 1 000 000 FCFA).
- **Business** : ventes, marge, charges → ventes à faire par jour et leviers pour atteindre l'objectif.
- **Discipline** : rythme adapté à l'activité, rappels, notifications, engagements de la semaine.
- **Suivi** : historique des versements.

Les données restent sur le téléphone de l'utilisateur (localStorage). Aucun serveur, aucun compte.

## Mettre en ligne avec GitHub Pages

1. Pousser ces fichiers à la racine du dépôt (branche `main`).
2. Sur GitHub : **Settings → Pages → Build and deployment → Source : Deploy from a branch**, branche `main`, dossier `/ (root)`, puis **Save**.
3. Après 1 à 2 minutes, l'app est en ligne sur `https://<utilisateur>.github.io/<depot>/`.

## Installer sur le téléphone

- **Android (Chrome)** : ouvrir le lien, puis bouton **Installer** dans l'app, ou menu ⋮ → **Ajouter à l'écran d'accueil**.
- **iPhone (Safari)** : bouton Partager → **Sur l'écran d'accueil**.

## Notifications

Dans **Discipline → Notifications**, appuyer sur **Activer les notifications**. L'app prévient des retards à son ouverture et pendant qu'elle tourne en arrière-plan. Sans serveur, une page web ne peut pas réveiller le téléphone à une heure précise quand elle est complètement fermée : pour un rappel garanti, ajouter aussi une alarme ou un évènement récurrent dans l'agenda du téléphone.

## Mettre à jour l'app

Modifier `index.html`, puis changer `VERSION` dans `sw.js` (ex. `mpf-v2`) pour que les téléphones récupèrent la nouvelle version.

## Structure

```
index.html            l'application (HTML, CSS, JavaScript)
manifest.webmanifest  nom, icônes, couleurs pour l'installation
sw.js                 service worker : hors connexion + clic sur notification
icons/                icônes de l'app
```
