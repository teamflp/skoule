<h1>FEEDBACK3 : APPRENANT3</h1>
<p>L'apprenant3 a fourni un travail solide, mais il y a des lacunes à corriger pour améliorer la qualité du code et le rendre conforme aux meilleures pratiques en PHP. Voici une évaluation en tenant compte des points forts et des points faibles de l'apprenant3 :</p>

<h2>Points forts</h2>

1. Le fichier index.php est bien organisé et structuré, malgré l'absence de certaines routes.
2. L'utilisation des namespaces et des classes dans l'application montre une compréhension des concepts de base de la programmation orientée objet en PHP.
3. Les vues sont bien réalisées et l'interface utilisateur est conviviale.

<h2>Points faibles</h2>

1. Il manque la classe CoreController, essentielle pour garantir une structure cohérente et modulaire dans toute l'application.
2. Les routes dans le fichier index.php sont incomplètes et certaines méthodes dans les contrôleurs sont manquantes.
3. La gestion des sessions utilisateur est absente.
4. Les méthodes de la classe CoreModel ne sont pas correctement implémentées.
5. Il n'y a pas de protection contre les attaques CSRF dans les formulaires de l'application.

<h2>Points à améliorer</h2>
1. **Ajouter la classe CoreController :** Il est important d'ajouter la classe CoreController pour définir les méthodes de base pour les contrôleurs et garantir une structure cohérente dans toute l'application.<br>
2. **Corriger et compléter le fichier index.php :** Il faut ajouter la ligne session_start(); pour gérer les sessions utilisateur, rendre le nommage des routes cohérent avec la correction, et ajouter les routes manquantes pour la suppression, la mise à jour des enseignants et des étudiants, ainsi que pour la gestion des utilisateurs.<br>
3. **Utiliser l'héritage dans le fichier MainController :** L'apprenant3 doit utiliser l'héritage pour rendre le code plus modulaire et facile à maintenir. La méthode show() devrait être déplacée dans une classe CoreController séparée et MainController devrait hériter de CoreController.<br>
4. **Compléter les fichiers StudentController et TeacherController :** Plusieurs méthodes pour ajouter, modifier et supprimer un étudiant ou un enseignant sont manquantes dans ces contrôleurs. De plus, il faut corriger le nommage des méthodes pour qu'il soit conforme aux conventions de nommage en PHP et ajouter un token anti-CSRF pour protéger les formulaires de l'application contre les attaques CSRF.<br>
5. **Améliorer la classe CoreModel :** Il manque les attributs $id et $status, ainsi que la méthode save() et les méthodes insert() et update() qui doivent être implémentées par les classes "enfants" de CoreModel pour que la méthode save() fonctionne correctement.

<p>En travaillant sur ces points d'amélioration, l'apprenant3 pourra renforcer ses compétences en PHP et développer un code plus robuste et conforme aux meilleures pratiques.</p>

<h2>Évaluation détaillée</h2>

1. **Compréhension des consignes :** L'apprenant3 a compris certains des objectifs du projet, mais a manqué de mettre en œuvre des éléments clés pour garantir une structure cohérente et modulaire de l'application.
2. **Qualité du code :** L'apprenant3 a un niveau de qualité de code moyen. Le code est bien organisé, mais il manque des éléments importants tels que la classe CoreController et certaines méthodes dans les contrôleurs.
3. **Connaissances techniques :** L'apprenant3 semble avoir une compréhension de base des concepts clés tels que l'utilisation de namespaces, les classes et les méthodes. Cependant, il y a des lacunes dans la mise en œuvre de certaines méthodes et la structure globale de l'application.
4. **Capacité à suivre les meilleures pratiques :** L'apprenant3 doit travailler sur l'application des meilleures pratiques, en particulier en ce qui concerne l'implémentation de la classe CoreController et la protection contre les attaques CSRF.

<h2>Évaluation globale</h2>

<p>L'apprenant3 a fourni un travail solide, mais des améliorations sont nécessaires pour améliorer la qualité du code et rendre l'application conforme aux meilleures pratiques en PHP. En particulier, l'ajout de la classe CoreController et la correction des méthodes manquantes dans les contrôleurs sont essentiels pour garantir une structure cohérente et modulaire dans toute l'application.</p>
<p>Continuez à travailler dur et à vous investir dans votre apprentissage, vous êtes sur la bonne voie pour atteindre vos objectifs.</p>

<h3>Badge: 🟡</h3>
