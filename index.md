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
