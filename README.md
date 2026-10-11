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

**c. (0,5 pt)** Calcul direct :
$$f'(x)=2xe^{-x}-x^2e^{-x}=e^{-x}(2x-x^2)=-e^{-x}(x^2-2x)$$

La formule pour $n=1$ donne $(-1)^1e^{-x}\big(x^2-2x+1\times0\big)=-e^{-x}(x^2-2x)$ : **identique** ✓.

**d. (0,5 pt)** Avec $n=10$ et $x=0$ :
$$f^{(10)}(0)=(-1)^{10}e^{0}\big(0-0+10\times9\big)=\boxed{90}$$

</details>

---

## Exercice 4 — Lire sur un pavé (3 points)

$ABCDEFGH$ est un pavé droit avec $AB=6$, $AD=4$ et $AE=2$ (base $ABCD$, $E$ au-dessus de $A$, $F$ au-dessus de $B$, $G$ au-dessus de $C$, $H$ au-dessus de $D$). On le rapporte au repère orthonormé d'origine $A$ dont les axes portent $(AB)$, $(AD)$, $(AE)$.

**a.** Donner les coordonnées de $C$, $F$, $G$ et $H$.

**b.** $I$ est le milieu de $[EH]$ et $J$ celui de $[BC]$. Calculer leurs coordonnées et montrer que $(IJ)$ est parallèle à $(BE)$.

**c.** $K$ est le point tel que $\overrightarrow{AK}=\dfrac12\overrightarrow{AG}$. Démontrer que $K$ est le milieu de $[IJ]$.

<details>
<summary><b>✅ Corrigé de l'exercice 4</b></summary>

**a. (0,5 pt)** Dans le repère $(A;\overrightarrow{AB},\overrightarrow{AD},\overrightarrow{AE})$ (orthonormé, avec les longueurs réelles) : $A(0;0;0)$, $B(6;0;0)$, $D(0;4;0)$, $E(0;0;2)$, d'où

$$C(6;4;0),\qquad F(6;0;2),\qquad G(6;4;2),\qquad H(0;4;2)$$

**b. (1,5 pt)** $E(0;0;2)$ et $H(0;4;2)$ donnent $I=\left(0;\,2;\,2\right)$.
$B(6;0;0)$ et $C(6;4;0)$ donnent $J=\left(6;\,2;\,0\right)$.

$$\overrightarrow{IJ}=(6;0;-2),\qquad \overrightarrow{BE}=(0-6;\,0-0;\,2-0)=(-6;0;2)$$

On remarque $\overrightarrow{BE}=-\overrightarrow{IJ}$ : les vecteurs sont colinéaires, donc **$(IJ)$ est parallèle à $(BE)$**.

*(Les droites sont bien distinctes : $(BE)$ est contenue dans le plan $y=0$, alors que $I$ a pour ordonnée $2$.)*

**c. (1 pt)** $\overrightarrow{AG}=(6;4;2)$, donc $\overrightarrow{AK}=\frac12\overrightarrow{AG}=(3;2;1)$ et $K(3;2;1)$.

Milieu de $[IJ]$ :
$$\left(\frac{0+6}2\,;\,\frac{2+2}2\,;\,\frac{2+0}2\right)=(3;2;1)=K$$

