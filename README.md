Plugins:
========
- LinkedIn SSO for Docker with env variables

## Deployment:

1. Add plugin to your hooks in app.yml

    ```
    hooks:
        after_code:
            - exec:
                cd: $home/plugins
                cmd:
                    - mkdir -p plugins
                    - git clone https://github.com/discourse/docker_manager.git
                    - git clone https://github.com/rangedsp/discourse-plugins.git
    ```

2. Add your LinkedIn Client API Key to your environmental variables

    ```
    env:
        LINKEDIN\_CLIENT\_ID: xxxxxx
        LINKEDIN\_CLIENT\_SECRET: xxxxx
    ```
    
3. Rebuild container

    ```
        ./launcher rebuild app
    ```

*Original Author: Jess Portnoy, Kaltura, Inc.*
