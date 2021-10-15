# Circuit Minimization
- Consider the circuit that ouputs 1 iff $x = y = z=1$ or $x=z=1$ and $y=0$
- We can simplify the expression:
$$xyz+x\bar{y}z = (y + \bar{y})(xz)=1\dot(xz)=xz$$
- $xz$ is a boolean expression with fewer operators that represents the circuit, thus it will have fewer logic gates
- Thus, we can use [[essential laws of propositional logic]] to minimize circuits.