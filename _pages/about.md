---
permalink: /
excerpt: "About me"
author_profile: true
redirect_from: 
  - /about/
  - /about.html
---

Hello! My name is Anthony and I am an AI researcher and CTO focused on using AI for high-impact real-world problems. I recently co-founded a company [Terra AI](terraai.com) that is developing decision-support tools for the development of large-scale [sustainable resource projects](/portfolio/1_sustainability/) such as mineral exploration, geothermal production, and carbon sequestration, where AI can improve both efficiency and safety. As part of an interdisciplinary team, we model these problems as large partially observable Markov decision processes (POMDPs) and develop [custom solvers](/portfolio/2_pomdp_planning) for them. Previously, I have worked on the [validation of safety critical autonomy](/portfolio/3_safety/) in domains such as autonomous driving and aviation. 

In my research I focus on three key pillars that enable the development of reliable autonomy for high-stakes applications
1. **Building Robust Models**: Modeling the environment is an essential step toward developing AI systems that can effectively operate in it. For example, in our [recent paper](https://arxiv.org/abs/2304.09352) we developed a deep neural network surorogate model of CO<sub>2</sub> reservoir dynamics to plan for geological carbon storage.
2. **Planning Under Uncertainty**: With the models developed, we need algorithms to plan optimal actions. See our recent work [BetaZero](https://arxiv.org/abs/2306.00249), which combines planning and learning to solve POMDPs. 
3. **Extensive Safety Validation**: Once the AI system has been developed, it needs extensive testing before deployment. See [this survey](https://arxiv.org/abs/2005.02979) on algorithms for automated testing of black-box autonomous systems that have been applied across many domains.


## Outreach on the Risks and Opportunities of AI

My research in safety-critical autonomy gives me a unique perspective into the risks and common pitfalls of deploying AI systems in high-stakes domains. I try to communicate these risks to non-technical audiences, seizing every opportunity to foster a broader understanding and awareness amongst key stakeholders. I enjoy discussing the challenges, best practices, and known limitations of AI systems with decision-makers in government (e.g. through HAI's [congressional bootcamp on AI](https://hai.stanford.edu/congressional-boot-camp-ai), or as a member of the [Wilson Center](https://www.wilsoncenter.org/)'s Pathway to AI Policy program), national security (e.g. at events hosted by [CISAC](https://cisac.fsi.stanford.edu/) or [IST](https://securityandtechnology.org/)), and industry (e.g. my [summer course](http://ancorso.github.io/teaching/2023-summer-AISafety) on reliable AI through SCPD).

## Hobbies and Interests

Beyond research I enjoy reading, spending time with friends and family, and being outside, especially rock climbing. It's my dream to one day make a clean ascent of [Freerider](https://www.mountainproject.com/route/106261545/freerider) on El Capitan. 


<div class="image-container">
    <img src="images/img1.jpg">
    <img src="images/img2.jpg">
</div>

<style>
    .image-container {
        display: flex;
        align-items: flex-start; /* Align images to the top of the container */
    }

    .image-container img {
        max-height: 350px; /* Set the maximum height for all images */
        margin: 5px; /* Add some margin between images */
        object-fit: cover; /* Preserve aspect ratio and cover the container */
    }
</style>