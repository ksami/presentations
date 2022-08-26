---
title: 'Node.js Events & Streams'
separator: \n---\n
verticalSeparator: \n...\n
theme: league
revealOptions:
    transition: 'fade'
---

# Node.js Events & Streams

---

## What?
Programming concepts used for handling asynchronous execution

---

# Events

> I want to know when something happens

Analogy: Mailing lists, billing subscriptions

...

- Emit and subscribe/listen for events
- `EventEmitter` in Node.js

    ```js
    const EventEmitter = require('events');
    const mailingList = new EventEmitter();
    ```

...

    ### Emitting

    ```js
    mailingList.emit('newMail', 'Some advertisement');
    ```

...

    ### Subscribing

    ```js
    mailingList.on('newMail', (message) => {
      console.log(message);  // Some advertisement
    });
    ```

---

# Streams

> I want to do something while something else is happening

Instead of waiting for the finished product, I can start work once I get a part of the product

...

Situation: Painter at a car factory assembly line


- Either wait for all cars to be manufactured before starting to paint
  - Overall car will take longer to be finished
  - Need enough space for all cars at the same location at the same time
- Or paint each car once each car is manufactured

...

- Streams in Node.js implemented using `EventEmitter`
- Usually not constructed directly but from libraries eg. `fs`
- Types of streams:
  - `Readable` used for reading
  - `Writable` used for writing
  - `Duplex` used for both

...

    ## Writing

    ```js
    const fileStream = fs.createWriteStream('shakespeare.txt');

    fileStream.write('Lorem Ipsum');
    fileStream.end();
    ```

...

    ## Reading

    ```js
    const fileStream = fs.createReadStream('shakespeare.txt');
    const chunks = [];

    fileStream.on('data', (chunk) => {
      chunks.push(chunk);
    });

    fileStream.on('end', () => {
      console.log(chunks.join(''));  // Lorem Ipsum
    })
    ```

...

    ## Piping: output from one stream as input for another stream

    ```js
    const inputStream = fs.createReadStream('input.txt');
    const outputStream = fs.createWriteStream('output.txt');

    inputStream.pipe(outputStream);
    // output.txt is now a copy of input.txt
    ```
...

- Useful events emitted:
  - `data`: When there is data available to be read
  - `end`: When there is no more data to read
  - `error`: When there is an error in writing/reading data

---

# Fin
