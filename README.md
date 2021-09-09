# Saikiran Agiru

## New York

- The **Vibrant City** which being one of the most famous cities in the world. It has famous **Iconic Sites** which includes skyscrapers such as the Empire State Building and sprawling Central Park. Broadway theater is staged in neon-lit Times Square.

---


### Directions

1. The Total distance from Maryville to New York is around 1100 miles.
2. It covers five differemt states which are:
    1. Iowa
    2. Illinois
    3. Indiana
    4. Ohio
    5. Pennsylvania
3. The maximum distance is covered on I-80 interstate which covers from West Coast to East Coast.

- Pressed Pennies
- Chocolate Treats
- Gamers Swag Merchandise from Nintendo
- New York-themed trinkets
- Artistic souvenirs from the Museum of Modern Art

Link to About Me : [AboutMe](AboutMe.md)

---

### Best Recommend Food/Drinks

- Some of the Signature dishes which would be Recommended and famous from it's place.

| Item | Location  | Price  |
|---|---|---|
| Dosa  | Ram Ki Bandi  | $1-$2  |
| Hyderabadi Briyani  | Cafe Bahar  | $7-$10 |
| Chaach  | Haryana  | $2-$3  |
| Fenny  | Goa   | $10-$50 |

---

### Quotes

Innovation distinguishes between a leader and a follower - *Steve Jobs*

One of the only ways to get out of a tight box is to invent your way out – *Jeff Bezos*

---

### Suffix automaton Algorithm

In computer science, a suffix automaton is an efficient data structure for representing the substring index of a given string which allows the storage, processing, and retrieval of compressed information about all its substrings. The suffix automaton of a string {\displaystyle S}S is the smallest directed acyclic graph with a dedicated initial vertex and a set of "final" vertices, such that paths from the initial vertex to final vertices represent the suffixes of the string.

[Source](https://en.wikipedia.org/wiki/Suffix_automaton)

```
void sa_extend(char c) {
    int cur = sz++;
    st[cur].len = st[last].len + 1;
    int p = last;
    while (p != -1 && !st[p].next.count(c)) {
        st[p].next[c] = cur;
        p = st[p].link;
    }
    if (p == -1) {
        st[cur].link = 0;
    } else {
        int q = st[p].next[c];
        if (st[p].len + 1 == st[q].len) {
            st[cur].link = q;
        } else {
            int clone = sz++;
            st[clone].len = st[p].len + 1;
            st[clone].next = st[q].next;
            st[clone].link = st[q].link;
            while (p != -1 && st[p].next[c] == q) {
                st[p].next[c] = clone;
                p = st[p].link;
            }
            st[q].link = st[cur].link = clone;
        }
    }
    last = cur;
}

```

[Source](https://cp-algorithms.com/string/suffix-automaton.html#toc-tgt-14)