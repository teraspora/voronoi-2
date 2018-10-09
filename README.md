# Voronoi-2

This is a fragment shader in GLSL that sets up a random set of points, computes the Voronoi partition by a distance metric And applies a variety of transformations to achieve an intersting effect.

# Manhattan Distance

I am using the random function given by Martijn in The Art of Code in [Voronoi Explained](https://www.youtube.com/watch?v=l-07BXzNdPw&t=371s) and as a starting point, his method.

In the current incarnation I am calling my Minkowsi distance function 

`float minkd(vec2 u, vec2 v, float order) {
    if (order <= 0.) return 0.;
	return abs(pow(abs(pow(v.x - u.x, order)) + abs(pow(v.y - u.y, order)), 1. / order)); 
}`

with order = 1.0, which produces the angular effects seen.   Calling it  with order = 2.0 for bog-standard Euclidean distance results in much more rounded shapes, and other values produce a more fragmented effect.

The shader is ripe for further experimentation.

