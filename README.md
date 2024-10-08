# Library Ulster University Website

### jQuery and JavaScript Features

These jQuery functions allow users to increase or decrease the text size on each page to improve accessibility:

![Test Size Image](IMG/Test_Size.png)

```javascript
$(document).ready(function(){
    $(".btn1").click(function(){
         $(".div6 p").animate({
             fontSize: '15px'
         });
     });
});

$(document).ready(function(){
    $(".btn2").click(function(){
         $(".div6 p").animate({
             fontSize: '16px'
         });
     });
});

$(document).ready(function(){
    $(".btn3").click(function(){
         $(".div6 p").animate({
             fontSize: '17px'
         });
     });
});

```
### Form Validation for Title Selection

This JavaScript function ensures that a user selects a title from a set of radio buttons before submitting the form:

```javascript
// Function to validate the selected title
function validateTitle() {
    // Get all elements with the name "title"
    var titleInputs = document.getElementsByName("title");
    var titleSelected = false;

    // Loop through each title input to check if any are selected
    for (var i = 0; i < titleInputs.length; i++) {
        if (titleInputs[i].checked) {
            titleSelected = true;
            break;
        }
    }

    // Set custom validity based on whether a title is selected or not
    if (!titleSelected) {
        for (var i = 0; i < titleInputs.length; i++) {
            titleInputs[i].setCustomValidity("Please select a title");
        }
    } else {
        for (var i = 0; i < titleInputs.length; i++) {
            titleInputs[i].setCustomValidity(""); // Clear custom validity
        }
    }
}

```
### Form Validation for Gender Selection

This JavaScript function ensures that a user selects a gender from a dropdown menu before submitting the form:

```javascript
// Function to validate the selected gender from a dropdown
function validateGender() {
    // Get the gender dropdown element
    var genderDropdown = document.getElementById("gender-dropdown");

    // Set custom validity based on whether a gender is selected or not
    if (genderDropdown.value === "") {
        genderDropdown.setCustomValidity("Please select an option");
    } else {
        genderDropdown.setCustomValidity(""); // Clear custom validity
    }
}

```
### Form Validation for First Name Input

This JavaScript function ensures that the user provides a valid first name input before submitting the form:

```javascript
// Function to validate the first name input
function validateFirstName() {
    // Get the first name input element
    var firstNameInput = document.getElementById("firstName");

    // Trim leading and trailing whitespace from the input
    var trimmedFirstName = firstNameInput.value.trim();

    // Validate the first name based on various conditions
    if (trimmedFirstName === "") {
        firstNameInput.setCustomValidity("Please enter first name");
    } else if (trimmedFirstName.length > 50) {
        firstNameInput.setCustomValidity("First name cannot exceed 50 characters");
    } else if (!/^[A-Za-z-' ]+$/.test(trimmedFirstName)) {
        firstNameInput.setCustomValidity("Invalid characters in first name");
    } else {
        firstNameInput.setCustomValidity(""); // Clear custom validity
    }
}

```

### Validate Address

This JavaScript function ensures that the user provides a valid address input before submitting the form:

```javascript
// Function to validate the address input
function validateAddress() {
    // Get the address input element
    var addressInput = document.getElementById("address");
    var trimmedAddress = addressInput.value.trim();

    // Validate the address based on various conditions
    if (trimmedAddress === "") {
        addressInput.setCustomValidity("Please enter your address");
    } else if (trimmedAddress.length > 100) {
        addressInput.setCustomValidity("Address cannot exceed 100 characters");
    } else if (!/^[A-Za-z0-9,.' -]+$/.test(trimmedAddress)) {
        addressInput.setCustomValidity("Invalid characters in address");
    } else {
        addressInput.setCustomValidity(""); // Clear custom validity
    }
}

```
### Validate Postcode

This JavaScript function ensures that the user provides a valid postcode input before submitting the form:

```javascript
// Function to validate the postcode input
function validatePostcode() {
    // Get the postcode input element
    var postcodeInput = document.getElementById("postcode");
    var trimmedPostcode = postcodeInput.value.trim();

    // Validate the postcode based on various conditions
    if (trimmedPostcode === "") {
        postcodeInput.setCustomValidity("Please enter your postcode");
    } else if (trimmedPostcode.length > 10) {
        postcodeInput.setCustomValidity("Postcode cannot exceed 10 characters");
    } else if (!/^[A-Za-z0-9]+$/.test(trimmedPostcode)) {
        postcodeInput.setCustomValidity("Invalid characters in postcode");
    } else {
        postcodeInput.setCustomValidity(""); // Clear custom validity
    }
}
```

### Validate Phone Number

This JavaScript function ensures that the user provides a valid phone number input before submitting the form:

```javascript
// Function to validate the phone number input
function validatePhoneNumber() {
    // Get the phone number input element
    var phoneNumberInput = document.getElementById("phoneNumber");
    var trimmedPhoneNumber = phoneNumberInput.value.trim();

    // Validate the phone number based on various conditions
    if (trimmedPhoneNumber === "") {
        phoneNumberInput.setCustomValidity("Please enter your phone number");
    } else if (!/^[0-9 ()+-]+$/.test(trimmedPhoneNumber)) {
        phoneNumberInput.setCustomValidity("Invalid characters in phone number");
    } else if (trimmedPhoneNumber.length < 7) {
        phoneNumberInput.setCustomValidity("Phone number must have at least 7 digits");
    } else if (trimmedPhoneNumber.length > 15) {
        phoneNumberInput.setCustomValidity("Phone number cannot exceed 15 characters");
    } else {
        phoneNumberInput.setCustomValidity(""); // Clear custom validity
    }
}

```
### Validate Email

This JavaScript function ensures that the user provides a valid email input before submitting the form:

```javascript
// Function to validate the email input
function validateEmail() {
    // Get the email input element
    var emailInput = document.getElementById("email");
    var trimmedEmail = emailInput.value.trim();

    // Validate the email based on various conditions
    if (trimmedEmail === "") {
        emailInput.setCustomValidity("Please enter your email address");
    } else if (trimmedEmail.length > 100) {
        emailInput.setCustomValidity("Email address cannot exceed 100 characters");
    } else if (!/^[a-zA-Z0-9._%+-]+@[a-zA-Z0-9.-]+\.[a-zA-Z]{2,}$/.test(trimmedEmail)) {
        emailInput.setCustomValidity("Invalid email address format");
    } else {
        emailInput.setCustomValidity(""); // Clear custom validity
    }
}

```

### Validate Message

This JavaScript function ensures that the user provides a valid message input before submitting the form:

```javascript
// Function to validate the message textarea
function validateMessage() {
    // Get the message textarea element
    var messageTextarea = document.getElementById('message');
    var messageValue = messageTextarea.value.trim();

    // Validate the message based on various conditions
    if (messageValue === "") {
        messageTextarea.setCustomValidity("Please enter your message.");
    } else if (messageValue.length > 500) {
        messageTextarea.setCustomValidity("Message cannot exceed 500 characters.");
    } else {
        messageTextarea.setCustomValidity(""); // Clear custom validity
    }

    document.getElementById("myForm").submit(); // Submit the form
}

```

### Validate Form

This JavaScript function validates all input fields in the form before submission:

```javascript
// Function to validate the entire form
function validateForm() {
    // Call individual validation functions
    validateTitle();
    validateGender();
    validateFirstName();
    validateLastName();
    validateAddress();
    validatePostcode();
    validatePhoneNumber();
    validateEmail();
    validateMessage();

    document.getElementById("myForm").submit();

    alert("Message sent");
}







