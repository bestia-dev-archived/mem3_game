# mem3_game

**A step toward idiomatic Rust, but not the final step.**  
***version: 3.0  date: 2019-05-20 author: [bestia.dev](https://bestia.dev) repository: [GitHub](https://github.com/bestia-dev/mem3_game)***  

![Hits](https://bestia.dev/webpage_hit_counter/get_svg_image/349050521)

Hashtags: #rustlang #game #tutorial  
My projects on Github are more like a tutorial than a finished product: [bestia-dev tutorials](https://github.com/bestia-dev/tutorials_rust_wasm).

Read the `Last project`:  
<https://github.com/bestia-dev/mem2>  
You can play the game here (hosted on google cloud platform):  
<https://bestia.dev/mem3>  

## Clone

```bash
git clone git@github.com:bestia-dev/mem3_game.git
cd mem3
```

## Build

Install cargo-make:  
`cargo install --force cargo-make`  
  
Build:  
`cargo make`  
It will:

- build both projects,
- copy pkg folder and index.html into server project,
- run 2 chrome tabs
- run the http+WebSocket server  
  
Please refresh the browser tabs manually after that, so they download the new files.  
A little about cargo-make:  
<https://medium.com/@sagiegurari/automating-your-rust-workflows-with-cargo-make-part-1-of-5-introduction-and-basics-b19ced7e7057>  

# Memory game rules

This game is for exactly 2 players.  
Both players must have the webpage simultaneously opened in the browser to allow communication.  
To start over just refresh the webpage.  
The first player clicks on 'Invite for play?' and broadcasts the message over WebSocket.  
He can choose different types of play: alphabet, animal,...  
Player2 then sees on the screen 'Click here to Accept play!', clicks it and sends the message back to Player1.  
The game starts with a grid of 8 randomly shuffled card pairs face down - 16 cards in all.  
On the screen under the grid are clear signals which player plays and which waits.  
Player1 flips over two cards with two clicks. The cards are accompanied by sounds and text on the screen.  
If the cards do not match, the other player clicks on 'Click here to Take your turn' and both cards are flipped back face down. Then it is his turn and he clicks to flip over his two cards.  
If the cards match, they are left face up permanently and the player receives a point. He continues to play, he opens the next two cards.  
The game is over when all the cards are permanently face up. It means that the sum of points is exactly 8.  
Click on "Play again?" to start the game over.  

## cargo crev reviews and advisory

It is recommended to always use [cargo-crev](https://github.com/crev-dev/cargo-crev)  
to verify the trustworthiness of each of your dependencies.  
Please, spread this info.  
On the web use this url to read crate reviews. Example:  
<https://web.crev.dev/rust-reviews/crate/num-traits/>  

## Next projects

<https://github.com/bestia-dev/mem4_game>  

## Changelog

- Only one WorkSpace for the frontend and end backend projects and commons. To see how it works.  
- use cargo make (build scripts) to copy needed files to webfolder. This folder can be then copied to some website and works.  
- mem3 RenderComponents have an internal cache for values. These are copied/cloned from game_data. ANd invalidated accordingly.
- For the research of different approach to game_data references I opened a new project with minimalistic code.  
<https://github.com/bestia-dev/dodrio_multi_component>  
2019-05-19
- player can choose more than one content: "images, sounds and text"
- fetch text.json from Rust asynchronously over WebSocket
2019-05-20
-- re-invite player for different game
- the server broadcasts only the first "Want to play?". All the rest is a private conversation between 2 players.  
- use files as separate modules of the same crate  
- cached PlayersAndScores

## References

### mem3  

Rust  
<https://doc.rust-lang.org/book/>  
<https://rust-lang-nursery.github.io/rust-cookbook/>  
virtual Dom  
<https://github.com/fitzgen/dodrio>  
web, http, css  
<https://github.com/brson/basic-http-server>  
<https://www.w3schools.com/w3css/>  
WebSocket  
<https://ws-rs.org/>  
<https://github.com/housleyjk/ws-rs>  
wasm, wasm-bindgen  
<https://rustwasm.github.io/docs/wasm-bindgen>  
<https://github.com/anderejd/wasm-bindgen-minimal-example>  
<https://github.com/grizwako/rust-wasm-chat-frontend>  
JsValue, future, promises  
<https://crates.io/crates/wasm-bindgen-futures>  
<https://github.com/fitzgen/dodrio/blob/master/examples/todomvc/src/router.rs>  
random  
<https://rust-random.github.io/book/>  
Images included free cartoon characters:  
<https://vectorcharacters.net/alphabet-vectors/alphabet-cartoon-characters>  
Favicon from  
<https://www.favicon-generator.org/search/BLACK/M>  

### mem3_server  

Rust  
<https://github.com/seanmonstar/warp>  
<https://docs.rs/env_logger/0.6.0/env_logger/struct.Builder.html>  
<https://github.com/tcr/rust-local-ip>  
<https://regex101.com/>  
<https://docs.rs/env_logger/*/env_logger/>  
<https://docs.rs/regex/1.1.2/regex/struct.Captures.html>  
<https://doc.rust-lang.org/reference/tokens.html#raw-string-literals>  
<https://github.com/clap-rs/clap>  
