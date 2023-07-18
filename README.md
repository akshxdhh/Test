// Get the form element
const loginForm = document.getElementById('loginForm');

// Add event listener for form submission
loginForm.addEventListener('submit', function(event) {
  event.preventDefault(); // Prevent default form submission

  // Get the entered username and password
  const username = document.getElementById('username').value;
  const password = document.getElementById('password').value;

  // Validate the credentials
  if (username === 'admin' && password === 'password') {
    displayMessage('success', 'Login successful!');
  } else {
    displayMessage('error', 'Invalid username or password.');
  }

  // Clear the form fields
  loginForm.reset();
});

// Function to display status message
function displayMessage(type, message) {
  const statusMessage = document.getElementById('statusMessage');
  statusMessage.textContent = message;
  statusMessage.className = type;

  // Clear the status message after 3 seconds
  setTimeout(function() {
    statusMessage.textContent = '';
    statusMessage.className = '';
  }, 3000);
}

