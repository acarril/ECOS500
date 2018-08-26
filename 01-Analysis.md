# 1. Analysis Problems

1. Let $\{ s_n \}_{n=1}^\infty$ be defined by $s_1=s_2=1$, and $s_{n+1} = s_n = s_{n-1}$ for $n\geq 2$. Find $s_{10}$.
**Solution:** This is the Fibonacci sequence with $F_1 = F_2 = 1$. The 10th term is 55.
2. Is the sequence $1,0,1,0,\ldots$ a subsequence of $1,2,3,4,\ldots$?
**Solution:** No, for various reasons. Intuitively, a subsequence is a sequence that can be derived from another sequence by removing some or no elements without chaning the order of the remaining elements. This obviously is not the case for the two given sequences.
More formally, a subsequence of $\{ a_n\}$ is a sequence $\{ b_k\}$ defined by $b_k = a_{n_k}$, where $n_1 < n_2 < \ldots$ is an increasing sequence of indices.
From this definition we have that $n\geq k$, and that
$$
\forall n \geq 1, \exists n \geq k : b_k = a_n.
$$
Now let $a_n = 1,2,3,\ldots = n$. Let $\{ b_k\} = 1,0,1,0,\ldots = \frac{(-1)^n + 1}{2}$. It is evident that $\{ b_k\}$ does not satisfy the definition of subsequence for $\{ a_n\}$, because $b_2=0 \notin \{a_n\}$.
3. Let $S$ be a sequence. Prove that every subsequence of a subsequence of $S$ is itself a subsequence of $S$.
**Solution:** Let $S_j$ be a sequence s.t. $T_k = S_{n_k}$ where $n_1 < n_2 < \ldots$ is an increasing sequence of indices (i.e. it is a subsequence of $S_j$).
Now let $U_l$ be a sequence defined by $U_l = T_{m_l}$, where again $m_1 < m_2 < \ldots$ is an increasing sequence of indices, so that $U_l$ is a subsequence of $T_k$.
Thus by construction we have that
$$
\forall j \geq 1, \exists j \geq k \geq l : U_l = T_k = S_j,
$$
so in particular $U_l$ is a subsequence of $S_j$.
4. If $\{ s_n\}_{n \in \mathbb{N}}$ is a sequence of real numbers with limit $L$, prove that this limit is unique.
**Solution:** First, if a sequence has a limit it is by definition convergent. So the statement to prove can be restated as "For all convergent sequences there exists a unique limit $L$". We're going to prove this by contradiction, assuming that there exists one convergent sequence which does not have a unique limit.
Let $\{ s_n\}_{n \in \mathbb{N}}$ denote a sequence with limits $l_1, l_2$, with $l_1 \neq l_2$. Now we choose $\epsilon = \frac{1}{3}|l_1 - l_2| > 0$ (because $l_1 \neq l_2$).
Since $l_1$ is a limit of $\{ s_n\}_{n \in \mathbb{N}}$ we can apply the definition of limit with our choice of $\epsilon$ to find $N_1 \in \mathbb{N}$ s.t.
$$
|a_n - l_1| < \epsilon \; \forall n \geq N_1.
$$
Analogously, we can also find $N_2 \in \mathbb{N}$ s.t.
$$
|a_n - l_2| < \epsilon \; \forall n \geq N_2.
$$
Note that we're not assuming that each of the two assumed limits, $l_1$ and $l_2$, we can find the *same* $N$, so that's why there's $N_1$ and $N_2$.
Now we choose any $m_0 > \max (N_1, N_2)$, so $|a_{m_0} - l_1|<\epsilon$ and $|a_{m_0} - l_2|<\epsilon$. This shows that both $l_1$ and $l_2$ are "close" to $a_{m_0}$. We can remove $a_{m_0}$ by using that $\forall a,b \in \mathbb{R}: |a|-|b| \leq |a-b|$, so that
$$
\begin{aligned}
|l_1 - l_2| &= |l_1 - a_{m_0}  + a_{m_0} + l_2| \\
&\leq |l_1 - a_{m_0}| + |a_{m_0} - l_2| \\
&< \epsilon + \epsilon \\
&= 2\epsilon = \frac{2}{3}|l_1 - l_2|.
\end{aligned}
$$ This a contradiction, so the limit must be unique.
5. If $\{ s_n\}_{n \in \mathbb{N}}$ is a sequence of real numbers such that $s_n \leq M \;\forall\; n$ and $\lim_{n\rightarrow\infty} s_n = L$, prove that $L<M$.
**Solution:** [I prove that $L\leq M$]
Assume $L>M$. Then there exists $n$ with $|a_n - L| < L-P$, which is the same as
$$M - L < a_n - L < L - M.$$ This implies that $a_n > M$, which contradicts the definition of $M$.
6. Suppose that $(s_n)$ converges to $s$, $(t_n)$ converges to $t$, and $s_n \leq t_n \: \forall \: n$. Prove that $s \leq t$.**Solution:** Suppose $s>t$ write $c=s-t$ there exists $N$ such that $n>N$ implies $|s_n-s|<c/4$. There exists $N'$ such that $n>N'$ implies $|t_n-t|<c/4$, take $n>\sup(N,N')$ $s_n-t_n=s_n-s+s-t+t-t_n\geq s-t-|s_n-s|-|t-t_n|\geq c-c/4-c/4\geq c/2$ contradiction.
7. f
8. f
9. f
10. f
11. f
12. f
13. f
14. f
15. f
16. f
17. f
18. f
19. Prove that every convergent sequence is Cauchy.
**Solution:** Given $\epsilon > 0, \exists N_1$ s.t. $\forall n \geq N_1 | x_n - a | < \epsilon/2 < \epsilon$.
Also, for some $m > n > N_1$ we have that $| x_m - a | < \epsilon/2 < \epsilon$.
Now let $N \geq N_1$, so that $\forall n, m \geq N$ we have that
$$
\begin{aligned}
|x_n - x_m| &= |x_n - a - x_m + a| \\
&< |x_n - a| + |-(x_m-a)| \\
&< \epsilon/2 + \epsilon/2 = \epsilon.
\end{aligned}
$$
20. If $\{s_n \}_{n=1}^\infty$ is a Cauchy sequence of real numbers having a subsequence that converges to $L$, prove that $\{s_n \}_{n=1}^\infty$ itself converges to $L$.
**Solution:** Let $S_{n_k} \rightarrow L$. We need to show that $\forall \epsilon > 0, \exists N$ s.t. $d(S_i, L) < \epsilon, \forall i \geq N$.
Since $S_n$ is Cauchy, $\exists M$ s.t. $j\geq M \implies d(S_m, S_j) < \epsilon/2 \implies d(S_m, L) < \epsilon/2$.
Taking $N=M$, we have that $$d(S_i, L) \leq d(S_N, L) + d(S_i, S_N) < \epsilon/2 + \epsilon/2 = \epsilon.$$
21.  Prove that every subsequence of a Cauchy sequence is a Cauchy sequence.
**Solution:** Let $\{a_n \}_{n\in \mathbb{N}}$ be Cauchy, and let $\{a_{n_k} \}_{k\in \mathbb{N}}$ be a non-Cauchy subsequence of $\{a_n \}$. Therefore, there must be some $\epsilon > 0$ s.t. $N\geq 1$ only if there is some $p,q \geq N$ s.t. $|a_{n_p} - a_{n_q}| \geq \epsilon$. However, by assumption there exists some $N' \geq 1$ s.t. $p,q \geq N'$ only if $|a_{n_p} - a_{n_q}| < \epsilon$, which is a contradiction. Therefore, there can't be such non-Cauchy subsequence.
22. Prove that $\lim_{x\rightarrow -2} x² + 3x = -2$ using *i)* the definition of a limit and *ii)* using results about continuous functions.
23. 
24. f
25. f
26. f
27. f
28. f
29. f
30. f
31. f
32. f
33. f
34. f
35. f
36. f
37. f
38. f
39. f
40. f
41. f
42. f
43. f
44. f
45. f
46. f
47. f
48. f
49. f
50. f
51. f
52. f
53. f
54. f 

