<strong>** DO NOT DISTRIBUTE OR PUBLICLY POST SOLUTIONS TO THESE LABS. MAKE ALL FORKS OF THIS REPOSITORY WITH SOLUTION CODE PRIVATE. PLEASE REFER TO THE STUDENT CODE OF CONDUCT AND ETHICAL EXPECTATIONS FOR COLLEGE OF INFORMATION TECHNOLOGY STUDENTS FOR SPECIFICS. ** </strong>

# WESTERN GOVERNORS UNIVERSITY 
## D287 – JAVA FRAMEWORKS
Welcome to Java Frameworks! This is an opportunity for students to implement user interfaces and learn to leverage existing frameworks, assets, and content for object-oriented programming.
FOR SPECIFIC TASK INSTRUCTIONS AND REQUIREMENTS FOR THIS ASSESSMENT, PLEASE REFER TO THE COURSE PAGE.
## BASIC INSTRUCTIONS
For this project, you will use the Integrated Development Environment (IDE) link in the web links section of this assessment to install the IDE, IntelliJ IDEA (Ultimate Edition). All relevant links are on the course page. Please refer to the course of study for specific links. You will sign up for a free student license using your WGU.edu email address. Please see the “IntelliJ Ultimate Edition Instructions” attachment for instructions on how do this. Next you will download the “Inventory Management Application Template Code” provided in the web links section and open it in IntelliJ IDEA (Ultimate Edition). You will upload this project to a private external GitLab repository and backup regularly. As a part of this, you have been provided with a base code (starting point). 

## B.  Create a README file 
I will include notes for parts C to J. Each below will include a prompt, file name, line number, and change.

## C.  Customize the HTML user interface for your customer’s application. The user interface should include the shop name, the product names, and the names of the parts.

File name: mainscreen.html </br>
updating my html to display the shop name and parts that the store NotnewEgg.com 
a computer shop will create and sell.
</br>
</br>
<b>line numbers and Changes Made:</b></br>
line 14 changed the name of the shop to My Pc Hardware store NotnewEgg.com</br>
`<title>Pc Hardware store NotnewEgg.com</title>`
</br>
line 19 the header one(h1) was changed to: NotnewEgg.com</br>
`<h1>NotnewEgg.com</h1>`
</br>
line 21 second header(h2) changed to: Computer Hardware Parts</br>
`<h2>Computer Hardware Parts</h2>`
</br>
line 53 header(h2) was changed to: Computer Products</br>
`<h2>Computer Products</h2>`
</br>
line 43 -45 to display a temp part name and price of an actual product aligned with the site.</br>
`<tr th:each="tempPart : ${parts}">
            <td th:text="${tempPart.name}">Computer CaseWith USB 3.0 Mini Tower ITX ATX Case</td>
            <td th:text="${tempPart.price}">$147.99</td>`
</br>
line 79 - 80 changed td to display a temp product Ultimate Pc Gaming real price </br>
`<tr th:each="tempProduct : ${products}">
            <td th:text="${tempProduct.name}">Ultimate PC Gaming System</td>
            <td th:text="${tempProduct.price}">$1,499.99</td>`
</br>


Note: Do not remove any elements that were included in the screen. You may add any additional elements you would like or any images, colors, and styles, although it is not required.


## D.  Add an “About” page to the application to describe your chosen customer’s company to web viewers and include navigation to and from the “About” page and the main screen.

File name: (Newly Created) aboutpage.html (can be found in templates folder)</br>
Changes made: </br>
Created an aboutpage.html for the new store: NotnewEgg.com with what the company is about
and how it came about to be. I also a made a controller for it in the directory(details
listed below in the notes for: @Controller) </br>
line numbers: 1-45</br>
line 1 added Doctype to be html</br>
line 2 created html lang="en" xmlns:th="http://www.thymeleaf.org" </br>
line 3 created Head</br>
lines 4, line 6,7, and 8 set up the Required meta tags</br>
line 10-12  comment for Bootstrap CSS and the link </br>
line 14 added Title using About </br>
line 15 ended the header</br>
line 16 created the start of the body</br>
line 18-21 created a nav with a link to mainscreen and aboutpage with style of 
text-align:center<br>
line 23 created a div container</br>
line 25 h1 Header "Welcome to NotnewEgg.com" </br>
line 24 & 26 a hr to create a line to separate the header from the paragraph</br>
line 28- 41 made (</p>) a paragraphs describing the company and what it
will provide to the customer. Along with it return policy and how long they have been in
business. using bold in line 28 and italics in line 34.</br>
line 43-45 ends the div, body and html</br>