**$K$ est donc le milieu de $[IJ]$** (c'est aussi le centre du pavé).

</details>

---

## Exercice 5 — Problème : un robot (6 points)

Dans un repère $(O;\vec\imath,\vec\jmath,\vec k)$, un robot part de $O(0;0;0)$ et avance **par pas** : chaque pas est une translation de vecteur $\vec\imath$, $\vec\jmath$ ou $\vec k$. Il doit rejoindre $P(3;2;1)$. Un chemin est noté par la liste de ses pas ; par exemple $\vec\imath\,\vec\imath\,\vec\jmath\,\vec k\,\vec\imath\,\vec\jmath$.

### Partie A — géométrie

**a.** Justifier qu'après un chemin comportant $a$ pas $\vec\imath$, $b$ pas $\vec\jmath$ et $c$ pas $\vec k$, le robot est au point $(a;b;c)$. Combien de pas de chaque sorte comporte un chemin de $O$ à $P$ ?

**b.** Après trois pas, le robot peut être en $R(3;0;0)$, $S(0;3;0)$, $T(0;0;3)$, $M(2;1;0)$, $N(0;2;1)$ ou $L(1;0;2)$. Démontrer que $R$, $S$, $T$ ne sont pas alignés, puis que $M$, $N$ et $L$ appartiennent au plan $(RST)$.

### Partie B — dénombrement

**a.** Combien de chemins mènent de $O$ à $P$ ? (On pourra choisir d'abord la place des pas $\vec\imath$, puis celle des pas $\vec\jmath$.)

**b.** Combien de ces chemins passent par le point $Q(1;1;1)$ ?

**c.** Combien l'évitent ?

**d.** Combien de chemins passent par le point $U(2;0;1)$ ?

> 🌟 **Question bonus (non notée).** Un chemin peut-il passer à la fois par $Q$ et par $U$ ? Justifier.

<details>
<summary><b>✅ Corrigé de l'exercice 5</b></summary>

### Partie A — géométrie

**a. (1 pt)** Chaque pas ajoute un vecteur : après $a$ pas $\vec\imath$, $b$ pas $\vec\jmath$ et $c$ pas $\vec k$ (dans n'importe quel ordre, l'addition vectorielle étant commutative), le robot est en $M$ tel que
$$\overrightarrow{OM}=a\,\vec\imath+b\,\vec\jmath+c\,\vec k$$
donc $M(a;b;c)$.

Pour atteindre $P(3;2;1)$, on doit avoir $a=3$, $b=2$, $c=1$ (unicité des coordonnées) : un chemin de $O$ à $P$ comporte **3 pas $\vec\imath$, 2 pas $\vec\jmath$ et 1 pas $\vec k$**, soit 6 pas en tout.

**b. (1,5 pt)**

*$R,S,T$ non alignés.* $\overrightarrow{RS}=(-3;3;0)$ et $\overrightarrow{RT}=(-3;0;3)$. Si ces vecteurs étaient colinéaires, on aurait $\overrightarrow{RT}=\lambda\overrightarrow{RS}$, d'où pour la troisième coordonnée $3=\lambda\times0$ : impossible. Les vecteurs ne sont pas colinéaires : **$R,S,T$ ne sont pas alignés**, ils définissent un plan.

*$M,N,L\in(RST)$.* Un point $X$ appartient à $(RST)$ si et seulement s'il existe $\alpha,\beta$ tels que $\overrightarrow{RX}=\alpha\overrightarrow{RS}+\beta\overrightarrow{RT}=(-3\alpha-3\beta\,;\,3\alpha\,;\,3\beta)$.

| Point | $\overrightarrow{RX}$ | $\alpha$ (2ᵉ coord.) | $\beta$ (3ᵉ coord.) | Vérification 1ʳᵉ coord. $-3\alpha-3\beta$ |
|---|---|---|---|---|
| $M(2;1;0)$ | $(-1;1;0)$ | $\frac13$ | $0$ | $-1$ ✓ |
| $N(0;2;1)$ | $(-3;2;1)$ | $\frac23$ | $\frac13$ | $-2-1=-3$ ✓ |
| $L(1;0;2)$ | $(-2;0;2)$ | $0$ | $\frac23$ | $-2$ ✓ |

Les trois points appartiennent donc au plan $(RST)$.

> 💡 **Autre façon de voir :** le plan $(RST)$ a pour équation $x+y+z=3$, et après trois pas, la somme des coordonnées vaut toujours $3$.

### Partie B — dénombrement

**a. (1 pt)** Un chemin comporte 6 pas. On choisit les places des 3 pas $\vec\imath$ parmi 6 : $\binom63=20$ façons. Parmi les 3 places restantes, on choisit celles des 2 pas $\vec\jmath$ : $\binom32=3$ façons. Le pas $\vec k$ occupe la dernière place.

$$20\times3=\boxed{60\text{ chemins}}$$

**b. (1 pt)** Passer par $Q(1;1;1)$ se fait forcément au bout de 3 pas ($1+1+1=3$) :

- de $O$ à $Q$ : un pas $\vec\imath$, un $\vec\jmath$, un $\vec k$ dans un ordre quelconque, soit $3!=6$ chemins ;
- de $Q$ à $P$ : $\overrightarrow{QP}=(2;1;0)$, donc 2 pas $\vec\imath$ et 1 pas $\vec\jmath$ : $\binom32=3$ chemins.

Par le principe multiplicatif : $6\times3=\boxed{18\text{ chemins}}$.

**c. (0,5 pt)** Chemins évitant $Q$ : $60-18=\boxed{42}$.

**d. (1 pt)** Passer par $U(2;0;1)$ se fait au bout de 3 pas :

- de $O$ à $U$ : 2 pas $\vec\imath$ et 1 pas $\vec k$ : $\binom31=3$ chemins ;
- de $U$ à $P$ : $\overrightarrow{UP}=(1;2;0)$, donc 1 pas $\vec\imath$ et 2 pas $\vec\jmath$ : $3$ chemins.

$$3\times3=\boxed{9\text{ chemins}}$$

**🌟 Bonus.** Non : $Q$ et $U$ sont deux points **distincts** atteints tous deux après exactement 3 pas. Le robot ne peut pas être en deux endroits différents au bout de 3 pas : aucun chemin ne passe par les deux (0 chemin).

</details>

---

## 📊 Récapitulatif du barème

| Exercice | Thème | Points | Note élève |
|---|---|:---:|:---:|
| 1 | Vecteurs, centre de gravité, alignement dans le cube | 3 | … |
| 2 | Python et dénombrement (parties, complémentaire) | 5 | … |
| 3 | Dérivées successives, formule de Leibniz | 3 | … |
| 4 | Repère orthonormé dans un pavé | 3 | … |
| 5 | Problème : robot (géométrie + dénombrement) | 6 | … |
| | **Total** | **20** | … |

---

## 🧑‍🏫 Notes pour le professeur

### Rappels nécessaires à la correction

- **Chasles :** $\overrightarrow{AB}=\overrightarrow{AC}+\overrightarrow{CB}$ ; centre de gravité $G$ de $ABC$ : $\overrightarrow{GA}+\overrightarrow{GB}+\overrightarrow{GC}=\vec0$.
- **Leibniz :** $(uv)^{(n)}=\displaystyle\sum_{k=0}^{n}\binom nk\,u^{(k)}v^{(n-k)}$ ; $\ (e^{ax})^{(j)}=a^je^{ax}$.
- **Dénombrement :** principe multiplicatif, $\dbinom nk=\dfrac{n!}{k!\,(n-k)!}$, passage au complémentaire.

### Erreurs fréquentes à surveiller

| Exercice | Piège |
|---|---|
| 1 | Oublier que $\overrightarrow{KB}=-\overrightarrow{BK}$ ; ne pas justifier $\overrightarrow{AD}=\overrightarrow{BC}$ et $\overrightarrow{DH}=\overrightarrow{BF}$ |
| 2 | Confondre $10^3$ (tous les codes) et $\binom{10}{3}$ (codes croissants) ; ne pas expliquer le rapport $\frac16=\frac1{3!}$ |
| 3 | Oublier que $u^{(k)}=0$ pour $k\geqslant3$ ; se tromper sur $(-1)^{n-1}$ ; ne pas factoriser |
| 4 | Conclure « parallèle » sans mentionner la colinéarité des vecteurs |
| 5 | Confondre « passer par $Q$ » et « finir en $Q$ » ; oublier de multiplier les deux étapes (avant / après le point) |

### Grille d'observation

- [ ] Rédige proprement chaque démonstration vectorielle
- [ ] Sait lire un programme et le traduire en dénombrement
- [ ] Maîtrise le passage au complémentaire
- [ ] Applique correctement la formule de Leibniz
- [ ] Lit et calcule des coordonnées dans un repère de l'espace
- [ ] Décompose un chemin en étapes (principe multiplicatif)
- [ ] Gère son temps sur 1 h 45
- [ ] Erreurs surtout calculatoires
- [ ] Erreurs surtout méthodologiques / de rédaction
