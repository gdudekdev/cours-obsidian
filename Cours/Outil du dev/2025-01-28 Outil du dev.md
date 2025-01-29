#outil-du-dev 

### **Récap sur la BDD**

Entité/Association

Cardinalité

N:N -> crée une table intermédiaire contenant deux clés étrangères faisant références aux deux clés primaires des tables en relation. Ce couple formera alors la clé primaire de la dite table intermédiaire.

![[Pasted image 20250128161826.png]]
![[Pasted image 20250128161841.png]]
N:1 -> crée une clé étrangère dans la table 1 relative à la clé primaire de la table correspondante  au N
![[Pasted image 20250128161645.png]]
![[Pasted image 20250128161635.png]]

1:1-> le placement de la clé étrangère se fait et au libre choix du développeur. Toutefois, il est bon de se poser la question si la création d'une entité est nécessaire dans ce cas.

![[Pasted image 20250128163512.png]]![[Pasted image 20250128163521.png]]
