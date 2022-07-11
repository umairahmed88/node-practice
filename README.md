# node-practice
This is for my practice

insatlling Node Js on linux

Step 1: Open your terminal or press Ctrl + Alt + T.

Step 2: sudo apt install nodejs

Step 3: to verify node installed enter command node -v or node –version

**NODE JS** It is JS run time like an environment in which a program written in JS we execute, outside of any browser


**fs** file system, we would access for reading, writing data

fs.readFileSync is a synchronus method to read file, this function needs two arguments, 1st path to the file, 2nd is character encoding i.e

fs.readFileSync('path', characterencoding);


for writing 

fs.writeFileSync the arguments will be ('path', fileName)


**Creating Simple Server**

it needs a package http i.e **{const http = require('http')}**

const server = http.createServer((req, res) => {
  res.end('Hello from the server')
}

server.listen(8000, "127.0.0.1", () => {
	console.log("Listening on port 8000");
});

**{const url = require('url')}**
it shows the url

const data = fs.readFileSync(`${__dirname}/data.json`, "utf-8");
const dataObject = JSON.parse(data);

const server = http.createServer((req, res) => {
	const pathName = req.url;

	if (pathName === "/" || pathName === "/overview") {
		res.end("This is overview page");
	} else if (pathName === "/product") {
		res.end("This is the product page");
	} else if (pathName === "/api") {
		res.writeHead(200, { "Content-type": "application/json" });
		res.end(data);
	} else {
		res.writeHead(404, {
			"Content-type": "text/html",
			"my-own-header": "hello- world",
		});

		res.end("<h1>Page not found!</h1>");
	}
});

server.listen(8000, "127.0.0.1", () => {
	console.log("Listening on port 8000");
});


