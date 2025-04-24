---
title: "Contactez-moi"
layout: page
---

<form name="contact" method="POST" data-netlify="true" netlify-honeypot="bot-field">
  <input type="hidden" name="form-name" value="contact">
  <p hidden>
    <label>Don’t fill this out: <input name="bot-field" /></label>
  </p>
  <div class="mb-3">
    <label for="name">Nom</label>
    <input type="text" name="name" id="name" class="form-control" required>
  </div>
  <div class="mb-3">
    <label for="email">Adresse Email</label>
    <input type="email" name="email" id="email" class="form-control" required>
  </div>
  <div class="mb-3">
    <label for="message">Message</label>
    <textarea name="message" id="message" rows="5" class="form-control" required></textarea>
  </div>
  <button type="submit" class="btn btn-primary">Envoyer</button>
</form>