File name: mainscreen.html</br>
updated the mainscreen to also have a navigation bar to link to about page.</br>
Line numbers and changes made: </br>
Lines 18-21 added a Navigation bar to link the mainscreen.html to aboutpage.html</br>

`<nav style="text-align:center;">
    <a class="active" href="http://localhost:8080/mainscreen">Home</a>
    <a href="http://localhost:8080/aboutpage">About</a>
    </nav>`
</br>
line 24 I added a horizontal line hr.</br>
`<hr>`
</br>


Folder name: @Controller</br>
File Named: (created controller) @AboutPageController so I can link my aboutpage.hmtl 
to localhost:8080 </br>
line numbers: 1-4, 6, 7, & 8-12: </br>
Changes made: </br>
On 1-4 added imports for controllers, springs Controller, spring ui.Model, 
and spring GetMapping. Then placed @ for Controller on line 6. line 7 created public class 
AboutPageController, 8-12 added @ GetMapping("/aboutpage") then placed a
public String aboutpage(Model theModel) that returns "aboutpage"</br>
`package com.example.demo.controllers;
import org.springframework.stereotype.Controller;
import org.springframework.ui.Model;
import org.springframework.web.bind.annotation.GetMapping;
@Controller
public class AboutPageController {
@GetMapping("/aboutpage")
public String aboutpage(Model theModel){
        return "aboutpage";
    }`
</br>

## E.  Add a sample inventory appropriate for your chosen store to the application. You should have five parts and five products in your sample inventory and should not overwrite existing data in the database.

File name: BootStrapData </br>
line number: 43 - 102 & line 3</br>
Changes made: Line 3 I added import statement `import com.example.demo.domain.InhousePart;`
</br>
then for 43-102 created an if statement `// Check if parts and products repositories are empty
if ((partRepository.count() == 0) && (productRepository.count() == 0))` to check the part and product repository's count
so if it hits 0 it can update. First I ` // Create In house part object for parts and products
            InhousePart computerCase = new InhousePart();` Inside I had it adding the 5 parts 
and 5 products and saved to repository with a set name, ID, inventory, and price.(One part example:) </br>
`//create the computer case values and save
computerCase.setName("Computer CaseWith USB 3.0 Mini Tower");
computerCase.setInv(15);
computerCase.setPrice(147.99);
computerCase.setPartId(1);
partRepository.save(computerCase);`</br>
</br>
</br>

File name: application.properties </br>
line number: 6 </br>
Changes made: changed `spring.datasource.url=jdbc:h2:file:~/spring-boot-h2-db102-` to have a -4 at
the end to update the localhost:8080 to show the update it to display the correct data
in BootStrapData.</br>

Note: Make sure the sample inventory is added only when both the part and product lists are empty. When adding the sample inventory appropriate for the store, the inventory is stored in a set so duplicate items cannot be added to your products. When duplicate items are added, make a “multi-pack” part.


## F.  Add a “Buy Now” button to your product list. Your “Buy Now” button must meet each of the following parameters:
•  The “Buy Now” button must be next to the buttons that update and delete products.
•  The button should decrement the inventory of that product by one. It should not affect the inventory of any of the associated parts.
•  Display a message that indicates the success or failure of a purchase.

File name: mainscreen.html </br>
line number: 55-56 & 93-94</br>
Changes made: Added to the Tbody of the thread another copy of a button but for Buy now in 
both the Parts and Product section of mainscreen.html</br>
</br>
`<a th:href="@{/buyPart(partID=${tempPart.id})}" class="btn btn-primary btn-sm mb-3"
                   onclick="if(!(confirm('Is this the part you want to buy?')))return false">Buy Now</a>`
