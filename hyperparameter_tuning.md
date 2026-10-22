# Podesavanje hiperparametara u klasifikaciji teksta

## 1. CountVectorizer i TfidfVectorizer

| Hiperparametar | Znacenje | Najcesce vrednosti |
|---|---|---|
| `min_df` | Minimalan broj ili udeo dokumenata u kojima se rec mora pojaviti. | `[1, 2, 5]` ili `[0.001, 0.01, 0.05]` |
| `max_df` | Maksimalan broj ili udeo dokumenata u kojima se rec moze pojaviti. | `[0.8, 0.9, 0.95, 1.0]` |
| `max_features` | Maksimalan broj karakteristika koje se zadrzavaju. | `[5000, 10000, 20000, None]` |
| `ngram_range` | Odredjuje da li se koriste pojedinacne reci i/ili kombinacije reci. | `[(1, 1), (1, 2), (1, 3)]` |

**Napomene:**
- `min_df=2` znaci da rec mora da se pojavi u najmanje 2 dokumenta.
- `min_df=0.01` znaci da se rec mora pojaviti u najmanje 1% dokumenata.
- `max_df=0.9` izbacuje reci koje se pojavljuju u vise od 90% dokumenata.
- `max_features=None` znaci da se ne postavlja ogranicenje broja karakteristika.
- `ngram_range=(1, 2)` koristi unigram-e i bigram-e.

## 2. Logistic Regression (LR)

## 3. Support Vector Machine (SVM)

Za oba modela jedan od najvaznijih hiperparametara je `C`.

| Hiperparametar | Znacenje | Najcesce vrednosti |
|---|---|---|
| `C` | Jacina regularizacije. Manji `C` znaci jacu regularizaciju, a veci `C` slabiju. | `[0.01, 0.1, 1, 10, 100]` |

## 4. Decision Tree

| Hiperparametar | Znacenje | Najcesce vrednosti |
|---|---|---|
| `min_impurity_decrease` | Uslovi pod kojima se grananje dozvoljava. | `[0.0, 0.001, 0.01, 0.05]` |
| `max_depth` | Maksimalna dubina stabla. | `[3, 5, 10, 20, None]` |


**Napomena:**
Parametri se navode u `param_grid` recniku koristeci naziv koraka iz `Pipeline`, dve donje crte (`__`) i naziv hiperparametra.

- Vektorizator: `vectorizer__min_df`
- Logistic Regression: `classifier__C`
- SVM: `classifier__C`
- Decision Tree: `classifier__max_depth`, `classifier__min_impurity_decrease`

Nazivi `vectorizer` i `classifier` moraju odgovarati imenima koraka u `Pipeline`.