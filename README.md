# StageNameCall
Java project



Design document

Java project done for my course. Logical ways to check what we’ve (supposed) to learn and know by this stage and trying to remember the rules. 
After hours of reading and (trying) understanding, I did my first attempt.
package exercise;
import java.util.Random;
import java.util.Scanner;

public class Exercise {
public static void main(String[] args) {

  Scanner kBoard = new Scanner (System.in);

  System.out.println("How many stage names do you need?");
  
  int times = kBoard.nextInt();
   
  String userNameIn="";
  String userLastname = ""; 
       
  for(int i = 0; i<times; i++){
    System.out.println("Please enter your name: ");
    userNameIn = kBoard.next();
    userLastname = kBoard.next();
  }
String[] stageNames = { "Monkey", "Lover", "Mouse", "Lipstick", "Wallet", "Cent",
                          "Keychain", "Scooby", "Hawkeye", "Captain", "Marvel", "Thor", 
 "Antman", "Storm", "Xavier", "Cat", "Wolverine", "Thanos", "Iron Man", 
"Hulk", "BlackWidow", "Abyss", "Ace", "Cyclops", "ProfessorX", "Pheonix", 
"Nightcrawler", "Rouge", "Magneto", "Mystique", "Quicksilver" };
       
Random r=new Random();
int randomNumber=r.nextInt(stageNames.length);
 String gangstaName = new String();
  {
 gangstaName = userNameIn.charAt(0).toUpperCase() + "" + stageNames[randomNumber] + "" + userLastname.toUpperCase()+ "" + userNameIn.toLowerCase()+"" + stageNames[randomNumber];
System.out.println("Your new stage name is " + "" + gangstaName); }

When I finally made the string gangstaName and it worked! I realized my string is always calling on the same random number. So, I realized I have to make two different Randoms so it can be called as a different random (randomNumber and randomNumberTwo) 
By the end of it my input looked like this:
How many stage names do you need?
2
Please enter your name: 
mike love
Please enter your name: 
konan barbarin
Your new stage name is K Quicksilver BARBARIN konan Monkey
BUILD SUCCESSFUL (total time: 12 seconds)
____________________________________________________________________
Yay! Almost there. SO now what is left is to arrange the code in a loop so that it can call string gangstaName for every input user makes.
I realized my for- loop is looping only user input. After that code runs further and executes everything else, but it doesn’t apply to ever user input.
I had to use google a lot and logic: why is my rule only applied to one (last) user input??? So I decided to change my string (userNameIn and userLastname) to array. Why? Because that way I will have an allocated “space in memory” for every input user makes and I can use the index value which will be remembered and not overwritten this time.
I’m finally in control! So, I declared my array names and inside for loop gave it a value to intake user input (first name), space in between and user input again (last name). This was after I realized that if I only have one input (kBoard.next) it will only take one name (for example “Joe” and not “Joe Bloggs”)
After that I put my string array with made up stage names, I declared random integers without a value (randomNumber and randomNumberTwo) and 3 strings that I will give a value in my next for loop.
After creating for loop, I assigned the value for my ints (take the random name from my stageNames array) and I made a line that looked like this:


gangstaName = names[i].substring(0, 1).toUpperCase() + " " 
    + stageNames[randomNumber] + " " 
    +names[i].substring(names[i].indexOf(" ")+1).toUpperCase()+ " " 
    +names[i].substring(0,names[i].indexOf(" ")).toLowerCase()+ " " 
    + stageNames[randomNumberTwo];
The most complicated thing to understand was how to tell the program: hey do you remember that user input? Well I want exactly x or y on this position. IDE and the hints helped a lot. names[i] – call the array, .substring(names[i].indexOf(“ “)+1). So after calling the array, display index number of everything after space (“ “) + 1 position (Joe Bloggs, space is on 3rd position, I need 4th ) and make it upper case. YAY! 
But still too messy. I want to make my gangstaName neater, so I would need to declare empty strings that will contain values explained above and then just call said strings.
End product:
lastName = names[i].substring(names[i].indexOf(" ")+1);
firstName = names[i].substring(0,names[i].indexOf(" "));
gangstaName = firstName.substring(0, 1).toUpperCase() + " " 
    + stageNames[randomNumber] + " " 
    + lastName.toUpperCase()+ " " 
    + firstName.toLowerCase()+ " " 
    + stageNames[randomNumberTwo];
Add some output print lines in between for loops and that’s it. 
I looked at our roboBar exercise and folder and wanted to make the same thing. So, following the logic on that one, I created another file in same folder, called it exerciseCall, made main method inside it, made new object and called in a class Exercise. And I changed my main method that was still in my file exercise to public void Snoop() and called that method in my new exerciseCall file. 
Since that was filled with comments and different messy trys, I made a new folder stageNameCall and that is my final submission.
Thank you for your time.

