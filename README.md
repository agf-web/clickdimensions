# ClickDimensions Implementation Guide

## Using the Form Designer

- **Do not use the columns in the Clickdimensions form editor.**
- Limiting the form to 1 column gives you more control over the CSS layout than relying on HTML table structure.

## Embedding the Form

For best results, **use the Clickdimensions Widget instead of the Iframe option**. Using the Widget option offers the following benefits over using the Iframe embed:
- The height for forms does not have to manually set and is fully responsive to the size of the form
- Custom web fonts will render wherever the form is embedded
- Redirects to external URLS (thank you pages, etc.) work properly

## Notes on Using the Embed Widget

- To avoid manually setting heights or clearing the form container&#39;s default float, it&#39;s necessary to wrap the form&#39;s div container in &lt;div style=&quot;overflow:hidden&quot;&gt;&lt;/div&gt;.
- When embedding the widget to secure sites (sites that are served over HTTPS), the Clickdimensions domain host should be updated from **http://** to **https://**

Example:

Before (this is the code that Clickdimensions provides in the Embed view):
~~~~
<script type="text/javascript">var loc = "http://analytics.clickdimensions.com/agfirstcom-asvkl/pages/";</script>
<script type="text/javascript" src="https://az124611.vo.msecnd.net/web/v10/CDWidget.js"></script>
<div pageID="abcd1234efghiklmno"></div>
~~~~

After:
~~~~
<script type="text/javascript">var loc = "https://analytics.clickdimensions.com/agfirstcom-asvkl/pages/";</script>
<script type="text/javascript" src="https://az124611.vo.msecnd.net/web/v10/CDWidget.js"></script>
<div style="overflow:hidden">
  <div pageID="abcd1234efghiklmno"></div>
</div>
~~~~

Note that on line 1 the protocol has been changed to HTTPS. Note that on lines 3 & 5, the form DIV container has been wrapped in another DIV containing the **overflow:hidden** style.

## Adding and Customizing Styles

Use the base-styles.css as a template for the form stylesheet. Add the entirety of this code to the &quot;Code Editor&quot; section of the Clickdimensions Form Design view. With this code, you can:

- Specify custom fonts and change the sizes of those fonts
- Manipulate the appearance and color of the button
- Add or remove padding to form fields
- Reposition fields and/or create a responsive layout (using the CSS section called FORM GRID DEFINITIONS)
- Much, much more!
