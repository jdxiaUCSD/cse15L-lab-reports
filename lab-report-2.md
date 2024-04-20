`class StringHandler implements URLHandler {`
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
}`
