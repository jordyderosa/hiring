# Bluetel Salesforce Candidate Questionnaire

Thanks for taking interest in a position at Bluetel! Answering this set of questions gives us a good idea about your technical and logical capabilities; as well as a couple of personal characteristics. You can be as brief or comprehensive as you wish in your answers. We don’t expect every candidate to know all the answers to these questions, so please don’t be discouraged if you don’t know the answer! Good luck!  

### Question 1
Create an algorithm that prints the integers from 17 to 53. However for multiples of two, print "Foo" instead  of the number and for multiples of five print "Bar". For numbers which are multiples of both two and five print "FooBar". 
### Answer 1
<?php
  for($i=17;$i<54;$i++)
  {
      //check if it's a multiple of 2
      if($i%2==0)
      echo "$i)Foo";
      //check if it's a multiple of 5
      if($i%5==0)
      echo "$i)Bar";
      //check if it's a number that isn't a multiple of 2 and 5
      if($i%2!=0 && $i%5!=0)
      echo "$i)";
      //just a line break
      echo "<br>";
  }
?>

### Question 2
In a relational database, why is redundant data (i.e. the same data stored in multiple tables) generally a bad thing?
### Answer 2
In a relationa db it's not a good idea having duplicated data and mainly because:
1)having duplicated data means have the same information stored in our DB and this increase the DB space uselessly
2)more space means higher costs for company
3)more data means slow queries and bad performances
4)it could be hard to update,modify or delete all duplicated data
This is the first 4 things that i have found . If you need to have redundant data maybe you can choose a NoSQL db that are designer to do that but they need more space.

### Question 3
In a relational database, why might redundant data be necessary in real world applications?
### Answer 3
i'm thinking about queries performance: if i have to access to 2,3,...10 tables with a JOIN to retrieve my information my query could be too slow. In this case duplicate data could speed up my query because i have to JOIN less tables. 

### Question 4
In development teams, multiple people are often involved in building and maintaining a single salesforce instance. They may be working on a single task together, or multiple tasks, and changes made by one developer may conflict with those of another. What system would you suggest to help manage this, and why would you choose your solution in particular?
### Answer 4
I think that a team should work on a single task together , task by task as a Scrum Team . Following Scrum Theory it speed up the process and can't generate conflict between developers. Speeding up process means a faster return of investment. Working alone could create competition between the people and in rare case this is a good thing. This is why a lot of company works with Scrum or Agile method.

### Question 5

The below Salesforce Apex code may fail on any line with a `DMLException`. Modify the code to ensure that if it were to fail then no data would be saved.

```c#
try {
  Database.insert(action);
  Database.update(actionPlan);
  Database.update(customer);
} catch (DmlException e) {
  //no action 
    System.debug('Exception occurred: ' + e.getMessage());
}
```

### Question 6

What is the difference between `Trigger.old` and `Trigger.new`? Under which types of trigger are they each available?
### Answer 6
Trigger.new returns a list of the new versions of an object and is only available in insert and update triggers while Trigger.old returns a list of the old versions of an object and is only available in update and delete triggers

### Question 7
Provide Salesforce Apex code which uses SOQL to extract the following fields from a custom object named `Visitors` into a List variable. Only records where the value of the `Company__c` field is equal to `Bluetel` should be retrieved.

- Id
- Name
- Visit_Time__c
- Visiting__c

### Answer 7
List <Visitors> VisitorsObjects = [select Id,Name, Visit_Time__c, Visiting__c from Visitors where Company__c = 'Bluetel'];

for(Visitors visitors : VisitorsObjects)
{
    System.debug('Id: ' + visitors.id + ',Name: '+ visitors.Name + ',Visit_Time__c:'+visitors.Visit_Time__c + ',Visiting__c:'+visitors.Visiting__c);
}


### Question 8

The following provides one test scenario for the requirement `Insurance Requests for amounts less than $100,000 should not be submitted to the insurer, and the user should be presented with an error if they attempt to make this submission`. Summarise the minimum test cases that you would define for the <u>entire</u> requirement.

> **Given** I am completing an insurance request 
>
> **When** I specify a cover amount of less than $100,000
> **AND** I choose to submit my request
>
> **THEN** I should receive an error 
> **AND** the request should not be submitted

### Answer 8
Sorry , i don't know how to answer , i haven't experiences with salesforce but i can study it and get ready quickly if needed.

