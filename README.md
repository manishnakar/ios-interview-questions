# ios-interview-questions


 1.What is latest iOS version?
		IOS - 6.1.3 (updated on 5/15/13 3:15 AM
		Pacific Daylight Time)
		2.What is latest Xcode version?
		Xcode- 4.6.2 (updated on 5/15/13 3:15 AM
		Pacific Daylight Time)


3.What is latest mac os version?
	 Mac- Mountain Lion (updated on 5/15/13 3:15 AM
	Pacific Daylight Time)

4.What is iPad screen size?
	1024X768

5.what is iPhone screen size?
	320X480

6.What are the features is IOS 6?

	1.Map :beautifully designed from the ground up (and the sky down)
	2.Integration of Facebook with iOS
	3.shared photo streams.
	4.Passbook - boarding passes, loyalty cards, retail coupons, cinema tickets and more all in one place
	5.Facetime - on mobile network as wifi 
	6.changed Phone app - *remind me later,*reply with message.
	7.Mail - redesigned more streamline interface.
	8.Camera with panorama . 

7.Who invented Objective c?
Broad cox and Tom Love

8.What is Cococa and cocoa touch?
Cocoa is for Mac App development  and cocoa touch is for apples touch devices - that provide all development environment 

9.What is Objective c?
*Objective-C is a reflective, object-oriented programming language which adds Smalltalk-style messaging to the C programming language. strictly superset of c.

10. how declare methods in Objective c? and how to call them?
 - (return_type)methodName:(data_type)parameter_name : (data_type)parameter_name

11. What is property in Objective c?
Property allow declared variables with specification like atomic/nonatmic, or retain/assign 

12.What is meaning of "copy" keyword?
copy object during assignment and increases retain count by 1
13.What is meaning of "readOnly" keyword?
 Declare read only object / declare only getter method

14.What is meaning of "retain" keyword?
Specifies that retain should be invoked on the object upon assignment. takes ownership of an object
15.What is meaning of "assign" keyword?
Specifies that the setter uses simple assignment. Uses on attribute of scalar type like float,int.
16.What is meaning of "atomic" keyword?
"atomic", the synthesized setter/getter will ensure that a whole value is always returned from the getter or set by the setter, only single thread can access variable to get or set value at a time
17.What is meaning of "nonatomic" keyword?
In non atomic no such guaranty that value is returned from variable is same that setter sets. at same time

18.What is difference between "assign" and "retain" keyword?

Retain -Specifies that retain should be invoked on the object upon assignment. takes ownership of an object
Assign - Specifies that the setter uses simple assignment. Uses on attribute of scalar type like float,int.

19.What is meaning of "synthesize" keyword ?
ask the compiler to generate the setter and getter  methods according to the specification in the declaration
20.What is "Protocol" on objective c?
A protocol declares methods that can be implemented by any class. Protocols are not classes themselves. They simply define an interface that other objects are responsible for implementing. Protocols have many advantages. The idea is to provide a way for classes to share the same method and property declarations without inheriting them from a common ancestor
21.What is use of UIApplication class?
The UIApplication class implements the required behavior of an application. 
22.What compilers apple using ?
The Apple compilers are based on the compilers of the GNU Compiler Collection.
23.What is synchronized() block in objective c? what is the use of that?
The @synchronized()directive locks a section of code for use by a single thread. Other threads are blocked until the thread exits the protected code.
24. What is the "interface" and "implementation"?
interface declares the behavior of class and implementation defines the behavior of class. 

25.What is "private", "Protected" and "Public" ?
private - limits the scope class variable to the class that declares it.
protected - Limits instance variable scope to declaring and inheriting classes.
public - Removes restrictions on the scope of instance variables

26. What is the use of "dynamic" keyword?
Instructs the compiler not to generate a warning if it cannot find implementations of accessor methods associated with the properties whose names follow.
27.What is "Delegate" ?
A delegate is an object that will respond to pre-chosen selectors (function calls) at some point in the future., need to implement the protocol method by the delegate object.
28.What is "notification"?
provides a mechanism for broadcasting information within a program, using notification we can send message to other object by adding observer .

29.What is difference between "protocol" and "delegate"?
protocol is used the declare a set of methods that a class that "adopts" (declares that it will use this protocol) will implement. 
Delegates are a use of the language feature of protocols. The delegation design pattern is a way of designing your code to use protocols where necessary.

