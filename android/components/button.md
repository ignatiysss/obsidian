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




## Changing colors of button

	 import androidx.compose.material3.ButtonDefaults
		 Button(  
		    onClick = { sizeState += 50.dp },  
		    colors = ButtonDefaults.buttonColors(  
		        contentColor = Color.Black,  
		        containerColor = Color.White //background  
		    )   
		)  
		{  
		    Text(text = "increase size ")  
		}