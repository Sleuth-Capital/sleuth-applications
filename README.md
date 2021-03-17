# applications_container

This is a template repository for a new Sleuth AI service.
Use the following steps to adapt it to a new container.

1. Clone this repository
2. Run ``poetry install``
3. Run ``poetry run rename``
4. Create new repository on gitlab and run
    ```
    git init
    git remote remove origin
    git remote add origin https://gitlab.com/sleuth-ai/applications_container.git
    git push -u origin --all
    git push -u origin --tags
    ```

*Make sure to make the service available at* **``/applications_container``** *in production!*

## Development
````
poetry install
export DISABLE_OAUTH="True"
poetry run container
````
## Test
````
poetry install
poetry run pytest
````
## Release
````
poetry run bumpversion [major|minor|patch]
git push --tags
````
## Container
````
docker build -t applications_container .
docker run -p 9090:9090 applications_container
````
