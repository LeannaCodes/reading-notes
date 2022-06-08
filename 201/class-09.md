# Forms

## Form Controls 

There are several types of form controls that you can use to collect information from visitors to your site. 

**Adding Text:** 

- **Text input** *(single-line)* = used for a single line of text such as email addresses and names.
- **Password Input** = Like a single line of text box but it masks the characters entered. 
- **Text area** *(multi-line)* = for longer areas of text, such as messages and comments. 

**Making Choices:**

- **Radio Buttons** = For use when a user must select one of a number of options.
- **Checkboxes** = When a user can select and unselect one or more options. 
- **Drop-down boxes** = When a user must pick one of a number of options from a list. 

**Submitting Forms:**

- **Submit Buttons** = To submit data from your form to another web page. 
- **Image Buttons** = Similar to submit buttons but they allow you to use an image. 

**Uploading Files:**

- **File Upload** = Allows you to upload files (e.g images) to a website. 

## Form Structure

FORM CONTROLS go INSIDE a `<form>`element. This element should always carry the *action* attribute and will always have a *method* and id attribute too. 

**Action** = Every `<form>` element requires an action attribute. Its value is the URL for the page on the server that will recieve the information in the form when it is submitted. 

**Method** = Forms can be sent using one of two methods: get or post. 

With the *get* method, the values from the form are added to the end of the URL specified in the action attribute. The *get* method is ideal for: 

- short forms (such as search boxes)
- When you are just retrieving data from the web server (not sending information that should be added to or deleted from a database)

With the *post* method, the values are sent in what are known as HTTP headers. As a rule of thumb you should use the post method in your form: 

- allows users to upload a file 
- is very long
- contains sensitive data (e.g passwords)
- adds information to, or deletes information from a database. 

**ID**

The value is used to identify the form distinctly from other elements on the page. 

The `<input>` element is used to create several different form controls. The value of the type attribute determines what kind of input they will be creating. 

**type="text"** When the type attribute has a value of text, it creates a single line text input. 

For example: 

```
<form action ="URL link">
<p>Username:
<input type="text" name="username" size="15" maxlength="30">
</p>
</form>
```

Drop down List Box

`<select>` is used for drop down list box (also known as a select box) allows users to select one option from a drop down list. 

The `<select>` element is used to create a drop down list box. It contains two or more `<option>` elements. 

The name attribute indicates the name of the form control being sent to the server, along with the value the user selected. 

for example: 
```
<form action="URL Link">
<p>What device do you listen to music on?</p>
<select name="devices">
<option value="ipod">ipod</option>
<option value="computer">computer</option>
<option> value="ipad">ipad<.option>
</select> 
</form>