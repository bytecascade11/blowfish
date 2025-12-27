<!-- Subscription Popup Modal -->
<div id="subscriptionModal" class="fixed inset-0 bg-black bg-opacity-50 hidden flex items-center justify-center z-50">
  <div class="bg-white rounded-lg shadow-xl p-8 max-w-md w-full relative">
    <button onclick="closeModal()" class="absolute top-4 right-4 text-gray-500 hover:text-gray-700 text-2xl">&times;</button>
    
    <div class="followit--follow-form-container" attr-a attr-b attr-c attr-d attr-e attr-f>
      <!-- Your full existing form HTML here -->
      <form action="https://api.follow.it/subscription-form/RGMwemhqUXlQMkhlaUdudTFHcnJvbGZWTUZFLzBEdkJLWGthVEJyay9jR1dzM2k1Ym1FRGlVaUlIS2dCY2lGU0tTVDNnMlRtenJLTTFWRHB4QU8xWXpGSlVGY2lXLzJkUTRoanRGMFlDM01QYjN5YzhyUnNvSlpTT1AyOExtRUJ8YnkyNjZOMVhOL2djVGllemE0OXNZQkY5R2xHK3pzWmNJWDVUQ3dqQVE0WT0=/8" method="post">
        <div class="form-preview" style="background-color: rgb(255, 255, 255); border-style: solid; border-width: 1px; border-color: rgb(204, 204, 204); position: relative;">
          <div class="preview-heading">
            <h5 style="font-family: Arial; font-weight: bold; color: rgb(0, 0, 0); font-size: 16px; text-align: center; text-transform: none !important;">
              Get new posts by email:
            </h5>
          </div>
          <div class="preview-input-field">
            <input type="email" name="email" required placeholder="Enter your email" spellcheck="false" style="font-family: Arial; font-weight: normal; color: rgb(0, 0, 0); font-size: 14px; text-align: center; background-color: rgb(255, 255, 255); text-transform: none !important;">
          </div>
          <div class="preview-submit-button">
            <button type="submit" style="font-family: Arial; font-weight: bold; color: rgb(255, 255, 255); font-size: 16px; text-align: center; background-color: rgb(0, 0, 0); text-transform: none !important;">
              Subscribe
            </button>
          </div>
        </div>
      </form>
      <a href="https://follow.it" class="powered-by-line">Powered by <img src="https://follow.it/images/colored-logo.svg" alt="follow.it" height="17px"/></a>
    </div>
  </div>
</div>

<!-- Include your full CSS <style> block here (same as before) -->

<script>
// Function to set cookie (expires in 24 hours)
function setCookie(name, value, hours) {
  const date = new Date();
  date.setTime(date.getTime() + (hours * 60 * 60 * 1000));
  document.cookie = name + "=" + value + ";expires=" + date.toGMTString() + ";path=/";
}

// Check if cookie exists
function getCookie(name) {
  const nameEQ = name + "=";
  const ca = document.cookie.split(';');
  for(let i = 0; i < ca.length; i++) {
    let c = ca[i];
    while (c.charAt(0) === ' ') c = c.substring(1);
    if (c.indexOf(nameEQ) === 0) return c.substring(nameEQ.length);
  }
  return null;
}

// Close modal and set cookie
function closeModal() {
  document.getElementById('subscriptionModal').classList.add('hidden');
  setCookie('subscriptionPopup', 'shown', 24);  // 24 hours
}

// Show popup if not seen today
window.onload = function() {
  if (!getCookie('subscriptionPopup')) {
    setTimeout(function() {
      document.getElementById('subscriptionModal').classList.remove('hidden');
    }, 10000);  // 10-second delay (change to 0 for immediate, or add exit-intent below)
  }
};

// Optional: Exit-intent trigger (shows when mouse leaves page)
document.addEventListener('mouseleave', function() {
  if (!getCookie('subscriptionPopup')) {
    document.getElementById('subscriptionModal').classList.remove('hidden');
    setCookie('subscriptionPopup', 'shown', 24);
  }
});
</script>
