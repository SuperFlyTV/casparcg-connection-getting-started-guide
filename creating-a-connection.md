# Connection Options

```js
    host: string = "localhost";
    port: number = 5250;
    autoConnect: boolean = true;
    autoReconnect: boolean = true;
    autoReconnectInterval: number = 1000;
    autoReconnectAttempts: number = Infinity;
    serverVersion: Options.CasparCGVersion | undefined = undefined;
    queueMode: Options.QueueMode = Options.QueueMode.SEQUENTIAL;
    virginServerCheck: boolean = false;
    debug: boolean = false;
    onLog: IStringCallback = undefined;
    onConnectionStatus: ISocketStatusCallback = undefined;
    onConnectionChanged: IBooleanCallback = undefined;
    onConnected: IBooleanCallback = undefined;
    onDisconnected: IBooleanCallback = undefined;
    onError: IErrorCallback = undefined;
```

V3.0.0 AMCPConnectionOptions

* **host:** IP address or DNS hostname of the CasparCG server. Defaults to "localhost", which is correct when the CasparCG server and the node server \(client\) run on the same computer.
* **port:** The port to establish the AMCP connection to CasparCG server on. CasparCG server default is 5250, and can be changed in the CasparCG server `casparcg.config`.
* **autoConnect:** Setting this to true \(the default\) means that the connection will be set up immediately once your `CasparCG` object is created. This is not preferred if you want to listen to events, as connection-events in most cases will fire before you get them set up. Connection callbacks defined as `ConnectionOptions` will however receive all updates and can safely be used. If you prefer events, you should set `autoConnect` to false, defines the event listeners, then call `.connect()` on your `CasparCG` connection object afterwards. 
* **autoReconnect: **Setting this to true \(the default\) means that the connection always will try to reconnect in case of lost connection, either due to network error or CasparCG server restarts, until you call `.disconnect()` on your `CasparCG` connection object.
* **autoReconnectInterval: **The timeout, in milliseconds, between each attempt to connect or reconnect to the CasparCG server.
* **autoReconnectAttempts: **How many times, pr. connection attempt, to try to connect to the CasparCG server before giving up.  If you have 3 `autoReconnectAttempts` and your first connections occurs after 2 attempts, you then have 3 new attempts the next time the connection is lost and `autoReconnect` starts trying to reconnect again. Defaults to `Infinity`, meaning the \(re\)connection will try forever until told to `.disconnect()` through the `CasparCG` object
* **serverVersion: **
* **queueMode:**
* **virginServerCheck:**
* **debug:**
* **onLog:**
* **onConnectionStatus:**
* **onConnectionChanged:**
* **onConnected:**
* **onDisconnected:**
* **onError:**



