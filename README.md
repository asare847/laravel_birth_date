Adding date of birth to registration from calender using jQuery datepicker

In app.blade.php add  this code to it

     <script src="https://code.jquery.com/jquery-1.12.4.js"></script>
     
     <script src="https://code.jquery.com/ui/1.12.1/jquery-ui.js"></script>
     <script>
         jQuery(document).ready(function($) {
               $('.datepicker').datepicker({
                     dateFormat: "dd-mm-yy" 
                    });
             });
      </script>

Add birth date input to register.php

 <div class="col-md-6">
     <input id="birth_date" type="text" class="form-control datepicker  @error('date_birth') is-invalid @enderror" name="birth_date" required autocomplete="birth_date">
 </div>

<img src="https://github.com/asare847/laravel_birth_date/blob/master/public/datepicker.png">
