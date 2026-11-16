# CONSECUTIVE CHARACTER REPETITION ANALYZER
# Longest Repeat Finder

A small Python script that scans a string and finds the longest run of the same character appearing back to back.

For example, in `aabbbcc` the longest run is `bbb`, which is 3 characters long.

I wrote this as part of my Python practice while working through my data analytics course. The goal was to get comfortable with loops, indexing, and comparing a character with the one before it.

## How it works

1. Start with the first character as both the current run and the longest run.
2. Move through the string one character at a time.
3. If the character matches the one before it, add it to the current run.
4. If it doesn't, start a new run from that character.
5. Whenever the current run becomes longer than the longest one, update the longest.

If two runs have the same length, the first one found is kept.

## Sample output

| Input         | Output    |
|---------------|-----------|
| `aabbbcc`     | `bbb (3)` |
| `xxyy`        | `xx (2)`  |
| `mississippi` | `ss (2)`  |
| `abc`         | `a (1)`   |

## Code

```python
samples = ["aabbbcc", "xxyy", "mississippi", "abc"]

for i in samples:
    longest = i[0]
    current = i[0]

    for ch in range(1, len(i)):
        if i[ch] == i[ch - 1]:
            current = current + i[ch]
        else:
            current = i[ch]

        if len(current) > len(longest):
            longest = current

    print(longest, "(" + str(len(longest)) + ")")
```

## Run it

You only need Python 3 installed.

```bash
python longest_repeat.py
```

## What I practiced

- Looping with `range()` and string indexing
- Comparing neighbouring characters
- Building and resetting strings inside a loop
- Tracking a "best so far" value

## Possible improvements

- Handle empty strings without an error
- Let the user type their own string instead of using fixed samples
- Return all runs when there is a tie

## About me

**Rammal Ahmed**

**AI & Data Science Enthusiast** | **Microsoft Dynamics 365 CRM Developer** | **Power Platform** | **UI/UX Designer** | **Graphic Designer & Illustrator**

[![LinkedIn](https://img.shields.io/badge/LinkedIn-Connect-0A66C2?style=flat&logo=linkedin&logoColor=white)](https://linkedin.com/in/rammal-ahmed-58184b325)
[![GitHub](https://img.shields.io/badge/GitHub-Rammal--Ahmed-181717?style=flat&logo=github)](https://github.com/Rammal-Ahmed)

<div align="center">

If you found this useful, consider giving it a star ⭐

**I truly value your feedback and welcome any suggestions for improvement**

**Always open to fresh perspectives, constructive feedback, and new ideas**


## License

This project is licensed under the **MIT License**. See the [LICENSE](LICENSE) file for details

---

*Developed as part of my Python programming practice*

---

**Project Status:** Completed

</div>
