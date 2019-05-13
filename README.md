Things are changing fast. This is the situation on 2019-05-13. Luciano Bestia  
Read the `Last project` first:  
https://github.com/LucianoBestia/mem3  
# mem3_game
Learning Rust Wasm/WebAssembly with Virtual Dom Dodrio and WebSocket communication - part three.
It is s time to let mem2 development as it is. A step toward idiomatic Rust, but not the final step.
# Build
Clone:  
```
git clone git@github.com:LucianoBestia/mem3_game.git
cd mem3
```
Install cargo-make:  
`cargo install --force cargo-make`  
  
Build:  
`cargo make`  

# TODO
. In mem3 I plan to:
- Only one WorkSpace for the frontend and end backend projects. To see how it works.  
- think more about references inside structs. I think, the lifetime <'a> is the solution. I have here all structs, that will live until the end of the application.  
- player can choose more than one content: "images, sounds and text"
- fetch text.json from Rust
- better documentation. Do I really have to write very long doc-comments in the code ? It looks terrible. But it is useful when reading the code. Maybe I can hide it in a region block. Dodrio has beautiful docs. How did he do it?  
- use cache for Dom sections e.g. players_and_scores
- Restart button and re-ask player.  
- use cargo make (build scripts) to copy the pkg of frontend to the backend folder - cargo-make ??  
- the server could broadcast only the first "Want to play?". All the rest should be a private conversation between 2 players. Maybe add a simple chat for the fun of it? 





