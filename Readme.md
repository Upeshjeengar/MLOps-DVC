## Why not directly git?
1. Storage issue: Size of the file which can be tracked using git is limited.
2. DVC is better than Git for large datasets because Git tracks changes line by line, which becomes inefficient with millions of rows. DVC handles large data more efficiently without overloading the system.

## How git versions Data
**Analogy**: Suppose you visit a temple and some items are not allowed inside it. There are 2 counters first for keeping phone, wallet and bag and second counter is for keeping shoes. How to identify which item belongs to whom?
Person on first counter and that will also work on counter 2.

so first counter works as git and it will you a token which works for DVC(second counter) too.

In short There will be always a unique data version with each code version

## Code part

1. Create virtual environment: `create env -n dvc`
2. install dvc: `pip install dvc`
3. `git init` and `python -m dvc init`
4. Add data `python -m dvc add Salary_Data.csv`
5. `git add Salary_Data.csv.dvc .gitignore`
6. `git commit -m "Track Dataset version 1 with DVC"`
7. Alterdata(or you can run `alterdata.py`)
8. `git checkout`

9. How to bring previous version?
`python -m dvc pull --force` 
from above command data will be reverted to previous version
We can also do above process for `.pkl` ML models.
