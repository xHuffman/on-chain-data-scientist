# 🎨 成为链上数据科学家（以 Dune 为例）

通过简短的 4 步指南，帮助您熟悉 ETH 链上数据，并弄清楚如何使用 Dune进行查询。

看完这些您将收获以下这些
1. 在Dune 上创建自己的看板.
2. 熟悉 ETH 链上真实的数据结构。
3. 根据数据决定是否要冲一个项目，并在决定后

我们就以 10 月初大火的 XEN 项目为例，当我听到或者看到 XEN 项目的相关信息时，这个项目已经相对比较火爆的。

这时，我面临一个选择，是否要冲这个项目？

在回答是否要冲这个项目之前，我需要问自己，我是打算无脑冲一波，还是研究判断一下，确定是否还有机会后，再决定要不要冲。

要回答是否还有机会这个问题，我需要了解一些项目的基本信息。

比如：
1. 有多少人已经参与了这个项目？
2. 已经参与的人采用的什么样的策略？
3. 未来一段时间又会有人参与进来？
4. 我应该采用什么样的策略，胜算更大一些？


## 一、基础概念
为了回答上面四个疑惑，我们需要储备一些基础的概念。

智能合约：
是什么？
* 是ETH 链上的一串地址。
* 是一堆代码，执行具体的方法，实现具体的功能。

不是什么？
和我们自己 ETH 收款的地址区别，
合约里面包括提前写好的代码方法（具体参照区块链基础课程）。

具体到XEN 这个项目，他的智能合约地址，就是页面右下角 0x开头的一串地址。


## 二、如何回答要问的问题？


## 三、建立查询


查询 XEN 项目的总用户数量

```sql
-- {{refresh}}
with claimed as (
    select 
        date_trunc('hour', block_time) as dt, 
        count(*) as nums 
    from ethereum.transactions 
    where to = lower('0x06450dEe7FD2Fb8E39061434BAbCFC05599a6Fb8') 
    and block_time>'2022-10-07'
    and left(data, 10)='0x9ff054df' -- claimRank
    group by 1
)
select * , (sum(nums)  over(order by dt)) as total_claimed from claimed
```

## 四、进行可视化


为什么你要成为链上数据科学家？
*  
*  数据给你一双看透本质的眼睛



**Good to know:** depending on the product you're building, it can be useful to explicitly document use cases. Got a product that can be used by a bunch of people in different ways? Maybe consider splitting it out!


## Figma Integrations
