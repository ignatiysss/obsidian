##### Sample of code 

  
	var count by remember {  
	    mutableStateOf(0.0f)  
	}  
	Button(onClick = { count += 0.1f}) {  
	    Text(text = "click me")  
	}  
	Box(  
	    modifier = Modifier.fillMaxSize(),  
	    contentAlignment = Alignment.Center  
	) {  
	  CircularProgressBar(percentage = count, number = 100 )  
	}
##### function
	@Composable  
	fun CircularProgressBar(  
	    percentage: Float,  
	    number: Int,  
	    fontSize: TextUnit = 28.sp,  
	    radius: Dp = 50.dp,  
	    color: Color = Color.Green,  
	    strokeWidth: Dp = 8.dp,  
	    animDuration: Int = 1000,  
	    animDelay: Int = 0  
	) {  
	    var animationPlayed by remember {  
	        mutableStateOf(false)  
	    }  
	  
	    val curPercentage = animateFloatAsState(  
	        targetValue = if (animationPlayed) percentage else 0f,  
	        animationSpec = tween(  
	            durationMillis = animDuration,  
	            delayMillis = animDelay  
	        ),  
	  
	        label = ""  
	  
	    )  
	  
	    LaunchedEffect(key1 = true) {  
	        animationPlayed = true  
	    }  
	  
	    Box(  
	        modifier = Modifier.size(radius * 2f),  
	        contentAlignment = Alignment.Center  
	    ) {  
	        Canvas(modifier = Modifier.size(radius * 2f)) {  
	            drawArc(  
	                color = color,  
	                -90f,  
	                360 * curPercentage.value,  
	                useCenter = false,  
	                style = Stroke(  
	                    strokeWidth.toPx(),  
	                    cap = StrokeCap.Round  
	                )  
	            )  
	        }  
	        Text(  
	            text = (curPercentage.value * number).toInt().toString(),  
	            color = Color.Black,  
	            fontSize = fontSize,  
	            fontWeight = FontWeight.Bold  
	        )  
	  
	    }  
	  
	}