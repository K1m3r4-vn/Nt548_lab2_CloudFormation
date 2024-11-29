Lab2
NT548 CloudFormation Guide:
1. git clone the project
2. Create a CodeCommit repo in AWS console named 'Group13-Nt548'.
3. Clone the CodeCommit repo to your computer.
4. Push this repo to CodeCommit
git add .
git commit -m 'first commit'
git push
5. Create a CodeBuild project:
   - Name: CloudformationBuild
   - Source: AWS CodeCommit
   - Repository: Group21-Lab2. Branch: main
   - Click Use buildspec file 'buildspec.yml'
6.Create a CodePipeline:
  - Name: Group21-Pipeline
  - Source stage: add the AWS CodeCommit you just created
  - Build stage: add the AWS CodeBuild you just created
  - Deploy stage:
      + Deploy provider: AWS Cloudformation
      + Input artifact: BuildArtifact
      + Action mode: Create or update stack
      + Stack name: Group13-Stack
      + Template: Artifact name: BuildArtifact; Filename: main.yaml
You will have your own pipeline here.
