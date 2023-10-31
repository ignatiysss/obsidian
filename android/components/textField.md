## Simple uses of textField

	var textFieldState by remember {
                mutableStateOf("")
            }

            TextField(
                value = textFieldState,
                label = { Text(text = "Enter your name")},
                onValueChange = {textFieldState = it}
            )