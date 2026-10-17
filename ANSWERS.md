# Midterm 1: answers

GitHub username: mirasermekbai
Session code: zebra-28
Fingerprint: 4e2634f0

> Fill in the three lines above from `my_data/DATA.md`. Do not rename headings or table columns: a script reads the numbers.
> Write only in the empty cells and lines. Percentages as 0.78 or 78 %, money as plain numbers.

## AI-use declaration

(About half a page: which assistants or tools you used and for what. If you used none, say so.)

## Part 1: Retrieval and cost decision

### 1a. Metrics (all 60 questions)

| config | recall@1 | recall@3 | recall@5 | MRR@10 |
|---|---|---|---|---|
| A | 0.550000 | 0.733333 | 0.750000 | 0.632963 |
| B | 0.333333 | 0.466667 | 0.683333 | 0.439491 |

### 1b. Recall and 95 % Wilson interval of each candidate (recall at its own k)

| candidate | recall@k | lower | upper |
|---|---|---|---|
| A, k=3 | 0.733333 | 0.609910 | 0.828675 |
| A, k=5 | 0.750000 | 0.627677 | 0.842236 |
| B, k=3 | 0.466667 | 0.346277 | 0.591068 |
| B, k=5 | 0.683333 | 0.557660 | 0.786943 |

### 1c. Annual model cost in USD

| candidate | annual cost |
|---|---|
| A, k=3 | 20013.73 |
| A, k=5 | 26597.41 |
| B, k=3 | 13239.65 |
| B, k=5 | 15307.28 |

### 1d. Decision (at most 150 words)

Chosen candidate: B, k=5

I would choose B, k=5. It costs 15307.28 a year, below the 23300 budget. Its recall is 41/60 (68.33%), with a 95% Wilson interval of [55.77%, 78.69%]. A, k=3 scores higher at 73.33% ([60.99%, 82.87%]), but the intervals overlap. Under the course rule, neither is shown to be better; this does not prove equal performance. B, k=5 saves 4706.45 a year compared with A, k=3. A, k=5 is over budget. A, k=3 beats B, k=3 under the interval rule, while B, k=5 versus B, k=3 is still uncertain. For B, k=5, recall is EN 16/20 (80%), RU 16/20 (80%) and KK 9/20 (45%). Kazakh users get the weakest results. I would start with B, k=5 and collect more evidence before paying extra for A, k=3.

### 1e. Next measurement (at most 60 words)

Test A, k=3 and B, k=5 on the same 600 new questions, 200 per language. Compare recall and final answer accuracy using 95% intervals, especially for KK. Before testing, set five percentage points as a useful improvement. Choose A, k=3 if the measured gain is worth its extra 4706.45 a year.

## Part 2: A document pipeline you can defend

### 2a. Numbers

| pipeline | overall accuracy | weakest cell (language, condition) | accuracy there | lower | upper | annual cost |
|---|---|---|---|---|---|---|
| H | | | | | | |
| L | | | | | | |

Personal-data pages per year sent abroad under H:

### 2b. Memo (at most 300 words)

## Part 3: Explain your own numbers

### Q1

Number:
Why (at most 40 words):

### Q2

Number:
Why (at most 40 words):

### Q3

Number:
Why (at most 40 words):

### Q4

Number:
Why (at most 40 words):

### Q5

Number:
Why (at most 40 words):
