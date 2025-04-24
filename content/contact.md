---
title: "Contactez-moi"
layout: page
---
N'hésitez pas à me contacter via ce formulaire :

{{ define "main" }}
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/bootstrap@3.4.1/dist/css/bootstrap.min.css" crossorigin="anonymous">
<script src="https://cdn.jsdelivr.net/npm/jquery@3.6.0/dist/jquery.min.js" crossorigin="anonymous"></script>

<div class="container my-5">
  <form action="https://formkeep.com/f/1b6392ead701" method="POST" enctype="multipart/form-data" accept-charset="UTF-8">
    <fieldset>
      <h2 class="text-center">Contactez-moi</h2>
      <div class="row">
        <div class="form-group col-sm-6">
          <label for="First_Name">Prénom</label>
          <input type="text" name="First Name" id="First_Name" class="form-control">
        </div>
        <div class="form-group col-sm-6">
          <label for="Last_Name">Nom</label>
          <input type="text" name="Last Name" id="Last_Name" class="form-control">
        </div>
      </div>

      <div class="row">
        <div class="form-group col-sm-6">
          <label for="Email">Email *</label>
          <input type="email" name="Email" id="Email" required placeholder="example@example.com" class="form-control">
        </div>
        <div class="form-group col-sm-6">
          <label for="Phone">Téléphone</label>
          <input type="tel" name="Phone" id="Phone" placeholder="06 00 00 00 00" class="form-control">
        </div>
      </div>

      <div class="form-group">
        <label for="Reason">Objet *</label>
        <select name="Reason" id="Reason" required class="form-control">
          <option value="">Choisissez</option>
          <option value="Support">Support technique</option>
          <option value="Formation">Demande de formation</option>
          <option value="Publication">Proposition de publication</option>
          <option value="Autre">Autre</option>
        </select>
      </div>

      <div class="form-group">
        <label for="Message">Message *</label>
        <textarea name="Message" id="Message" required class="form-control" rows="5"></textarea>
      </div>

      <div style="opacity:0;position:absolute;top:0;left:-5000px;height:0;width:0">
        <input name="subscribe_1b6392ead701_48334" type="email" tabindex="-1" autocomplete="off" placeholder="Your email here">
      </div>

      <input type="submit" value="Envoyer" class="btn btn-primary btn-block">
    </fieldset>
  </form>
</div>
{{ end }}
