// Mobile nav toggle
document.addEventListener('DOMContentLoaded', function () {
  var toggle = document.querySelector('.nav-toggle');
  var mobileNav = document.querySelector('.mobile-nav');

  if (toggle && mobileNav) {
    toggle.addEventListener('click', function () {
      var isOpen = mobileNav.classList.toggle('open');
      toggle.setAttribute('aria-expanded', isOpen ? 'true' : 'false');
    });

    // Close menu after tapping a link
    mobileNav.querySelectorAll('a').forEach(function (link) {
      link.addEventListener('click', function () {
        mobileNav.classList.remove('open');
        toggle.setAttribute('aria-expanded', 'false');
      });
    });
  }

  // Logo fallback: if logo.svg fails to load, show text wordmark instead
  var logoImg = document.querySelector('.logo-img');
  var logoFallback = document.querySelector('.logo-fallback');
  if (logoImg && logoFallback) {
    logoImg.addEventListener('error', function () {
      logoImg.style.display = 'none';
      logoFallback.style.display = 'block';
    });
  }

  // Client-side file size check on the quote form (server/FormSubmit has its own limits too)
  var form = document.querySelector('.quote-form');
  var fileInput = document.querySelector('#data_sheet_upload');
  var fileError = document.querySelector('#file-error');
  var MAX_MB = 10;

  if (form && fileInput && fileError) {
    form.addEventListener('submit', function (e) {
      var file = fileInput.files[0];
      if (file && file.size > MAX_MB * 1024 * 1024) {
        e.preventDefault();
        fileError.textContent = 'That file is over ' + MAX_MB + 'MB. Please compress it or email it to us directly.';
        fileError.classList.add('show');
        fileInput.focus();
      } else {
        fileError.classList.remove('show');
      }
    });
  }
});
