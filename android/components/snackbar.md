## Simple uses of cnackbar

	 val snackbarHostState = remember { SnackbarHostState() }  
    val scope = rememberCoroutineScope()  
    Surface(  
        modifier = Modifier.fillMaxSize(),  
    ) {  
        Column(  
            modifier = Modifier  
                .fillMaxSize()  
                .padding(16.dp)  
        ) {  
            Scaffold(  
                snackbarHost = { SnackbarHost(snackbarHostState) },  
                floatingActionButton = {  
                    ExtendedFloatingActionButton(  
                        onClick = {  
                            // show snackbar as a suspend function  
                            scope.launch {  
                                snackbarHostState.showSnackbar(  
                                    "You click on snackbar"  
                                )  
                            }  
                        }                    ) { Text("Show snackbar") }  
                },  
                content = { innerPadding ->  
                    Column(  
                        modifier = Modifier  
                            .fillMaxSize()  
                            .padding(innerPadding)  
                    ) {  
                        Text(text = "Text 1")  
                        Text(text = "Text 2")  
                    }  
                }            )  
        }  
    }