</br>
`<a th:href="@{/buyProduct(productID=${tempProduct.id})}" class="btn btn-primary btn-sm mb-3"
                   onclick="if(!(confirm('Is this the product you want to buy?')))return false">Buy Now</a>`
</br>

File name: successful.html</br>
line number: 1-12 </br>
Changes made: Created a simple html set up with a title 'Successful' `<title>Successful</title>`,
a paragraph stating "Your part or product has been added successfully!" `<p>Your part or product has been added successfully!</p>`
and a link back to the home page. `<a href="http://localhost:8080/">Link
to Main Screen</a>`</br>
</br>

File name: unsuccessful.html</br>
line number: 1-12 </br>
Changes made: Created a simple html set up with a title Buy Now Error `<title>Buy Now Error</title>`
, a paragraph stating "Cannot buy now this part or product right now, sorry for the inconvenience.!"
`<p>Cannot buy now this part or product right now, sorry for the inconvenience.</p>`
and a link back to the home page. 
`<a href="http://localhost:8080/">Link
to Main Screen</a>`</br>
</br>

File name: AddPartController.java</br>
line number: 70-92 </br>
Changes made: created @GetMapping("/buyPart") with a public string to return the changes
of clicking the buy now button. set up using the beans to update it in spring, and making sure to
associate it with the partsId to keep track of the inventory being correctly updated.
Created a if statement there is 0 then the link would send them to the
unsuccessful.html, otherwise it would take the part object and update the inventory by 
removing inventory in increments of one. Then it was saved to the repository and sent to the 
page of successful.html to inform customer of the update.</br>
</br>
`@GetMapping("/buyPart")
    public String buyPart(@Valid @RequestParam("partID") int theId,  Model theModel){
        PartService repo = context.getBean(PartServiceImpl.class);
        Part part=repo.findById(theId);
        //variable to store the value in the inventory
        int inventory = part.getInv();
`
`

    if(inventory == 0){

            //direct user the unsuccessful.html page
            return "unsuccessful";
        }
        else{
            //update inventory
            part.setInv(inventory - 1);
            //save new inventory value
            partRepository.save(part);

            //direct user to successful.html page
            return "successful";
        } 
`

File name: AddProductController.java</br>
line number: 176-196 </br>
Changes made: created @GetMapping("/buyProduct") with a public string method to return the changes
of clicking the buy now button. set up using the beans to update it in spring and connect it
to the productID that the customer selected. After I placed an if statement so when it became 0 
the link would send them to the unsuccessful.html, otherwise it would take the product object
and update the inventory by removing inventory in increments of one. Then it was saved to the 
repository and sent to the page of successful.html to inform customer of the update.</br>
</br>

`@GetMapping("/buyProduct")
    public String buyProduct(@Valid @RequestParam("productID") int theId,  Model theModel) {
        ProductService productService = context.getBean(ProductServiceImpl.class);
        Product product2 = productService.findById(theId);
`
`

    int inventory = product2.getInv();

        if (inventory == 0) {
            // Direct user to unsuccessful.html page if inventory is 0
            return "unsuccessful";
        } else {
            // Update inventory
            product2.setInv(inventory - 1);
            // Save updated product inventory
            productService.save(product2);
            // Direct user to successful.html page
            return "successful";
        }
    }`

## G.  Modify the parts to track maximum and minimum inventory by doing the following:
•  Add additional fields to the part entity for maximum and minimum inventory.
•  Modify the sample inventory to include the maximum and minimum fields.
•  Add to the InhousePartForm and OutsourcedPartForm forms additional text inputs for the inventory so the user can set the maximum and minimum values.
•  Rename the file the persistent storage is saved to.
•  Modify the code to enforce that the inventory is between or at the minimum and maximum value.

