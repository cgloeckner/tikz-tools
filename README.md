# tikz-tools
Some tools for creating maths stuff for school purposes.
This is only a draft version, quickly bashed together.

## Constructing Triangles
```tex
\input{./dreiecke.tikz}
```

Things are named in German, so be aware :D 

### Given by Side-Side-Side
```tex
\begin{tikzpicture}
	% clip view to trim help lines
	\clip (-1, -1) rectangle (6, 3.5);

	% given sides 2.9cm, 3.9cm, 4.9cm
	\dreieckSSS{2.9}{3.9}{4.9}

  % combine and label edges
	\draw[very thick] (A)
		to node[below] {$c$} (B)
    to (C2) to cycle;
	\node[below] at (A) {$A$};
	\node[below] at (B) {$B$};
	\node[above] at (C2) {$C$};
\end{tikzpicture}
```

### Given by Angle-Side-Angle
```tex
\begin{tikzpicture}
	\clip (-1, -1) rectangle (6.25, 3.5);

	\dreieckWSW{32}{6}{53}

	\draw[very thick] (A)
  	to node[below] {$a$} (B)
    to (C) to cycle;

	\node[below] at (A) {$B$};
	\node[below] at (B) {$C$};
	\node[above] at (C) {$A$};
	
	\draw pic["$\beta$", draw, angle radius=1.25cm] {angle=B--A--C};
	\draw pic["$\gamma$", draw, angle radius=1.25cm] {angle=C--B--A};
\end{tikzpicture}
```

### Given by Side-Angle-Side
```tex
\begin{tikzpicture}
	\clip (-1, -0.5) rectangle (8.5, 4);

	\dreieckSWS{6}{120}{3}

	\draw[very thick] (A)
		to node[below] {$a$} (B)
		to node[below right] {$b$} (C) to cycle;
	
	\node[below] at (A) {$B$};
	\node[below] at (B) {$C$};
	\node[right] at (C) {$A$};

	\draw pic["$\gamma$", draw, angle radius=0.75cm] {angle=C--B--A};
\end{tikzpicture}
```
