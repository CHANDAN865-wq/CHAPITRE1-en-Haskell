HC1T5 - Tâche 5 : Paresse en Haskell

---

# 🧠 Rappel théorique : paresse en Haskell

👉 En Haskell :

* Les expressions **ne sont évaluées que si nécessaire**
* Une **liste infinie** est donc possible
* On peut travailler avec une liste infinie **sans bloquer le programme**, à condition de n’en utiliser qu’une partie

📌 Exemple clé :

```haskell
take 5 [1..]   -- fonctionne !
```

---

# ✅ Solution complète en Haskell

```haskell
-- Fonction qui génère une liste infinie de nombres
infiniteNumbers :: [Int]
infiniteNumbers = [1..]

-- Fonction main
main :: IO ()
main = do
    let n = 10
    let result = take n infiniteNumbers
    putStrLn "Les n premiers nombres de la liste infinie sont :"
    print result
```

---

# 🧾 Explication détaillée (correction)

---

## 1️⃣ Fonction `infiniteNumbers`

```haskell
infiniteNumbers :: [Int]
infiniteNumbers = [1..]
```

### 🔍 Explication

* `[1..]` signifie :

  > commence à 1 et continue **indéfiniment**
* Cette liste est **infinie**
* En langage strict, cela provoquerait une erreur
* En Haskell, grâce à la **paresse**, la liste n’est **jamais calculée entièrement**

📌 **Point clé pour la correction** :
👉 *Haskell ne calcule que ce qui est demandé.*

---

## 2️⃣ Fonction `take`

```haskell
take n infiniteNumbers
```

### 🔍 Explication

* `take n` demande seulement les `n` premiers éléments
* Haskell génère **uniquement ces éléments**
* Le reste de la liste infinie **n’est jamais évalué**

📌 Exemple :

```haskell
take 5 [1..] → [1,2,3,4,5]
```

---

## 3️⃣ Fonction `main`

```haskell
main :: IO ()
main = do
```

* Point d’entrée du programme
* `IO ()` : programme avec affichage

---

## 4️⃣ Définition de `n`

```haskell
let n = 10
```

* `n` est le nombre d’éléments à extraire
* Peut être modifié facilement

---

## 5️⃣ Extraction des `n` premiers éléments

```haskell
let result = take n infiniteNumbers
```

* `result` est une **liste finie**
* Elle est calculée à partir d’une liste infinie

---

## 6️⃣ Affichage du résultat

```haskell
print result
```

### 📤 Résultat affiché :

```text
[1,2,3,4,5,6,7,8,9,10]
```

---

# 🔁 Version alternative (plus pédagogique)

```haskell
infiniteNumbers :: Int -> [Int]
infiniteNumbers start = [start..]

main :: IO ()
main = do
    let n = 5
    print (take n (infiniteNumbers 3))
```

📤 Résultat :

```text
[3,4,5,6,7]
```

---

# 📚 Ce qu’il faut absolument retenir (pour l’examen)

✔️ Haskell est **paresseux**
✔️ Les listes infinies sont possibles
✔️ `take` limite l’évaluation
✔️ Pas d’erreur tant qu’on n’essaie pas d’afficher toute la liste

❌ Ce qui provoquerait une erreur :

```haskell
print infiniteNumbers
```

---

# ✅ Conclusion

La paresse permet de :

* définir des **structures infinies**
* les manipuler **en toute sécurité**
* extraire seulement ce qui est nécessaire
