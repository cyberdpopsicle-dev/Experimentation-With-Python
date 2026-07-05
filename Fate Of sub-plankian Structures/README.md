## The Fate of Sub-Planckian Structures: Simulating Decoherence in Phase Space

In this simulation, I take the next step by modeling the system as an open quantum system using the Lindblad master equation. Instead of evolving an isolated quantum state, the simulation captures how interactions with the environment gradually destroy quantum coherence.
The dynamics are governed by two competing processes:
• Kerr nonlinearity: The system evolves into a macroscopic quantum superposition, producing intricate interference structures in the Wigner distribution.
• Photon loss: Amplitude damping models photons leaking into the environment, causing the system to lose coherence over time.
As the simulation progresses, pay close attention to the center of the Wigner distribution. The fine interference fringes that characterize the sub-Planckian structures begin to fade as decoherence takes hold. These delicate quantum features depend entirely on coherent phase relationships, and even modest environmental interactions are enough to erase them.
What remains is a classical statistical mixture, illustrating the transition from quantum behavior to classical physics.
This simulation highlights one of the fundamental challenges in quantum computing, quantum sensing, and quantum error correction: preserving quantum coherence long enough to perform meaningful computations or measurements. Understanding how quickly decoherence destroys these fragile quantum features is essential for designing more robust quantum technologies.
The simulation video is attached below, along with the complete optimized Python implementation using QuTiP's open-system solver.
