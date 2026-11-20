# Golang Web Server

This is a beginner-friendly web server built with Go's standard `net/http`
package. It serves HTML files and handles simple HTTP requests.

## What this project does

- Serves the files inside the `static` folder.
- Shows a home page at `/`.
- Returns `Hello!` from the `/hello` route.
- Accepts a name and address from a form at `/form`.
- Prints the submitted form values in the server response.

## What I learned

- How to create a basic HTTP server in Go.
- How to use `http.Handle` for static files.
- How to use `http.HandleFunc` for custom routes.
- The difference between `GET` and `POST` requests.
- How to read form values with `r.FormValue`.
- How to start a server with `http.ListenAndServe`.
- How a browser communicates with a backend server.

## Project structure

```text
Golang-Web-Server/
├── main.go
├── go.mod
└── static/
    ├── index.html
    └── form.html
```

## How to run

### 1. Open a terminal in this folder

```powershell
cd "C:\Users\anujj\OneDrive\Desktop\GO\Golang-Web-Server"
```

### 2. Start the server

```powershell
go run main.go
```

You should see:

```text
Server started at http://localhost:8080
```

### 3. Open the pages

Open these URLs in a browser:

- Home page: <http://localhost:8080/>
- Hello route: <http://localhost:8080/hello>
- Form page: <http://localhost:8080/form.html>

Submit the form to send a `POST` request to `/form`.

### 4. Stop the server

Press `Ctrl + C` in the terminal.

## How the code works

1. `http.FileServer` serves HTML files from the `static` folder.
2. `/hello` is connected to `helloHandler`.
3. `/form` is connected to `formHandler`.
4. `formHandler` reads the submitted `name` and `address`.
5. `http.ListenAndServe(":8080", nil)` starts the server on port `8080`.

## Useful commands

```powershell
go mod tidy
go run main.go
go build
```

`go build` creates an executable that can be run without using `go run`.
