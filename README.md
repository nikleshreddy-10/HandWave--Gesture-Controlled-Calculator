The calculator evaluates mathematical expressions based on hand gestures, with real-time UI updates and the ability to confirm input with a fist gesture.
 
 This project involves several key steps that integrate computer vision, hand gesture recognition, and basic arithmetic operations. Below is an overview of the main steps involved:
 
 Setup and Initialization 
 1.Video Capture Setup: The cv2.VideoCapture function is used to access the webcam feed. The video resolution is set to 1280x720 pixels. 
 2.Mediapipe Hands Model Initialization: The Mediapipe library is used for hand landmark detection. The hand model is initialized with a detection confidence threshold of 85% and a tracking confidence of 50%. 
 3.UI Design Setup: The input areas and operator buttons are defined. The buttons allow the user to input numbers, select operators, and confirm the calculation.
 
 Drawing UI Components 
 1.Drawing Boxes for Inputs and Operators: Rectangles are drawn on the screen to represent input areas for numbers, the operator selection buttons (like +, -, etc.), and the confirmation area. 
 2.Displaying Labels: Text is displayed near each box to indicate their function (e.g., "Input 1", "Input 2", and "Confirm (Fist)") and to show the operator options. 
 
 Hand Gesture Recognition 
 1.Landmark Detection: For each hand detected by the model, the 3D coordinates of the hand landmarks (i.e., the positions of the fingers and wrist) are extracted. 
 2.Counting Fingers for Input: Based on the hand landmarks, the number of extended fingers is counted. The fingers' positions are used to determine whether a user is inputting a number. 
 Left hand gestures are used to input digits in the first input box, and the right hand gestures are used for the second box. 
 3.Operator Selection: The position of the index finger is used to detect if it is pointing to any operator button (e.g., +, -, etc.). 
 
 Gesture-Based Confirmation 
 1.Fist Gesture for Confirmation: If the user makes a fist within the designated confirmation area, the current input (number or operator) is accepted and added to the expression. 
 2.Multiple Fists Detection: The system tracks the number of fist gestures to confirm the completion of an expression, triggering evaluation after two consecutive fists are detected. 
 
 Expression Evaluation 
 1.Building the Mathematical Expression: The system builds the expression by combining the detected numbers and operators as the user interacts with the UI. 
 2.Evaluating the Expression: Once the user confirms the expression by making a fist gesture, the expression is evaluated using Python’s eval() function. The result is displayed on the screen. 
 
 Real-Time Display Updates 
 1.Displaying the Current Expression: The ongoing expression is shown on the screen as the user inputs numbers and operators. 
 2.Displaying the Final Result: Once the user confirms the expression, the result of the evaluated expression is displayed. 
 
 Error Handling: 
 1.If there's an error in the expression (e.g., a syntax issue), it is caught, and an "Error" message is displayed. 
 
 User Input Reset and Exit 
 1.Reset Functionality: If the user presses the 'r' key, the expression and results are reset. 
 2.Exit Functionality: If the user presses the 'q' key, the program exits. 
