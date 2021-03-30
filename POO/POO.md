# Création d’un objet

Dans le fichier index.php : `require ‘nomDeLaClasse.php’`

1. Créer la classe, la convention dit qu’il faut créer un fichier PHP par class :
    `class nomDeLaClasse {}`
    
2. Dans index.php, création d’une nouvelle instance de ma class (objet) : `$nom = new nomDeLaClasse();``
3. Définir une propriété dans la classe nomDeLaClasse (une propriété est en gros l’équivalent d’une variable ) : `public $nomDeLaPropriété = 100;` 
4. Récupérer le contenu de la propriété (variable) : `var_dump($nomDeLaClasse->nomDeLaProprété);`
5. Définir une méthode (fonction) : 
    `public  function  crier() {
            echo  'leroyyyyyy jenkins';
      }`
      
6. Accéder à la méthode : Dans index.php -> `var_dump($merlin->crier());`
7. Changer la valeur d’une propriété : `$nomDeL’instance = nomDeLaClasse->nomDeLaPropriété = 80;`
8. `$this` fait référence à l’instance (objet) en cours
9. ATTENTION : chaque instance de la classe (chaque objet) est différent.
10. ATTENTION : on peut définir des propriétés à la volée en les définissants directement, par contre cela est déconseillé. Il vaut mieux définir toutes les propriétés dans la class. exemple -> `$nomDeL’instance->nomDeLaPropriété = valeur;`
11. Le constructeur existe par défaut dans toutes les classes mais il est vide. 
    `public  function  __construct($parametre)
    {
            $this->parametre = $parametre;
    }`
    
    Dans index.php : `$nomDeL’instance = new nomDeLaClasse(parametre);`
    
 12. La portée des variables (public, private et protected) :
    * public : la variable est accessible depuis l’extérieur ;
    * private : la variable n’est accessible que depuis l’intérieur de la class, pour y accéder depuis l’extérieur, il faut créer une fonction à l’intérieur de la class.
            exemple : `public function getNomDeLaVariable() {
                                    return $this->nomDeLaVariable; }`
                                    
* protected : Aussi strict que le private sauf que l’on peut y accéder depuis des class qui hérite de la class parente.    

En général on crée tous en private et si on a besoin d’y accéder depuis l’extérieur on crée des GETTERS. Les SETTERS font la même chose mais en sens inverse (définissent une valeur à la variable).

13. Propriétés et méthodes statiques, on ajoute `static` à la classe : 
                    `class  Text
                    {
                            public  static  function  withZero($chiffre)
                            {
                                    if($chiffre <  10)
                                    {
                                            return  '0'  . $chiffre;
                                    } else {
                                            return $chiffre;
                                    }
                            }
                    }`
                    
Pour appeler la méthode, on utilise deux points : `Text::withZero(4);`

SELF : `class  Text
{
        public  function  publicWithZero ($chiffre)
        {
            return  self::withZero($chiffre);
        }
        private  static  function  withZero($chiffre)
        {
                if($chiffre <  10)
                {
                        return  '0'  . $chiffre;
                } else {
                        return $chiffre;
                }
        }
}`

SELF peut être utilisé également au niveau de l’instance.

14. L’héritage : Pour dire qu’une class hérite des mêmes propriétés et méthodes qu’une autre class, `class nomClassFille extends nomParentClass`
            * Cela permet d’ajouter de nouvelles méthodes ou nouvelles propriétés par l’intermédiaire de la classe fille.
            * Si on veut que la class fille puisse accéder à une propriété private de la classe parente, il faut transformer le private en protected. A ce moment la, l’enfant peut choisir de mettre la propriété en public ou en protected mais pas en private.
            * L’héritage fonctionne aussi bien pour les propriétés que pour les fonctions. Cela permet de redéfinir une fonction.
            * Pour appeler une fonction d’une class parente dans la fonction d’une class enfant on utilise : `parent::nomFonctionParente();`

ATTENTION : Quand on redéfini une fonction, il faut qu’elle est la même signature (nom et paramètres). La redéfinition peut être utile pour redéfinir un constructeur.

15. L’autoloading : Permet de charger automatiquement les différentes class. `spl_autoload_register(‘mon_autoloader’);`

16. Les Namespaces : 