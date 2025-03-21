## Array
```Java
String[] cars; //declares the array

String[] cars = {"Volvo","BMW","Ford","Mazda"};//instatiates the cars array 

cars[0] = "Lamborghini"; //changes array[0]

cars.length; //gets the length of the array cars (even if inside is empty/null)

for (int i = 0; i < cars.length; i++) { //loops cars.length times
	//do something
}

for (String car: cars) { //loops through as a "for-each" loop
	//do something
}

int[][] myNumbers = {{1,2,3,4},{5,6,7,8}} // 2D array

myNumbers[0,3] //accesses 4

for (int[] row: myNumbers) { //loops through the rows in myNumbers (make sure type is of int[])
	for (int num: row) { //loops through the numbers 
		//do something
	}
} 
```

## Math
```Java
Math.max(num1,num2); //gets the max 
Math.min(num1,num2); //gets the min
Math.sqrt(num1,num2); //gets the square root
Math.abs(-4.5); gets the absolute value
```

## String
```Java
String txt = "Random String";
txt.indexOf("String"); //returns 7, the index of the Starting letter S

//to get length
txt.length(); //gets the length of the string

String firstName = "John";
String lastName = "Doe";
String newString = firstName + " " + lastName; // O(m + n) where m is firstName.length and n is lastName.length

for (int i = 0; i < newString.length(); i++) { //prints out all the String character by character
	char result = newString.charAt(i);
	System.out.println(result);
}

char result = newString.charAt(0); //gets the character at index 0

char result = newString.charPointAt(0); //gets the unicode(ascii) at index 0

String str1 = "hello";
String str2 = "hello";

System.out.println(str1.equals(str2)); //compare two Strings

//checks if a string contains "hel" O(n)
myStr.contains("hel"); //returns true 

//starts with and ends with
str1.startsWith("hel") //returns true
str1.endsWith("llo") //returns true

List<String> words = List.of("apple", "banana", "cherry");
String result = String.join(" ", words); //String.join with " " as delimiter

String newStr = String.valueOf(true); //changes true to string

String otherStr = newStr.toUpperCase() //changes to upper case

char[] myArray = result.toCharArray(); //gets char array of words 
// {'a','p','p','l','e',...}
//can now change the contents of the String

//to convert back
String backToString = new String(myArray)//back to String

String xStr = backToString.trim() //trims the String


```

## ArrayList
```Java
ArrayList<String> cars = new ArrayList<>(); //only takes in Objects as its elements

//to append
cars.add("New car");

//to access by index
cars.get(0);

//to change - changes element at index 0 to "Opel"
cars.set(0,"Opel");

// to remove - removes at index 0 
cars.remove(0);

//to remove all elements
cars.clear()

//to get length
cars.size()

//sorting
Collections.sort(cars); //sorts in ascending order

//sorting for reverse order
Collections.sort(cars,Collections.reverseOrder()); 


//instatiate a list of zero's
ArrayList<Integer> newList = new ArrayList<>(Collections.ncopies(10,0));
//where first argument (0) is the number of copies, and second argument is the value

```

## HashMap
```Java
HashMap<String, String> capitalCities = new HashMap<>();
// sets the key value in hashmap
capitalCities.put("Key","Value");

//gets the value using key
capitalCities.get("Key"); //if key not in hashMap, returns null

//using getOrDefault
capitalCities.getOrDefault("Key",0); //returns 0 if key not in hashmap

// remove an item (removes item with key = "Key" )
capitalCities.remove("Key"); 

//gets size of hashMap
capitalCities.size()

//iterating through all the keys
for (String i : capitalCities.keySet()) {
	//do something
}

//iterating through all the values
for (String i : capitalCities.values()) {
	//do something
}
```

## HashSet
```Java
//instatiate hashSet

HashSet<String> cars = new HashSet<String>(); //create set that can contain strings

cars.add("Mazda"); //adds O(1)

cars.remove("Volvo"); //removes O(1)

cars.size(); //O(1) returns length

cars.contains("Mazda"); //checks if it contains

HashSet<String> hs1 = new HashSet<String>();
hs1.add("Pen");
hs1.add("Paper");
hs1.add("Pencil");
hs1.add("Rubber");

HashSet<String> hs2 = new HashSet<String>();
hs2.add("Pen");
hs2.add("Paper");

hs1.retainAll(hs2); //hs1 only retains the intersection of itself and hs2
```


## Stacks
```Java
Stack<Integer> stack = new Stack<>();

//pushing O(1)
stack.push("Item");

//popping O(1)
String popped = stack.pop()

//peeking O(1)
String peeked = stack.peek()

stack.isEmpty() //returns whether stack is empty or not
```

## Queues
```Java
Queue<Integer> queue = ArrayDeque<>(); //instatiating and deque

//to add to end of queue
queue.add();

//to remove from start of queue
queue.poll();

//to peek 
queue.peek()

queue.isEmpty(); //returns boolean 
```

## Priority Queues(heap)
```Java
Queue<Integer> queue = PriorityQueue<>();

//to add
queue.add()

//to pop
queue.poll()

//to peek
queue.peek()


queue.isEmpty(); //returns boolean 
```

