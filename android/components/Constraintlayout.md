## Dependency: 
	implementation ("androidx.constraintlayout:constraintlayout-compose:1.0.0-alpha05")

## Simple uses of constraintlayout
	val constraints = ConstraintSet {  
	    val bluebox = createRefFor("bluebox")  
	    val yellowbox = createRefFor("yellowbox")  
	  
	    constrain(bluebox) {  
	        top.linkTo(parent.top)  
	        start.linkTo(parent.start)  
	        end.linkTo(parent.end)  
	        width = Dimension.fillToConstraints  
	        height = Dimension.value(130.dp)  
	    }  
	    constrain(yellowbox) {  
	        top.linkTo(bluebox.bottom)  
	        start.linkTo(parent.start)  
	        end.linkTo(parent.end)  
	        width = Dimension.fillToConstraints  
	        height = Dimension.value(130.dp)  
	    }  
	}  
	  
	ConstraintLayout(constraints, modifier = Modifier.fillMaxSize()) {  
	  
	    Box(  
	        modifier = Modifier  
	            .background(Color.Blue)  
	            .layoutId("bluebox")  
	    )  
	    Box(  
	        modifier = Modifier  
	            .background(Color.Yellow)  
	            .layoutId("yellowbox")  
	    )  
	  
	}