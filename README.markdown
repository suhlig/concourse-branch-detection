# Spike on Concourse Branch Detection

1. Create a `secrets.yml`:

    ```yaml
    github:
      access_token: t0tallys3cret
    ```

1. Set the pipeline with

    ```command
    $ fly set-pipeline \
      --pipeline branch-detection \
      --config pipelines/branch-detection.yml \
      --load-vars-from <(ansible-vault view secrets.yml)
    ```
