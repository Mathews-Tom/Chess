# Chess

## Strategies

When it comes to building any board game engine, there are multiple strategies:

- Reinforcement Learning
- Minimax
- ML model trained on human knowledge

### My Strategy is Simple

I opted for an hybrid of the second and third strategies: As a Data scientist, I am fond of working with large datasets and machine learning models. Also, despite being a little slower, Minimax is a quite reliable algorithm and does a good job at capturing enemy pieces. Reinforcement learning is simply too complex.

- Using machine learning model, the engine will dismiss 50% of the possible moves given a board. It does so by finding the probability of a move being a ‘good move’. All the moves are sorted according to this probability and only the 50th percentile remains.
- The engine will perform the Minimax algorithm on the remaining moves. Depending on the complexity of the board, the search tree will go to a certain depth.

## Data

In order to make accurate predictions, we need a lot of data. For this project, I will be using a dataset that I found on [Kaggle](https://www.kaggle.com/datasets/liury123/chess-game-from-12-top-players). This dataset is a collection of thousands of games played by chess grand masters in the .pgn format (portable game notation).

The next step is to extract all the moves from all the games and label them as good or bad. For this project, I will be using only a few of the player data from the original dataset.

In my opinion, a ‘good move’ is a move that the winner played at some point during the game. A ‘bad move’ is a legal move that the winner chose not to play.

The [python script](Script/process_data.py) got the job done leaving me with a brand new .csv dataset.