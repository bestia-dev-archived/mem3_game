Things are changing fast. This is the situation on 2019-05-13. Luciano Bestia  
# mem3_server

Learning to code Rust for a http + WebSocket server on the same port  
using Warp for a simple memory game for kids - mem3.  
  
The Http server is just a simple static file server. All the logic is in Wasm in the browser.  
The browser uses the root route /. The served files are in the folder /mem3/.  
The WebSocket server broadcasts the first msg "Want to play" to all connected clients. From that on, it is a private communication between 2 players.  
## Build and Serve locally
Look at the workspace readme.md.  
## References
Rust  
https://github.com/seanmonstar/warp  
https://docs.rs/env_logger/0.6.0/env_logger/struct.Builder.html  
https://github.com/tcr/rust-local-ip  
https://regex101.com/
https://docs.rs/env_logger/*/env_logger/
https://docs.rs/regex/1.1.2/regex/struct.Captures.html
https://doc.rust-lang.org/reference/tokens.html#raw-string-literals
https://github.com/clap-rs/clap  

