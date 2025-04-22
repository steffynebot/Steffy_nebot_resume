---
widget: contact
headless: true  # This file represents a page section.

title: Contactez-moi
subtitle: "Pour toute demande de formation, collaboration ou autre"
weight: 10

content:
  autolink: true

  form:
    provider: netlify
    netlify:
      captcha: false

  email: contact@monsite.fr
  phone: '+33 6 12 34 56 78'
  address:
    street: 123 Rue de la Science
    city: Paris
    region: Île-de-France
    postcode: '75000'
    country: France
    country_code: FR
  coordinates:
    latitude: '48.8566'
    longitude: '2.3522'
  directions: Merci de remplir le formulaire pour toute prise de contact.
  office_hours:
    - 'Lundi 09:00 à 12:00'
    - 'Mercredi 14:00 à 17:00'
  appointment_url: 'https://calendly.com/monagenda'

  contact_links:
    - icon: envelope
      icon_pack: fas
      name: Email
      link: 'mailto:contact@monsite.fr'
    - icon: linkedin
      icon_pack: fab
      name: LinkedIn
      link: 'https://www.linkedin.com/in/tonprofil/'

design:
  columns: '1'
---