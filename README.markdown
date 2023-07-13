# Spike on Concourse Branch Detection

> Beware, this is a spike. If you want to use this for real, turn the branch detection into a proper resource so that pipelines can trigger on branches added or removed (instead of polling via job).

1. Create a `secrets.yml`:

    ```yaml
    github:
      access_token: t0tallys3cret
    ```

1. Set the pipeline with

    ```command
    $ fly set-pipeline \
      --pipeline branch-detection \
      --config pipelines/branch-detector.yml \
      --load-vars-from <(ansible-vault view secrets.yml)
    ```
