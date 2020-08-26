# Complete_use_of_UART2
This is an stm32CubeIDE project for Blue Pill board. The same project should be uploadded into two different Blue Pill boards, where lines 28,29,30 should be commented for the board that connects with PC via USB. 
Let's call board_1 is the one that connects with PC via USB. Board_2, the one that connects with Board_1

the procedure is the following:
1) Board_2 toggles port PA1 each 2 seconds and immediately sends data to Board_1.
2) when PA0 on board_1 detects a rising edge, it generates an interrupt.
3) in the interrup handler, we recieve data from board_2.
4) after recieving data, another interrupt is generated "Receive register is not empty interrupt".
5) in the interrup handler, we recieve send data from board_1 to PC via USB.
