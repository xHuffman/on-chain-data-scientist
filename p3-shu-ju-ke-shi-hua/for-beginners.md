# ð¨ æä¸ºé¾ä¸æ°æ®ç§å­¦å®¶ï¼ä»¥ Dune ä¸ºä¾ï¼

éè¿ç®ç­ç 4 æ­¥æåï¼å¸®å©æ¨çæ ETH é¾ä¸æ°æ®ï¼å¹¶å¼æ¸æ¥å¦ä½ä½¿ç¨ Duneè¿è¡æ¥è¯¢ã

çå®è¿äºæ¨å°æ¶è·ä»¥ä¸è¿äº
1. å¨Dune ä¸åå»ºèªå·±ççæ¿.
2. çæ ETH é¾ä¸çå®çæ°æ®ç»æã
3. æ ¹æ®æ°æ®å³å®æ¯å¦è¦å²ä¸ä¸ªé¡¹ç®ï¼å¹¶å¨å³å®å

æä»¬å°±ä»¥ 10 æåå¤§ç«ç XEN é¡¹ç®ä¸ºä¾ï¼å½æå¬å°æèçå° XEN é¡¹ç®çç¸å³ä¿¡æ¯æ¶ï¼è¿ä¸ªé¡¹ç®å·²ç»ç¸å¯¹æ¯è¾ç«ççã

è¿æ¶ï¼æé¢ä¸´ä¸ä¸ªéæ©ï¼æ¯å¦è¦å²è¿ä¸ªé¡¹ç®ï¼

å¨åç­æ¯å¦è¦å²è¿ä¸ªé¡¹ç®ä¹åï¼æéè¦é®èªå·±ï¼ææ¯æç®æ èå²ä¸æ³¢ï¼è¿æ¯ç ç©¶å¤æ­ä¸ä¸ï¼ç¡®å®æ¯å¦è¿ææºä¼åï¼åå³å®è¦ä¸è¦å²ã

è¦åç­æ¯å¦è¿ææºä¼è¿ä¸ªé®é¢ï¼æéè¦äºè§£ä¸äºé¡¹ç®çåºæ¬ä¿¡æ¯ã

æ¯å¦ï¼
1. æå¤å°äººå·²ç»åä¸äºè¿ä¸ªé¡¹ç®ï¼
2. å·²ç»åä¸çäººéç¨çä»ä¹æ ·çç­ç¥ï¼
3. æªæ¥ä¸æ®µæ¶é´åä¼æäººåä¸è¿æ¥ï¼
4. æåºè¯¥éç¨ä»ä¹æ ·çç­ç¥ï¼èç®æ´å¤§ä¸äºï¼


## ä¸ãåºç¡æ¦å¿µ
ä¸ºäºåç­ä¸é¢åä¸ªçæï¼æä»¬éè¦å¨å¤ä¸äºåºç¡çæ¦å¿µã

æºè½åçº¦ï¼
æ¯ä»ä¹ï¼
* æ¯ETH é¾ä¸çä¸ä¸²å°åã
* æ¯ä¸å ä»£ç ï¼æ§è¡å·ä½çæ¹æ³ï¼å®ç°å·ä½çåè½ã

ä¸æ¯ä»ä¹ï¼
åæä»¬èªå·± ETH æ¶æ¬¾çå°ååºå«ï¼
åçº¦éé¢åæ¬æååå¥½çä»£ç æ¹æ³ï¼å·ä½åç§åºåé¾åºç¡è¯¾ç¨ï¼ã

å·ä½å°XEN è¿ä¸ªé¡¹ç®ï¼ä»çæºè½åçº¦å°åï¼å°±æ¯é¡µé¢å³ä¸è§ 0xå¼å¤´çä¸ä¸²å°åã


## äºãå¦ä½åç­è¦é®çé®é¢ï¼


## ä¸ãå»ºç«æ¥è¯¢


æ¥è¯¢ XEN é¡¹ç®çæ»ç¨æ·æ°é

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

## åãè¿è¡å¯è§å


ä¸ºä»ä¹ä½ è¦æä¸ºé¾ä¸æ°æ®ç§å­¦å®¶ï¼
*  
*  æ°æ®ç»ä½ ä¸åçéæ¬è´¨çç¼ç



**Good to know:** depending on the product you're building, it can be useful to explicitly document use cases. Got a product that can be used by a bunch of people in different ways? Maybe consider splitting it out!


## Figma Integrations
