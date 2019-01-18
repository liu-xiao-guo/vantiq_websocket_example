This is an example to show how to send data from a webpage to Vantiq platform and receive data from Vantiq platform using websocket.

When using the example, you need put your token in the following part of the code.

 ws.onopen = function() {
                  
	// Web Socket is connected, send data using send()
	var body = {};
	body.op = "validate";
	body.resourceName = "system.credentials";
	body.object = "YOUR TOKEN";
	// body.op =  "authenticate";
	// body.resourceName = "system.credentials";
	// body.object = { "username": "YOUR USERNAME", "password": "YOUR PASSWORD" };
  
  console.log("Sent message: " + JSON.stringify(body));
  
  ws.send(JSON.stringify(body));
  // alert("Message is sent...");
		console.log("Message is sent...");
};

Meanwhile, you can creaet a type in Vantiq, and it has the following three properties:

1) id: Integer
2) name: String
3) number: String

You can insert data into the table by clicking the "send" hyperlink, and you can receive data notification when there is a new data insert on the Vantiq cloud.