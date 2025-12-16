Interactive Bézier Rope (Web)
This project shows a cubic Bézier curve behaving like a springy rope, rendered on an HTML5 canvas and controlled by mouse movement.

How to run:
Open bezier_rope.html in any modern browser (Chrome, Edge, Firefox).

Move the mouse up and down over the canvas to bend the “rope”.

Core ideas:
The curve uses the cubic Bézier formula:
B(t)=(1−t)3P0+3(1−t)2tP1+3(1−t)t2P2+t3P3B(t)=(1−t)3P0+3(1−t)2tP1+3(1−t)t2P2+t3P3.
​
Tangent vectors are computed from the derivative:
B′(t)=3(1−t)2(P1−P0)+6(1−t)t(P2−P1)+3t2(P3−P2)B′(t)=3(1−t)2(P1−P0)+6(1−t)t(P2−P1)+3t2(P3−P2).
​
Endpoints P0P0 and P3P3 are fixed; control points P1P1 and P2P2 move using a spring–damping model:
acc=−k(position−target)−damping⋅velocityacc=−k(position−target)−damping⋅velocity.​

Implementation notes:
All Bézier math, derivative, and physics are implemented manually in JavaScript (no Bézier or physics libraries).​

Rendering, input, and animation are done with HTML Canvas 2D and requestAnimationFrame.
