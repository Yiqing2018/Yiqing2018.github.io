---
layout:     post
title:      Convert Decimal digit to Binary digit in Java
subtitle:   JavaProgramming 
date:       2018-05-17
author:     Yiqing
header-img: img/post-bg-c.jpg
catalog: true
tags:
    - Java

---

>Programming learning



### Approach1 Mathematic thinking
![How Randomness Rules Our Lives](https://ws4.sinaimg.cn/large/006tNc79gy1fsthslcb9aj309106x0sm.jpg){:height="50%" width="50%"}

### Approach2 Shift Operation 
```
		int n=19;
		for(int i=31;i>=0;i--){  //here we set i=31 because int is 32-bit
			System.out.print( n>>>i&1 );
		}
```

### Approach3 API
<pre><code> String result=Integer.toBinaryString(n); </code></pre>

