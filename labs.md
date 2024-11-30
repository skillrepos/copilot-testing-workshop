# Testing with GitHub Copilot Workshop
## Revision 1.1 - 11/29/24

**Follow the startup instructions in the README.md file IF NOT ALREADY DONE!**

**NOTE: To copy and paste in the codespace, you may need to use keyboard commands - CTRL-C and CTRL-V.**

**Lab 1 - Using Copilot to create tests**

**Purpose: In this lab, we'll see basic ways to have Copilot create tests for us.**

1. In our repository, there is an example Python file named *prime.py* that we'll be starting with. You can open it by clicking on [**prime.py**](./prime.py) , or, in the terminal, enter

```
code prime.py
```

2. First, let's see how to use the context menu to generate some tests. Highlight the code in the *prime.py* file, right-click on it, then select *Copilot* and then *Generate Tests*. After a moment, Copilot should generate some basic tests in another temporary file to the right.

![using the context menu to gen tests](./images/new-tests-context-menu.png?raw=true "using the context menu to gen tests")

3. You can scroll down and look at the output. We're going to use the shortcut command to generate the final file we want. So, just click on the *Discard* button and then click at the top to close the proposed *test_prime.py* file. We don't need to save it.

![discard suggested tests](./images/new-discard-and-close-suggested-tests.png?raw=true "discard suggested tests")

4. Now, let's use the shortcut command */tests* to generate some tests. In the same prime.py file, highlight the code and use the *CMD+I* shortcut to bring up the inline chat dialog. In the text entry box for the dialog, enter the */tests* command and click on the arrow on the right at the end to submit it.

![using the shortcut command to gen tests](./images/new-slash-tests-command.png?raw=true "using the shortcut command to gen tests")

5. After running the command, Copilot generates some basic assert-based tests in a new file. You can just save this file as *test_prime.py*. To do this, click on the *3-bar* menu in the upper left corner of the codespace, then click *File*, then *Save As* (or use the menu shortcut). Reply yes to the dialog asking about saving AI-generated results.
   
![proposed tests into new file](./images/new-slash-tests-output.png?raw=true "proposed tests into new file")
![saving file](./images/new-save-test_prime.png?raw=true "saving file")


6. We can also use comments to have Copilot create tests. Let's try this in the original *prime.py* file. Under the code, add a comment line that tells Copilot to create tests for the code above.

```
# Create tests for the code above
```

![tests from comments](./images/ct74.png?raw=true "tests from comments")

