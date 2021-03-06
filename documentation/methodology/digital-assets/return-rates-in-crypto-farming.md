---
description: A basic introduction to the role of pool rates in crypto asset farming
---

# Return Rates in Crypto Farming

Decentralized Finance \(DeFi\) has attracted a lot of attention in the recent years. A rather new and hot topic inside the world of DeFi is yield farming, which allows to earn passive income on token holdings using various investment strategies coded into smart contracts.  
There is an ever growing number of products labeled as yield farming. Many of those are advertised with an APY \(Annual Percentage Yield\) rate.  
We emphasize that in this context, the term APY is to be read with caution. In classical finance, it refers to the annual rate of return in an investment and is a predefined rate. Hence, an investor can be sure to obtain the corresponding interest in their investment. However, most farming products heavily rely on the investment strategy in volatile crypto markets. In contrast to APYs in lending and borrowing, rates published in farming are either APYs of past periods or projections based on past data.

Due to the complexity of this topic, our first step consists of publishing the pool rates as emitted in the smart contracts of various farming products. The basic idea of pool rates is pretty straightforward and can be understood as follows. Consider a farming pool of token $$X$$ and let $$A_X(i)$$ be the amount of token $$X$$ at block number $$i$$. Assume, farming starts at block number $$i_0$$, then we have the following equation

$$
A_X(i)=A_X(i_0)\cdot p_X(i)
$$

where $$p_X(i)$$ is the price corresponding to the pool of token $$X$$ . Initially, $$i=i_0$$ and hence $$p_X(i_0)=1$$. Motivated by this fact, we write

$$
p_X(i)=1+r_X(i).
$$

Here, $$r_X(i)$$ is the _pool rate_ corresponding to the pool of token $$X$$ .

As the initial supply $$A_X(i_0)$$ is constant, the price depends on the evolution of $$A_X(i)$$ and hence on the pool's investment strategy - if the number of tokens $$A_X(i)$$ increases with block number $$i$$ , so will the pool rate. In other words, the return of an investment is determined by the change in the pool rate.  
The following example illustrates the relation between the pool rate and the return on an investment. We remark that in general, as for interest rates in traditional finance, differences of pool rates can be used for simple interest calculation as well as for compounded interest.

Example:  
Assume an investor puts an amount of $$100$$ tokens $$X$$ into an empty pool at block number $$10000000$$ . With the notation from above this means $$i_0=10000000$$ and $$A_X(10000000)=100$$. Further assume that $$1000$$ blocks later, the investment strategy has increased the number of tokens in the pool to $$101$$ tokens, so $$A_X(10001000)=101$$. The return on the initial investment after these $$1000$$ blocks can be obtained by the difference of the pool rates at blocks $$10001000$$ and $$10000000$$ respectively. Indeed, we have $$p_X(10000000)=1$$ and thus $$r_X(10000000)=0$$. By the above equation for $$A_X(i)$$ we have $$p_X(10001000)=\frac{A_X(10001000)}{A_X(10000000)}=\frac{101}{100}$$ and thus $$r_X(10001000)=\frac{1}{100}$$. This yields

$$
r_X(10001000)-r_X(10000000)=\frac{1}{100}
$$

and hence a return rate of 1%.

Again, whether the amount of tokens in a pool increases or decreases solely depends on the investment strategy. The return rates for past time ranges can be computed by considering pool rate differences, such as done in the example above. In order to estimate future return rates, one can apply mathematical methods which allow for the estimation of future values based on past data. The simplest way of doing so is to fit a linear function to the data, which is also known under the name of \(linear\) regression. However, for most cases, such simple models do not yield good results for bigger time ranges. Mathematicians have tackled such problems since a long time and there is a wide range of techniques available. Nowadays, many of these are used under the name of _machine learning_.

