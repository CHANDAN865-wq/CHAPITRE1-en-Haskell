

# ✅ **Tâche 2 : Fonction pure en Haskell**

On veut écrire une fonction :

```
circleArea :: Float -> Float
```

qui calcule l’aire d’un cercle à partir du rayon.

La formule mathématique est :

[
A = \pi r^2
]

Haskell possède déjà la constante **pi**, définie dans Prelude.

---

# 🔹 1. Qu’est-ce qu’une fonction pure en Haskell ?

Une fonction est **pure** si :

* elle dépend *uniquement* de ses arguments,
* elle n'accède à **aucun état externe**,
* elle ne provoque **aucun effet de bord** (pas d’affichage, pas de lecture clavier, pas de modification mémoire),
* à la même entrée correspond *toujours la même sortie*.

Haskell assure naturellement la pureté tant qu’on ne touche pas au monde IO.

---

# 🔹 2. Définition de la fonction `circleArea`

Voici la version la plus simple :

```haskell
circleArea :: Float -> Float
circleArea r = pi * r * r
```

---

# 🔍 Explication ligne par ligne

### ✔ `circleArea :: Float -> Float`

C’est la signature de type :

* elle reçoit un `Float` (le rayon),
* elle renvoie un `Float` (l’aire).

### ✔ `circleArea r = ...`

`r` représente le rayon passé à la fonction.

### ✔ `pi * r * r`

C’est la traduction directe de :

[
\pi r^2
]

La fonction n’a besoin de :

* aucune variable globale
* aucune entrée utilisateur
* aucun système IO
* aucune mémoire mutable

Elle est donc parfaitement **pure**.

---

# 🔹 3. Exemple d’utilisation

```haskell
main :: IO ()
main = do
    print (circleArea 1)     -- 3.1415927
    print (circleArea 2.5)   -- 19.634954
```

---

# 🔹 4. Version plus générale (optionnelle)

Pour rendre la fonction compatible avec tout type numérique flottant (`Float`, `Double`, etc.) :

```haskell
circleArea :: Floating a => a -> a
circleArea r = pi * r * r
```

Cela signifie : pour tout type `a` appartenant à la classe `Floating` (qui inclut `pi`), la fonction marche.

---

# 📌 **Code final (simple et pur)**

```haskell
circleArea :: Float -> Float
circleArea r = pi * r * r
```

---