30.What is "Push Notification"?
to get the any update /alert from server .

31.How to deal with SQLite database?
Dealing with sqlite database in iOS:
1. Create database : sqlite3 AnimalDatabase.sql
2.Create table and insert data in to  table :
CREATE TABLE animals ( id INTEGER PRIMARY KEY, name VARCHAR(50), description TEXT, image VARCHAR(255) );

INSERT INTO animals (name, description, image) VALUES ('Elephant', 'The elephant is a very large animal that lives in Africa and Asia', 'http://dblog.com.au/wp-content/elephant.jpg');

3. Create new app --> Add SQLite framework and database file to project
4. Read the database and close it once work done with database :
// Setup the database object
 sqlite3 *database;

 // Init the animals Array
 animals = [[NSMutableArray alloc] init];

 // Open the database from the users filessytem
 if(sqlite3_open([databasePath UTF8String], &database) == SQLITE_OK) {
  // Setup the SQL Statement and compile it for faster access
  const char *sqlStatement = "select * from animals";
  sqlite3_stmt *compiledStatement;
  if(sqlite3_prepare_v2(database, sqlStatement, -1, &compiledStatement, NULL) == SQLITE_OK) {
   // Loop through the results and add them to the feeds array
   while(sqlite3_step(compiledStatement) == SQLITE_ROW) {
    // Read the data from the result row
    NSString *aName = [NSString stringWithUTF8String:(char *)sqlite3_column_text(compiledStatement, 1)];
    NSString *aDescription = [NSString stringWithUTF8String:(char *)sqlite3_column_text(compiledStatement, 2)];
    NSString *aImageUrl = [NSString stringWithUTF8String:(char *)sqlite3_column_text(compiledStatement, 3)];

    // Create a new animal object with the data from the database
    Animal *animal = [[Animal alloc] initWithName:aName description:aDescription url:aImageUrl];

    // Add the animal object to the animals Array
    [animals addObject:animal];

    [animal release];
   }
  }
  // Release the compiled statement from memory
  sqlite3_finalize(compiledStatement);

 }
 sqlite3_close(database);


32.What is storyboard? 
With Storyboards, all screens are stored in a single file. This gives you a conceptual overview of the visual representation for the app and shows you how the screens are connected. Xcode provides a built-in editor to layout the Storyboards.

    .storyboard is essentially one single file for all your screens in the app and it shows the flow of the screens. You can add segues/transitions between screens, this way. So, this minimizes the boilerplate  code required to manage multiple screens.
      2.   Minimizes the overall no. of files in an app.


33.What is Category in Objective c?
A category allows you to add methods to an existing class—even to one for which you do not have the source.
34.What is block in objective c?
Blocks are a language-level feature added to C, Objective-C and C++, which allow you to create distinct segments of code that can be passed around to methods or functions as if they were values. Blocks are Objective-C objects, which means they can be added to collections like NSArray or NSDictionary. They also have the ability to capture values from the enclosing scope, making them similar to closures or lambdas in other programming languages.
35. How to parse xml? explain in deep.

Using NSXMLParser.  
Create xml parser object with xml data, set its delegate , and call the parse method with parserObject.
Delegate methods getting called :
– parserDidStartDocument:
– parserDidEndDocument:
– parser:didStartElement:namespaceURI:qualifiedName:attributes:
– parser:didEndElement:namespaceURI:qualifiedName:
– parser:didStartMappingPrefix:toURI:
– parser:didEndMappingPrefix:
– parser:resolveExternalEntityName:systemID:
– parser:parseErrorOccurred:
– parser:validationErrorOccurred:
– parser:foundCharacters:
– parser:foundIgnorableWhitespace:
– parser:foundProcessingInstructionWithTarget:data:
– parser:foundComment:
– parser:foundCDATA:

36.How to parse JSON? explain in deep.
By using NSJSONSerialization. 
For example : NSArray *jsonArray = [NSJSONSerialization JSONObjectWithData: data options: NSJSONReadingMutableContainers error: &e];

37.How to use reusable cell in UITableview?
By using dequeReusableCellWithIdentifier

