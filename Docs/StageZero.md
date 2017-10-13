## Stage Zero Notes

- Main storyboard, this is where we lay out our UI.

 ![Main Xcode Screen][1]


- Add table view controller to the board (Image)

- Delete the initial view controller (cmd-delete) (Image)

- Set as table view controller as initial view controller (Image)

- Run the application, should see empty table view controller (Image)

- Let's edit the code now, switch to the ViewController in your project file structure (Image)

- First let's make this a UITableViewController instead of a ViewController. This is the first step to allow us to control the Table View we just created in our storyboard. We are also going to rename our class to make it clearer. Replace this:  
```
class ViewController: UIViewController
```    
With this:  
```
class MainTableViewController: UITableViewController
```  

- We also need to rename the actual file. To do this, open your file navigator on the left and rename the ViewController file to MainTableViewController. (Image)

- Finally, to associate our MainTableViewController with our Table View that we created in our storyboard, we need to head back to the Main.storyboard and add MainTableViewController as custom class. (Image)

- Now we can start writing code to directly manipulate our table view. Table view's consist of things called rows and sections. For the moment we won't worry about sections and will focus on rows. A row is essentially an element in the table view and we can tell it how many to have and what to put in each one. To start, we will create 10 rows and make their background colour pink!  
First we will add this function just underneath our didReceiveMemoryWarning function in our ViewController file.  
```  
override func tableView(_ tableView: UITableView, numberOfRowsInSection section: Int) -> Int {
    return 10
}
```  
This function is telling the table view how many rows it should be showing. If you run the application now, you won't see any change from previously as iOS fills the rest of the screen with empty rows so it won't look any different. 
 
- Now that we have ten rows let's start to make them display things! First we have to give the cell (TODO:Explain Cell & how it relates to rows) a reuse identifier so that we can reference the cell in our code. Head back over to your storyboard file and first select your table view cell in the view hierarchy (Image) then head over to the right hand side and make sure the 'attributes' tab is active (Image), in this you will find an identifier text box, add `mainTableViewCell`.

- Now we should head back to our MainTableViewController and add this code underneath the closing bracket of the last function you added.  
```
override func tableView(_ tableView: UITableView, cellForRowAt indexPath: IndexPath) -> UITableViewCell {
    let cell = tableView.dequeueReusableCell(withIdentifier: "mainTableViewCell", for: indexPath)
        
    cell.backgroundColor = .red
        
    return cell
}
```
- Now we have a tableview with coloured cells, well done! Time to head over to [stage two]().

[1]:images/StageZero/StageZero-Mainscreen.png
<!-- [1]:
[1]:
[1]:
[1]:
[1]:
[1]:
[1]:
[1]:
[1]: -->