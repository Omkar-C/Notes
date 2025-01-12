
For Every Polygon with n vertices where n >= 3, it can be divided into n-2 triangles using diagonals

### Proof
For n = 3, the polygon is a triangle and thus it holds true.
Let T(n) = number of triangles that can be formed with polygon of vertices n.

Let take a polygon with n vertices. Let's divide the polygon into two polygons by drawing a diagonal 
![[Pasted image 20250111230107.png]]
Let's assume our statement holds for all i where i >= 3 and i < n.

Hence when we have divided our polygon into two polygons we can say
$$ 
\begin{matrix}
T(a) = a - 2 \\ 
T(b) = b - 2 \\
Also, n = a + b - 2 \\
T(n) = T(a) + T(b) \\
T(n) = a - 2 + b - 2 \\
T(n) = a + b - 4 \\
Substituting \: a + b = n - 2 \: from \: above \\
T(n) = n - 2 \\
\end{matrix}
$$
Thus we have proved that for T(n) = n - 2.
By proof of induction we have proved that 
**Every n Polygon can be Triangulated Into Exactly n-2 Triangles**