File name: mainscreen.html</br>
line number: 44-45(th tag) & 54-55(td)</br>
Changes made: For Computer Hardware Parts Added a th tag to define the header for the
minimum and maximum inventory columns, followed by td elements to display the corresponding 
values in the table.</br>
`   <th>Min Inventory</th>`
</br>
`   <th>Max Inventory</th>`
</br>

File name: Part.java</br>
line number: 4 & 23, 33-37, 92-104</br>
Changes made: Line for I added an import for ValidInventory and created the `@ValidInventory`
line 23. Then to have a min and max inventory I created 33-37 to have
`//create a minimum inventory and maximum inventory to always be a positive number
    @Min(value = 0, message = "Min inventory value must be positive")
    int minInv;
    @Min(value = 0, message = "Max inventory value must be positive")
    int maxInv;` for both 
min inventory and max in the Parts class. Lastly created a getter and setter for both min
and max inventory.</br>
`public int getMinInv() {
        return minInv;
    }`
</br>
`public void setMinInv(int minInv) {
        this.minInv = minInv;
    }`
</br>
</br>
`public int getMaxInv() {
        return maxInv;
    }`
</br>
`public void setMaxInv(int maxInv) {
        this.minInv = maxInv;
    }`
</br>

File name: ValidInventory.java (newly created file Late Removed for #H. and replaced with
ValidEnufParts/EnufPartsValidator)</br>
line number: 1-25</br>
Changes made: Created package com.example.demo.validators; and then imported
Constraint, Payload,ElementType, Retention,RetentionPolicy, and Target. Then placed
@Constraint(validatedBy = {InventoryValidator.class})
@Target({ElementType.TYPE})
@Retention(RetentionPolicy.RUNTIME)
lastly added public @interface ValidInventory to see if the Inventory had an error, if so
it would then produce a message stating "Inventory error!" to user.</br>
</br>

File name: InventoryValidator.java (newly created file Late Removed for #H. and replaced with 
ValidEnufParts/EnufPartsValidator)</br>
line number: 1-43</br>
Changes made: Created a new file InventoryValidator with imports to Part class,
ConstraintValidator, and ConstraintValidatorContext. Made a public class
InventoryValidator implements ConstraintValidator<ValidInventory, Part>
then inside it a public boolean isValid to check to see if the computerPart.getInv()
was either bigger or smaller than computerPart.getMinInv() or computerPart.getMaxInv().
Having the boolean return true if they were correct if not a message saying if it is too small
or to big for the inventory.</br>
</br>


File name: BootStrapData.java</br>
line number: 56-57, 65-66, 74-75, 84-85, 93-94</br>
Changes made: Added into BootStrapData the 5 parts to have a min inventory 
and max inventory. (one example: `computerCase.setMinInv(1);
computerCase.setMaxInv(20);`)</br>
</br>

File name: InhousePartForm.html</br>
line number: 26-37</br>
Changes made: Added into the form both a min Inventory and max Inventory. Stating for the
line 32-37 I made a div to display a div with a ul and a list if it had an error. 
To inform the user if they put in an incorrect amount of inventory.</br>
`    <div th:if ="${#fields.hasAnyErrors()}">
        <ul>
            <li th:each="err : ${#fields.allErrors()}" th:text="${err}"></li>
        </ul>
    </div>`
</br>

File name: OutsourcedPartForm.html</br>
line number: 27-38</br>
Changes made: Added into the form both a min Inventory and max Inventory. Stating for the
line 33-38 I made a div to display a div with a ul and a list if it had an error.
To inform the user if they put in an incorrect amount of inventory.</br>
</br>
`    <div th:if ="${#fields.hasAnyErrors()}">
        <ul>
            <li th:each="err : ${#fields.allErrors()}" th:text="${err}"></li>
        </ul>
    </div>`
</br>

File name: application.properties</br>
line number: 6</br>
Changes made: updated the `spring.datasource.url=jdbc:h2:file:~/spring-boot-h2-db102-7`
so that the new data in BootStrapData.java could display into the webpage.</br>
</br>

