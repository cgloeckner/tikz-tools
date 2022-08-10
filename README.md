# tikz-tools
Some tools for creating maths stuff for school purposes.

This is only a draft version, quickly bashed together. Things are named in German, so be aware :D 

## Constructing Triangles
```tex
\input{./dreiecke.tikz}
```
Note, that sometimes two points are generated, named C1 and C2 instead of C. Pick what suits your needs.

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

### Given by Side-side-Angle
```tex
\begin{tikzpicture}
	\clip(-0.5, -1) rectangle (9, 8);

	\dreieckSsW{7.5}{6}{48}

	\draw[very thick] (A) to node[below] {$6cm$} (B) to node[above right] {$7.5cm$} (C) to cycle;
	
	\node[below] at (A) {$A$};
	\node[below] at (B) {$B$};
	\node[above left] at (C) {$C$};

	\draw pic["$48$°", draw, angle radius=1.25cm] {angle=B--A--C};
\end{tikzpicture}
```

If the first side given isn't longer than the second one, an additional C2 point is generated:
```tex
\begin{tikzpicture}
	\clip(-1, -1) rectangle (8, 7);

	\dreieckSsW{6}{7.5}{48}

	\node at (C2) {\textbf x};

	\draw[very thick] (A) to node[below] {$7,5cm$} (B) to node[above right] {$6cm$} (C) to cycle;
	\draw[very thick] (A) to (B) to node[above right] {$6cm$} (C2) to cycle;
	
	\node[below] at (A) {$A$};
	\node[below] at (B) {$B$};
	\node[above left] at (C) {$C_1$};
	\node[above left] at (C2) {$C_2$};

	\draw pic["$48$°", draw, angle radius=1.25cm] {angle=B--A--C};
\end{tikzpicture}
```
