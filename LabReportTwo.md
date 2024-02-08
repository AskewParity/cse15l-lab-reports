# Lab 3

## Part 1

***
### Code 

```java
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;
import java.util.List;

class Handler implements URLHandler {
  List<String> chatlog = new ArrayList<>();

  public String handleRequest(URI url) {
    if (url.getPath().equals("/")) {
      return String.format("chatlog size: %d", chatlog.size());
    } else {
      // handles adding messages in the form "/add-message?s=MESSAGE&user=USERNAME"
      if (url.getPath().contains("/add-message")) {
        String[] parameters = url.getQuery().split("=");

        if (parameters.length < 3 || !parameters[0].equals("s")) {
          return "400 Bad Request";
        }

        String[] middleTerm = parameters[1].split("&");

        if (middleTerm.length < 2 || !middleTerm[1].equals("user")) {
          return "400 Bad Request";
        }

        String message = middleTerm[0];
        String user = parameters[2];

        chatlog.add(String.format("%s: %s", user, message));

        return printLog();
      }
      return "404 Not Found!";
    }
  }

  private String printLog() {
    String log = "";

    for (String str : chatlog) {
      log += str + "\n";
    }

    return log;
  }
}

class ChatServer {
  public static void main(String[] args) throws IOException {
    if (args.length == 0) {
      System.out.println("Missing port number! Try any number between 1024 to 49151");
      return;
    }

    int port = Integer.parseInt(args[0]);

    Server.start(port, new Handler());
  }
}
```

### Examples

![image](https://github.com/AskewParity/cse15l-lab-reports/assets/147351354/80f8110a-7880-4c47-b18f-1a59a756cbe3)

The methods run are `handleRequest()` and `printLog()`. 

There was a `URI` or a universal resource identifier passed into `handleRequest()`, the `URI` is a string that has predefined methods to get specific parts that are relevant to the actions for reading and manipulating the `URI`.

Within the `URI`, the relevant components were `s=Hello` and `user=jpolitz` where `s` refered to the message and `user` refered to the user. The List `chatlog` was empty before the screenshot, but now has a new string element at index 0, composed of "user: s" or "jpolitz: Hello" in this case. The result of this change is displayed in the text printed (each line cooresonds to the nth elmenet in `chatLog`).

![image](https://github.com/AskewParity/cse15l-lab-reports/assets/147351354/91df55b3-e861-43be-93df-2e5b447a6bff)

There was a `URI` or a universal resource identifier passed into `handleRequest()`, the `URI` is a string that has predefined methods to get specific parts that are relevant to the actions for reading and manipulating the `URI`.

The methods run are `handleRequest()` and `printLog()`. The relevant argumetns passeed in were `s=How are you` and `user=yash` where `s` refered to the message and `user` refered to the user. The List `chatlog` is changed as a string documenting this message is put into the List; specifically, there is already an existing elmeent, and this is added strictly added after the previous message at index 1, composed of "user: s" or "yash: How are you" in this case. The result of this change is displayed in the text printed (each line cooresonds to the nth elmenet in `chatLog`).

## Part 2

***

![image](https://github.com/AskewParity/cse15l-lab-reports/assets/147351354/57421f01-b1bd-4b8c-843b-1a983dcade49)

![image](https://github.com/AskewParity/cse15l-lab-reports/assets/147351354/a5648017-ae43-4baa-984e-b53e3e4b566f)


The private key is `id_rsa` on my local machine whereas the public key on the server `ieng6` is `authorized_keys` 

- Absolute path of private key: `/Users/chris/.ssh/id_rsa`
- Absolute path of publid key: `/home/linux/ieng6/oce/69/chl225/.ssh/authorized_keys`


![image](https://github.com/AskewParity/cse15l-lab-reports/assets/147351354/87cafb48-f575-436a-b3ad-2b244dc3ee7d)

Here, I log into an `ieng6` without needed to provide a password (because my public key is stored on the server).

> ignore `Fig` and `Kitty`, they are some issues from my local setup

## Part 3

***

I didn't know how to copy files between two machines. Now, using the `scp` command, I can interface between my machines, and not just work in sandboxes (the machines themselves). This enables me to work in one environment when its convinient to, and then switch to the other if I need something (or space) that doesn't exist on the original machine. 
