---
layout: single
title: Contact VentureBeyond
permalink: /contact/
---

<!-- <iframe src="https://docs.google.com/forms/d/e/1FAIpQLSfum1de1J1dgYvPU-9971Q8gNKXY43h4BWBhvzOglPpziYOLA/viewform?embedded=true" width="640" height="689" frameborder="0" marginheight="0" marginwidth="0">Loading…</iframe> -->

<!-- stylesheet: https://codepen.io/colorlib/pen/KVoZyv -->


<body>
  <div class="container">
    <form id="contact" onsubmit="return postToGoogle();">
      <h3>Contact Form</h3>
      <h4>Connect with us</h4>
      <fieldset>
        <input  placeholder="Your name"
                type="text" 
                name="entry.1540342564" 
                data-name="Name" 
                id="Name" 
                required>
      </fieldset>
      <fieldset>
        <input 
                placeholder="Your Email Address" 
                type="email" 
                name="entry.1630340827" 
                data-name="Email" 
                id="Email" 
                required>
      </fieldset>
      <fieldset>
      <fieldset>
        <textarea 
                placeholder="Type your message here...." 
                data-name="Enquiry" 
                id="Enquiry" 
                name="entry.452833952" 
                required>
        </textarea>
      </fieldset>
      <fieldset>
        <button type="submit" id="contact-submit">Submit</button>
      </fieldset>
    </form>
  </div>

  <script>
    function postToGoogle() {
      var field1 = $("#Name").val();
      var field2 = $("#Email").val();
      var field3 = $("#Phone").val();
      var field4 = $("#Message").val();

      $.ajax({
        url: "https://docs.google.com/forms/u/0/d/e/1FAIpQLSfum1de1J1dgYvPU-9971Q8gNKXY43h4BWBhvzOglPpziYOLA/formResponse",
        data: {
          "entry.1540342564": field1,
          "entry.1630340827": field2,
          "entry.452833952": field3,
        },
        type: "POST",
        dataType: "xml",
        success: function (d) {
          $('#contact').trigger('reset');
        },
        error: function (x, y, z) {
          $('#contact').trigger('reset');
        }
      });
      return false;
    }
  </script>
  <script src="https://ajax.googleapis.com/ajax/libs/jquery/3.3.1/jquery.min.js"></script>
