## HC1T8
---

## 🧠 Notion clé : fonction d’ordre supérieur

En Haskell, une **fonction d’ordre supérieur** est une fonction qui :

* prend **une autre fonction en argument**, et/ou
* retourne une fonction.

👉 Ici, `applyTwice` **prend une fonction** et **l’applique deux fois**.

---

## 📐 Principe mathématique

Si on a une fonction `f` et une valeur `x` :

[
applyTwice(f, x) = f(f(x))
]

---

## ✍️ Signature de la fonction

```haskell
applyTwice :: (a -> a) -> a -> a
```

### 🔍 Explication de la signature

* `(a -> a)` : une fonction qui prend un `a` et retourne un `a`
* `a -> a` : la valeur d’entrée et le résultat
* Le type est **générique** (`a`) → fonctionne avec n’importe quel type

---

## ✅ Définition de `applyTwice`

```haskell
applyTwice :: (a -> a) -> a -> a
applyTwice f x = f (f x)
```

### 🧩 Explication

* `f x` : première application de la fonction
* `f (f x)` : deuxième application
* Le résultat final est retourné

---

## 🖥️ Programme complet avec `main`

```haskell
-- Fonction d'ordre supérieur : applyTwice

applyTwice :: (a -> a) -> a -> a
applyTwice f x = f (f x)

-- Exemple de fonction simple
double :: Int -> Int
double x = x * 2

main :: IO ()
main = do
    let valeur = 5
    let resultat = applyTwice double valeur
    putStrLn ("Valeur initiale : " ++ show valeur)
    putStrLn ("Après application deux fois : " ++ show resultat)
```

---

## 🧠 Explication détaillée du programme

### 1️⃣ Fonction `double`

```haskell
double :: Int -> Int
double x = x * 2
```

➡️ Multiplie un nombre par 2

---

### 2️⃣ Appel de `applyTwice`

```haskell
applyTwice double valeur
```

➡️ Équivaut à :

```haskell
double (double 5)
```

Calcul :

* `double 5 = 10`
* `double 10 = 20`

---

### 3️⃣ Affichage

```haskell
putStrLn ("Après application deux fois : " ++ show resultat)
```

➡️ Affiche le résultat final

---

## ▶️ Exemple d’exécution

```
Valeur initiale : 5
Après application deux fois : 20
```

---

## 🔎 Autre exemple (fonction anonyme)

```haskell
applyTwice (\x -> x + 1) 3
```

➡️ Résultat :

```
5
```

Explication :

* `(3 + 1) = 4`
* `(4 + 1) = 5`

---

## 📝 Résumé

✔ Fonction d’ordre supérieur
✔ Utilisation de fonctions comme arguments
✔ Type générique et réutilisable
✔ Exemple clair avec `main`

