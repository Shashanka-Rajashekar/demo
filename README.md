# demo- <br> github
package lab6.lab6;



import java.io.FileReader;

import java.io.IOException;



import org.json.simple.JSONObject;

import org.json.simple.parser.JSONParser;

import org.json.simple.parser.ParseException;

public class demo {

    public static void main(String[] args) throws IOException, ParseException {

        JSONParser jsonParser = new JSONParser();

        

        try (FileReader reader = new FileReader(".\\JSON\\demo.json")) {

            Object obj = jsonParser.parse(reader);

            

            JSONObject empJsonObject = (JSONObject) obj;

            

            String fname = (String) empJsonObject.get("first name");

            String lname = (String) empJsonObject.get("last name");

            

            System.out.println("First name: " + fname);

            System.out.println("Last name: " + lname);

            

        } catch (IOException | ParseException e) {

            e.printStackTrace();

        }

    }


}
FROM openjdk 
WORKDIR /app
COPY . /app
RUN javac pr.java
CMD ["java","pr"]




class pr {
  public static void main(String[] args) {
    
    System.out.println(" google ");
    
  }
} 

docker build -t prog .
docker run --name gs prog


---------------------------------

docker images
//take image id

docker tag <imageid> accountname/prog
docker login
// it will ask username password
docker push docker.io/accountname/prog

docker pull mysql
