## Simple uses of button

	var count = 0  
	Button(  
	    onClick = {  
	        Toast.makeText(this, "You click on button ${++count}",  
	            Toast.LENGTH_SHORT).show()  
	    },  
	    modifier = Modifier  
	        .fillMaxWidth()  
	        .padding(16.dp)  
	        .padding(vertical = 200.dp)  
	) {  
	    Text(text = "Click me")  
	}