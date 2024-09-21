+++
title = "3. CORS Proxy URL"
weight = 3
+++


Since our [Notion to Markdown website](https://notion-to-md.bamidev.com/) is 100% hosted on GitHub Pages, we **WILL NOT** store any of your information. Everything stays in your browser, and all requests will be made directly from it.


However, Notion’s CORS policy restricts these kinds of requests . We’ll use a **CORS Proxy** as a middleman to bypass this.


To use the **free CORS Proxy**, we input our free CORS Proxy URL.


(Optional) For convenience, I’ve added a proxy note. Clicking it will automatically fill in [`https://cors-anywhere.herokuapp.com/`](https://cors-anywhere.herokuapp.com/) and open a new tab.


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/8b3be9f1-97c4-418b-bbaa-d8da15555e46/99d4f8db-3d4f-4395-9600-c83491f6274d/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45HZZMZUHI%2F20240921%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20240921T010957Z&X-Amz-Expires=3600&X-Amz-Signature=3c3dc59c0cd233f551e3a0ac36e9d9234b5eb6a4f8c698008c808b83b4dbc9ce&X-Amz-SignedHeaders=host&x-id=GetObject)


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/8b3be9f1-97c4-418b-bbaa-d8da15555e46/d4c2fb94-bee2-4f02-b8a7-909a80dbc0dd/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45HZZMZUHI%2F20240921%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20240921T010957Z&X-Amz-Expires=3600&X-Amz-Signature=f1f5109d05ae2985015f62ca4934ca11700b9d06d26b9942fa648e660ce496df&X-Amz-SignedHeaders=host&x-id=GetObject)


On the new tab, click **"Request temporary access"** to allow the use of this free CORS Proxy.


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/8b3be9f1-97c4-418b-bbaa-d8da15555e46/414eb1b3-945d-4ac1-9acb-5e473ab5c781/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45HZZMZUHI%2F20240921%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20240921T010957Z&X-Amz-Expires=3600&X-Amz-Signature=26bcf2ba3234894d1450efaef48ba43a7d89b3b8a1b2106bb79289a0acab86b7&X-Amz-SignedHeaders=host&x-id=GetObject)


**DISCLAIMER:** 

1. **A CORS Proxy acts as a middleman**, meaning it can read all your requests and response credentials. Therefore, it is important to choose a trusted CORS Proxy or build your own for the highest level of security.
2. In this tutorial, we’ll use a **Free CORS Proxy URL** for convenience, please be fully aware of the **risk of exposing our NOTION credentials** (both requests and responses).
3. But to be honest, I’m not too concerned because we have already **limited our Notion token permissions** to **Read content** with **No user information**. Additionally, the **Notion URL is for a published page** (which is already public). So even in the worst-case scenario where we lose our **Notion credentials**, a hacker **cannot update or delete anything**—they would only be able to read the public and selected pages.
4. If you're still worried about security, you can use **your own CORS Proxy URL** or a **trusted CORS Proxy URL**. You are very welcome to do so.
5. The only time we use this **CORS Proxy** is when you **click "Convert"** to retrieve the Notion page information. **No other features or actions** will use this CORS Proxy.

	![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/8b3be9f1-97c4-418b-bbaa-d8da15555e46/93b315cf-572c-4d78-b3bb-d1d225239063/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45HZZMZUHI%2F20240921%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20240921T011000Z&X-Amz-Expires=3600&X-Amz-Signature=d4c80f10950931cae128b202924d5b69c8f85737d4cb8e67d45d52f4cf94c3aa&X-Amz-SignedHeaders=host&x-id=GetObject)


