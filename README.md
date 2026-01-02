# Mini Projet DevOps  
## pour plus de details - voir rapport
##  Étudiant
- Nom : Bouhmadi
- Prénom : Manar

##  Objectif
Mise en place d’une chaîne CI/CD complète en utilisant :
Git, GitHub, GitHub Actions, Jenkins, Docker et Slack.

---

##  Structure du projet
![Structure](github-repo.png)

---

### Pull Request
![PR](github-pr.png)

---

##  GitHub Actions
Workflow CI déclenché sur push et pull request.
![Actions](github-actions.png)

---

##  Jenkins Pipeline
Pipeline Jenkins avec les étapes :
- Checkout
- Build
- Test
- Archive

![Pipeline](jenkins-pipeline.png)
![Stages](jenkins-stages.png)

---

##  Slack Notification
Notification automatique après succès du pipeline.
![Slack](slack-notification.png)

---

##  Résultat 
Le pipeline CI/CD fonctionne correctement :
- Build réussi
- Tests validés
- Archive générée
- Notification Slack envoyée
