# Web workers
Web workers runs as a separate thread from the main thread in the browser itself and they communicate using `postMessage` and `onmessage` handlers.

There are 2 types of web workers `Dedicated Workers` and `Shared workers`. following is the example of `Dedicated worker`.

## Dedicated Worker
Dedicated workers are only accessible from the script that created the worker.

### How to create a worker ?
```javascript
const myWorker = new Worker("worker.js");
```

As workers run as a separate thread it doesn't have access to some browser like window object and it also cannot manipulate dom as well.

### How to post a message ?
```javascript
submitBtn.onclick = () => {
  myWorker.postMessage([first.value, second.value]);
};
```

### How to handle message in worker ?
```javascript
onmessage = (e) => {
  console.log("Message received from main script");
  let result = 0;
  for (let i = e.data[0]; i < e.data[1]; i++) {
    result += i;
  }
  const workerResult = `Result: ${result}`;
  console.log("Posting message back to main script");
  postMessage(workerResult);
};
```

## Shared worker
