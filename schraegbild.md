## Drawing Oblique Images
```tex
\input{./schraegbild.tikz}
```
Shapes that are not affected by projection can be drawn directly - others need to be projected seperately.

### Trigonal Prism resting on a rectangle face
```tex
\begin{tikzpicture}
	\projRechteck{A}{B}{C}{D}{5cm}{4cm}

	\begin{scope}[xshift=2.5cm, yshift=3cm]
		\projKante{E}{F}{4cm}
	\end{scope}

	\draw (A) to (B) to (C) to (F) to (E) to (A);
	\draw (B) to (E);
	\draw[dashed] (A) to (D) to (C);
	\draw[dashed] (D) to (F);
\end{tikzpicture}
```

### Trigonal Prisma resting on a triangle face
```tex
\begin{tikzpicture}
	\projDreieckGleichschenklig{A}{B}{C}{}{5cm}{3.5cm}

	\begin{scope}[yshift=3cm]
		\projDreieckGleichschenklig{D}{E}{F}{}{5cm}{3.5cm}
	\end{scope}

	\draw (D) to (A) to (B) to (E) to (D) to (F) to (E);
	\draw[dashed] (A) to (C) to (B);
	\draw[dashed] (C) to (F);
\end{tikzpicture}
```

### Pyramid on an isosceles triangle
```tex
\begin{tikzpicture}
	\projDreieckGleichschenklig{A}{B}{C}{}{5cm}{3.5cm}

	\begin{scope}[yshift=3cm]
		\projDreieckGleichschenklig{D}{E}{F}{}{5cm}{3.5cm}
	\end{scope}

	\draw (D) to (A) to (B) to (E) to (D) to (F) to (E);
	\draw[dashed] (A) to (C) to (B);
	\draw[dashed] (C) to (F);
\end{tikzpicture}
```

### Pyramid on a equilateral triangle
```tex
\begin{tikzpicture}
	\projDreieckGleichseitig{A}{B}{C}{F}{5cm}
	\path (F) ++(0, 4cm) coordinate (S);

	\draw (A) to (B) to (S) to cycle;
	\draw[dashed] (A) to (C) to (B);
	\draw[dashed] (C) to (S);
	\draw[help lines] (C) to (F) to (S);
	\draw[help lines] (A) to (F) to (B);
\end{tikzpicture}
```
