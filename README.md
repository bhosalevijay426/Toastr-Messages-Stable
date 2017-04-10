# Toastr-Messages-Stable
This is a stable JS file to display Toastr messages in your application (Designed for Java And .Net applications)
<p>It is a javascript library to display non-blocking messages to users.</p>
<h1>Demo</h1>
<p>Demo Can Be found at <a href="http://codeseven.github.io/toastr/demo.html" target="_blank">http://codeseven.github.io/toastr/demo.html</a></p>
<ul>
<li>I have modified current Toastr for use it to display from code behind in .Net</li>
<li>It can be used in any JAVA or .Net or any other application as u need</li>
<li>It is highly customizable</li>
<li>You can find its options and settings on <strong>demo</strong> page</li>
</ul>
<h2>Quick Start</h2>
<ul>
<li>Link to toastr.css</li>
<li>Link to toastr.js
</li>
<li>use toastr to display a toast for info, success, warning or error
<h3>Options in Toastr</h3>
<pre> // Display a warning toast, with no title
toastr.warning('My name is Vijay!')
// Display a success toast, with a title
toastr.success('File Uploaded Successfully.!!')
// Display an error toast, with a title
toastr.error('Error while uploading file!')
// Immediately remove current toasts without using animation
toastr.remove()
// Remove current toasts using animation
toastr.clear()
// Override global options
toastr.success('File Uploaded Successfully.!!', 'Success Message', {timeOut: 5000})
 </pre>
</li>
</ul>
<h1>To use Toastr from Codebehind in .net</h1>
<ul>
<li>Include css and JS as described Earlier(Note:Jquery must be included before toastr.js)</li>
<li>Declare one hiden field in your masterpage and set its properties as folows:
<pre>Properties:
 public string SetHiddenValue
 {
 get
 {
 return hiddenSuccess.Value;
 }
 set
 {
 hiddenSuccess.Value = value;
 }
 }
 </pre>
</li>
<li>Set all the options in Masterpage only (Include Following code in Javascript for options and settings)
<pre>$(function(){
 var val = $("#&lt;%=hiddenSuccess.ClientID %&gt;").val();
 var type = "";
 var msg = "";
 if (val != "") {
 type = val.split(/,(.+)/)[0];
 msg = val.split(/,(.+)/)[1];
 toastr.options = { <strong>Customize Your Toastr by modifying these options</strong>
 "closeButton": true,
 "debug": false,
 "newestOnTop": false,
 "progressBar": true,
 "positionClass": "toast-bottom-right",
 "preventDuplicates": true,
 "onclick": null,
 "showDuration": "300",
 "hideDuration": "1000",
 "timeOut": "6000",
 "extendedTimeOut": "1000",
 "showEasing": "swing",
 "hideEasing": "linear",
 "showMethod": "fadeIn",
 "hideMethod": "fadeOut",
 };
 switch (type) {
 case "success":
 toastr.success(msg);
 break;
 case "warning":
 toastr.warning(msg);
 break;
 case "info":
 toastr.info(msg);
 break;
 case "error":
 toastr.error(msg);
 }
 $("#&lt;%=hiddenSuccess.ClientID %&gt;").val("");
 }
 });
 </pre>
</li>
</ul>
<b>Thanks Guys Enjoy the Toastr</b>
<h1>Credits</h1>
<p>Inspired By <a href="https://github.com/CodeSeven/toastr" target="_blank">https://github.com/CodeSeven/toastr</a></p>
