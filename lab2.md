# Lab Report 2

**Part 1**
**Code of** `ChatServer`
```
import java.io.IOException;
import java.net.URI;

class Handler implements URLHandler {
    String chat = "";

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return "No message entered yet.";
        }
        if (url.getPath().equals("/add-message")) {
            String query = url.getQuery();

            int firstEqual = query.indexOf('=');
            int ampersand = query.indexOf('&');
            int secondEqual = query.lastIndexOf('=');

            String message = query.substring(firstEqual + 1, ampersand);
            String user = query.substring(secondEqual + 1);

            chat += user + ": " + message + "\n";

            return chat;
        }
        return "404 Not Found!";
    } 
}   


class ChatServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new Handler());
    }
}
```

