##### Main call of function 
	fun HomeScreen(  
	    partOfDay: String = "Morning",  
	    outsideCorners: Dp = 24.dp,  
	    padding: Dp = 8.dp  
	) {  
	    val insideCorners = outsideCorners - padding  
	    Box(  
	        modifier = Modifier  
	            .background(DeepBlue)  
	            .fillMaxSize()  
	    ) {  
	        Column {  
	            GettingSection(partOfDay = partOfDay, padding = padding, outsideCorners = insideCorners)  
	            ChipSection(  
	                chips = listOf("Sweet sleep", "Insomnia", "Depression"),  
	                padding = padding,  
	                outsideCorners = outsideCorners  
	            )  
	            CurrentMeditation(  
	                outsideCorners = insideCorners,  
	                partOfDay = partOfDay,  
	                padding = padding  
	            )  
	            FeatureSection(  
	                features = listOf(  
	                    Feature(  
	                        title = "Sleep meditation",  
	                        R.drawable.ic_headphone,  
	                        BlueViolet1,  
	                        BlueViolet2,  
	                        BlueViolet3  
	                    ),  
	                    Feature(  
	                        title = "Tips for sleeping",  
	                        R.drawable.ic_videocam,  
	                        LightGreen1,  
	                        LightGreen2,  
	                        LightGreen3  
	                    ),  
	                    Feature(  
	                        title = "Night island",  
	                        R.drawable.ic_headphone,  
	                        OrangeYellow1,  
	                        OrangeYellow2,  
	                        OrangeYellow3  
	                    ),  
	                    Feature(  
	                        title = "Calming sounds",  
	                        R.drawable.ic_headphone,  
	                        Beige1,  
	                        Beige2,  
	                        Beige3  
	                    ),  
	                    Feature(  
	                        title = "Night island",  
	                        R.drawable.ic_headphone,  
	                        OrangeYellow1,  
	                        OrangeYellow2,  
	                        OrangeYellow3  
	                    ),  
	                    Feature(  
	                        title = "Calming sounds",  
	                        R.drawable.ic_headphone,  
	                        Cyan1,  
	                        Cyan2,  
	                        Cyan3  
	                    ),  
	                ),  
	               outsideCorners = outsideCorners,  
	                padding = padding  
	            )  
	        }  
	        BottomMenu(  
	            items = listOf(  
	                BottomMenuContent("Home", R.drawable.ic_home),  
	                BottomMenuContent("Meditate", R.drawable.ic_bubble),  
	                BottomMenuContent("Sleep", R.drawable.ic_moon),  
	                BottomMenuContent("Music", R.drawable.ic_music),  
	                BottomMenuContent("Profile", R.drawable.ic_profile),  
	            ), outsideCorners = insideCorners,  
	            padding = padding,  
	            modifier = Modifier.align(Alignment.BottomCenter)  
	        )  
	  
	  
	    }  
	  
	  
	}

##### 