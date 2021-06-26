Adding date of birth to registration from calender using jQuery datepicker
in app.blade.php add  this code to it
     <script src="https://code.jquery.com/jquery-1.12.4.js"></script>
     
     <script src="https://code.jquery.com/ui/1.12.1/jquery-ui.js"></script>
     <script>
         jQuery(document).ready(function($) {
               $('.datepicker').datepicker({
                     dateFormat: "dd-mm-yy" 
                    });
             });
      </script>

<img src="https://github.com/asare847/laravel_birth_date/blob/master/public/datepicker.png">
