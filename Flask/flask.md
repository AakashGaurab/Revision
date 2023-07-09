## Flask Developer 
# What is Flask?
- Flask is a microweb framework that provides an API to build up web applications. Flask’s framework is also easier to learn because of its diversified working style. Flask is based on the WSGI (Web Server Gateway Interface) toolkit and the Jinja2 template engine. It is very flexible to implement a simple web application. Also, Flask provides visual debugging, which gives more control over the component.
  Importances
- Lightweight and minimalistic: Flask is a lightweight web framework with minimal dependencies on external libraries. It allows developers to start small and scale up to complex applications as needed. This simplicity makes it easier to understand and learn, especially for beginners in web development.
- Template engine and easy integration: Flask comes with a built-in template engine that allows developers to use the same user interface for multiple pages. This feature simplifies the development process and improves code reusability. Flask also integrates well with other technologies and libraries, making it easier to add external features and functionalities to the application.
- Integrated support for testing: Flask provides integrated support for unit testing, making it easier to write and execute tests for your web application. It comes with a built-in development server and a fast debugger, which helps in identifying and fixing issues during the testing phase.

# What is the default host port and port of Flask?
- The default local host of the flask is 127.0.0.1, and the default port is 5000.

# why do we use Flask(__name__) in Flask?
- In Flask, when we create an instance of the Flask class, we typically pass __name__ as the first argument. This pattern, app = Flask(__name__), is commonly used in Flask applications. The purpose of passing __name__ is to provide the Flask application with the name of the application package.

- The __name__ is a special Python variable that represents the name of the current module. In the context of Flask, it represents the name of the application's module or package. By passing __name__ as the argument to the Flask constructor, we are informing Flask about the name of our application package.

Here are a few reasons why we use __name__ in Flask:

- Finding resources: Flask uses the name of the application package to locate and load resources such as templates, static files, and instance folders. By providing the application package name, Flask knows where to look for these resources when they are requested.
Blueprints: In Flask, blueprints are used to organize and modularize routes and views. When defining a blueprint, the __name__ argument is used to specify the blueprint's import name. This import name is used to locate blueprint-specific resources, similar to how it works for the application instance.
- CLI integration: The name of the Flask application instance, which is derived from __name__, is used in the Flask CLI (Command-Line Interface). When you print the Flask application instance, it displays the name. Additionally, if you integrate the Flask CLI into a parent CLI, the name of the Flask application would be used as the group name for accessing the Flask application commands.

- It's important to note that while passing __name__ is a common practice, it is not mandatory. In some cases, you might deviate from this pattern and pass alternative values depending on your project structure and requirements.
- 
# What does url_for do in Flask?
- The url_for() method is used to generate a URL to a specific function dynamically. After the first argument, which is the name of the selected function, we can send any number of keyword arguments matching the variable portion of the URL. This function is useful since it allows us to create URLs dynamically instead of hard-coding them into the templates.

```
<a href=”{{ url_for(‘get_post_id’, post_id=post.id}}”>{{post.title}}<a>
```
# What HTTP methods does Python Flask provide?
-  GET	The most widely used approach. The server responds with data after receiving a GET message.
 - POST	To submit HTML form data to the server, use this method. The server does not save the data supplied via the POST method.
 - PUT	Upload content to replace all current representations of the target resource.
 - DELETE	Deletes all current representations of the URL’s target resource.
 - HEAD	Retrieves the headers for a resource, without retrieving the resource itself.

# In Flask, what do you mean by template engines?
- Template engines are used when we want to build web applications that are split into different components.  It is used for server-side applications that are not created as APIs and run on a single server. Templates also make it possible to render the server-side data that must be provided to the application quickly, such as the body, navigation, footer, dashboard, and so on.

Ejs, Jade, Pug, Mustache, HandlebarsJS, Jinja2, and Blade are some popular template engines.

# What is the use of jsonify() in Flask?
-  Jsonify is one of the flask.json module’s functions. It converts data to JSON and encapsulates it in a response object with the mime-type application/JSON. It loads directly from the flask module instead of the flask itself. To put it another way, jsonify() is a Flask helper method for correctly returning JSON data. The application/JSON mime-type is set by jsonify(), whereas json.dumps() just deliver a JSON data string. This could have unanticipated ramifications.

- The jsonify() function is useful in Flask apps because it automatically sets the correct response headers and content type for JSON responses, and allows you to easily return JSON-formatted data from your route handlers. This makes it easier and more convenient to create APIs that return JSON data.


# Explain how one can one-request database connections in Flask?
- Creating and closing database connections all the time is very inefficient, Because database connections encapsulate a transaction, you must ensure that the connection is only used by one request at a time. The Flask framework allows its users to request databases in three ways. They are:

- before_request(): No parameters are given when these connections are invoked before making a request.
- after_request(): After initiating a request, these connections are called, and a response is sent to the client.
- teardown_request(): This decorator is called when an exception is raised or everything went well (the error parameter will be None).

