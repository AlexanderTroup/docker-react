docker run -it -p 3000:3000 CONTAINER_ID

      web:
        stdin_open: true

        this is needed due to a recent create react app change.
-------------------
-------------------
-------------------
lecture 100 travis keys
Travis Keys Update

In the upcoming lecture we will be adding our AWS variables to the deploy script of the .travis.yml file. There is a slight change that will be required, otherwise you will get an error when Travis attempts to run your code.

The code will now look like this:

    access_key_id: $AWS_ACCESS_KEY
    secret_access_key: $AWS_SECRET_KEY

-------------------
-------------------
-------------------
