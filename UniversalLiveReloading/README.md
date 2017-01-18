# Universal Live Reloading Example

This example shows how to get live-reloading working with both a Suave backend and a Fable-Elmish frontend.

Steps to setup:

1. Install the dotnet core cli tools preview 4 msbuild based
    * [https://github.com/dotnet/cli](https://github.com/dotnet/cli)
2. Clone the repository
    * `git clone https://github.com/Banashek/Universal-FSharp-Samples`
3. Restore and run the projects ( I typically do this in two terminal tabs )
    1. Server
        ```
        cd src
        dotnet restore
        dotnet watch run
        ```
    2. Client
        ```
        cd src/client
        npm run dev
        ```
## Things to know
* Server
    * Watch the output of the server command to see which port it binds to. It will increment the port to find an unused one upon restarting.
* Client
    * The server does not send a no-cache for the bundle.js file. After you save a file, fable will recompile it, but then you will need to reset your browsers cache for the file. In chrome, you can open the dev tools, right click on the refresh button, and select "Empty Cache and Hard Reload"