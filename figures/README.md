# Figures Directory

Place all your image files (PNG, JPG, PDF, SVG/EPS) in this directory.

In LaTeX, you can reference images using relative paths starting inside this directory because `main.tex` includes:
`\graphicspath{{figures/}}`

Example usage in LaTeX:
```latex
\begin{figure}[htbp]
    \centering
    \includegraphics[width=0.8\textwidth]{my_diagram.png}
    \caption{Description of my diagram.}
    \label{fig:my_diagram}
\end{figure}
```
