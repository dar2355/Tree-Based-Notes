---


---

<ul>
<li>Dendron Project
<ul>
<li><strong>Schematics:</strong>
<ul>
<li>Statement Types:
<ul>
<li><code>:= identifier expression</code></li>
<li><code>@ expression</code></li>
</ul>
</li>
<li>Specifications:
<ul>
<li>Identifiers must begin with alphabetic character</li>
<li>expressions represent integer calculations</li>
<li>Everything is integers
<ul>
<li>if it is not an integer, floor it (basically just cast it to an int)</li>
</ul>
</li>
</ul>
</li>
<li>Nodes:
<ul>
<li>DendronNode
<ul>
<li>ActionNode
<ul>
<li>Assignment</li>
<li>Print</li>
<li>ActionSequence</li>
</ul>
</li>
<li>ExpressionNode
<ul>
<li>Constant</li>
<li>Variable</li>
<li>UnaryOperation
<ul>
<li>Negation ( _ )</li>
<li>Square Root (#)</li>
</ul>
</li>
<li>BinaryOperation
<ul>
<li>add (+)</li>
<li>Subtract (-)</li>
<li>Multiply (*)</li>
<li>Divide (/)</li>
</ul>
</li>
</ul>
</li>
</ul>
</li>
</ul>
</li>
</ul>
</li>
<li><strong>Tests</strong>:
<ul>
<li>Test 3:
<ul>
<li>Raw data:
<ul>
<li><code>[:=, x, 1, :=, x, +, x, x, :=, x, *, x, x, :=, x, -, 2, _, x, @, x, :=, x, /, x, 2, :=, pastafagiole, #, +, 19, x]</code></li>
</ul>
</li>
<li>Converted To Lines:
<ul>
<li><code>:= x 1</code></li>
<li><code>:= x + x x</code></li>
<li><code>:= x * x x</code></li>
<li><code>:= x - 2 _ x</code></li>
<li><code>@ x</code></li>
<li><code>:= x / x 2</code></li>
<li><code>:= pastafagiole # + 19 x</code></li>
</ul>
</li>
<li>What happens:
<ul>
<li><code>x = 1</code><br>
declare x and set it to 1</li>
<li><code>x = x + x</code><br>
add x to itself</li>
<li><code>x = x * x</code><br>
multiply x by itself</li>
<li><code>x = 2 - -x</code><br>
set x to two minus (negative) x</li>
<li><code>print x</code><br>
display x</li>
<li><code>x = x / 2</code><br>
divide x by two.</li>
<li><code>pastafagiole = sqrt(19 + x)</code><br>
set pastafagiole to the square root of 19 plus x</li>
</ul>
</li>
<li>into “nodes”:
<ul>
<li>Ass() = Assignment()
<ul>
<li><code>Ass(x, 1)</code></li>
<li><code>Ass(x, Add(x, x) )</code></li>
<li><code>Ass(x, Mul(x, x) )</code></li>
<li><code>Ass(x, Sub(x, Neg(x) ) )</code></li>
<li><code>Print(x)</code></li>
<li><code>Ass(x, Div(x, 2) )</code></li>
<li><code>Ass(pastafagiole, Sqrt(Add(19, x) ) )</code></li>
</ul>
</li>
</ul>
</li>
<li>into “Machine” code:
<ul>
<li><code>PUSH 1</code></li>
<li><code>STORE x</code></li>
<li>—</li>
<li><code>LOAD x</code></li>
<li><code>LOAD x</code></li>
<li><code>ADD</code></li>
<li><code>STORE x</code></li>
<li>—</li>
<li><code>LOAD x</code></li>
<li><code>LOAD x</code></li>
<li><code>MUL</code></li>
<li><code>STORE x</code></li>
<li>—</li>
<li><code>PUSH 2</code></li>
<li><code>LOAD x</code></li>
<li><code>NEG</code></li>
<li><code>SUB</code></li>
<li><code>STORE x</code></li>
<li>—</li>
<li><code>LOAD x</code></li>
<li><code>PRINT</code></li>
<li>—</li>
<li><code>LOAD x</code></li>
<li><code>PUSH 2</code></li>
<li><code>DIV</code></li>
<li><code>PUSH x</code></li>
<li>—</li>
<li><code>PUSH 19</code></li>
<li><code>LOAD x</code></li>
<li><code>ADD</code></li>
<li><code>SQRT</code></li>
<li><code>PUSH pastafagiole</code></li>
</ul>
</li>
</ul>
</li>
</ul>
</li>
</ul>
</li>
</ul>

