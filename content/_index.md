<!-- Subscription Popup Modal -->
<div id="subscriptionModal" class="fixed inset-0 bg-black bg-opacity-50 hidden flex items-center justify-center z-50">
  <div class="bg-white dark:bg-gray-800 rounded-lg shadow-2xl p-8 max-w-md w-full mx-4 relative">
    <button onclick="closeModal()" class="absolute top-4 right-4 text-gray-500 hover:text-gray-900 dark:hover:text-white text-3xl font-bold">&times;</button>
    
    <h3 class="text-2xl font-bold text-center mb-6 text-gray-900 dark:text-white">Subscribe to ByteCascade</h3>
    <p class="text-center text-gray-700 dark:text-gray-300 mb-8">Get the latest tech news, reviews, and comparisons delivered to your inbox!</p>
    
    <div class="followit--follow-form-container" attr-a attr-b attr-c attr-d attr-e attr-f>
      <form action="https://api.follow.it/subscription-form/RGMwemhqUXlQMkhlaUdudTFHcnJvbGZWTUZFLzBEdkJLWGthVEJyay9jR1dzM2k1Ym1FRGlVaUlIS2dCY2lGU0tTVDNnMlRtenJLTTFWRHB4QU8xWXpGSlVGY2lXLzJkUTRoanRGMFlDM01QYjN5YzhyUnNvSlpTT1AyOExtRUJ8YnkyNjZOMVhOL2djVGllemE0OXNZQkY5R2xHK3pzWmNJWDVUQ3dqQVE0WT0=/8" method="post" target="_blank">
        <div class="form-preview" style="background-color: #ffffff; border: 1px solid #cccccc; padding: 20px; border-radius: 8px;">
          <div class="preview-heading text-center mb-4">
            <h5 class="text-lg font-bold">Get new posts by email:</h5>
          </div>
          <div class="preview-input-field mb-4">
            <input type="email" name="email" required placeholder="Enter your email" class="w-full px-4 py-3 border border-gray-300 rounded-lg text-center focus:outline-none focus:border-black">
          </div>
          <div class="preview-submit-button">
            <button type="submit" class="w-full py-3 bg-black text-white font-bold rounded-lg hover:bg-gray-800 transition">Subscribe</button>
          </div>
        </div>
      </form>
      <div class="text-center mt-4 text-sm text-gray-600">
        Powered by <a href="https://follow.it" target="_blank" class="underline">follow.it</a>
      </div>
    </div>
  </div>
</div>

<style>
/* Keep your original custom CSS here if needed for extra styling */
.followit--follow-form-container .form-preview {
  box-shadow: 0 5px 25px rgba(34, 60, 47, 0.25);
}
</style>

<script>
// Close modal
function closeModal() {
  document.getElementById('subscriptionModal').classList.add('hidden');
  setCookie('subscriptionPopupShown', 'true', 24); // Show again after 24 hours
}

// Cookie functions
function setCookie(name, value, hours) {
  const date = new Date();
  date.setTime(date.getTime() + (hours * 60 * 60 * 1000));
  document.cookie = name + "=" + value + "; expires=" + date.toUTCString() + "; path=/";
}

function getCookie(name) {
  const nameEQ = name + "=";
  const ca = document.cookie.split(';');
  for(let i = 0; i < ca.length; i++) {
    let c = ca[i].trim();
    if (c.indexOf(nameEQ) == 0) return c.substring(nameEQ.length);
  }
  return null;
}

// Show popup on load if not shown today
window.addEventListener('load', function() {
  if (!getCookie('subscriptionPopupShown')) {
    setTimeout(function() {
      document.getElementById('subscriptionModal').classList.remove('hidden');
    }, 8000); // 8-second delay – adjust as needed
  }
});

// Optional: Exit-intent (uncomment if you want)
// document.addEventListener('mouseout', function(e) {
//   if (e.clientY < 10 && !getCookie('subscriptionPopupShown')) {
//     document.getElementById('subscriptionModal').classList.remove('hidden');
//     setCookie('subscriptionPopupShown', 'true', 24);
//   }
// });
</script>
