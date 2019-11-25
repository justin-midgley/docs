# How to start in 60 seconds

Requirements:

* `dotnet` SDK
* `mono` (on Linux/MacOS)
* `fake`

---


1. Install the `dotnet` template with `dotnet new -i Saturn.Template`
2. Create a new folder and move into it - `mkdir SaturnSample && cd SaturnSample`
3. Create a new Saturn application - `dotnet new saturn -lang F#`
4. Run the build process to ensure everything was scaffolded correctly and restore dependencies - `fake build`
5. Go into the subdirectory with the server application - `cd src/SaturnSample`
6. Create a new controller with `dotnet saturn gen Book Books id:string title:string author:string`
7. Run migrations that will create the database and Books table (as for now, the generator is using only SQLite DB) - `dotnet saturn migration`
8. Open the folder in your favourite editor (VSCode) and insert the line (`forward "/books" Books.Controller.resource`) into `browserRouter` in `Router.fs` file
9. Start the application by running `fake build -t run` from the root of the solution. This will start the application in watch mode (automatic recompilation on changes) and open your browser on [http://localhost:8085](http://localhost:8085) which should display the index page.
10. Go to [http://localhost:8085/books](http://localhost:8085/books) to see the generated view. All buttons should be working; you can add new entries, and remove or edit old ones.
