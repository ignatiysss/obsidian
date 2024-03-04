
##### change size
    var sizeState by remember {  
        mutableStateOf(200.dp)  
    }  
    val size by animateDpAsState(  
        targetValue = sizeState,  
        spring(  
            Spring.DampingRatioHighBouncy  
        ),  
        label = ""  
    )  

##### color
    val color by rememberInfiniteTransition(label = "").animateColor(  
        initialValue = Color.Red,  
        targetValue = Color.Blue,  
        animationSpec = infiniteRepeatable(  
            tween(durationMillis = 2500),  
            repeatMode = RepeatMode.Reverse  
        ), label = ""  
    )