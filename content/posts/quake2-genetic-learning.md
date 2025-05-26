---
date: '2025-05-26T14:09:54+10:00'
title: 'Quake2 Genetic Learning'
---

About 20 years ago, I experimented by adding simple neural net and genetic algorithm based agents to quake2.

Here's what I did back then:

* [Ecosystem: Constructing a simple self-perpetuating society of adaptable agents
](https://web.archive.org/web/20080722115754/http://www.it.swin.edu.au/personal/jbrownlee/other/ecosystem/index.html) (archived)

I was thinking about that again today.

It might be fun to develop a suite of mini experiments using genetic learning an neural net learning in little q2 agents. To setup little ecosystems on server processes and let them run for days and weeks and see what happens.

The 3d nature of the world can make things more fun. And the client-server nature of things means we could allow people to come in and interact or for entities to jump servers.

The Q2 source is good for this. It's very clean, written in C if I recall correctly and very easy to use.

I was chatting with grok3 about this, here are some suggestions of experiments to try:

- **Evolving Harvesting Efficiency**: Evolve creatures to optimize resource collection (e.g., plants) while avoiding predators, using genetic algorithms to balance speed, search radius, and caution.
- **Predator-Prey Co-evolution**: Co-evolve Harvesters and Predators to create an arms race, with Harvesters improving evasion and Predators enhancing hunting strategies.
- **Evolving Pack Behavior**: Evolve pack-based creatures to optimize cooperative resource collection, balancing cooperation, aggression, and communication traits.
- **Leadership Emergence**: Evolve pack leaders with traits that direct group actions, optimizing pack success in resource gathering or combat.
- **Adapting to Resource Scarcity**: Evolve creatures to adapt to dynamic resource availability, switching between resource types (e.g., plants to meat) based on scarcity.
- **Seasonal Adaptation**: Evolve creatures to handle cyclic resource changes (e.g., abundant “spring” vs. scarce “winter”) through migration or storage strategies.
- **Countering Player Strategies**: Evolve creatures to adapt to player actions (e.g., weapon use, movement), creating personalized challenges like flanking or evasion.
- **Player as Ecosystem Factor**: Evolve creatures to treat players as predators or hazards, balancing resource collection with player avoidance.
- **Evolving Creature Morphology**: Evolve physical traits (e.g., size, speed, armor) alongside behaviors to create unique creature designs suited to their roles.
- **Learning from Players**: Evolve creatures to mimic successful player strategies (e.g., pathfinding) by incorporating observed behaviors into their genomes.

And ideas for "plant" like agents:

- **Evolving Resource Yield**: Evolve plants to optimize resource output (e.g., energy or health) based on traits like growth rate, size, or attractiveness to Harvesters, balancing yield with vulnerability to overharvesting.
- **Adaptive Placement**: Evolve plant spawn locations to maximize survival, with traits like preference for terrain type (e.g., near walls, open areas) or proximity to other plants, adapting to creature and player activity.
- **Defensive Mechanisms**: Evolve plants with defensive traits (e.g., toxins, thorns, or camouflage) to deter overharvesting by creatures or destruction by players, optimizing survival fitness.
- **Reproductive Strategies**: Evolve plants to spread seeds based on traits like dispersal range or germination speed, adapting to map conditions and creature harvesting patterns.
- **Symbiotic Relationships**: Evolve plants to form symbiotic bonds with specific creatures (e.g., attracting Harvesters that protect them), with traits like scent strength or mutual resource boosts.
- **Seasonal Adaptation**: Evolve plants to adjust growth cycles (e.g., fast growth in “spring,” dormancy in “winter”) based on map cycles, optimizing resource availability for creatures.
- **Resource Competition**: Evolve plants to compete for space and nutrients, with traits like root spread or light absorption, creating dense or sparse resource patches that affect creature behavior.
- **Player Interaction Response**: Evolve plants to adapt to player actions (e.g., avoiding areas frequently visited by players), with traits like regrowth speed or relocation probability.
- **Environmental Resilience**: Evolve plants to withstand map-specific hazards (e.g., lava, traps) with traits like heat resistance or rapid regrowth, ensuring persistent resource availability.
- **Dynamic Resource Types**: Evolve plants to produce varied resources (e.g., health, energy, or buffs) based on map conditions and creature needs, adapting to ecosystem demands.

Sounds like a lot of fun!

Maybe record little videos to share what happens.