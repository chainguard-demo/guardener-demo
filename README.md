# Guardener Demo

This is a demo of the Guardener. Please follow the script in DEMO.md.

[Recording](https://drive.google.com/file/d/11IiklC_bNzjw37B8inbPB7g-H86SSXcG/view?usp=sharing)

# Note
The Guardener is an AI tool that migrates customers to Chainguard trusted artifacts. Today it supports Chainguard Actions and Chaingaurd Containers. This demo focuses on migrating customer Dockerfiles to use Chainguard Images (cgr.dev/chainguard/chainguard-base). It uses Claude as the migration engine — iteratively converting instructions, building images, comparing results, and fixing issues until the Dockerfile builds a Chainguard-based image.
This allows prospects and customers to convert their Dockerfiles with ease, and optimize them to align with best practices.

For the demo for migration from GitHub Actions to Chainguard Actions using the Guardener GitHub app, go to [actions-and-guardener-gh-app-demo](github.com/chainguard-demo/actions-and-guardener-gh-app-demo).

## Getting Started
1. Create a fork of this repository
2. Generate a GitHub IAM identity locally using chainctl by running: `chainctl iam identities create github gh --github-repo={YOUR_REPO} --github-ref=refs/heads/main --role=owner --github-audience=https://github.com/{GITHUB_USER} --parent={YOUR_ORGNAME/ID}`
3. Create a secret in Settings > Actions called `GUARDENER_DEMO_CHAINCTL_IDENTITY` and assign it the value above.

## Running CI
1. Access the pipeline in the Actions section
2. Select `Run the Guardener` and input your group ID, desired image tag name, and your repo namespace
- Note: Ensure that under Settings > Actions > General > Workflow permissions, `Read and write permissions` are enabled
- Note: Ensure that under Your Profile > Packages > guardener-demo > Package Settings > Manage Actions access your repo is listed with write access. If not, add it.
