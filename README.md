# create-ezp-lists
Générateur de liste de chansons pour EasyPrompter
Architecture du site de chansons www.avcxjo-moko-kantas.fr
/www ¬
      L==mp3
      L==arrays ¬
                 L== getID3

on recherche la chanson dans katalogo.inc.php (situé à la racine du site www) donc dans $specoj

/* rappel de la structure de katalogo.inc.php
$specoj= array("Catégorie"=>array(array('rang'=>,'html'=>"",
                                        'lib'=>'   ',
                                        'alt'=>'  '[,
                                        'lang'=>' ',
                                        'autoro'=>' ' || 'amiko'=>' ',
                                        'brassens'=>true,
                                        'pennarbed'=>true]
                                        ),[,…]
                                  ),
                "Autre cat"=>array(array('rang'=> ,'html'=>"   ",
                                         'lib'=>'  ',
                                         'alt'=>'   '[,
                                         'lang'=>' ',
                                         'autoro'=>' ' || 'amiko'=>' ',
                                         'brassens'=>true,
                                         'pennarbed'=>true]
                                         )[,…]
                                   )[,…]
                 ) 
*/

/* rappel de la structure d'un fichier de chanson dans www/arrays/
<?php
$charsize=18;
$kanto=array('rango'=>,
	     'titolo'=>'',
	     'subtitolo'=>'',
	     'dato'=>'',
	     'kreatita'=>'',
	     'autoro'=>'Copyleft MoKo',
	     'capo'=>'[Capo °]',
	     'cxefvortoj'=>array(),
	     'YT'=>'',
	     'pagxoj'=>array(1=>array(array('tipo'=>'strofo',
	      				    'versoj'=>array("")
	      				    ),
	      			      array('tipo'=>'rekantajxo',
	      			            'titolo'=>'Refrain',
	      				    'versoj'=>array("")
	      				    ),
	      			      array('tipo'=>'strofo',
	      				    'versoj'=>array("")
	      				    ),
	      			      array('tipo'=>'rekantajxo',
	      			            'titolo'=>'Au refrain',
	      				    'versoj'=>array()
	      				    )
	      			      ),
	      		      2=>array(array('tipo'=>'strofo',
	      				    'versoj'=>array("")
	      				    ),
	      			      array('tipo'=>'rekantajxo',
	      			            'titolo'=>'Refrain',
	      				    'versoj'=>array("")
	      				    ),
	      			      array('tipo'=>'strofo',
	      				    'versoj'=>array("")
	      				    ),
	      			      array('tipo'=>'rekantajxo',
	      			            'titolo'=>'Au refrain',
	      				    'versoj'=>array()
	      				    )
	      			     )
		            ),
	      'accords'=>array('titolo'=>'Accords utilisés',
	      		       'versoj'=>array(array(),
	      		             	       array(),
	      		             	       array()	      		             	       
	      		             	       )
	      		      ),
	      'bildo'=>''
	     );
*/

/* structure d'un fichier EZP
{"items":{"ID12CHIFFRES":{"titre":"le titre de la chanson",
                          "contenu":"chaque ligne avec un retour chariot \n sauf à la dernière",
                          "id":"reprend l'ID à 12 chiffres",
                          "speed":vitesse de défilement pouvant varier de 0 à 20 0=-10, 20=+10 ),
                          "font-class":"sans-serif" (adaptable ???)
                          },
            "IDSUIVANTE":{titre suivant, etc.}
                         }
         },
         "itemsOrder":[les id des chansons entre guillemets séparées par des virgules],
         "version":0.94,
         "zoom": pouvant varier de 10 à 100
 }

*/
