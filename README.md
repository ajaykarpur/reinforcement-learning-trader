# DeepBubble
Trading altcoins using deep reinforcement learning.

## Strategy
Start with a small-cap, low-volume altcoin market. First, train it with paper trading. Next, let it start trading with real money. Once the agent has learned to successfully make money when trading with real money, move it up to the next market (by market cap or volume).

## Implementation Plan
- [ ] Uses ccxt library for trades.
- [ ] use OpenAI gym (implement the Env interface) for the exchange.
	- [ ] For simplicity, constrain trades to just the Bittrex exchange (ie. do not allow for an arbitrage strategy).
	- [ ] Inputs to the system are the order book (including bid, ask, spread) and the price ticker.
	- [ ] Outputs are {do nothing, place buy order, place sell order, cancel open order}. Buy and sell orders also have floats for price and quantity.
	- [ ] The score is the total value of holdings, using BTC as the reference. Calculate the score as follows: (BTC in BTC wallet) + (amount of ALT held * value of ALT in BTC)
- [ ] Use Keras with a Tensorflow backend for the agent (deep recurrent Q-network).

## Resources

http://www.wildml.com/2018/02/introduction-to-learning-to-trade-with-reinforcement-learning/

### trading
- https://github.com/kroitor/ccxt
- https://github.com/kroitor/ccxt/wiki/Manual

### deep reinforcement learning
- https://github.com/eriklindernoren/ML-From-Scratch/blob/master/mlfromscratch/reinforcement_learning/deep_q_network.py
- https://github.com/matthiasplappert/keras-rl
- https://github.com/rlcode/reinforcement-learning
- https://github.com/devsisters/DQN-tensorflow
- https://github.com/carpedm20/deep-rl-tensorflow
- https://github.com/awjuliani/DeepRL-Agents
- https://github.com/openai/gym/tree/master/gym/envs
- https://github.com/openai/gym/wiki/Environments

## References

### must-read
- https://deepmind.com/blog/deep-reinforcement-learning/
- https://www.intelnervana.com/demystifying-deep-reinforcement-learning/
- http://videolectures.net/rldm2015_silver_reinforcement_learning/
- https://medium.com/emergent-future/simple-reinforcement-learning-with-tensorflow-part-6-partial-observability-and-deep-recurrent-q-68463e9aeefc
- https://arxiv.org/abs/1507.06527
- https://github.com/awjuliani/DeepRL-Agents/blob/master/Deep-Recurrent-Q-Network.ipynb

### relevant
- https://github.com/mhauskn/dqn/tree/recurrent
- https://arxiv.org/abs/1506.08941
- http://rll.berkeley.edu/deeprlcourse/
- https://arxiv.org/abs/1112.2397
- https://arxiv.org/abs/1701.07274
- https://arxiv.org/abs/1601.01987
- https://arxiv.org/abs/1509.06461
- https://arxiv.org/abs/1511.05952
- https://arxiv.org/abs/1511.06581
- https://arxiv.org/abs/1509.02971
- https://www.cs.toronto.edu/~vmnih/docs/dqn.pdf
- http://www.davidqiu.com:8888/research/nature14236.pdf

### tangentially relevant
- https://en.wikipedia.org/wiki/High-frequency_trading
- https://en.wikipedia.org/wiki/Market_microstructure
- https://en.wikipedia.org/wiki/Stochastic_control
- https://cs224d.stanford.edu/notebooks/vanishing_grad_example.html
- https://www.quora.com/Is-anyone-making-money-by-using-deep-learning-in-trading
- http://www.investopedia.com/articles/trading/06/neuralnetworks.asp
- https://www.reddit.com/r/algotrading/
- https://arxiv.org/abs/1705.09851
- https://www.cis.upenn.edu/~mkearns/papers/KearnsNevmyvakaHFTRiskBooks.pdf
- https://www.quantopian.com/posts/applying-deep-learning-to-enhance-momentum-trading-strategies-in-stocks-45-dot-93-percent-annual-return
- https://www.infoq.com/podcasts/eric-horesnyi-ai-hft
- https://medium.com/@alexrachnog/neural-networks-for-algorithmic-trading-part-one-simple-time-series-forecasting-f992daa1045a
- https://www.qplum.co/investing-library/81/machine-learning-in-high-frequency-algorithmic-trading
- http://www.turingfinance.com/misconceptions-about-neural-networks/
