# Infrastructure

Central Repository for AWS Sensei Infrastructure in this workspace.

## CI/CD Projects

- AWS Sensei Blog CI/CD: Modular SAM + CodePipeline stack for the blog, including Hugo build/deploy. See `aws-sensei-blog-cicd/README.md`.
- AWS Sensei Flashcards CI/CD: Modular SAM + CodePipeline stack for the flashcard app, including Flutter build/deploy. See `aws-sensei-flashcards-cicd/README.md`.
- AWS Sensei Spotify CI/CD: Modular SAM + CodePipeline stack for the Spotify backend infrastructure. See `aws-sensei-spotify-cicd/README.md`.

## Common layout

Each project follows the same multi-template SAM structure with a `master.yaml` entrypoint, nested `foundation/`, `build/`, and `pipeline/` templates, plus a dedicated project README for deployment details.
