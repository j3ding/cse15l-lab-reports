# ***Hello, world!***

---
# **Lab Report 2**

## ***Part One***
In this part, write a `StringServer.java` web server in `wavelet` and expect to print input strings on the page.
* The request format should be like this: `/add-message?s=XXX` where XXX stands for the input string. Write the code like this.
```
public String handleRequest(URI url) {
    if (url.getPath().equals("/")) {
        return String.format("My String: \n%s", str);
    } else if (url.getPath().equals("/increment")) {
        num += 1;
        return String.format("Number incremented!");
    } else {
        System.out.println("Path: " + url.getPath());
        if (url.getPath().contains("/add-message")) {
            String[] parameters = url.getQuery().split("=");
            if (parameters[0].equals("s")) {
                str += parameters[1] + "\n";
                return String.format("New string implemented! It's now \n%s", str);
            }
        }
        return "404 Not Found!";
    }
}
```
```
class StringServer {
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

Then, to see and change the website, compile in the terminal in VScode. Type this in the terminal.
```
javac Server.java StringServer.java
java StringServer 8000
```

`8000` is the port number (can try other numbers, but suggest to choose higher numbers), then the terminal gives a link `http://localhost:8000`(Command + Click to open it), and the page should be like this.
![2-1-1](https://user-images.githubusercontent.com/122497181/215298931-88d81e51-1347-45c4-84d3-5d8f8c7f627f.png)
* Now type in the URL to append strings to the page. In this case, type `http://localhost:8000/add-message?s=Hello` to input the string `Hello` and press Enter. \
This line calls the `handleRequest(URI url)` method, and the relevant argument is the entire `else{...}` portion where `Hello` is `parameter[1]`. The string `str` changes from ` ` to `\n Hello \n`. \
Then, can visit this link, which look like the following in the page.
![2-1-2](https://user-images.githubusercontent.com/122497181/215298932-04c847ec-3eb0-402e-9ca9-926b568b25e6.png)
* Repeat the previous step several times to append more strings. For example, enter `http://localhost:8000/add-message?s=Welcome!` to input `Welcome!`. \
This line calls the `handleRequest(URI url)` method, and the relevant argument is the entire `else{...}` portion where `Welcome!` is `parameter[1]`. The string `str` changes from `\n Hello \n` to `\n Hello \n Welcome! \n`. \
Visit the page, which should be like this. 
![2-1-3](https://user-images.githubusercontent.com/122497181/215298933-7547abfe-af19-42c5-9155-e4fec4280514.png)
* To check the current string, enter `http://localhost:8000/` in the terminal, and the page should look like this.
![2-1-4](https://user-images.githubusercontent.com/122497181/215298934-aed7d6d9-2ae2-4a89-b7ec-33eda93bb72c.png)
* All of these commands in the terminal should look like this:
![2-1-5](https://user-images.githubusercontent.com/122497181/215298935-69b92ba2-eb5c-41c9-b1e9-e0bd11733f1e.png)
Note: If want to stop, press Control + C.
