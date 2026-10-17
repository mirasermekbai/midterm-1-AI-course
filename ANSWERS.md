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
| H | 0.900000 | KK, degraded | 0.766667 | 0.590713 | 0.882078 | 49858.09 |
| L | 0.822222 | KK, degraded | 0.666667 | 0.487797 | 0.807697 | 18000.00 |

Personal-data pages per year sent abroad under H: 189800

### 2b. Memo (at most 300 words)

To: Head of Operations

I would choose L. It got 148/180 invoices right (82.22%), compared with H's 162/180 (90.00%). Annual costs are 18000 for L and 49858.09 for H. Both did worst on degraded Kazakh scans: L got 20/30 right, 66.67% (95% Wilson interval [48.78%, 80.77%]); H got 23/30, 76.67% ([59.07%, 88.21%]). The overall scores hide this problem. There are only 30 invoices in each group. The intervals overlap, so we cannot be sure H really performs better for this group.

With H, every scan goes abroad. That includes 189800 pages a year with names and IINs. We know the provider receives them, but need to find out where copies are stored, who else can access or store them, and how long images, logs and backups are kept. No. 94-V covers IIN; a vendor's promise is not a compliance review.

With L, scans go to the bank's servers in Kazakhstan, and the bank manages the main storage. We still need to check administrator access, whether backups or telemetry leave the country, and when stored copies and logs are deleted.

For L, block outgoing scan transfers and check firewall logs. Encrypt stored files, limit access by role and record access. Set deletion deadlines for scans, extracted data, logs and backups; test deletion and backup restores. Have a person check results before payment, especially degraded Kazakh scans. Each month, test fresh labelled invoices by language and scan condition and report errors and Wilson intervals.

L needs two servers and saves 31858.09 a year. Lower observed accuracy, Kazakh errors, security failures and extra review costs remain risks. Reconsider after a larger test.

## Part 3: Explain your own numbers

### Q1

Number: 2.42
Why (at most 40 words): The token ratio is 2.71. Output tokens cost six times as much as input tokens. EN has a larger share of output tokens, so counting their higher price gives a smaller bill ratio of 2.42.

### Q2

Number: 22.1 %
Why (at most 40 words): A full chunk becomes 657.5 e5 tokens in EN, 320 in RU and 190 in KK. Only EN exceeds 512. Its last 145.5 tokens (22.1%) are cut off, so the embedding cannot use their information.

### Q3

Number: 80.2 %
Why (at most 40 words): At T = 0.4, Monday becomes more likely, but the token order stays the same. All five tokens still have a chance of being sampled. Temperature changes probabilities; it does not cut tokens out.

### Q4

Number: 29.6 %
Why (at most 40 words): The course's simplified bound applies to birthdays and account numbers. I left out multiplication and sequences because rules can produce their answers. Saying 'never invent' adds no missing knowledge, so this instruction alone does not remove the bound.

### Q5

Number: 29400
Why (at most 40 words): The first message is paid for 24 times, once on each turn. Caching can reuse the repeated history and may lower its price. It does not change the full history or this uncached total.
