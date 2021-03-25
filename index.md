---
layout: lesson
root: .  # Is the only page that doesn't follow the pattern /:path/index.html
permalink: index.html  # Is the only page that doesn't follow the pattern /:path/index.html
email: ["support@archer2.ac.uk"]
address: "online"
---

{% if page.address == "online" %}
{% assign online = "true_private" %}
{% else %}
{% assign online = "false" %}
{% endif %}

<h2>Description</h2>

This lesson provides an introduction to using ARCHER2 for users who:
  - have already used other HPC systems; and
  - want to compile (and possibly) develop HPC software on ARCHER2.

The lesson aims to answer the following questions:
  - What hardware is available on ARCHER2?
    + What does it consist of (login nodes, compute nodes, file systems, backup)?
    + How does this impact me as a user?
  - How can I access ARCHER2 interactively and transfer data?
  - What does the ARCHER2 application development environment look like and how do I use it?
  - How do I write job submission scripts and submit them to the ARCHER2 scheduler?
  - How can I be a good ARCHER2 citizen?
  - How can I check what resources I am using and look at historical usage?
  - What are the next steps for me using ARCHER2 and how can I get more help?

<hr/>

<h2 id="general">General Information</h2>

{% comment %}
  SPECIAL REQUIREMENTS

  Modify the block below if there are any special requirements.
{% endcomment %}
<p id="requirements">
  <strong>Requirements:</strong> {% if online == "false" %} Participants must bring a laptop with a Mac, Linux, or Windows operating system (not a tablet, Chromebook, etc.) that they have administrative privileges on. {% else %} Participants must have access to a computer with a Mac, Linux, or Windows operating system (not a tablet, Chromebook, etc.) that they have administrative privileges on. {% endif %} They should have a few specific software packages installed (listed
  <a href="#setup">below</a>). They are also required to abide by the <a href="https://www.archer2.ac.uk/training/code-of-conduct/">ARCHER2 Training Code of Conduct</a>.
</p>

{% comment %}
  ACCESSIBILITY

  Modify the block below if there are any barriers to accessibility or
  special instructions.
{% endcomment %}
<p id="accessibility">
  <strong>Accessibility:</strong> {% if online == "false" %} We are committed to making this workshop accessible to everybody. The workshop organizers have checked that:

The room is wheelchair / scooter accessible.
Accessible restrooms are available.
Materials will be provided in advance of the workshop and large-print handouts are available if needed by notifying the organizers in advance. If we can help making learning easier for you (e.g. sign-language interpreters, lactation facilities) please get in touch (using contact details below) and we will attempt to provide them.

{% else %} We are dedicated to providing a positive and accessible learning environment for all. Please notify the instructors in advance of the workshop if you require any accommodations or if there is anything we can do to make this workshop more accessible to you.
{% endif %}
</p>

{% comment %}
  CONTACT EMAIL ADDRESS

  Display the contact email address set in the configuration file.
{% endcomment %}
<p id="contact">
  <strong>Contact:</strong>
  Please email
  {% if page.email %}
  {% for email in page.email %}
  {% if forloop.last and page.email.size > 1 %}
  or
  {% else %}
  {% unless forloop.first %}
  ,
  {% endunless %}
  {% endif %}
  <a href='mailto:{{email}}'>{{email}}</a>
  {% endfor %}
  {% else %}
  to-be-announced
  {% endif %}
  for more information.
</p>

<hr/>

> ## Prerequisites
> You should have used remote HPC facilities before. In particular, you should be happy with connecting
> using SSH, know what a batch scheduling system is and be familiar with using the Linux command line.
> You should also be happy editing plain text files in a remote terminal (or, alternatively, editing them
> on your local system and copying them to the remote HPC system using `scp`). Finally, you should be 
> comfortable with compiling parallel HPC source code that uses MPI and OpenMP.
{: .prereq}

<hr/>

{% include links.md %}

