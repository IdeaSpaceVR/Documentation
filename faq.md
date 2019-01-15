# FAQ

### I have lost my password and cannot login. How can I reset my password?

You have to locate the directory where you installed IdeaSpaceVR. 

Then edit the file `config/app.php` and at the bottom of the file you will find a config parameter: `'disable_forgot_password' => true`. Set this to `false` and save the file. 

Open a web browser and go to your IdeaSpaceVR login page, for example `yourdomain.com/login`. You will find a reset password link there. Click on the link and follow the instructions. 

Once your password is reset, make sure to disable the reset password link in the `config/app.php` file again by setting it to `true`.



