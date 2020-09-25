# Langages de programmation et compilation

## Cours 1 : Mise à niveau OCaml

### Opérations bitwise

-  and, or, xor, not = `land`, `lor`, `lxor`, `lnot`  ( l=logical )
- left/right shifts = `lsl`, `lsr`

Entiers binaires = `0b1000101101`

### Modules

En première approximation fichier = module.

Pour compiler sans faire d'exécutable on utilise `ocamlopt -c fichier.ml`. Avcec plusieurs fichiers compilés comme ceci ( f1 et f2 ) on peut créer un fichier complet comme ceci : `ocamlopt f1.cmx f2.cmx -o out`.

On peut exporter seulement certaines valeurs en les spécifiant dans un fichier `.mli` puis en exécutant successivement `ocamlopt -c f.mli` et `ocamlopt -c f.ml`.

On peut utiliser ça pour restreindre la visibilité de la définition d'un type en créant un type abstrait.

On peut écrire des modules dans des fichiers avec la syntaxe suivante

```ocaml
module M = struct
	let a = 100
	let f x = a * x
	...
end
```

De même pour les signatures comme ceci :

``` ocaml
module type S = sig
	val f: int -> int
end

module M: S = struct
	let a = 2
	let f x = a * x
end
```

De sorte que `M.a` retourne `Unbound value M.a`.

### Foncteurs

Ce sont des modules paramétrés par d'autres modules. La syntaxe est la suivante :

```ocaml
module F(M: S) = struct
	let f2 x = M.f (M.f x)
end

module F(M: S): sig
	val f: int -> int
end
```

