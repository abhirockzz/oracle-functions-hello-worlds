# Oracle Functions Ruby Hello World

Create and deploy your first Ruby function on Oracle Functions.

Start by logging in to your development environment as an Oracle Functions developer

## Pre-requiste: Create an application

Start by [creating an application](create-application.md)

## Bootstrap a Ruby function

 Create a Ruby function by entering:

`fn init --runtime ruby helloworld-func-ruby`

A directory called `helloworld-func-ruby` is created, containing:

- the `func.rb` file which contains your actual Ruby function
- a function definition file called `func.yaml`
- `Gemfile` which specifies all the dependencies for your Ruby function.

## Deploy your function

Change directory to the `helloworld-func-ruby` directory created in the previous step:

`cd helloworld-func-ruby`

Enter the following single command to build the function and its dependencies as a Docker image called `helloworld-func-ruby`, push the image to the specified Docker registry, and deploy the function to Oracle Functions:

`fn -v deploy --app helloworld-app`

## Invoke your function

Invoke the `helloworld-func-ruby` function by entering:

`fn invoke helloworld-app helloworld-func-ruby`

The `{"message":"Hello World!"}` output is displayed.

You can also pass in a payload to invoke the function:

`echo -n '{"name":"Bob"}' | fn invoke helloworld-app helloworld-func-ruby`

The `{"message":"Hello Bob!"}` output is displayed.

Congratulations! You've just created, deployed, and invoked your first Ruby function using Oracle Functions!
