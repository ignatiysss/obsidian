
##### Whole section

	@Composable  
	fun FeatureSection(  
	    features: List<Feature>,  
	    outsideCorners: Dp,  
	    padding: Dp  
	) {  
	    val insideCorner = outsideCorners - padding  
	    Column(  
	        modifier = Modifier.fillMaxWidth()  
	    ) {  
	        Text(  
	            text = "Features",  
	            style = MaterialTheme.typography.headlineMedium,  
	            color = TextWhite,  
	            modifier = Modifier.padding(padding)  
	        )  
	        LazyVerticalGrid(  
	            columns = GridCells.Fixed(2),  
	            contentPadding = PaddingValues(  
	                start = padding,  
	                end = padding,  
	                bottom = 100.dp  
	            ),  
	        ) {  
	            items(features.size) {  
	                FeatureItem(feature = features[it], padding = padding, outsideCorners = outsideCorners)  
	            }  
	        }  
	  
	    }  
	}  
##### Item
	@Composable  
	fun FeatureItem(  
	    feature: Feature,  
	    outsideCorners: Dp,  
	    padding: Dp  
	) {  
	    val insideCorners = outsideCorners - padding  
	    BoxWithConstraints(  
	        modifier = Modifier  
	            .padding(padding)  
	            .clip(RoundedCornerShape(outsideCorners))  
	            .aspectRatio(1f)  
	            .background(feature.darkColor)  
	    ) {  
	        val height = constraints.maxHeight  
	        val width = constraints.maxWidth  
	  
	        val mediumColoredPoint1 = Offset(0f, height * 0.3f)  
	        val mediumColoredPoint2 = Offset(width * 0.25f, height * 0.1f)  
	        val mediumColoredPoint3 = Offset(width * 0.4f, height * 0.05f)  
	        val mediumColoredPoint4 = Offset(width * 0.7f, height * 0.7f)  
	        val mediumColoredPoint5 = Offset(width * 10f, -height.toFloat())  
	  
	        val mediumColoredPath = Path().apply {  
	            moveTo(mediumColoredPoint1.x, mediumColoredPoint1.y)  
	            standardQuadTo(mediumColoredPoint1, mediumColoredPoint2)  
	            standardQuadTo(mediumColoredPoint2, mediumColoredPoint3)  
	            standardQuadTo(mediumColoredPoint3, mediumColoredPoint4)  
	            standardQuadTo(mediumColoredPoint4, mediumColoredPoint5)  
	            lineTo(width + 100f, height + 100f)  
	            lineTo(width - 100f, height + 100f)  
	            close()  
	        }  
	        val lightColoredPoint1 = Offset(0f, height * 0.3f)  
	        val lightColoredPoint2 = Offset(width * 0.25f, height * 0.15f)  
	        val lightColoredPoint3 = Offset(width * 0.4f, height * 0.3f)  
	        val lightColoredPoint4 = Offset(width * 0.7f, height * 1f)  
	        val lightColoredPoint5 = Offset(width * 10f, -height.toFloat() / 3f)  
	  
	        val lightColoredPath = Path().apply {  
	            moveTo(lightColoredPoint1.x, lightColoredPoint1.y)  
	            standardQuadTo(lightColoredPoint1, lightColoredPoint2)  
	            standardQuadTo(lightColoredPoint2, lightColoredPoint3)  
	            standardQuadTo(lightColoredPoint3, lightColoredPoint4)  
	            standardQuadTo(lightColoredPoint4, lightColoredPoint5)  
	            lineTo(width + 100f, height + 100f)  
	            lineTo(width - 100f, height + 100f)  
	            close()  
	        }  
	        Canvas(modifier = Modifier.fillMaxSize()) {  
	            drawPath(  
	                path = mediumColoredPath,  
	                color = feature.mediumColor  
	            )  
	            drawPath(  
	                path = lightColoredPath,  
	                color = feature.lightColor  
	            )  
	        }  
	        Box(  
	            modifier = Modifier  
	                .fillMaxSize()  
	                .padding(padding)  
	        ) {  
	            Text(  
	                text = feature.title,  
	                style = MaterialTheme.typography.headlineMedium,  
	                lineHeight = 34.sp,  
	                color = TextWhite,  
	  
	                modifier = Modifier.align(Alignment.TopStart).padding(padding)  
	            )  
	            Icon(  
	                painter = painterResource(id = feature.iconId), contentDescription = feature.title,  
	                tint = Color.White,  
	                modifier = Modifier.align(Alignment.BottomStart)  
	                    .padding(padding)  
	            )  
	            Text(  
	                text = "Start",  
	                color = TextWhite,  
	                fontSize = 14.sp,  
	                fontWeight = FontWeight.Bold,  
	                modifier = Modifier  
	                    .clickable {  
	  
	  
	                    }                    .align(Alignment.BottomEnd)  
	                    .clip(RoundedCornerShape(insideCorners))  
	                    .background(ButtonBlue)  
	                    .padding(padding)  
	            )  
	        }  
	    }}