## H.  Add validation for between or at the maximum and minimum fields. The validation must include the following:
•  Display error messages for low inventory when adding and updating parts if the inventory is less than the minimum number of parts.
•  Display error messages for low inventory when adding and updating products lowers the part inventory below the minimum.
•  Display error messages when adding and updating parts if the inventory is greater than the maximum.

File name: EnufPartsValidator.java </br>
line number: 36-40</br>
Changes made: Updated isValid to check if the product when updated to associated
part that it wouldn't create the part to go below the min inventory or max inventory.
</br>
</br>
` if (p.getInv() < (product.getInv() - myProduct.getInv())) {
     constraintValidatorContext.disableDefaultConstraintViolation();
     constraintValidatorContext.buildConstraintViolationWithTemplate("Incorrect inventory allowed for part: " + p.getName()).addConstraintViolation();
     return false;
     }
     if (p.invalidInvAmount()) return false;`</br>
</br>

File name: Part.java </br>
line number: 23, 47-48, 56-57, 111-114</br>
Changes made: Removed @ValidInventory. Added to public Part to have 
` this.minInv = 0; //make sure minimum inventory will not fall below 0
        this.maxInv = maxInv;` to make sure it will not let
the inventory fall below 0 or the maxInv the part is allowed. 
Created invalidInvAmount to check if the min or max is correct. </br>
</br>
`public boolean validInvAmount(){
        return (inv <= minInv) || (inv >= maxInv);
    }`
</br>
</br>

File name: AddInhousePartController.java </br>
line number: 38-52</br>
Changes made: Added into @showFormAddInPart if statements to check the inventory when a
part would be updated if it is too high or too low.
</br>
</br>
`if (part.invalidInvAmount()) {
if (part.getInv() < part.getMinInv()) {
theBindingResult.rejectValue("inv", "LowInventoryAmount", "Below minimum inventory amount for the part(s).");
return "InhousePartForm";
}
            if (part.getInv() > part.getMaxInv()) {
                theBindingResult.rejectValue("inv", "HighInventoryAmount", "Above maximum inventory amount for the part(s).");
                return "InhousePartForm";
            }
            theBindingResult.rejectValue("inv", "InvalidInventoryAmount", "Invalid inventory amount!");
            return "InhousePartForm";
        }`
</br>
</br>

File name: AddOutsourcedPartController.java </br>
line number: 23, 111-114</br>
Changes made: Added into @showFormAddOutPart if statements to check the inventory when a
part would be updated if it is too high or too low.</br>
</br>
`if(part.invalidInvAmount()){
            if (part.getInv() < part.getMinInv()){
                bindingResult.rejectValue("inv", "LowInventoryAmount", "Below minimum inventory amount for part(s).");
                return "OutsourcedPartForm";
            }
            if(part.getInv() > part.getMaxInv()){
                bindingResult.rejectValue("inv", "HighInventoryAmount", "Below maximum inventory amount for part(s).");
                return "OutsourcedPartForm";
            }
            bindingResult.rejectValue("inv","invalidInvAmount","Invalid inventory amount!");
            return "OutsourcedPartForm";
        }`
</br>

File name: productForm.html </br>
line number: 23-28</br>
Changes made: Adjusted the #fields.hasAnyErrors to just look more clean.
</br>
</br>
`<div th:if ="${#fields.hasAnyErrors()}">
        <ul>
            <li th:each="err : ${#fields.allErrors()}" th:text="${err}"></li>
        </ul>
    </div>`
</br>

File name: InhousePartForm.html </br>
line number: 22,26, and 29</br>
Changes made: Removed line 22 and adjusted the form of Min Inventory or Max Inventory to have the 
placer to hold the name so customers can be informed what to enter the box.</br>
</br>
`<p><input type="text" path="minInv" th:field="*{minInv}" placeholder="Min Inventory" class="form-control mb-4 col-4"/></p>`
`<p><input type="text" path="maxInv" th:field="*{maxInv}" placeholder="Max Inventory" class="form-control mb-4 col-4"/></p>`
</br>
</br>

