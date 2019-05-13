Things are changing fast. This is the situation on 2019-05-13. Luciano Bestia  
Read the `Last project` first:  
https://github.com/LucianoBestia/mem1  
# mem3
Learning to use Rust Wasm/WebAssembly with Dodrio Virtual Dom and WebSockets communication - third iteration.  
This is a simple memory game for kids. The images are funny cartoon characters from the alphabet.  
## Build
Look at the workspace readme.md.  
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

# Upgrades, refactoring and enhancement over mem1
- onw workspace with 2 projects
- cargo make
## Next projects
vacation  
## References
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
Reference counting, Borrow Checker in runtime instead of compile time  
https://manishearth.github.io/blog/2015/05/27/wrapper-types-in-rust-choosing-your-guarantees/  


