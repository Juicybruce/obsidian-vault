This is managed container registry service  (managed DockerHub)

Each AWS account is given a public and private registry
- within each registry you can have many repositories
- each repo can have many images
- images can have several tags
![[Pasted image 20250123162628.webp]]

ECR has:
- integration with IAM for permissions
- iamge scaning, basic and enhanced
- real-time metrics for CloudWatch
- API actions are piped into cloud trail
- Events into event bridge
- replication of images cross region and account