# CHAPITRE1-en-Haskell

---

# ✅ **Tâche 1 : Composition de fonctions en Haskell**

On doit définir trois fonctions :

1. **double** : multiplie un nombre par 2
2. **increment** : ajoute 1
3. **doubleThenIncrement** : applique *double*, puis *increment*, en utilisant la **composition de fonctions** (`.` en Haskell)

---

# 🔹 1. Définition de `double`

En Haskell, la définition est très simple :

```haskell
double :: Int -> Int
double x = 2 * x
```

---

# 🔹 2. Définition de `increment`

```haskell
increment :: Int -> Int
increment x = x + 1
```

---

# 🔹 3. Définition de `doubleThenIncrement`

On nous demande d’utiliser la **composition de fonctions**.

En Haskell, l’opérateur de composition est :

```
(f . g) x = f (g x)
```

Cela signifie : appliquer d’abord **g**, puis **f**.

Nous voulons :

1. prendre un nombre `x`
2. lui appliquer `double`
3. puis appliquer `increment`

Donc :

* la deuxième fonction appliquée dans l’ordre réel est écrite **en premier** dans la composition :

```haskell
doubleThenIncrement :: Int -> Int
doubleThenIncrement = increment . double
```

---

# 🔍 **Explication détaillée de la composition**

`doubleThenIncrement = increment . double`
signifie exactement :

[
doubleThenIncrement(x) = increment(double(x))
]

Donc :

* `double 3 = 6`
* `increment 6 = 7`

Ainsi :

```haskell
doubleThenIncrement 3   -- renvoie 7
```

---

# 📌 **Code complet**

```haskell
double :: Int -> Int
double x = 2 * x

increment :: Int -> Int
increment x = x + 1

-- Composition de fonctions : increment . double
doubleThenIncrement :: Int -> Int
doubleThenIncrement = increment . double
```

---

# 🎉 Exemple d’utilisation

```haskell
main = do
    print (double 5)              -- 10
    print (increment 10)          -- 11
    print (doubleThenIncrement 5) -- 11
```

---


