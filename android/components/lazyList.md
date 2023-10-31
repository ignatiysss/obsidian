## Simple uses of lazyList

	LazyColumn {
	                items(5000) {
	                    Text(
	                        text = "Button number ${it + 1}",
	                        modifier = Modifier
	                            .fillMaxWidth()
	                            .padding(vertical = 12.dp),
	                        textAlign = TextAlign.Center,
	                    )
	                }
	            }