# Langages formels

## Introduction : résumé

/!\ Définition des automates finis non déterministes avec un seul état initial.

$\varepsilon$-NFAs = NFAs ( Non-deterministic Finite Automatas = AFND ) en ajoutant des transitions gratuites

- DFA $\iff$ NFA $\iff$ $\varepsilon$-NFA

La construction d'un $\varepsilon$-NFA à partir d'une expression régulière est inductivement assez claire, beaucoup plus que l'algorithme de Glushkov.

Dans l'autre sens on utilise des $\varepsilon$-transitions pour standardiser facilement l'automate puis on enlève un a un les états en créant les transitions avec les nouvelles expressions régulières associées.

Les regex ( donc langages reconnaissables ) sont stables par toutes les opérations ensemblistes finies, par mirroir, et par image directe et réciproque d'homomorphismes ( morphismes pour la concaténation ).

Minimisation des automates en déterminant les classes d'états équivalents comme complémentaires des états distinguables.

