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

in the RegisterController.php add birth_date attributes like so

 

    protected function validator(array $data)
    {
	   return Validator::make($data, [
            'name' => ['required', 'string', 'max:255'],
            'email' => ['required', 'string', 'email', 'max:255', 'unique:users'],
            'password' => ['required', 'string', 'min:8', 'confirmed'],
            'birth_date'=> ['required', 'string'],
        ]);
		
    }

    /**
     * Create a new user instance after a valid registration.
     *
     * @param  array  $data
     * @return \App\Models\User
     */
    protected function create(array $data)
    {
        return User::create([
            'name' => $data['name'],
            'email' => $data['email'],
            'password' => Hash::make($data['password']),
            'birth_date'=> $data['birth_date'],
        ]);
    }