## KaTeX

You can render LaTeX mathematical expressions using [KaTeX](https://khan.github.io/KaTeX/):

The *Gamma function* satisfying $\Gamma(n) = (n-1)!\quad\forall n\in\mathbb N$ is via the Euler integral

$$
\Gamma(z) = \int_0^\infty t^{z-1}e^{-t}dt\,.
$$

> You can find more information about **LaTeX** mathematical expressions [here](http://meta.math.stackexchange.com/questions/5020/mathjax-basic-tutorial-and-quick-reference).


# Files

StackEdit stores your files in your browser, which means all your files are automatically saved locally and are accessible **offline!**

## Create files and folders

The file explorer is accessible using the button in left corner of the navigation bar. You can create a new file by clicking the **New file** button in the file explorer. You can also create folders by clicking the **New folder** button.

## Switch to another file

All your files are listed in the file explorer. You can switch from one to another by clicking a file in the list.

## Rename a file

You can rename the current file by clicking the file name in the navigation bar or by clicking the **Rename** button in the file explorer.

## Delete a file

You can delete the current file by clicking the **Remove** button in the file explorer. The file will be moved into the **Trash** folder and automatically deleted after 7 days of inactivity.

## Export a file

You can export the current file by clicking **Export to disk** in the menu. You can choose to export the file as plain Markdown, as HTML using a Handlebars template or as a PDF.


# Synchronization

Synchronization is one of the biggest features of StackEdit. It enables you to synchronize any file in your workspace with other files stored in your **Google Drive**, your **Dropbox** and your **GitHub** accounts. This allows you to keep writing on other devices, collaborate with people you share the file with, integrate easily into your workflow... The synchronization mechanism takes place every minute in the background, downloading, merging, and uploading file modifications.

There are two types of synchronization and they can complement each other:

- The workspace synchronization will sync all your files, folders and settings automatically. This will allow you to fetch your workspace on any other device.
	> To start syncing your workspace, just sign in with Google in the menu.

- The file synchronization will keep one file of the workspace synced with one or multiple files in **Google Drive**, **Dropbox** or **GitHub**.
	> Before starting to sync files, you must link an account in the **Synchronize** sub-menu.

## Open a file

You can open a file from **Google Drive**, **Dropbox** or **GitHub** by opening the **Synchronize** sub-menu and clicking **Open from**. Once opened in the workspace, any modification in the file will be automatically synced.

## Save a file

You can save any file of the workspace to **Google Drive**, **Dropbox** or **GitHub** by opening the **Synchronize** sub-menu and clicking **Save on**. Even if a file in the workspace is already synced, you can save it to another location. StackEdit can sync one file with multiple locations and accounts.

## Synchronize a file

Once your file is linked to a synchronized location, StackEdit will periodically synchronize it by downloading/uploading any modification. A merge will be performed if necessary and conflicts will be resolved.

If you just have modified your file and you want to force syncing, click the **Synchronize now** button in the navigation bar.

> **Note:** The **Synchronize now** button is disabled if you have no file to synchronize.

## Manage file synchronization

Since one file can be synced with multiple locations, you can list and manage synchronized locations by clicking **File synchronization** in the **Synchronize** sub-menu. This allows you to list and remove synchronized locations that are linked to your file.


# Publication

Publishing in StackEdit makes it simple for you to publish online your files. Once you're happy with a file, you can publish it to different hosting platforms like **Blogger**, **Dropbox**, **Gist**, **GitHub**, **Google Drive**, **WordPress** and **Zendesk**. With [Handlebars templates](http://handlebarsjs.com/), you have full control over what you export.

> Before starting to publish, you must link an account in the **Publish** sub-menu.

## Publish a File

You can publish your file by opening the **Publish** sub-menu and by clicking **Publish to**. For some locations, you can choose between the following formats:

- Markdown: publish the Markdown text on a website that can interpret it (**GitHub** for instance),
- HTML: publish the file converted to HTML via a Handlebars template (on a blog for example).

## Update a publication

After publishing, StackEdit keeps your file linked to that publication which makes it easy for you to re-publish it. Once you have modified your file and you want to update your publication, click on the **Publish now** button in the navigation bar.

> **Note:** The **Publish now** button is disabled if your file has not been published yet.

## Manage file publication

Since one file can be published to multiple locations, you can list and manage publish locations by clicking **File publication** in the **Publish** sub-menu. This allows you to list and remove publication locations that are linked to your file.


# Markdown extensions

StackEdit extends the standard Markdown syntax by adding extra **Markdown extensions**, providing you with some nice features.

> **ProTip:** You can disable any **Markdown extension** in the **File properties** dialog.


## SmartyPants

SmartyPants converts ASCII punctuation characters into "smart" typographic punctuation HTML entities. For example:

|                |ASCII                          |HTML                         |
|----------------|-------------------------------|-----------------------------|
|Single backticks|`'Isn't this fun?'`            |'Isn't this fun?'            |
|Quotes          |`"Isn't this fun?"`            |"Isn't this fun?"            |
|Dashes          |`-- is en-dash, --- is em-dash`|-- is en-dash, --- is em-dash|


## KaTeX

You can render LaTeX mathematical expressions using [KaTeX](https://khan.github.io/KaTeX/):

The *Gamma function* satisfying $\Gamma(n) = (n-1)!\quad\forall n\in\mathbb N$ is via the Euler integral

$$
\Gamma(z) = \int_0^\infty t^{z-1}e^{-t}dt\,.
$$

> You can find more information about **LaTeX** mathematical expressions [here](http://meta.math.stackexchange.com/questions/5020/mathjax-basic-tutorial-and-quick-reference).


## UML diagrams

You can render UML diagrams using [Mermaid](https://mermaidjs.github.io/). For example, this will produce a sequence diagram:

```mermaid
sequenceDiagram
Alice ->> Bob: Hello Bob, how are you?
Bob-->>John: How about you John?
Bob--x Alice: I am good thanks!
Bob-x John: I am good thanks!
Note right of John: Bob thinks a long<br/>long time, so long<br/>that the text does<br/>not fit on a row.

Bob-->Alice: Checking with John...
Alice->John: Yes... John, how are you?
```

And this will produce a flow chart:

```mermaid
graph LR
A[Square Rect] -- Link text --> B((Circle))
A --> C(Round Rect)
B --> D{Rhombus}
C --> D
```
<!--stackedit_data:
eyJoaXN0b3J5IjpbLTE5NzQyODAwNTcsLTg5NTkxMDIzMiwxND
A0OTgxNTk5LC0xNzE1NTgyMjcyLDEyMjkzOTU4NDAsNDY5Njgw
Nzc1LC0xNjgwMjA2ODUxLC0xNjA3OTI2NDgwLC0xOTEwMjA1NT
YxXX0=
-->