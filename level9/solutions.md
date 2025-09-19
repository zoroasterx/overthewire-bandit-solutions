# Level 9  - Bandit
**Goal**: Find the password in `data.txt`, which is the only line of text that occurs exactly once.


## Concepts

**`sort`**: Sorts lines of text alphabetically or numerically

Used to group identical lines togheter, which is required for `uniq` to work correctly.

**`uniq`**: Filters adjacent duplicate lines in sorted text.

**`uniq` key flags**: `-u`: Outputs only unique lines (that appear exactly once).

		      `-d`: Outputs only duplicated lines

		      `-c`: Counts occurences of each line

`uniq` command always requires using `sort` before `uniq`.

##Command used

```bash
sort data.txt | uniq -u
``` 
