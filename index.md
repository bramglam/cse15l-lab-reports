# Lab Report #2

##Part 1:

```
import java.io.IOException;
import java.net.URI;
import java.util.ArrayList;

class Handler implements URLHandler {
    // The one bit of state on the server: a number that will be manipulated by
    // various requests.
    ArrayList<String> allStrings = new ArrayList<String>();

    public String handleRequest(URI url) {
        if (url.getPath().equals("/")) {
            return String.format("Welcome! This is my search engine :)");
        } else if (url.getPath().equals("/add")) {
            String[] parameters = url.getQuery().split("=");
            if (parameters[0].equals("s")) {
                    allStrings.add(parameters[1]);
                    return String.format(parameters[1] + " added to catalog");
                }
        } else if (url.getPath().equals("/search")){
            String[] parameters = url.getQuery().split("=");
            String appendSearch = "";
            if (parameters[0].equals("s")) {
                    for(int i = 0; i < allStrings.size(); i++){
                        if(allStrings.get(i).contains(parameters[1])){
                            appendSearch = appendSearch.concat(allStrings.get(i) + " ");
                        }
                    }
                    
                    return String.format("This is your list of words that contain " + parameters[1] + ": " + appendSearch);
                }

        }else{
            System.out.println("Path: " + url.getPath());
            String allEntries = "";
            if (url.getPath().contains("/allEntries")) {
                for(int i = 0; i < allStrings.size(); i++){
                    allEntries.concat(allStrings.get(i));
                }
            }
            return String.format("Entries: " + allEntries);
        }
        return "404 Not Found!";
    }
}

class SearchEngine {
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

<img width="1440" alt="Screen Shot 2022-10-28 at 9 01 52 PM" src="https://user-images.githubusercontent.com/75295066/198813120-d646cc44-7ad3-4012-997e-ebda1892a9aa.png">





<img width="1440" alt="Screen Shot 2022-10-28 at 9 03 15 PM" src="https://user-images.githubusercontent.com/75295066/198813127-b403a765-1caa-447e-a836-8a99f981f3f4.png">


* The add method was used in this image
* The string value s is "anewstringtoadd"
* The string value does not update by the end

<img width="1440" alt="Screen Shot 2022-10-28 at 9 03 31 PM" src="https://user-images.githubusercontent.com/75295066/198813130-66204cf1-52c0-468e-8ee8-78ea08c4520e.png">


* The add method was used in this image
* The string value s is "apple"
* The string value does not update by the end

<img width="1440" alt="Screen Shot 2022-10-28 at 9 03 31 PM" src="https://user-images.githubusercontent.com/75295066/198813297-65bf38eb-cbce-4490-b28a-099f56fec5fe.png">

* The add method was used in this image
* The string value is "app"
* The string value updats to apple by the end of running the command

##Part 2




