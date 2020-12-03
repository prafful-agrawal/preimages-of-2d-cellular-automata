# Preimages of 2D Cellular Automata
*Google's foobar challenge - Expanding Nebula*

The last level of the Google's **foobar** challenge requires us to find the number of preimages of a given 2D cellular automata. <sup>[\[1\]][1]</sup>

The problem statement is as given below:
- Problem statement - [Expanding Nebula](expanding-nebula.md)


The problem of counting preimages of a cellular automata has been well researched for 1 Dimension. <sup>[\[2,][2] [3\]][3]</sup> Whereas, the research for 2D cellular automata is generally limited. From the available research, I found the following two main approaches:
1. Brute force search, and
2. de Bruijn diagram.

## Solution 1 - Brute force search

In this method, we can simply generate all the possible combinations of preimages then check them one by one. But, this will be computationally intensive and will surely fail the foobar challenge. Hence, to simplify the problem, I came up with the following improvements:

- Generate the preimages of a row one at a time and filter these preimages by comparing their overlaps with the preimages of preceding row and so on.
- To keep the space requirement low, store only the preimages of the current row and its previous row during each iteration. Filter and update the remaining preimages before moving to the next row.
- Also, transpose the given 2D grid such that the number of columns is *always* less than the number of rows. This minimizes the number of candidate preimages before they are filtered out.

The solution is given below:

> [Expanding Nebula - Brute force search](expanding-nebula---brute-force-search.py)

## Solution 2 - de Bruijn diagram

**de Bruijn diagram** is a popular method for finding the preimages of 1D cellular automata. Harold V. McIntosh initially studied the application of de Bruijin diagrams for Linear Cellualar Automata. <sup>[\[4\]][4]</sup> Iztok Jeras and Andrej Dobnikar later extended his work and presented a new graphical representation for it known as the **preimage network**. <sup>[\[5\]][5]</sup>

Iztok Jeras advanced the preimage network from 1D to 2D cellular automata in his thesis work. This can be used to develop an efficient algorithm to count preimages of a 2D cellular automata. <sup>[\[6\]][6]</sup> Sadly, the original work is in Slovenian. Hence, I painstakingly translated the thesis into english using google translate. The original thesis along with the google translated version is available below:

- Thesis - [Original](Jeras_Iztok_-_Predslike_2D_celičnih_avtomatov.pdf)
- Thesis - [Google translated](Jeras_Iztok_-_Preimages_of_2D_Cellular_Automata.pdf)

Please, feel free to send a pull request if you improve the translation.

## References

1. Google's foobar challenge - [Link][1]
2. Cellular Automata - [Wikipedia][2]
3. Counting preimages of cellular automata - [Wikibooks][3]
4. Harold V. McIntosh, *Linear Cellular Automata via de Bruijn Diagrams*, 1991 - [PDF][4]
5. Iztok Jeras and Andrej Dobnikar, *Algorithms for computing preimages ofcellular automata configurations*, 2007 - [PDF][5]
6. Iztok Jeras, *Preimages of 2D Cellular Automata*, 2016 - [Link][6], Original - [PDF](Jeras_Iztok_-_Predslike_2D_celičnih_avtomatov.pdf), Google Translated - [PDF](Jeras_Iztok_-_Preimages_of_2D_Cellular_Automata.pdf)

[1]: <https://foobar.withgoogle.com/> 'foobar challenge'
[2]: <https://en.wikipedia.org/wiki/Cellular_automaton> 'Cellular Automata'
[3]: <https://en.wikibooks.org/wiki/Cellular_Automata/Counting_Preimages> 'Counting Preimages'
[4]: <http://delta.cs.cinvestav.mx/~mcintosh/comun/cf/debruijn.pdf> 'Linear Cellular Automata via de Bruijn Diagrams'
[5]: <http://www.rattus.info/al/files/preimages.pdf> 'Algorithms for computing preimages ofcellular automata configurations'
[6]: <http://eprints.fri.uni-lj.si/3614/> 'Preimages of 2D Cellular Automata'
