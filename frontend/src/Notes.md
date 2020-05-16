# Notes

Remember you can override the default command simply by adding the command you want to run instead of the default. so for example

docker run -it 381c6cf59092 npm run test

this will do interactive, sure. but the key point is that you can write a dockerfile that builds and runs the code by default, but tweak it for other purposes, like running tests.

when it comes to reusing what we're already done. one approach is to override the defaults, and another is to reuse an already existing container with a new command instead(npm run test for example). But it's quite a lot of steps to start up a container, get its id, and then reuse with an alternate command. another approach is to just create another service in your compose file.

Problem with adding to the compose file is that you get output from both main app and tests in the same output from docker compose, and there's no way to interact with just one!

We can use docker attach to connect to a set place, but that doesn't solve the problem because what's actually running is a separate process started by node(for tests).

Multi stage builds. once for building; one for running!

Applying it to our functions

One stage to publish the thing.

One stage to deploy the function.

Output gives us a function folder ready to be uploaded!