7. Hit return (if you haven't). Copilot may supply a generic testing routine, such as below, the start of a routine, or a set of actual assert-based tests (NOTE: if you only get a blank line at first, try hitting return again to see if it starts filling in the function on the second line):

```
def test_is_prime(number, expected):
    result = is_prime(number)
    assert result == expected, f"Expected {expected} but got 
{result}"
```

8. Depending on your particular comment and context, Copilot may produce a more generic testing function or a set of individual test cases. To ensure you get the latter,  delete the generated code from the previous comment and redo the steps with this comment. (You may need to hit return again and give Copilot a few seconds to generate the tests.)

```
# Create a set of 10 unit tests for the code above
```

9. In this case, Copilot will usually generate a more explicit set of tests wrapped in a testing function. An example is shown next.You can delete them after looking at them since we already have other tests.

![test by comment](./images/ct14.png?raw=true "test by comment")    

<p align="center">
**[END OF LAB]**
</p>
</br></br>


**Lab 2 - High-level Copilot Testing Advice**

**Purpose: In this lab, we’ll start to learn about getting more general assistance from Copilot for testing**

1. In our repository, there is an example Python file we'll be using to start with. You can open it by clicking on [**webscraper.py**](./webscraper.py) , or, in the terminal, enter

```
code webscraper.py
```
 
2. Let's ask Copilot for some general testing advice for this code. Switch to the separate chat area, and ask it:

```
How can I test #file:webscraper.py?
```

![query in chat](./images/new-how-to-test-select-file.png?raw=true "query in chat")

3. Copilot will likely have generated some output with a set of instruction and some example code similar to what's shown below. Notice that it brings in a unit testing framework. The generated code may not be complete - for example, it may have *placeholders* for input and output data.
   
![testing suggestions for file](./images/new-how-to-test-webscraper.png?raw=true "testing suggestions for file")

4. Let's take the generated code and put it into a new file. Click on the checkmark in the top right corner of the code block (next to the trash can).
   
![apply edits](./images/new-click-to-apply-edits.png?raw=true "apply edits")

5. After this, you should see the testing code as a new file in your editor. **Save the file as test_webscraper.py to make sure it has the correct name.**

![insert into new file](./images/new-test-output-to-file.png?raw=true "insert into new file")

![save new file](./images/new-save-test_webscraper.png?raw=true "save new file")

6. Let's also look at how we can add code coverage information for the *webscraper.py* file. Switch to the separate chat dialog. To keep things clean, let's start a new chat. Also, let's remove the default context in the chat. Click on the icon next to the test_webscraper.py file to delete it. 

![start new chat](./images/new-new-chat.png?raw=true "start new chat")  
![delete default context](./images/new-delete-default-context.png?raw=true "delete default context")

7. Now, let's add the *webscraper.py* file as our context. In the chat input area, click on the icon that looks like a paperclip. Then in the list of options that pops up in top center, select the *webscraper.py* file. After that, it should show up in the context of the chat.

![add context](./images/new-add-context.png?raw=true "add context") 
![add context](./images/new-choose-webscraper.png?raw=true "add context") 
![updated context](./images/new-updated-context.png?raw=true "updated context") 

8. Now, let's ask Copilot how we can measure code coverage on the file?
```
How can I measure code coverage on this file?
```

![query on code coverage](./images/new-code-coverage.png?raw=true "query on code coverage")

9. In the chat output, you'll see a set of steps interspersed with commands that can be run from the command line. 
   
![query on code coverage](./images/new-hover-and-insert-into-terminal.png?raw=true "query on code coverage")

10. You can hover over each and click the icon that looks like a terminal to send these commands directly to the terminal. Try this with the one for "pip install coverage". When you click on that terminal icon, it should populate the terminal with that command and you can run it.
    
![insert command from chat to terminal](./images/new-command-from-chat-to-terminal.png?raw=true "insert command from chat to terminal")

11. Finally, let's have Copilot help us identify any other edge cases that we should consider. Uncheck the "eye" icon. Switch back to the *test_prime.py* file, highlight the text, and start a new chat. Then, in the Chat interface, enter the prompt "Are there any other edge cases that should be tested?".

```
Are there any other edge cases that should be tested?
```

![finding other test cases](./images/new2-edge-cases-to-apply.png?raw=true "Finding other test cases")

12. This should result in some additional test cases being generated in Chat that you can then just replace in the *test_prime.py* file by using the *Apply in Editor* icon that shows up when you hover over the code and then clicking on the *Accept changes* link above the code change.

![adding test cases](./images/new2-apply-edge-cases.png?raw=true "Adding test cases")

    
<p align="center">
**[END OF LAB]**
</p>
</br></br>

**Lab 3 - Validating Inputs**

**Purpose: In this lab, we'll see how to have Copilot help validate inputs in functions.**

1. Copilot can also help with other kinds of validation besides general test cases. It can also validate that inputs going into a function are valid. Go back to the *prime.py* file, highlight your *is_prime* code and enter the prompt below into the Copilot Chat interface.

```
generate asserts to ensure that the inputs to the function are valid
```

2. Click on the "rerun without" link next to the "Workspace" section to get a run more targeted towards what we want.

![rerun without](./images/new-rerun-without.png?raw=true "rerun without")

3. From here, Copilot should respond and suggest asserts, as requested, to validate the functions inputs. The response may look something like the following (again you do not have to change anything).

![validating inputs with asserts](./images/new-inputs-asserts.png?raw=true "validating inputs with asserts")   

4. We can also be more directive and tell Copilot to generate checks within our *is_prime* function for valid inputs. Try this prompt (again in the Chat interface):

```
generate checks inline with the is_prime function to ensure that the inputs to the is_prime function are valid and raise an error if they are not
```

5. This should allow Copilot to generate code to validate the inputs, but with a more standard coding mechanism to surface any issues. Here's what example output from that might look like.

![validating inputs with checks](./images/new-generate-checks-to-ensure-that-inputs-to-function-are-valid.png?raw=true "validating inputs with checks")  


6. When you're happy with this code, you can go ahead and replace the highlighted code in the file by hovering over the code in the chat, clicking the apply button and then accepting the change in the file itself (click on *Accept Changes* above the updated code). 

![validating inputs with checks](./images/new-update-is-prime-with-checks-and-accept.png?raw=true "validating inputs with checks")  

7. While we are discussing inputs, we should also consider other types of inputs to test for. Switch back to the *test_prime.py* file with the test cases and have it open in the editor. Before we prompt Copilot about additional test cases, we need to be sure that it is considering the whole file for context. Even though it shows *test-prime.py* as the current file context in the chat, it will only include the part of the file that's visible in the editor.  To see that, enter this prompt and note what reference it used.

```
What other kinds of test cases should we check for?
```

8. Notice that in my example, only lines 11-28 were used as a reference - which corresponds to what was visible in the editor (aka #editor). With only a subset of the test cases visible, it's possible/likely that Copilot would repeat some that were already in the parts of the file that weren't visible in the editor.  With this prompt, Copilot will likely add some additional test cases like these.

![only visible context](./images/new-only-editor-visible-context.png?raw=true "only visible context") 
   
9. To make sure we get the entire file as context, we could use the *#file* selector. But we can also do it a different way. First, let's *cancel* the current context in the chat dialog by clicking on the icon that looks like an "eye" at the end of the *test-prime.py* item n the chat. (See below for where to click and what it should look like after.)
   
![disable current file context](./images/new-disable-current-file-context.png?raw=true "disable current file context") 

![disabled current file context](./images/new-disabled-current-file-context.png?raw=true "disabled current file context") 

10. Click on the *paper clip* icon and select the *test-prime.py* file from the dialog that pops up to add the entire file as context. Afterwards, the chat window should look like the second screenshot below.

![attach file context](./images/new-attach-context.png?raw=true "attach file context") 

![attached file context](./images/new-attached-file-for-context.png?raw=true "attached file context") 


11. Now, we can input the same prompt again and we should see that the entire file was used instead of just the visible portion. Input the same prompt and notice the output. Since the entire file was used as context, the new test cases should not overlap the existing ones. Afterwards, you can add the changes into the *test-prime.py* file if you want.

```
What other kinds of test cases should we check for?
```

![distinct test case context](./images/new-distinct-test-case-context.png?raw=true "distinct test case context") 

12. Finally, let's see if Copilot can help refactor our code to make it more testable. We'll use the *webscraper.py* file for this since it is more substantial.  Enter the query below in the Chat interface. 

```
refactor the code in #file:webscraper.py to make it more easily testable
```

13. You should see some suggestions for improving testability in the file in the chat output. These can be applied to the current code if you want.
    
![Refactoring for testing](./images/new-refactor-for-testability.png?raw=true "refactoring for testing")  


<p align="center">
**[END OF LAB]**
</p>
</br></br>

**Lab 4 - Leveraging frameworks and TDD**

**Purpose: In this lab, we'll see how to leverage Copilot with testing frameworks and how to do Test-Driven Development with it.**

**Important Note: If any steps in this lab run with /tests by default, run them again using the "run without" option**

1. Let's look at a TDD approach of creating the test cases with a failing test and then immplementing the code to be tested. Consider a simple example where we want to create a test class and tests for students at a university. We'll use Mockito in our testing framework. Let's have Copilot create a pom.xml file for us with a mockito dependency. In the separate chat interface, start a new chat session, and enter the following prompt:

```
add a pom.xml file with a mockito dependency version 3.3.3, and compiler source and target version 1.8
```

![add pom with mockito dependency](./images/ct33.png?raw=true "add pom with mockito dependency")  

2. Now, let's put the generated content into a new file in our project. Hover over the generated code, select the *... (More actions)* at the end and then click on *Insert into New File*. Then save the file as *pom.xml* via the *3 bar* menu in the upper left, then *File*, then *Save As..* (or use the keyboard shortcut).

![insert into new file](./images/ct34.png?raw=true "insert into new file")  

![save file](./images/ct29.png?raw=true "save file") 

3. Now, let's create an appropriate test class and initial set of tests. Do this in the Copilot separate Chat interface, since we expect a significant amount of output and we may want to put it in a separate file. We'll use a prompt that tells Copilot to focus on the *pom.xml* file we just created.

```
Referencing #file:pom.xml, create a StudentTest class for students enrolled at a university and add tests
```

4. The suggested StudentTest class from this prompt is likely overkill for what we want for a simple test case for a *Student* class. However, Copilot will likely detect that we need the Junit dependency at the start of the output. There may be a step or segment of code to *update pom.xml with JUnit dependencies* at the top or bottom of the output. (If you don't see it, click on the "Run without" to run the prompt without /tests.)  If you see it, go ahead and add that part only into your *pom.xml* file. (You can just have the **corresponding section** of the pom.xml file contents highlighted and then *Apply* to replace it.) Save the changes to the *pom.xml* file afterwards.

![add junit dependency](./images/new-update-pom-2.png?raw=true "add junit dependency")  
   
5. Let's restructure the prompt to ask for something more specific for the StudentTest class. Enter the following in chat.

```
Referencing #file:pom.xml, create only a StudentTest class for a student enrolled at a university. A student will have personal attributes such as a first and last name, a phone number, an address, and a contact email. The StudentTest class should be part of a com.example package.
```
![more specific query to create tests](./images/ct21.png?raw=true "more specific query to create tests")  

6. The output from Copilot now likely looks more like what we wanted as a starting point. Click into the output for the *StudentTest* class, hover over the top right, and use the icon (or copy and paste) to put it in a different file. Save the file as **src/test/java/com/example/StudentTest.java**.

![save new test](./images/new-save-into-file-studenttest.png?raw=true "save new test")
![save new test](./images/new-save-into-file-path.png?raw=true "save new test")

7. Now, let's execute Maven to try the testing. (Note: We expect it to fail because we don't have the *Student* class implemented yet.)

```
mvn test
```

![initial test](./images/ct32.png?raw=true "initial test")


8. Folllowing the TDD methodology, let's next create the minimum code to make this test pass. We can use Copilot for that. Make sure the *StudentTest.java* file is open in the editor, and then use this prompt to create the code.

```
Referencing #editor, create a student class with verbose comments.
```

![output of query to create student class with comments](./images/ct35.png?raw=true "output of query to create student class with comments")

9. As we did before, hover over the output, insert the code into a new file. Then save it as **src/main/java/com/example/Student.java**

![saving student file](./images/new-save-into-file-student.png?raw=true "saving student file")

10. Finally, let's run the test again and it should pass. 

```
mvn test
```

![run test and see it pass](./images/ct37.png?raw=true "run test and see it pass")


<p align="center">
[END OF LAB]
</p>

<p align="center">
THANKS!
</p>
 

