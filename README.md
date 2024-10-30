# Least Action Principle

Credit to [Veritasium](https://youtu.be/Q10_srZ-pbs?si=i39xyI3WLzjpCByf). Watch the video for the full history of the action principle.

## The Basics
### The Law of Least Action
We start by defining the original form as defined by Maupertuis.
$$
S_{0} = \sum mvs
$$
In here $S_{0}$ is the action principle, $m$ is the mass, $v$ is the velocity, and $s$ is the position.

Euler converted the sum into an integral, which is what we will do.
$$
S_{0} = \int_{c}  mv ds
$$

Where $c$ is the path chosen.

### Assumptions

We can derive the Euler-Lagrange equation but first we have to make a few assumptions for this form of the action principle:

1. Energy is conserved.
2. Energy is the same for all paths. $E_1 = E_2 = ... = E_n$

## The General Approach.
If there are infinitely many paths to get from one point to another, how to find the point that minimizes the action?

To find the minimum of any curve in calculus, we typically find the points where the derivative is zero. So if we take small steps $\eta$ at the minima, the value doesn't change.

Let's assume that our path of least action is parametrized and of the form $x(t)$ where $t$ is time.

Similar to nudging minima of a 1D function, we will nudge the path of least action to get to the minima. However, here our nudge is also a parametrized function $\eta(t)$. We will call this new perturbed path $q(t)=x(t)+\eta(t)$. If $x(t)$ is the path of least action, then any other path must have more action.

If we go back to our derivative example, let's assume we have the minima of a parabola where x is at $\frac{df}{dx}=0$ and the changes to the minima by some value $\eta$ is proportional to $f(x) \propto \eta$ then there exists a lower point of minima which is not possible since any changes in $\eta$ cannot produce a "lower" minima. But if we have changes proportional to something like $f(x) \propto \eta^2$ then any changes to the left or right have to be greater than the derivative at $x$. The same goes for potentially higher orders of $\eta$.

Let's go back to our action model taking that into consideration. If the first order changes cannot produce a lower action, then the difference between the actions of $q(t)$ and $x(t)$ must be zero.

$$
S_0\left[ q(t) \right] - S_0\left[ x(t) \right] = 0
$$

In other words, the variation of action is zero.

$$
\delta S_0 = 0
$$

And this is how we will start the derivation.

### Derivation

Starting with Maupertuis action definition.
$$
\delta S_0 = \delta \sum mvs
$$

The Euler integral definition, however, is more appropriate to start with.
$$
\delta S_0 = \delta \int mv ds = 0
$$

Recall that the velocity is the time derivative of the position.
$$
v = \frac{ds}{dt} \rightarrow ds = v\;dt 
$$

So we can rewrite the variation in action as:
$$
\delta \int mv^2 dt = 0
$$

The definition of kinetic energy is $T=\frac{1}{2}mv^2$ so this becomes:
$$
\delta \int 2T dt = \delta \int (T + T)\; dt = 0
$$

The definition of total energy is $E=T+V$ or $T=E-V$ so we can replace one of them to become:

$$
\delta \int (T + E - V)\; dt = \delta \int (T - V)\; dt + \delta \int E \; dt = 0
$$

And since $E$ is independent of the path, we can take it out of the integral to get:

$$
\delta \int (T - V)\; dt + \delta (E\;t) = 0
$$

We can use the product rule for $E\;t$ to get:

$$
\delta \int (T - V)\; dt + \delta (E) \;t + E \delta(t) = 0
$$

Recall that energy is conserved so the variation of the total energy is zero.

$$
\delta \int (T - V)\; dt = - E \delta(t) 
$$

Now we have to make a third assumption if we are to consider this an optimization problem.

3. The time taken across different times is the same.

This assumption further assumes that all perturbations of the path $x(t)$ must take the same time.

With this assumption, our final least action takes this form:

$$
\delta \int (T - V)\; dt = 0
$$

Now we have fully converted the least principle into the difference between kinetic and potential energy. This is known as Hamilton's principle.

The action definition in terms of energies can be written as:

$$
S = \int (T - V)\; dt
$$


### The Euler-Lagrange Equations

To derive the E-L equations, we must first assume that we have a path $q(t)$ and the perturbations to such path will be something like $\delta q(t)$

The difference between the kinetic and potential energy is known as the Lagrangian:

$$L(q, \.q, t) = T-V$$

$$
\delta \int (T - V)\; dt = \delta \int L(q,\.q, t)\; dt = 0
$$

#### Caveat
Before moving forward, let's take a look at what happens when we take the first order variations. Recall that we are interested in the linear variations (first order) and that will be reflected in all Taylor series approximations.

$$\delta S = S(q+\delta q) - S(q)$$

In the case of the Lagrangian, this becomes
$$ \delta L(q, \.q, t) = L(q + \delta q, \.q + \delta \.q, t) - L(q, \.q, t)$$

And by looking at the first few terms of the series expansion, we have.

$$
L(q + \delta q, \.q + \delta \.q, t) \approx L(q, \.q, t) + \frac{\partial L}{\partial q} \delta q + \frac{\partial L}{\partial \.q} \delta \.q
$$

Now applying the variations the Lagrangian we get:

$$
\int_{t_1}^{t_2} \left ( \frac{\partial L}{\partial q} \delta q + \frac{\partial L}{\partial \.q} \frac{d}{dt}(\delta q) \right) dt = 0
$$

Let's integrate the second term by parts to get:

$$
\int_{t_1}^{t_2} \frac{\partial L}{\partial \.q} \frac{d}{dt}(\delta q)\; dt = \left [ \frac{\partial L}{\partial \.q} \delta q \right ]_{t_1}^{t_2} - \int_{t_1}^{t_2} \frac{d}{dt} \left ( \frac{\partial L}{\partial \.q} \right ) \delta q \; dt
$$

Note that we want the variations to vanish at the starting and end points $\delta q(t_1) = \delta q(t_2) = 0$ so this term goes to zero.
$$
\left [ \frac{\partial L}{\partial \.q} \delta q \right ]_{t_1}^{t_2} = 0
$$

Leaving us with:

$$
\int_{t_1}^{t_2} \left ( \frac{\partial L}{\partial q} \delta q - \frac{d}{dt} \left ( \frac{\partial L}{\partial \.q} \right ) \delta q  \right ) dt = 0
$$

Factor out $\delta q$ to get:

$$
\int_{t_1}^{t_2} \left ( \left [ \frac{\partial L}{\partial q} - \frac{d}{dt} \left ( \frac{\partial L}{\partial \.q} \right ) \right ] \delta q \right ) dt  = 0
$$

Now remember that this has to be zero for all possible $\delta q$ which means that this portion of the integrand has to be zero.

$$
\boxed{
    \frac{\partial L}{\partial q} - \frac{d}{dt} \left ( \frac{\partial L}{\partial \.q} \right ) = 0
}
$$

This is the Euler-Lagrange Equations derived from the action principle.
