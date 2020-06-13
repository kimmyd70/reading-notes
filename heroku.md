## Heroku Deployment

[Node.js for beginners](https://howtonode.org/deploy-blog-to-heroku)

Building a simple server:

```
var http = require("http");

http.createServer(function(request, response) {
  response.writeHead(200, {"Content-Type": "text/plain"});
  response.write("It's alive!");
  response.end();
}).listen(3000);
```
Then run in the terminal:
`node server.js`

Browser: ` http://localhost:3000/`

If you know your laptop's IP:
You can check it with your smartphone. Let's suppose, your laptop's IP address within your local network is 192.168.1.101. You can connect to your server through the 3000th port (for this particular example) by typing in your browser. `http://192.168.1.101:3000/` 

Log into Heroku on terminal to host it on their cloud platform: 

`heroku login`

!!See the rest of the article at top for creating a project with a server inside!! Or check out the tutorial below:

[Heroku Dev Center Tutorial](https://devcenter.heroku.com/articles/getting-started-with-nodejs)

(complete through view logs)