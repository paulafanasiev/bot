//если умер, то респавн и вылететь вперед
 	WAITMS(300)
GETSCREEN
IF(PXL(888,585)= 6076508)
	WAITMS(300)
	LOGWRITE ("умер")

	LDOWN(888,585)
	WAITMS(300)
	LUP(888,585)
	WAITMS(3000)
	KEYPRESS(#3)
	WAITMS(300)
	KEYDOWN(#W)
	WAITMS(15000)
	KEYUP(#W)
	WAITMS(300)
else  //Если жив



	$a=0
	$needHeal=1

	GETSCREEN
	// нужен ли хил
	IF(PXL(122,118)= 4703063)
		IF(PXL(125,146)= 12944397)
			$needHeal=0
		END_IF
	END_IF
	IF(PXL(962,568)= 13744197)
		$a=1
	END_IF

//если не нужен хил
	IF($needHeal=0)

		GETSCREEN
	IF((PXL(229,124)= 4703063)and(PXL(935,1006)=15126299))
				
		



		KEYDOWN(#W)
		WAITMS(30)
		KEYUP(#W)
		KEYDOWN(#s)
		WAITMS(30)   
		KEYUP(#s)
  //атака с проверкой хп 
		WAITMS(300)
		KEYPRESS(#2) 
		WAIT(2) 
   		GETSCREEN//проверка хп
			IF(PXL(122,118)= 6253913)
				GOTO(19)
			END_IF
   		WAIT(2) 
		GETSCREEN//проверка хп
		IF(PXL(122,118)= 6253913)
			GOTO(19)
		END_IF
		WAIT(2) 
		GETSCREEN//проверка хп
		IF(PXL(122,118)= 6253913)
			GOTO(19)
		END_IF
		WAIT(2) 
	else
	KEYPRESS(#Tab)	
	END_IF	

	ELSE
19:
		KEYDOWN(#W)
		WAITMS(30)
		KEYUP(#W)
		KEYDOWN(#s)
		WAITMS(30)
		KEYUP(#s)
		WAITMS(300)

		KEYPRESS(#4)

		WAIT(7) 
	END_IF
END_IF


GETSCREEN
IF(PXL(888,585)= 4496708)
	WAITMS(300)
	LOGWRITE ("умер-темный пиксель")

	LDOWN(888,585)
	WAITMS(300)
	LUP(888,585)
	WAITMS(3000)
	KEYPRESS(#3)
	WAITMS(300)
	KEYDOWN(#W)
	WAITMS(15000)
	KEYUP(#W)
	WAITMS(300)
END_IF
