+++
title = "2. Process Notion to Github Repo"
weight = 2
+++


Open [Notion to MD](https://notion-to-md.bamidev.com/), fill in the information, and proceed to the step where you click "Parse into Hugo Relearn".


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/8b3be9f1-97c4-418b-bbaa-d8da15555e46/7f5b08f1-9a0c-4573-9688-4753f5316016/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45HZZMZUHI%2F20240921%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20240921T010957Z&X-Amz-Expires=3600&X-Amz-Signature=5a490aa42f102dbcf09c1e830c9a55fa8495413a6f0fb653edb32e86e8b93d2f&X-Amz-SignedHeaders=host&x-id=GetObject)


It will show the “Chapter Structure” table, where we can preview and check if the Git repository structure matches the headings inside our Notion page.


The repository structure will follow two simple rules:

1. **Header H1** will always create a new directory.
2. **Headers with larger numbers** will always be inside the nearest smaller header. For example, **H2** will be inside **H1**.

Try not to overthink this structure for now. Just follow the trial-and-error principle, and we’ll be fine.


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/8b3be9f1-97c4-418b-bbaa-d8da15555e46/734d2bdb-4d95-45fe-9301-1ca56f6bbc81/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45HZZMZUHI%2F20240921%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20240921T010957Z&X-Amz-Expires=3600&X-Amz-Signature=8c0331a65c52349f7f3505dc22aef5efee7a6a912f164d46f3b7a9ef510acd5b&X-Amz-SignedHeaders=host&x-id=GetObject)


Fill in the Sync to GitHub information and start the “Sync to GitHub” process.


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/8b3be9f1-97c4-418b-bbaa-d8da15555e46/dd0f7f6a-7400-49c9-8d40-2cb87782831c/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45HZZMZUHI%2F20240921%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20240921T010957Z&X-Amz-Expires=3600&X-Amz-Signature=3562ec0cb08a9760a6fa6cc028fae2e0dc5b62273b6c2ed90044c5ce1bba1560&X-Amz-SignedHeaders=host&x-id=GetObject)


(Troubleshooter) This error may occur if you use a brand-new repository without any initialized commits.


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/8b3be9f1-97c4-418b-bbaa-d8da15555e46/9ca18a8d-d4cd-42de-9754-434db4afccc0/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45HZZMZUHI%2F20240921%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20240921T010957Z&X-Amz-Expires=3600&X-Amz-Signature=7623f0f6880acf7b60e9867c17634100ac5ce5b31f0cfd01bbcbf6f0fea3a71a&X-Amz-SignedHeaders=host&x-id=GetObject)


The solution is to initialize the Git repository. Just use the simple git instruction, and that should be enough.


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/8b3be9f1-97c4-418b-bbaa-d8da15555e46/3acd0bc4-c842-4f67-9653-0918fac0c598/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45HZZMZUHI%2F20240921%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20240921T010957Z&X-Amz-Expires=3600&X-Amz-Signature=fb69fe8f4f0eef0496b7534093148e45d7b6bc1c8c399c9514767c845d647f6d&X-Amz-SignedHeaders=host&x-id=GetObject)


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/8b3be9f1-97c4-418b-bbaa-d8da15555e46/24114125-4a39-44a5-9902-95060bc2a9df/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45HZZMZUHI%2F20240921%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20240921T010957Z&X-Amz-Expires=3600&X-Amz-Signature=c7a539b296b6d5b5b949bc00e1d46781a8c053dc3005831f8a6efd5d283ecfdf&X-Amz-SignedHeaders=host&x-id=GetObject)


If everything is working correctly, the process will start and scroll through each step. When it’s complete, you will see this message.


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/8b3be9f1-97c4-418b-bbaa-d8da15555e46/cf47aa4a-a10a-408c-9682-35a9652f2bba/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45HZZMZUHI%2F20240921%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20240921T010957Z&X-Amz-Expires=3600&X-Amz-Signature=894b9ae662c55c190adafd7720c46b2d3b66196d622a26576e32260b8a5831bc&X-Amz-SignedHeaders=host&x-id=GetObject)


Double-check the GitHub repository. You should see the `content` directory (holding contents) and the `static` directory (holding images) created, indicating success.


![image.png](https://prod-files-secure.s3.us-west-2.amazonaws.com/8b3be9f1-97c4-418b-bbaa-d8da15555e46/90005ad0-9a69-462e-a9ce-0fee77ab147e/image.png?X-Amz-Algorithm=AWS4-HMAC-SHA256&X-Amz-Content-Sha256=UNSIGNED-PAYLOAD&X-Amz-Credential=AKIAT73L2G45HZZMZUHI%2F20240921%2Fus-west-2%2Fs3%2Faws4_request&X-Amz-Date=20240921T010957Z&X-Amz-Expires=3600&X-Amz-Signature=7768367adce94e69884aa542fcae89a343b9b0248029a820a6b9a52d814f6c7c&X-Amz-SignedHeaders=host&x-id=GetObject)


