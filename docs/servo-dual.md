# Servo Dual

```javascript
var five = require("../lib/johnny-five.js"),
    board, servos;

board = new five.Board({
  debug: true
});

board.on("ready", function() {

  servos = {
    claw: new five.Servo({
      pin: 9,
      range: [ 10, 170 ]
    }),
    arm: new five.Servo(10)
  };

  // Inject the `servo` hardware into
  // the Repl instance's context;
  // allows direct command line access
  board.repl.inject({
    s: servos
  });


  // Log moves to repl
  Object.keys( servos ).forEach(function( which ) {
    servos[ which ].on("move", function( err, degrees ) {
      console.log( which + " moved: " + degrees + " degrees" );
    });
  });
});

```

## Breadboard




## Documentation

_(Nothing yet)_









## Contributing
All contributions must adhere to the the [Idiomatic.js Style Guide](https://github.com/rwldrn/idiomatic.js),
by maintaining the existing coding style. Add unit tests for any new or changed functionality. Lint and test your code using [grunt](https://github.com/cowboy/grunt).

## Release History
_(Nothing yet)_

## License
Copyright (c) 2012 Rick Waldron <waldron.rick@gmail.com>
Licensed under the MIT license.