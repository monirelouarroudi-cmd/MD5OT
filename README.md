# 📝 Devoir blanc — Préparation au contrôle-bilan n°2

**Terminale · Spécialité Maths**

| | |
|---|---|
| ⏱️ **Durée** | 1 h 45 |
| 🧮 **Calculatrice** | autorisée |
| 🎯 **Barème** | 20 points |
| 📚 **Thèmes** | Vecteurs et repère de l'espace · Dénombrement et Python · Dérivées successives (formule de Leibniz) · Combinatoire appliquée à la géométrie |

> Ce devoir blanc reprend **les mêmes thèmes, la même structure et la même répartition des points** que le sujet d'entraînement TG-E-02, mais avec des questions différentes. Il se travaille dans les conditions réelles : chronomètre lancé, rédaction complète, sans le cours.

---

## 📑 Sommaire

- [Déroulement de la séance](#-déroulement-de-la-séance)
- [Exercice 1 — Un alignement dans le cube](#exercice-1--un-alignement-dans-le-cube-3-points)
- [Exercice 2 — Un programme à déchiffrer](#exercice-2--un-programme-à-déchiffrer-5-points)
- [Exercice 3 — Formule de Leibniz](#exercice-3--formule-de-leibniz-3-points)
- [Exercice 4 — Lire sur un pavé](#exercice-4--lire-sur-un-pavé-3-points)
- [Exercice 5 — Problème : un robot](#exercice-5--problème--un-robot-6-points)
- [Récapitulatif du barème](#-récapitulatif-du-barème)
- [Notes pour le professeur](#-notes-pour-le-professeur)

---

## ⏳ Déroulement de la séance

| Temps | Activité |
|---|---|
| 0–5 min | Consignes, mise en condition d'examen |
| 5–110 min | **Devoir blanc** (1 h 45) — rédaction sur copie |
| 110–120 min | Ramassage, autocorrection flash avec le corrigé, repérage des points faibles |

> 💡 Si le temps manque, la correction détaillée peut se faire à la séance suivante : chaque corrigé est conçu pour être relu seul.

---

## Exercice 1 — Un alignement dans le cube (3 points)

$ABCDEFGH$ est un cube (base $ABCD$, face supérieure $EFGH$, avec $E$ au-dessus de $A$, $F$ au-dessus de $B$, $G$ au-dessus de $C$ et $H$ au-dessus de $D$).

On note $K$ le point tel que $\overrightarrow{KA}+\overrightarrow{KC}+\overrightarrow{KF}=\vec 0$ (centre de gravité du triangle $ACF$).

**a.** En introduisant le point $B$ dans chacun des trois vecteurs, démontrer que
$$\overrightarrow{BK}=\frac13\left(\overrightarrow{BA}+\overrightarrow{BC}+\overrightarrow{BF}\right).$$

**b.** Exprimer $\overrightarrow{BH}$ en fonction de $\overrightarrow{BA}$, $\overrightarrow{BC}$, $\overrightarrow{BF}$.

**c.** En déduire que $B$, $K$ et $H$ sont alignés, et préciser la position de $K$ sur $[BH]$.

<details>
<summary><b>✅ Corrigé de l'exercice 1</b></summary>

**a. (1 pt)** D'après la relation de Chasles :

$$\overrightarrow{KA}=\overrightarrow{KB}+\overrightarrow{BA},\qquad \overrightarrow{KC}=\overrightarrow{KB}+\overrightarrow{BC},\qquad \overrightarrow{KF}=\overrightarrow{KB}+\overrightarrow{BF}$$

En additionnant et en utilisant l'hypothèse :

$$3\overrightarrow{KB}+\overrightarrow{BA}+\overrightarrow{BC}+\overrightarrow{BF}=\vec0
\ \Longrightarrow\ 3\overrightarrow{KB}=-\left(\overrightarrow{BA}+\overrightarrow{BC}+\overrightarrow{BF}\right)$$

Comme $\overrightarrow{BK}=-\overrightarrow{KB}$ :

$$\boxed{\overrightarrow{BK}=\frac13\left(\overrightarrow{BA}+\overrightarrow{BC}+\overrightarrow{BF}\right)}$$

**b. (1 pt)** Par Chasles : $\overrightarrow{BH}=\overrightarrow{BA}+\overrightarrow{AD}+\overrightarrow{DH}$.

- $ABCD$ est un carré, donc $\overrightarrow{AD}=\overrightarrow{BC}$ ;
- les arêtes verticales du cube sont parallèles et de même longueur, donc $\overrightarrow{DH}=\overrightarrow{BF}$.

$$\boxed{\overrightarrow{BH}=\overrightarrow{BA}+\overrightarrow{BC}+\overrightarrow{BF}}$$

**c. (1 pt)** D'après a. et b. :

$$\overrightarrow{BK}=\frac13\overrightarrow{BH}$$

Les vecteurs $\overrightarrow{BK}$ et $\overrightarrow{BH}$ sont colinéaires : **$B$, $K$, $H$ sont alignés**. De plus, le coefficient $\frac13$ est dans $[0;1]$ : $K$ appartient au segment $[BH]$, **au tiers de sa longueur à partir de $B$** ($BK=\frac13BH$).

</details>

---

## Exercice 2 — Un programme à déchiffrer (5 points)

Un code d'accès est formé de **3 chiffres**, de `000` à `999`. On considère la fonction suivante.

```python
def mystere():
    n = 0
    for a in range(10):
        for b in range(10):
            for c in range(10):
                if a < b < c:
                    n = n + 1
    return n
```

**a.** Combien de fois le test `if` est-il effectué ? Justifier par un dénombrement.

**b.** Décrire en français les codes comptés par la fonction. Donner deux exemples et un contre-exemple.

**c.** Expliquer pourquoi ces codes correspondent exactement aux parties à 3 éléments de $\{0,1,\dots,9\}$. En déduire la valeur renvoyée par la fonction.

**d.** Combien de codes ont leurs trois chiffres distincts ? Quelle fraction d'entre eux est comptée par la fonction ? Expliquer ce rapport.

**e.** Combien de codes comportent au moins deux chiffres égaux ?

**f.** Écrire en Python la condition à placer dans le `if` pour que la fonction compte tous les codes dont les trois chiffres sont distincts. Quelle valeur renvoie alors la fonction ?

<details>
<summary><b>✅ Corrigé de l'exercice 2</b></summary>

**a. (0,5 pt)** Il y a trois boucles imbriquées, chacune parcourant 10 valeurs (de 0 à 9) : le test est effectué
$$10\times10\times10=10^3=\boxed{1000}\text{ fois}$$
(un test par code possible, de `000` à `999`).

**b. (1 pt)** La fonction compte les codes $abc$ dont les chiffres sont **strictement croissants** de gauche à droite ($a<b<c$).

- Exemples : `013`, `489`.
- Contre-exemple : `112` (deux chiffres égaux, donc pas strictement croissant) ; ou `210` (décroissant).

**c. (1 pt)** À un code $abc$ vérifiant $a<b<c$, on associe l'ensemble $\{a,b,c\}$ : ses trois éléments sont distincts (inégalités strictes), c'est donc une partie à 3 éléments de $\{0,\dots,9\}$.

Réciproquement, une partie à 3 éléments se range d'**une seule façon** dans l'ordre croissant, ce qui donne **un unique** code $a<b<c$.

On a ainsi une correspondance un-à-un entre ces codes et les parties à 3 éléments. La fonction renvoie donc le nombre de parties à 3 éléments d'un ensemble à 10 éléments :

$$\binom{10}{3}=\frac{10\times9\times8}{3\times2\times1}=\boxed{120}$$

**d. (1 pt)** Codes à chiffres distincts : 10 choix pour $a$, 9 pour $b\neq a$, 8 pour $c$ :
$$10\times9\times8=\boxed{720}$$

Fraction comptée par la fonction :
$$\frac{120}{720}=\boxed{\frac16}$$

**Explication :** chaque partie $\{a,b,c\}$ fournit $3!=6$ codes à chiffres distincts (les $6$ ordres possibles), et **un seul** de ces six codes est rangé dans l'ordre croissant. La fonction compte donc « un code sur six ».

**e. (0,5 pt)** Par passage au complémentaire : $1000-720=\boxed{280}$ codes comportent au moins deux chiffres égaux.

*(Vérification : 10 codes aux trois chiffres égaux + $3\times10\times9=270$ codes avec exactement deux chiffres égaux $=280$.)*

**f. (1 pt)** Condition :

```python
if a != b and a != c and b != c:
```

La fonction renvoie alors $\boxed{720}$.

</details>

---

## Exercice 3 — Formule de Leibniz (3 points)

Soit $f$ la fonction définie sur $\mathbb{R}$ par $f(x)=x^2e^{-x}$.

**a.** Donner, pour tout entier $j$, la dérivée $j$-ième de $x\mapsto e^{-x}$ (sans démonstration).

**b.** À l'aide de la formule de Leibniz, démontrer que, pour tout entier $n\geqslant2$,
$$f^{(n)}(x)=(-1)^n\,e^{-x}\Big(x^2-2nx+n(n-1)\Big).$$

**c.** Vérifier que la formule est aussi vraie pour $n=1$, par un calcul direct de $f'$.

**d.** Calculer $f^{(10)}(0)$.

<details>
<summary><b>✅ Corrigé de l'exercice 3</b></summary>

**a. (0,5 pt)** Pour tout entier $j$ :
$$\left(e^{-x}\right)^{(j)}=(-1)^j\,e^{-x}$$

**b. (1,5 pt)** Posons $u(x)=x^2$ et $v(x)=e^{-x}$. La formule de Leibniz donne :

$$f^{(n)}=\sum_{k=0}^{n}\binom nk\,u^{(k)}\,v^{(n-k)}$$

Les dérivées de $u$ sont $u'(x)=2x$, $u''(x)=2$ et $u^{(k)}=0$ pour $k\geqslant3$. Seuls les termes $k=0,1,2$ subsistent (ils existent bien car $n\geqslant2$) :

$$f^{(n)}(x)=\binom n0x^2(-1)^ne^{-x}+\binom n1\,2x\,(-1)^{n-1}e^{-x}+\binom n2\,2\,(-1)^{n-2}e^{-x}$$

Or $(-1)^{n-1}=-(-1)^n$, $(-1)^{n-2}=(-1)^n$, $\binom n1=n$ et $\binom n2\times2=n(n-1)$. En factorisant par $(-1)^ne^{-x}$ :

$$\boxed{f^{(n)}(x)=(-1)^n\,e^{-x}\Big(x^2-2nx+n(n-1)\Big)}$$

