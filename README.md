Things are changing fast. This is the situation on 2019-05-13. Luciano Bestia  
Read the `Last project` first:  
https://github.com/LucianoBestia/mem2  
# mem3_game
Learning Rust Wasm/WebAssembly with Virtual Dom Dodrio and WebSocket communication - part three.
It is s time to let mem2 development as it is. A step toward idiomatic Rust, but not the final step.  
## Clone
```
git clone git@github.com:LucianoBestia/mem3_game.git
cd mem3
```
## Build
Install cargo-make:  
`cargo install --force cargo-make`  
  
Build:  
`cargo make`  
It will:
- build both projects, 
- copy pkg folder,
- run 2 chrome tabs
- run the server  
  
Please refresh the browser tabs manually after that, so they download the new files.  
# Memory game rules
This game is for exactly 2 players.  
Both players must have the webpage simultaneously opened in the browser to allow communication.  
To start over just refresh the webpage.  
The first player clicks on 'Ask Player2 to play?' and broadcasts the message over WebSocket.  
Player2 then sees on the screen 'Click here to Accept play!', clicks it and sends the message back to Player1.  
The game starts with a grid of 8 randomly shuffled card pairs face down - 16 cards in all.  
On the screen under the grid are clear signals which player plays and which waits.  
Player1 flips over two cards with two clicks.  
If the cards do not match, the other player clicks on 'Click here to Take your turn' and both cards are flipped back face down. Then it is his turn and he clicks to flip over his two cards.  
If the cards match, they are left face up permanently and the player receives a point. He continues to play, he opens the next two cards.  
The player with more points wins.  
## Next projects
vacation  
## TODO:
In mem3 I plan to:
- think more about references inside structs. I think, the lifetime <'a> is the solution. I have here all structs, that will live until the end of the application.  
- player can choose more than one content: "images, sounds and text"
- fetch text.json from Rust
- better documentation. Do I really have to write very long doc-comments in the code ? It looks terrible. But it is useful when reading the code. Maybe I can hide it in a region block. Dodrio has beautiful docs. How did he do it?  
- use cache for Dom sections e.g. players_and_scores
- Restart button and re-ask player.  
- the server could broadcast only the first "Want to play?". All the rest should be a private conversation between 2 players. Maybe add a simple chat for the fun of it? 

## Changelog
- Only one WorkSpace for the frontend and end backend projects. To see how it works.  
- use cargo make (build scripts) to copy the pkg of frontend to the backend folder  
- I cannot find an easy way to make a simple static struct tree and access the data of the parent struct. I tried a lot of things:
1. In mem2 I successfully used Rc<RefCell<>>, but it is not a compile time approach.  
2. Inside a struct tree, Rust cannot have a normal reference to another field/struct. Because all objects are movable, that reference will be bad after the struct moves.
3. Lifetimes are a mess. I have Dodrio here, that lives longer then the main() function. So I cannot have any struct, that lives long enough. Except the one struct, that I move into Dodrio. It can be only one struct, because it is a Dodrio function and the parameters are fixed.  
4. Box, UnsafeCell, ... acrobatics
5. A single arena for all the data?? All have the same lifetime.
6. There is a Pin struct for making unmovable data.
7. Making 'static mutable Mutex? As global data?
8. There are strange crates for terrible workarounds:  
https://github.com/diwic/refstruct-rs  
https://github.com/Kimundi/owning-ref-rs  
https://github.com/jpernst/rental  
- For every small change there is a mountain of refactoring to do. Lifetimes are the worst.  


## References
### mem3  
Rust  
https://doc.rust-lang.org/book/  
https://rust-lang-nursery.github.io/rust-cookbook/  
virtual Dom  
https://github.com/fitzgen/dodrio  
web, http, css  
https://github.com/brson/basic-http-server  
https://www.w3schools.com/w3css/  
WebSocket  
https://ws-rs.org/
https://github.com/housleyjk/ws-rs  
wasm, wasm-bindgen  
https://rustwasm.github.io/docs/wasm-bindgen  
https://github.com/anderejd/wasm-bindgen-minimal-example  
https://github.com/grizwako/rust-wasm-chat-frontend  
JsValue, future, promises  
https://crates.io/crates/wasm-bindgen-futures  
https://github.com/fitzgen/dodrio/blob/master/examples/todomvc/src/router.rs  
random  
https://rust-random.github.io/book/  
Images included free cartoon characters:  
https://vectorcharacters.net/alphabet-vectors/alphabet-cartoon-characters  
Favicon from  
https://www.favicon-generator.org/search/BLACK/M  


### mem3_server  
Rust  
https://github.com/seanmonstar/warp  
https://docs.rs/env_logger/0.6.0/env_logger/struct.Builder.html  
https://github.com/tcr/rust-local-ip  
https://regex101.com/
https://docs.rs/env_logger/*/env_logger/
https://docs.rs/regex/1.1.2/regex/struct.Captures.html
https://doc.rust-lang.org/reference/tokens.html#raw-string-literals
https://github.com/clap-rs/clap  


