HTML Input Types

Here are the different input types you can use in HTML:

-   \<input type="button"\>
-   \<input type="checkbox"\>
-   \<input type="date"\>
-   \<input type="email"\>
-   \<input type="file"\>
-   \<input type="image"\>
-   \<input type="number"\>
-   \<input type="password"\>
-   \<input type="radio"\>
-   \<input type="reset"\>
-   \<input type="search"\>
-   \<input type="submit"\>
-   \<input type="text"\>

**Tip:** The default value of the type attribute is "text".

## Input Type Text

\<input type="text"\> defines a **single-line text input field**:

![](media/63ad0d6804de8ebb6eee6e67f2af12b6.png)

## Input Type Password

\<input type="password"\> defines a **password field**:

![](media/1af781a376e9132c71eaf10e3d8eb6a5.png)The characters in a password field are masked (shown as asterisks or circles).

## Input Type Submit

\<input type="submit"\> defines a button for **submitting** form data to a **form-handler**.

The form-handler is typically a server page with a script for processing input data.

The form-handler is specified in the form's action attribute:

![](media/17f2e8516cdd652f89460448725f9aac.png)

If you omit the submit button's value attribute, the button will get a default text:

## HTML Images Syntax

The HTML \<img\> tag is used to embed an image in a web page.

Images are not technically inserted into a web page; images are linked to web pages. The \<img\> tag creates a holding space for the referenced image.

The \<img\> tag is empty, it contains attributes only, and does not have a closing tag.

The \<img\> tag has two required attributes:

-   src - Specifies the path to the image
-   alt - Specifies an alternate text for the image

### Syntax

\<img src="*url*" alt="*alternatetext*"\>

## The src Attribute

The required src attribute specifies the path (URL) to the image.

**Note:** When a web page loads, it is the browser, at that moment, that gets the image from a web server and inserts it into the page. Therefore, make sure that the image actually stays in the same spot in relation to the web page, otherwise your visitors will get a broken link icon. The broken link icon and the alt text are shown if the browser cannot find the image.

![](media/3df3acc78efd31a3984e5ab197097ea5.png)

![](media/d87607db5e26e11de8dae1673b0383e7.png)

## Input Type Reset

\<input type="reset"\> defines a **reset button** that will reset all form values to their default values:

![](media/657e22cddeac215c2bcb5a18b7e17c5b.png)

If you change the input values and then click the "Reset" button, the form-data will be reset to the default values.

## Input Type Radio

\<input type="radio"\> defines a **radio button**.

Radio buttons let a user select ONLY ONE of a limited number of choices:

![](media/2458011107b70534c111e143d03f3a44.png)

## Input Type Checkbox

\<input type="checkbox"\> defines a **checkbox**.

Checkboxes let a user select ZERO or MORE options of a limited number of choices.

![](media/56ca3a135544cf9034f6d8844ad285d2.png)

## Input Type Button

\<input type="button"\> defines a **button**:

![](media/e7fdc007dfc9a5ab1eac918c662b3262.png)

## Input Type Date

The \<input type="date"\> is used for input fields that should contain a date.

Depending on browser support, a date picker can show up in the input field.

![](media/388663c501435fa3d4d796e561168280.png)You can also use the min and max attributes to add restrictions to dates:

![](media/66e7cb7a7aec8603b181e5911213f8c3.png)

## Input Type Email

The \<input type="email"\> is used for input fields that should contain an e-mail address.

Depending on browser support, the e-mail address can be automatically validated when submitted.

Some smartphones recognize the email type, and add ".com" to the keyboard to match email input.

![](media/94db42f6073c2cc9732d14477abb52b5.png)

## Input Type File

The \<input type="file"\> defines a file-select field and a "Browse" button for file uploads.

![](media/332267652486dfab082bb96dd288921f.png)

## Input Type Number

The \<input type="number"\> defines a **numeric** input field.

You can also set restrictions on what numbers are accepted.

The following example displays a numeric input field, where you can enter a value from 1 to 5:

## ![](media/548f06795650184ff081a3b40e5e15f8.png)Input Type Search

The \<input type="search"\> is used for search fields (a search field behaves like a regular text field).

![](media/22db32e7fb2cb4fceb06101ebaeafa3e.png)

# HTML Images

The HTML \<img\> tag is used to embed an image in a web page.

Images are not technically inserted into a web page; images are linked to web pages. The \<img\> tag creates a holding space for the referenced image.

The \<img\> tag is empty, it contains attributes only, and does not have a closing tag.

The \<img\> tag has two required attributes:

-   src - Specifies the path to the image
-   alt - Specifies an alternate text for the image

### Syntax

\<img src="*url*" alt="*alternatetext*"\>

## The src Attribute

The required src attribute specifies the path (URL) to the image.

**Note:** When a web page loads, it is the browser, at that moment, that gets the image from a web server and inserts it into the page. Therefore, make sure that the image actually stays in the same spot in relation to the web page, otherwise your visitors will get a broken link icon. The broken link icon and the alt text are shown if the browser cannot find the image.

![](media/261b7293cb25ff95f7d5401daff80cd5.png)
