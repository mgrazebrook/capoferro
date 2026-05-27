# capoferro
Capoferro is a wireless fencing hit detector. Each fencer has a [BBC Microbit](https://microbit.org/) linked by bluetooth to the opponent's device. The name honours the [Italian fencing master](https://en.wikipedia.org/wiki/Ridolfo_Capo_Ferro) who published a treasie on the rapier in 1610.

By basing the project on microbits, making this should be both fairly cheap and literally childsplay. 
# The theory
Guess: A fencer and sword are around 100pF. 

Reasoning: Let a conducting fencing jacket has a capacitance as a 60cm diameter object: \(C = 4 \pi \epsilon_0 R\) so about 7e-11 or 70 pF; the sword might add around 10 pF. This could be confounded by sweat and the fencer's body position. Also increased somewhat by the irregularity of the suit. Also a human has a capacitance of around 120 pF. Say 200 pF in all.

So using a [470pF capacitor](https://kitronik.co.uk/products/3008-470uh-470uh-inductor-470uh) and the formula $f = \frac{1}{2\pi\sqrt{LC}}$ so about 500 MHz. Or with a [4.7 mH Bobbin Inductor](https://uk.rs-online.com/web/p/leaded-inductors/7156832), 164 KHz

Guess: When there's a hit, the capacitance rougly doubles so the frequency reduced by $\sqrt{ 2 }$

164 KHz is too fast to count in code so we need to reduce the frequency it using a counter