File name: OutsourcedPartForm.html </br>
line number: 23</br>
Changes made: Removed line 23 so that it didn't show the error twice.</br>
</br>
`<p th:if="${#fields.hasErrors('inv')}" th:errors="*{inv}">Inventory Error</p>`
</br>

File name:  BootStrapData.java </br>
line number: 102 & 104</br>
Changes made: Changed/updated 2 products prices.
</br>
</br>
`Product preOwnedPc = new Product(8, "Ultimate PC Gaming System(Second-Hand)", 899.99, 20);`</br>
`Product ultimateComputer = new Product(10 , "Ultimate Pc Gaming System",999.99, 12);`
</br>
</br>

File name:  application.properties </br>
line number: 6</br>
Changes made: updated the `spring.datasource.url=jdbc:h2:file:~/spring-boot-h2-db102-29` </br>
</br>

## I.  Add at least two unit tests for the maximum and minimum fields to the PartTest class in the test package.

File name: PartTest.java</br>
line number: 161-197</br>
Changes made: Five tests were added; the first two were to ensure they could add (#1st Unit test)
minimum Inventory or (#2) max Inventory. Next (#3), check if you set a minimum and a maximum and 
put the inventory as mid so that it is true to the check. The last two, if is it would assert 
false when inventory (#4) goes above the max or (#5) goes below the minimum inventory, it 
returns a statement.</br>

    `@Test
    void testMinInv(){
    partIn.setMinInv(1);
    partOut.setMinInv(1);
    assertEquals(partIn.getMinInv(), partOut.getMinInv());
    }

    @Test
    void testMaxInv(){
        partIn.setMaxInv(100);
        partOut.setMaxInv(100);
        assertEquals(partIn.getMaxInv(), partOut.getMaxInv());
    }

    @Test
    void testInvWithinRange() {
        partIn.setMinInv(1);
        partIn.setMaxInv(100);
        partIn.setInv(50); // Set inventory within range
        assertTrue(partIn.getInv() >= partIn.getMinInv() && partIn.getInv() <= partIn.getMaxInv());
    }

    @Test
    void testMaxInvWithinRange() {
        partIn.setMaxInv(100);
        partIn.setInv(150);
        assertFalse(partIn.getInv() <= partIn.getMaxInv(), "max inv should be less than or equal to max inv");
    }
    
    @Test
    void testMinInvWithinRange() {
        partIn.setMinInv(1);
        partIn.setInv(0);
        assertFalse(partIn.getInv() >= partIn.getMinInv(), "Min inv should be greater than or equal to inv");
    }`
## J.  Remove the class files for any unused validators in order to clean your code.

File name: DeletePartValidator.java</br>
line number: All</br>
Changes made: Since this whole file wasn't in use I deleted it all.</br>
</br>
File name: ValidDeletePart.java</br>
line number: All</br>
Changes made: Since this whole file wasn't in use I deleted it in its entirety.</br>
</br>
File name: Part.java</br>
line number: 3 & 18</br>
Changes made: I deleted the line 3 and 18 since they were calling but not using the code
`import com.example.demo.validators.ValidDeletePart;`
and `@ValidDeletePart` from files DeletePartValidator.java and ValidDeletePart.java</br>
</br>
File name: BootStrapData.java</br>
line number: 113-128 & 134-139, 144</br>
Changes made: Deleted lines 113-128 and 134-139 since they were comments not being used.
But I also added a comment above `//print name of a part and the company of an outsourced part`
for the code `List<OutsourcedPart> outsourcedParts=(List<OutsourcedPart>) outsourcedPartRepository.findAll();
        for(OutsourcedPart part:outsourcedParts){
            System.out.println(part.getName()+" "+part.getCompanyName());
        }`</br>
</br>
File name: MainscreenControllerr.java</br>
line number: 34-37</br>
Changes made: Deleted the commented out ` /*   public MainScreenControllerr(PartRepository partRepository, ProductRepository productRepository) {
this.partRepository = partRepository;
this.productRepository = productRepository;
}*/`. Since it was not in use and there was already a public MainScreenControllerr in use.</br>
</br>