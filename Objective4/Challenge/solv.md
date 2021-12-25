# Goal 

Reach 1000$ in the "Casino Spin Game"

# How

Use Parameter tampering using a web proxy ( I used Burp Suite ) 

See burpSolution.png to understand

Modify a parameter into a negative number. Since it remove the value of the bet to the "wallet" when you loose. If the value is negative you actually win money ! 

And finally check the Response and enter it in the game. 
