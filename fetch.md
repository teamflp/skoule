Objet : Conseil technique avancé sur la méthode fetch en PHP

Cher(e) apprenant(e),

Je suis ravi de voir que vous vous en sortez bien avec votre projet et que vous souhaitez approfondir vos connaissances sur certaines notions. Comme vous l'avez demandé, je vais vous expliquer comment réaliser des requêtes HTTP en PHP. Bien que la méthode fetch ne soit pas disponible en PHP, vous pouvez utiliser la bibliothèque cURL pour envoyer des requêtes HTTP similaires.

Qu'est-ce que cURL en PHP ?
cURL est une bibliothèque qui permet d'envoyer des requêtes HTTP et de communiquer avec des API ou des serveurs en PHP. Elle offre une grande flexibilité et prend en charge divers protocoles tels que HTTP, HTTPS, FTP, etc.

<h3>Voici un aperçu de la syntaxe de base pour utiliser cURL en PHP :</h3>

````
$ch = curl_init();
curl_setopt($ch, CURLOPT_URL, $url);
curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);
$response = curl_exec($ch);
curl_close($ch);
````
<h3>Exemple pratique et détaillé d'une requête HTTP avec cURL</h3>
<p>Imaginons que vous avez une route dans pour récupérer la liste des étudiants</p>

````
GET /api/students
````
Voici comment vous pouvez utiliser cURL pour récupérer ces données et les afficher avec deux solutions :

<h3>Solution 1: utiliser une fonction</h3>

````
// On créé une fonction pour récupérer les données JSON à partir d'une URL
function fetchJsonData($url) {
    // Initialisation d'une nouvelle session cURL
    $ch = curl_init();

    // Définition de l'URL de la requête cURL
    curl_setopt($ch, CURLOPT_URL, $url);
    // On demande à cURL de retourner la réponse au lieu de l'afficher directement
    curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);

    // Exécution la requête cURL et stocke la réponse dans une variable
    $response = curl_exec($ch);
    // On fermee la session cURL pour libérer les ressources
    curl_close($ch);

    // On décode la réponse JSON en un tableau associatif et retourner le résultat
    return json_decode($response, true);
}

// Définition de l'URL de l'API
$apiUrl = "http://127.0.0.1:3000/api/students";

// Ici on utilise la fonction fetchJsonData pour récupérer les données JSON à partir de l'URL
$data = fetchJsonData($apiUrl);

// On affiche le contenu du tableau de données
print_r($data);

````
<p>Dans cet exemple, j'ai créé une fonction nommée fetchJsonData qui prend une URL en argument. Cette fonction encapsule la logique de cURL pour effectuer la requête et décoder la réponse JSON. Ainsi, il est possible de réutiliser cette fonction pour d'autres requêtes simplement en changeant l'URL passée en argument.</p>

<h3>Solution 2 : utiliser une classe</h3>

````
class Fetcher {
    // Propriété pour stocker l'URL, avec une déclaration de type (string)
    private string $url;

    // Constructeur pour initialiser l'URL, avec une déclaration de type pour le paramètre
    public function __construct(string $url) {
        $this->url = $url;
    }

    // Méthode pour récupérer les données JSON à partir d'une URL, avec une déclaration de type (array) pour le retour
    public function fetchJsonData(): array {
        // Initialisation d'une nouvelle session cURL
        $ch = curl_init();

        // Définition de l'URL de la requête cURL
        curl_setopt($ch, CURLOPT_URL, $this->url);
        // On demande à cURL de retourner la réponse au lieu de l'afficher directement
        curl_setopt($ch, CURLOPT_RETURNTRANSFER, true);

        // On exécution la requête cURL et stocke la réponse dans une variable
        $response = curl_exec($ch);
        // On ferme la session cURL pour libérer les ressources
        curl_close($ch);

        // On décode la réponse JSON en un tableau associatif et retourner le résultat
        return json_decode($response, true);
    }
}
````
<h3>Comment utiliser la classe Fetcher</h3

Pour utiliser cette classe, on instancie un nouvel objet Fetcher et appelle la méthode fetchJsonData

````
$url = "http://127.0.0.1:3000/api/students";
$jsonFetcher = new Fetcher($url);
$data = $jsonFetcher->fetchJsonData();

````

<h3>La différence entre ces deux solutions</h3>

Les deux solutions que je vous ai présenté sont des approches différentes pour résoudre le même problème : récupérer des données JSON à partir d'une URL. <br>Voici les principales différences entre les deux solutions :

**Fonction fetchJsonData :**

1. La fonction est une approche procédurale pour résoudre le problème. Elle nécessite simplement d'appeler la fonction avec l'URL souhaitée pour récupérer les données JSON.
2. La fonction est plus simple et plus facile à utiliser pour des cas d'utilisation ponctuels.
3. La fonction n'a pas de gestion d'état, donc chaque appel nécessite de passer l'URL à la fonction.


**Classe Fetcher :**

1. La classe est une approche orientée objet pour résoudre le problème. Elle encapsule l'état (l'URL) et le comportement (la récupération des données JSON) dans un objet.
2. La classe permet une meilleure organisation du code et une extensibilité accrue. Par exemple, vous pouvez ajouter des méthodes supplémentaires ou des propriétés à la classe pour prendre en charge d'autres fonctionnalités liées à la récupération de données JSON.
3. La classe nécessite une instanciation d'objet, ce qui peut être légèrement plus complexe que l'utilisation d'une simple fonction. Cependant, cela permet de conserver l'état (l'URL) et d'utiliser la méthode fetchJsonData plusieurs fois sans avoir à passer l'URL à chaque appel.

<p>Par conséquent, le choix entre les deux solutions dépendra de vos préférences personnelles.</p>

<p>N'hésitez pas à adapter cet exemple à votre projet et à l'essayer avec différentes routes de votre serveur pour vous familiariser avec les requêtes HTTP en PHP.</p>

<p>J'espère que cette explication vous aidera à mieux comprendre comment réaliser des requêtes HTTP en PHP et à l'utiliser dans vos projets futurs. 
Si vous avez des questions ou si vous souhaitez plus d'exemples, n'hésitez pas à me contacter.</p>
Bonne continuation dans votre apprentissage !
