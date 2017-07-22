# Connection Options

```js
	host: string = "localhost";
	port: number = 5250;
	autoConnect: boolean = true;
	autoReconnect: boolean = true;
	autoReconnectInterval: number = 1000;
	autoReconnectAttempts: number = Infinity;
	serverVersion: Options.CasparCGVersion | undefined = undefined;
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
* **port:** The port to establish the AMCP connection to CasparCG Server on. CasparCG default is 5250, and can be changed in the CasparCG `casparcg.config`.
* **autoConnect:** 
* **autoReconnect:**
* **autoReconnectInterval:**
* **autoReconnectAttempts:**
* **serverVersion:**
* **queueMode:**
* **virginServerCheck:**
* **debug:**
* **onLog:**
* **onConnectionStatus:**
* **onConnectionChanged:**
* **onConnected:**
* **onDisconnected:**
* **onError:**



