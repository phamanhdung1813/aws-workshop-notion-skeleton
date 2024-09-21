+++
title = "4. Setup GitHub Action"
weight = 4
+++


To run GitHub Action for automatic CI/CD, we need to set up a workflow file.


I’ve already configured this in my skeleton repo, so your repo's workflow file should work correctly without any changes.


I also fixed the bug where the **custom domain** would be lost when deploying with GitHub Action.


You can find the [latest file here](https://github.com/heo001997/aws-workshop-notion-to-md/blob/main/.github/workflows/hugo.yaml).


Add this file to your project at the path `.github/workflows/hugo.yaml`. Once done, your GitHub Action is ready.


