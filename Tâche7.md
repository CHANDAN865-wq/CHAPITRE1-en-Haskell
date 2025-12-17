# HC1T7


---

## 📐 Formule mathématique

La conversion se fait avec la formule :

[
C = (F - 32) \times \frac{5}{9}
]


---

## 🧠 Choix du type en Haskell

* On utilise le type **`Double`** pour gérer les nombres réels
* La fonction prendra un **Fahrenheit** et retournera un **Celsius**

---

## ✅ Fonction `fToC`

```haskell
fToC :: Double -> Double
fToC fahrenhein = (f - 32) * 5 / 9
```

### 🔍 Explication

* `Double -> Double` : la fonction prend un réel et retourne un réel
* `fahrenhein - 32` : soustraction de 32 degrés
* `* 5 / 9` : application du facteur de conversion

---

## 🖥️ Programme complet avec `main`

```haskell
-- Conversion Fahrenheit vers Celsius

-- Conversion Fahrenheit vers Celsius

fToC :: Double -> Double
fToC fahrenheit = (fahrenheit - 32) * 5 / 9

main :: IO ()
main = do
    putStrLn "Entrez la température en Fahrenheit :"
    
    let fahrenheit = 100
    let celsius = fToC fahrenheit
    putStrLn ("La température en Celsius est : " ++ show celsius)

```

---

## 🧩 Explication détaillée de `main`

### 1️⃣ Affichage d’un message

```haskell
putStrLn "Entrez la température en Fahrenheit :"
```

➡️ Affiche une instruction à l’utilisateur

---

### 2️⃣ Lecture de l’entrée utilisateur

```haskell
input <- getLine
```

➡️ Lit la valeur saisie (sous forme de **String**)

---

### 3️⃣ Conversion en nombre réel

```haskell
let f = read input :: Double
```

➡️ Transforme la chaîne de caractères en `Double`

---

### 4️⃣ Appel de la fonction `fToC`

```haskell
let celsius = fToC fahrenhein
```

➡️ Convertit Fahrenheit → Celsius

---

### 5️⃣ Affichage du résultat

```haskell
putStrLn ("La température en Celsius est : " ++ show c)
```

➡️ `show` convertit le nombre en texte pour l’affichage

---

## ▶️ Exemple d’exécution

```
Entrez la température en Fahrenheit :
98.6
La température en Celsius est : 37.0
```

---

## 📝 Résumé

✔ Fonction pure `fToC`
✔ Utilisation correcte des types (`Double`)
✔ Programme interactif avec `main`
✔ Code clair, lisible et bien structuré
