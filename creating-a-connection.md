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
* **autoConnect:** Setting this to true \(the default\) means that the connection will be set up immediately once your `CasparCG` object is created. This is not preferred if you want to listen to events, as connection-events in most cases will fire before you get them set up. Connection callbacks defined as `ConnectionOptions` will however receive all updates and can safely be used. If you prefer events, you should set `autoConnect` to false, defines the event listeners, then call `.connect()` on your `CasparCG` connection object afterwards. See Callback and Events for an example.
* **autoReconnect: **Setting this to true \(the default\) means that the connection always will try to reconnect in case of lost connection, either due to network error or CasparCG server restarts, until you call `.disconnect()` on your `CasparCG` connection object.
* **autoReconnectInterval: **The timeout, in milliseconds, between each attempt to connect or reconnect to the CasparCG server.
* **autoReconnectAttempts: **How many times, pr. connection attempt, to try to connect to the CasparCG server before giving up.  If you have 3 `autoReconnectAttempts` and your first connections occurs after 2 attempts, you then have 3 new attempts the next time the connection is lost and `autoReconnect` starts trying to reconnect again. Defaults to `Infinity`, meaning the \(re\)connection will try forever until told to `.disconnect()` through the `CasparCG` object
* **serverVersion: **If you know what version of CasparCG server you are connection to, you can specify it here. If you don't specify anything \(the default\), a query to the CasparCG server will be done once this information is needed. The only motivation to specify a serverVersion is to prevent this extra `INFO SERVER` command to run, which only happens once pr. connection session, and only if needed.
* **queueMode: **Defaults to "sequential", which is also the only mode implemented at this time. In the future this option will allow for faster and smarter handling of the execution of commands.
* **virginServerCheck: **Setting this to true \(default is false\) will make the connection query the CasparCG server upon each connection to determine if the CasparCG server is "untouched"/"freshly started" or have been active before the connection. An "untouched" state means that no content is playing on any channels. This information is useful if your client script keeps some sort of internal state, and needs to know in what condition the CasparCG server is. **Important: **_the check does not take into account MIXER settings, only active layers pr. channel. _The check costs 1+n AMCP commands, where n is the number of channels on the CasparCG server.
* **debug: **Setting this to true \(default is false\) enables outputting all events/callbacks as strings through console.log\(\) or console.error\(\).
* **onLog: **Callback for all information messages throughout the system.
* **onConnectionStatus:** Callback for each time the connection status verifies.
* **onConnectionChanged:** Callback for each time the connection status changes \(from disconnected to connected, or vice versa\).
* **onConnected:** Callback for each time the connection status is set to connected.
* **onDisconnected:** Callback for each time the connection status is set to disconnected.
* **onError:** Callback for all errors being thrown throughout the system.

See Callbacks and Events for more information on callback behaviours and data available through callbacks. 



