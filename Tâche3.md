

---

## 📌 Programme Haskell complet

```haskell
-- Définition de la fonction
greaterThan18 :: Int -> Bool
greaterThan18 x = x > 18

-- Fonction principale
main :: IO ()
main = do
    let nombre = 20
    if greaterThan18 nombre
        then putStrLn "Le nombre est strictement supérieur à 18"
        else putStrLn "Le nombre n'est pas strictement supérieur à 18"
```

---

## 🧠 Explication détaillée (correction)

---

## 1️⃣ Définition de la fonction `greaterThan18`

```haskell
greaterThan18 :: Int -> Bool
greaterThan18 x = x > 18
```

### 🔍 Explication

* `greaterThan18` : nom de la fonction
* `Int` : type du paramètre (nombre entier)
* `Bool` : type du résultat (`True` ou `False`)
* `x > 18` :

  * retourne `True` si `x` est supérieur à 18
  * retourne `False` sinon

👉 Cette fonction **ne fait aucun affichage**, elle ne fait **qu’un test logique**.

---

## 2️⃣ La fonction `main`

```haskell
main :: IO ()
```

### 🔍 Explication

* `main` est le **point d’entrée** de tout programme Haskell
* `IO ()` signifie que :

  * le programme effectue des **entrées/sorties**
  * il ne retourne pas de valeur utile

---

## 3️⃣ Bloc `do`

```haskell
main = do
```

* `do` permet d’exécuter plusieurs instructions `IO` **les unes après les autres**.

---

## 4️⃣ Déclaration de la variable `nombre`

```haskell
let nombre = 20
```

* `let` sert à définir une variable locale
* ici, `nombre` vaut `20`
* on peut changer cette valeur pour tester d’autres cas

---

## 5️⃣ Utilisation de la fonction `greaterThan18`

```haskell
if greaterThan18 nombre
```

* on appelle la fonction avec `nombre`
* le résultat est un `Bool`

---

## 6️⃣ Affichage du résultat

```haskell
then putStrLn "Le nombre est strictement supérieur à 18"
else putStrLn "Le nombre n'est pas strictement supérieur à 18"
```

### 🔍 Explication

* `putStrLn` affiche une chaîne de caractères à l’écran
* selon le résultat de la condition :

  * `True` → premier message
  * `False` → second message

---

## 🧪 Exemple d’exécution

### Cas 1 : `nombre = 20`

```
Le nombre est strictement supérieur à 18
```

### Cas 2 : `nombre = 18`

```
Le nombre n'est pas strictement supérieur à 18
```

---

## 📚 Version encore plus pédagogique (avec `if` dans la fonction)

```haskell
greaterThan18 :: Int -> Bool
greaterThan18 x =
    if x > 18
        then True
        else False

main :: IO ()
main = do
    let nombre = 15
    print (greaterThan18 nombre)
```

👉 Ici, `print` affiche directement `True` ou `False`.

---

## ✅ Ce qu’un correcteur attend

✔️ Une fonction bien typée
✔️ Une logique correcte (`x > 18`)
✔️ Une fonction `main` fonctionnelle
✔️ Un affichage clair du résultat

---

