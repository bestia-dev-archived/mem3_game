Things are changing fast. This is the situation on 2019-05-11. Luciano Bestia  
Read the `Last project` first:  
https://github.com/LucianoBestia/mem2  
# mem3_game
Learning Rust Wasm/WebAssembly with Virtual Dom Dodrio and WebSocket communication - part three.
# TODO
Is time to let mem2 as it is. In mem3 I plan to:
- have the frontend end backend projects in one Rust Workspace. To see how it works.  
- think more about references inside structs. Maybe, the lifetime <'static> is the solution. I have here structs, that will live untill the end of the application. Maybe even a bump allocator for my structs - to have exactly the same lifetime.  
- more than one content: "images, sounds and text"
- fetch text.json from Rust
- better documentation. Do I really have to write very long doc-comments in the code ?
- use cache for dom sections e.g. players_and_scores
- Restart button and re-ask player.

