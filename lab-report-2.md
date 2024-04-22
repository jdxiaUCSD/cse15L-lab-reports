# Lab 2 

## Part 1:
### `ChatServer` Server Contents With Helper Method `StringHandler`

```
class StringHandler implements URLHandler {
    List<String> lines = new ArrayList<>();
    public String handleRequest(URI url){
        if (url.getPath().equals("/")){
            String toBeShown ="";
            for (String line:lines){
                toBeShown += line + "\n";
            }
            return toBeShown;
        }
        String query = url.getQuery();
        if (url.getPath().equals("/")) {
            return null;
        }
        if (query==null){
            return "use /add-message to chat";
        }
        String[] queries = query.split("&");
        if (url.getPath().equals("/add-message")) {
            if (queries[0].startsWith("s=")) {
                String toAdd = queries[0].split("=")[1];
                if (queries[1].startsWith("user=")){
                    toAdd = queries[1].split("=")[1] + ": " + toAdd;
                    lines.add(toAdd);
                    String toBeShown ="";
                    for (String line:lines){
                        toBeShown += line + "\n";
                    }
                    return toBeShown;
                }
                else{
                    return "must include user query parameter user =";
                }
            }
        else {
          return "Chatting requires a query parameter /add-message\n";
        }
      }
        return null;
    }
}
class ChatServer {
    public static void main(String[] args) throws IOException {
        if(args.length == 0){
            System.out.println("Missing port number! Try any number between 1024 to 49151");
            return;
        }

        int port = Integer.parseInt(args[0]);

        Server.start(port, new StringHandler());
    }
}
```

### Chat Server Examples
1.
![Chat Server Example 1](https://github.com/jdxiaUCSD/cse15L-lab-reports/blob/main/Image%202.jpg)
a. I utilize a `main` method and a method called `handleRequest`.

b. The `main` method takes in an integer to create a port. The `handleRequest` method takes in a url as an argument. For this example, the `main` method took in the integer 4005 to create a port at this address. The `handleRequest` took in the url. "http://localhost:4005/add-message?s=Hey!&user=User2". The class field `lines` holds all of the chat logs of this server. 

c. This request changed the `URI` url to "http://localhost:4005/add-message?s=Hey!&user=User2", the `lines` field to include the `String` "User1: Hi!", and the `String[]` "queries".

2.
![Chat Server Example 2](https://imgur.com/a/V80CrCi)
a. I utilize a `main` method and a method called `handleRequest`.

b. The `main` method takes in an integer to create a port. The `handleRequest` method takes in a url as an argument. For this example, the `main` method took in the integer 4005 to create a port at this address. The `handleRequest` took in the url. "http://localhost:4005/add-message?s=Hi!&user=User1". The class field `lines` holds all of the chat logs of this server. 

c. This request changed the `URI` url to "http://localhost:4005/add-message?s=Hi!&user=User1", the `lines` field to include the `String` "User2: Hey!", and the `String[]` "queries".

## Part 2

1. ![Alt Text1](./Image 4-19-24 at 6.58 PM (1).jpg)

2. ![Alt Text1](https://github.com/jdxiaUCSD/cse15L-lab-reports/blob/main/Image%204-19-24%20at%207.55%20PM.jpg)

3. ![Alt Text3](https://github.com/jdxiaUCSD/cse15L-lab-reports/blob/main/Image%204-19-24%20at%207.44%20PM.jpg)

## Part 3

I didn't know that urls and an internet brower's search tools could be used to manipulate code. I thought that the integration of CS principles I'm learning in my classes being tied to my everyday applications of the web was very interesting.
