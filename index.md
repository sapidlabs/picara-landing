---
# Feel free to add content and custom Front Matter to this file.
# To modify the layout, see https://jekyllrb.com/docs/themes/#overriding-theme-defaults

layout: home
---
<link rel="stylesheet" href="{{ site.baseurl }}/css/site.css">
<div class="split-l left">
  <img src="/picara-landing/assets/images/picara.png" alt="Picara mockup">
</div>

<div class="split-r right">
  <div class="centered">
    <!-- <img src="img_avatar.png" alt="Avatar man"> -->
    <h2 class='head'>Pícara</h2>
    <p class='help-text'>Your Beauty Partner</p>
    <form data-form='true' class='form-inline' action="https://formcarry.com/s/MQQyBqYP-W0" accept-charset="UTF-8">
      <input type='email' placeholder='Enter Your Email' name='email'>
      <input type="hidden" name="_gotcha">
      <input type='submit' value='Get Download Link'>
    </form>
  </div>
</div>

<script src="https://ajax.googleapis.com/ajax/libs/jquery/2.2.4/jquery.min.js"></script>
<script>
  $(function() {
    $("[data-form=true]").submit(function(e){
      e.preventDefault();
      var href = $(this).attr("action");
      var form = $(this)[0];
      $.ajax({
        type: "POST",
        dataType: "json",
        url: href,
        data: $(this).serialize(),
        success: function(response){
          if(response.status == "success"){
            alert("Thank you for your interest!! We will send you the download link soon");
            $('[data-form=true]')[0].reset();
          }else{
            alert("An error occured: " + response.message);
          }
        }
      });
    });
  })
</script>
