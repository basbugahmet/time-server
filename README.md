# TIME SERVER
The objective is to create a simple time server that communicates with a client using the "telnet" console command on a Linux machine. The server will respond to date requests from the client by utilizing the "date" command to generate the correct output. The communication will occur over port 60000, and the server should close the port when it receives the "CLOSE_SERVER" command from the client.

Here is a basic outline of how the server should function:

1.  **Define Constants:**
    
    -   `#define PORT_NUMBER 60000`: Specifies the port number to be used by the server.
2.  **Server Implementation:**
    -   The server will create a socket, bind it to the specified port, and listen for incoming connections.
    -   When a connection is accepted, the server will communicate with the client and handle date requests.
3.  **Communication Protocol:**
    -   The server expects the client to send specific commands for date requests.
    -   Examples of valid commands and server responses:
        -   `GET_TIME`: Server responds with the current time (e.g., "13:45:56").
        -   `GET_DATE`: Server responds with the current date (e.g., "13.01.2023").
        -   `GET_TIME_DATE`: Server responds with both the current time and date (e.g., "13:45:56, 13.01.2023").
        -   `GET_TIME_ZONE`: Server responds with the current time zone (e.g., "+03:00").
        -   `GET_DAY_OF_WEEK`: Server responds with the current day of the week (e.g., "Friday").
        -   `CLOSE_SERVER`: Server responds with "GOOD BYE" and closes the connection and the port.
4.  **Handling Incorrect Requests:**
    -   If the client sends any other input or incorrect requests, the server responds with "INCORRECT REQUEST" without further explanation.
5.  **Closing the Server:**
    -   The server should close the port when it receives the "CLOSE_SERVER" command from the client to ensure that the port is released for future use.
