+++
title = "1. Setup GitHub Personal Account Token"
weight = 1
+++


Open the [PAT management page](https://github.com/settings/tokens?type=beta), and go to Generate new token (may require re-authentication).


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/8b3be9f1-97c4-418b-bbaa-d8da15555e46/0c3bc2b7-e9ba-46d5-a4d6-cac299316d2c/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45HZZMZUHI%2F20240921%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20240921T010957Z&X-Amz-Expires=3600&X-Amz-Signature=31463e35a11e5a4ec2f9ebe1e94bd57c0209bbae1cf922a8ceadccf51aa0daca&X-Amz-SignedHeaders=host&x-id=GetObject)


Fill in the necessary information and **only allow this token to access some repositories**.


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/8b3be9f1-97c4-418b-bbaa-d8da15555e46/c0891c9f-2f78-4857-a718-1d015596639c/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45HZZMZUHI%2F20240921%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20240921T010957Z&X-Amz-Expires=3600&X-Amz-Signature=ed66ad07446415ee8eab3277e257bd8f33186cd25f0bc23cb33efa3872d735fb&X-Amz-SignedHeaders=host&x-id=GetObject)


Repository access → only some repositories → Select `sample-notion-to-repo` repository.


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/8b3be9f1-97c4-418b-bbaa-d8da15555e46/5e2b0d5e-8ca7-4f94-be9f-f24c6d96a07f/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45HZZMZUHI%2F20240921%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20240921T010957Z&X-Amz-Expires=3600&X-Amz-Signature=5ec24e293d483dc5a91862560e25366baf88282738d58afed100b08d702b2f34&X-Amz-SignedHeaders=host&x-id=GetObject)


It looks like this when the desired repository is selected.


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/8b3be9f1-97c4-418b-bbaa-d8da15555e46/d38f6984-af3b-4949-83fa-6dece68a309f/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45HZZMZUHI%2F20240921%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20240921T010957Z&X-Amz-Expires=3600&X-Amz-Signature=229ab2d59634ad5d3b667fd16babfd02f71bb00dfc8a7e3caed6908885a077a4&X-Amz-SignedHeaders=host&x-id=GetObject)


We **don’t need** any **Account permissions**, any only **allow these** **Repository permissions**.


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/8b3be9f1-97c4-418b-bbaa-d8da15555e46/9a8987d3-3feb-4b45-8a99-fa0871437113/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45HZZMZUHI%2F20240921%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20240921T010957Z&X-Amz-Expires=3600&X-Amz-Signature=3c0604c6922d6bc35906bf0d00db56994dfeafd3880b8ddaae27b1c5d0de319a&X-Amz-SignedHeaders=host&x-id=GetObject)


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/8b3be9f1-97c4-418b-bbaa-d8da15555e46/3bd47b0f-8256-4b75-9e2d-a5b2a413842c/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45HZZMZUHI%2F20240921%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20240921T010957Z&X-Amz-Expires=3600&X-Amz-Signature=b219896c1a707803831c430a9f601c67a5495a0ec598610b28f0b0c4fd9c162d&X-Amz-SignedHeaders=host&x-id=GetObject)


Check the permissions overview last time, generate token.


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/8b3be9f1-97c4-418b-bbaa-d8da15555e46/9d877ade-6894-41aa-93ad-39d41bae56d1/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45HZZMZUHI%2F20240921%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20240921T010957Z&X-Amz-Expires=3600&X-Amz-Signature=b9c6ec53f4cade81abe533125816b4475d1534cd11895214e8efd7c78e950cb6&X-Amz-SignedHeaders=host&x-id=GetObject)


**Please copy this PAT and save it carefully**, that note is not kidding.


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/8b3be9f1-97c4-418b-bbaa-d8da15555e46/cbbda674-f5b2-426b-9a60-ea2fc6be21e5/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45HZZMZUHI%2F20240921%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20240921T010957Z&X-Amz-Expires=3600&X-Amz-Signature=3512ce39adf4a66e0508c83b92975ea51025bdd7b3cb95dd7128d2af6930b123&X-Amz-SignedHeaders=host&x-id=GetObject)


