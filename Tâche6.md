

---

# 📌 Énoncé

Définir une fonction **`addNumbers`** qui prend **deux entiers** et retourne **leur somme**, en utilisant **une signature de type**.

---

# 🧠 Rappel théorique : signatures de type en Haskell

En Haskell, une **signature de type** :

* précise **le type des paramètres**
* précise **le type du résultat**
* permet de détecter des erreurs **avant l’exécution**

📌 Forme générale :

```haskell
nomFonction :: Type1 -> Type2 -> TypeResultat
```

---

# ✅ Solution complète en Haskell

```haskell
-- Définition de la fonction avec signature de type
addNumbers :: Int -> Int -> Int
addNumbers x y = x + y

-- Fonction principale
main :: IO ()
main = do
    let a = 7
    let b = 5
    let resultat = addNumbers a b
    putStrLn "La somme des deux nombres est :"
    print resultat
```

---

# 🧾 Explication détaillée (correction)

---

## 1️⃣ Signature de type de `addNumbers`

```haskell
addNumbers :: Int -> Int -> Int
```

### 🔍 Explication

* `Int` (premier) : type du premier paramètre
* `Int` (deuxième) : type du second paramètre
* `Int` (dernier) : type de la valeur retournée

👉 **Lecture correcte** :

> `addNumbers` prend un `Int`, puis un autre `Int`, et retourne un `Int`.

📌 En Haskell, une fonction prend **un seul argument à la fois** (currying).

---

## 2️⃣ Corps de la fonction

```haskell
addNumbers x y = x + y
```

### 🔍 Explication

* `x` et `y` sont les deux paramètres
* `+` est l’opérateur d’addition
* Le résultat est la **somme des deux entiers**

📌 Aucune instruction `return` n’est nécessaire en Haskell.

---

## 3️⃣ Fonction `main`

```haskell
main :: IO ()
main = do
```

* Point d’entrée du programme
* `IO ()` indique que le programme fait de l’affichage

---

## 4️⃣ Déclaration des variables

```haskell
let a = 7
let b = 5
```

* `a` et `b` sont deux entiers
* Utilisés comme données de test

---

## 5️⃣ Appel de la fonction

```haskell
let resultat = addNumbers a b
```

### 🔍 Explication

* La fonction reçoit `a` et `b`
* Le calcul est effectué
* Le résultat est stocké dans `resultat`

---

## 6️⃣ Affichage du résultat

```haskell
print resultat
```

📤 Résultat affiché :

```text
12
```

---

# 🔁 Variante pédagogique (avec saisie utilisateur)

```haskell
addNumbers :: Int -> Int -> Int
addNumbers x y = x + y

main :: IO ()
main = do
    putStrLn "Entrez le premier nombre :"
    x <- readLn
    putStrLn "Entrez le second nombre :"
    y <- readLn
    print (addNumbers x y)
```

---

# ✅ Ce que le correcteur attend

✔️ Signature de type correcte
✔️ Fonction simple et claire
✔️ Utilisation de `main`
✔️ Code compilable et lisible

---

# 📚 Conclusion

Les **signatures de type** :

* rendent le code plus sûr
* facilitent la compréhension
* sont fortement recommandées en Haskell

---
