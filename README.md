# Android TicTacToe
 
 This is an tic tac toe application with firebase authentication. Android Version. The user has the option to login, register, and then be taken to the main page with a tictactoe game. Note: This game requires 2 players 

 ![index](Screen1.png)


# Getting Started 

Player must login or register to use application. 

## Prerequisites
This app is able to run on emulator only currently. 

# Code Snippet

The following function takes the user's email and password and creates a new user if they do not already exist. If they do not exist then the user is added to the database and taken to the main tic tac toe page.
```
private void createFirebaseUser() {
    String email = mEmailView.getText().toString();
    String password = mPasswordView.getText().toString();
    mAuth.createUserWithEmailAndPassword(email, password).addOnCompleteListener(this, new OnCompleteListener<AuthResult>() {
        @Override
        public void onComplete(@NonNull Task<AuthResult> task) {
            Log.d("Test", "create user" + task.isSuccessful());

            if(!task.isSuccessful()) {
                Log.d("test", "user creation failed");
                showErrorDialog("Registration failed");
            } else {
                Intent intent = new Intent(RegisterActivity.this, MainActivity.class);
                finish();
                startActivity(intent);
            }
        }
    });
}
```

# Built With
- Android Studio 
- Firebase database
- Firebase authentication

# Author
* **Muhammad** - https://github.com/mawais54013