38.What is the meaning of "strong"keyword?
*strong -o "own" the object you are referencing with this property/variable. The compiler will take care that any object that you assign to this property will not be destroyed as long as you (or any other object) points  to it with a strong reference.
39.What is the meaning of "weak" keyword? 
*Weak - weak reference you signify that you don't want to have control over the object's lifetime. The object you are referencing weakly only lives on because at least one other object holds a strong reference to it. Once that is no longer the case, the object gets destroyed and your weak property will automatically get set to nil.
40.What is difference strong and  weak reference ? explain.
complier with be responsible for lifetime of object which is declared as strong. for weak object - compiler will destroy object once strong reference that hold weak object get destroyed.

41.What is ARC ? How it works? explain in deep.
Automatic reference counting (ARC)  If the compiler can recognize where you should be retaining and releasing objects, and put the retain and release statement in code.

42. What manual memory management ?  how it work?
In Manual memory management  developers is responsible for life cycle of object. developer has to retain /alloc and release the object wherever needed.

43. How to find the memory leaks in MRC?
By using - 
1.  Static analyzer.
2. Instrument 
44.what is use of NSOperation? how NSOperationque works?
An operation object is a single-shot object—that is, it executes its task once and cannot be used to execute it again. You typically execute operations by adding them to an operation queueAn NSOperationQueue object is a queue that handles objects of the NSOperation class type. An NSOperation object, simply phrased, represents a single task, including both the data and the code related to the task. The NSOperationQueue handles and manages the execution of all the NSOperation objects (the tasks) that have been added to it.
45.How to send crash report from device?

46.What is autorealease pool?
Every time -autorelease is sent to an object, it is added to the inner-most autorelease pool. When the pool is drained, it simply sends -release to all the objects in the pool.
Autorelease pools are simply a convenience that allows you to defer sending -release until "later". That "later" can happen in several places, but the most common in Cocoa GUI apps is at the end of the current run loop cycle.
47.What happens when we invoke a method on a nil pointer?

48.Difference between nil and Nil.
Nil is meant for class pointers, and nil is meant for object pointers
49.What is fast enumeration?
for(id object in objets){
}

50. How to start a thread? 
- (void)performSelectorInBackground:(SEL)aSelector withObject:(id)arg on NSObject
  NSThread* evtThread = [ [NSThread alloc] initWithTarget:self
                            selector:@selector( saySomething )
                          object:nil ];
    [ evtThread start ];

51.How to download something from the internet?
By Using NSURLConnection , by starting connection or sending synchronous request.

52.what is synchronous web request and asynchronous ?
In  synchronous request main thread gets block and control will not get back to user till that request gets execute.
In Asynchronous control gets back to user even if request is getting execute.

53. Difference between sax parser and dom parser ?
SAX (Simple API for XML)

    Parses node by node
    Doesn't store the XML in memory
    We can not insert or delete a node
    Top to bottom traversing


DOM (Document Object Model)

    Stores the entire XML document into memory before processing
    Occupies more memory
    We can insert or delete nodes
    Traverse in any direction


54.Explain stack and heap?


55.What are the ViewController  lifecycle in ios?
loadView - viewDidLoad-viewWillAppear-viewDidAppear - viewDisappear  - viewDidUnload

56.Difference between coredata & sqlite?

There is a huge difference between these two. SQLLite is a database itself like we have MS SQL Server. But CoreData is an ORM (Object Relational Model) which creates a layer between the database and the UI. It speeds-up the process of interaction as we dont have to write queries, just work with the ORM and let ORM handles the backend. For save or retrieval of large data, I recommend to use Core Data because of its abilities to handle the less processing speed of IPhone.


57.Steps for using coredata?
NSFetchedResultsController - It is designed primarily to function as a data source for a UITableView

58.Procedure to push the app in AppStore?

59.What are the Application lifecycle in ios?
ApplicationDidFinishLaunchingWithOption -ApplicationWillResignActive- ApplicationDidBecomeActive-ApplicationWillTerminate


60.Difference between release and autorelease ?
release - destroy the object from memory,
autorelease - destroy the object from memory in future when it is not in use.

61.How to start a selector on a background thread
- (void)performSelectorInBackground:(SEL)aSelector withObject:(id)arg on NSObject

62.What happens if the methods doesn’t exist
App will crash with exception unrecognized selector sent to instance.

63. How Push notification works?
Server - Apple server - device by using APNs

