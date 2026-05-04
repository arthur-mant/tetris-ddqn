This repository implements a Tetris playing agent based on Double Deep Q-Learning. It provides 2 main contributions: the utilization of post-states to reduce the size of the domain of the quality function, and a variable reward function, that changes through the training to force the agent to use more efficient strategies.

#Training

To train a new network, run:

`python main.py -n`

In case you wish to use an already trained network as the basis for training, run (DEPRECATED)

`python main.py "network_file"`

Where `"network_file"` is the file that contains the weights of the chosen network

The trained network's filename is defined on `main.py`, and will be saved on the `saved_nns/` directory. The graphs generated during training will have the same filename, concatenated with the graph's subject, and will be saved on the `graphs/` directory.

#Testing
To test a network, run:

`python gameplay.py "network_file"`

This will make the agent a number of games and will return it's stats. If you wish to see the agent playing, include the flag `-s`, which will open an GUI showing every move made.

#Avaliable trained networks

There are 4 trained networks, each of them has a different implementation of the reward function:

- The `main` branch (and the `original-continuous` branch, from which the main branch is a copy of) implements a variable reward function that changes continuously. This is the best performing agent and, therefore, was chosen as the main one. The file containing the trained network is `trained_nns/continuous.h5`.


- The `original-discrete` branch implements a variable reward function that changes discretely. The file containing the trained network is `trained_nns/discrete.h5`.


- The `test-original` branch implements a fixed reward function. The file containing the trained network is `trained_nns/fixo.h5`.

- The `score-real` branch implements a reward function directly derived from the game's scoring system, not using our proposed reward function. The file containing the trained network is `trained_nns/real.h5`.

