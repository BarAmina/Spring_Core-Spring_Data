# Spring_Core-Spring_Data
exemple d'application java avec Spring Data

#Le projet TP.Spring.Data.demo est une application java spring-boot qui implémente 3 techniques de connexion à la BD : Jdbc templace , Entity Manager avec spécifications JPA ,Spring Data.

Spring Boot est un nouveau framework conçu pour simplifier le démarrage et le développement de nouvelles applications Spring.  Boot se veut être un acteur majeur dans le secteur croissant du développement d'applications rapide.


Spring Boot soutient des conteneurs embarqués (embeddes containers).Cela permet des application web d’exécuter indépendamment sans déploiement sur Web Server.


La structure générale du projet :
       
       -main.java.com.example.demo-->YassinApplication.java
                                   
                  .com.example.demo.person.service--> Person.java
						             
                                                  -->PersonEntity.java
						             
                                                  --> PersonEntityManagerFromFactory.java
						             
                                                  --> PersonJdbcTemplate.java
						             
                                                  -->  PersonRep.java
						              
                                                  --> PersonSpringData.java
                                   
                  .com.example.demo.rest--> HelloWorldRestController.java
				                          
                                        --> PersonRestController.java  
                                  
      -main.java.resources-->application.proprieties

      -test.java.com.example.demo.rest--> ApplicationTests.java
					        
      - target
      - pom.xml

Points à noter:

- YassinApplication.java:
Cette classes est annotées par   @SpringBootApplication. Cette annotation  équivaut à utiliser  @Configuration, @EnableAutoConfiguration et  @ComponentScan avec ses attributs par défaut.

Donc  @SpringBootApplication vous aide de configurer automatiquement Spring, et automatiquement scanner (Scan) le projet intégral afin de découvrir des composants de  Spring

L’application est lancé par l'exécution de la classe  YassinApplication. C’est le main()de l’application Spring Boot ;elle declenche la configuration automatique de l’infrastructure Spring.

- Person.java :
C’est une classe qui permet la définition des attributs et des méthodes de l’objet Person.
En utilisant les spécifications JPA on ajoute les attributs à la BD :

    @Id et @Generatevalue pour créer la clé primaire
    @Column : pour spécifier la colonne d’attribut dans la BD.
    
- PersonEntity.java:
Pour Spring Data JPA Entity Manager permet l’accès rapide aux données et permet l’interaction avec ‘’ persistence context’’. Elle permet une gestion explicite et facile des requetés.


- PersonJdbcTemplate.java:
Cette classe implémente une template jdbc pour la connexion avec la base de données. On définit les paramètres de connexion et ensuite on specifie la requête SQL

- PersonRep.java:
Une interface annotée par @Repository  qui permet de chercher les personnes  par leur noms en utilisant la méthode findBy[Attribut] sans utiliser les requêtes SQL.

- PersonSpringData.java:
Une classe qui utilise un objet de l’interface PersonRep par injection @Autowired et définit une méthode qui retourne un objet Person recherché par son nom en utilisant les méthodes de Spring Data.

- HelloWorldRestController.java et  PersonRestController.java  :
Elles représentent les classes contrôleurs de l’application qui définissent les URI des vues avec la technique mapping REST 

- application.proprieties: C’est le fichier qui définit l’hibernate de JPA et url de l’application .

- pom.xml : le fichier où on définit les dépendances de l’application.
