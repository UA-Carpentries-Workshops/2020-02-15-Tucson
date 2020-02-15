---
layout: workshop      # DON'T CHANGE THIS.
venue: "University of Arizona"        # brief name of host site without address (e.g., "Euphoric State University")
address: "check your email"      # full street address of workshop (e.g., "Room A, 123 Forth Street, Blimingen, Euphoria")
country: "en"      # lowercase two-letter ISO country code such as "fr" (see https://en.wikipedia.org/wiki/ISO_3166-1#Current_codes)
language: "en"     # lowercase two-letter ISO language code such as "fr" (see https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes)
latitude: "30.231901"     # decimal latitude of workshop venue (use https://www.latlong.net/)
longitude: "88.9495000"    # decimal longitude of the workshop venue (use https://www.latlong.net)
humandate: "Feb 15-16, 2020"    # human-readable dates for the workshop (e.g., "Feb 17-18, 2020")
humantime: "8:30 am - 5:00 pm"    # human-readable times for the workshop (e.g., "9:00 am - 4:30 pm")
startdate: 2020-02-15      # machine-readable start date for the workshop in YYYY-MM-DD format like 2015-01-01
enddate: 2020-02-16        # machine-readable end date for the workshop in YYYY-MM-DD format like 2015-01-02
instructor: ["Drake Asberry", "Nathalia Graf Gachet", "Uwe Hilgert"] # boxed, comma-separated list of instructors' names as strings, like ["Kay McNulty", "Betty Jennings", "Betty Snyder"]
helper: ["Ryan Bartelme", "Alex Bigelow", "Gustavo de Oliveira Almeida", "Noah Giebink", "Fayu Jiang", "Albert Reiber", "Zhixue Shu", "Heidi Steiner", "Travis Struck", "Isabella Viney", "Jeremy Weiss", "Derrick Yoo"]     # boxed, comma-separated list of helpers' names, like ["Marlyn Wescoff", "Fran Bilas", "Ruth Lichterman"]
email: ["hilgert@bio5.org"]    # boxed, comma-separated list of contact email addresses for the host, lead instructor, or whoever else is handling questions, like ["marlyn.wescoff@example.org", "fran.bilas@example.org", "ruth.lichterman@example.org"]
collaborative_notes: http://pad.software-carpentry.org/2020-02-15-Tucson # optional: URL for the workshop collaborative notes, e.g. an Etherpad or Google Docs document
eventbrite:           # optional: alphanumeric key for Eventbrite registration, e.g., "1234567890AB" (if Eventbrite is being used)
---

<p><h4><center><strong>Apply for the workshop at <a href="http://bit.ly/35NErJo" target='blank'>http://bit.ly/35NErJo</a>.</strong></center></h4></p>


{% if site.carpentry == "dc" or site.carpentry == "dc" %}
{% unless site.curriculum == "dc-ecology" or site.curriculum == "dc-genomics" or site.curriculum == "dc-socsci" or site.curriculum == "dc-geospatial" %}
<div class="alert alert-warning">
It looks like you are setting up a website for a Data Carpentry curriculum but you haven't specified the curriculum type in the <code>_config.yml</code> file (current value in <code>_config.yml</code>: "<strong>{{ site.curriculum }}</strong>", possible values: <code>dc-ecology</code>, <code>dc-genomics</code>, <code>dc-socsci</code>, or <code>dc-geospatial</code>). After editing this file, you need to run <code>make serve</code> again to see the changes reflected.
</div>
{% endunless %}
{% endif %}

{% comment %}
EVENTBRITE

This block includes the Eventbrite registration widget if
'eventbrite' has been set in the header.  You can delete it if you
are not using Eventbrite, or leave it in, since it will not be
displayed if the 'eventbrite' field in the header is not set.
{% endcomment %}
{% if page.eventbrite %}
<iframe
  src="https://www.eventbrite.com/tickets-external?eid={{page.eventbrite}}&ref=etckt"
  frameborder="0"
  width="100%"
  height="280px"
  scrolling="auto">
</iframe>
{% endif %}


<h2 id="general">General Information</h2>

{% comment %}
INTRODUCTION

Edit the general explanatory paragraph below if you want to change
the pitch.
{% endcomment %}
{% if site.carpentry == "swc" %}
{% include swc/intro.html %}
{% elsif site.carpentry == "dc" %}
{% include dc/intro.html %}
{% elsif site.carpentry == "lc" %}
{% include lc/intro.html %}
{% endif %}

{% comment %}
AUDIENCE

Explain who your audience is.  (In particular, tell readers if the
workshop is only open to people from a particular institution.
{% endcomment %}
{% if site.carpentry == "swc" %}
{% include swc/who.html %}
{% elsif site.carpentry == "dc" %}
{% include dc/who.html %}
{% elsif site.carpentry == "lc" %}
{% include lc/who.html %}
{% endif %}

{% comment %}
LOCATION

This block displays the address and links to maps showing directions
if the latitude and longitude of the workshop have been set.  You
can use https://itouchmap.com/latlong.html to find the lat/long of an
address.
{% endcomment %}
{% if page.latitude and page.longitude %}
<p id="where">
  <strong>Where:</strong>
  {{page.address}}.
  Get directions with
  <a href="//www.openstreetmap.org/?mlat={{page.latitude}}&mlon={{page.longitude}}&zoom=16">OpenStreetMap</a>
  or
  <a href="//maps.google.com/maps?q={{page.latitude}},{{page.longitude}}">Google Maps</a>.
</p>
{% endif %}

{% comment %}
DATE

This block displays the date and links to Google Calendar.
{% endcomment %}
{% if page.humandate %}
<p id="when">
  <strong>When:</strong>
  {{page.humandate}}.
  {% include workshop_calendar.html %}
</p>
{% endif %}

{% comment %}
SPECIAL REQUIREMENTS

Modify the block below if there are any special requirements.
{% endcomment %}
<p id="requirements">
  <strong>Requirements:</strong> Participants must bring a laptop with a
  Mac, Linux, or Windows operating system (not a tablet, Chromebook, etc.) that they have administrative privileges on. They should have a few specific software packages installed (listed <a href="#setup">below</a>).
</p>

{% comment%}
CODE OF CONDUCT
{% endcomment %}
<p id="code-of-conduct">
<strong>Code of Conduct:</strong>  Everyone who participates in Carpentries activities is required to conform to the <a href="https://docs.carpentries.org/topic_folders/policies/code-of-conduct.html">Code of Conduct</a>. This document also outlines how to report an incident if needed.
</p>


{% comment %}
ACCESSIBILITY

Modify the block below if there are any barriers to accessibility or
special instructions.
{% endcomment %}
<p id="accessibility">
  <strong>Accessibility:</strong> We are committed to making this workshop
  accessible to everybody.
  The workshop organizers have checked that:
</p>
<ul>
  <li>The room is wheelchair / scooter accessible.</li>
  <li>Accessible restrooms are available.</li>
</ul>
<p>
  If we can help making learning easier for
  you (e.g. sign-language interpreters, lactation facilities) please
  get in touch (using contact details below) and we will
  attempt to provide them.
</p>

{% comment %}
CONTACT EMAIL ADDRESS

Display the contact email address set in the configuration file.
{% endcomment %}
<p id="contact">
  <strong>Contact</strong>:
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
<p>Information about the <a href="http://tucsonrodeo.com/schedule/"><b>Tucson Rodeo Week 2020</b></a></p>

<hr/>

{% comment %} 
SURVEYS - DO NOT EDIT SURVEY LINKS 
{% endcomment %}
<h2 id="surveys">Surveys</h2>
<p>Please be sure to complete these surveys before and after the workshop.</p>
<p><a href="{{ site.pre_survey }}{{ site.github.project_title }}">Pre-workshop Survey</a></p>
<p><a href="{{ site.post_survey }}{{ site.github.project_title }}">Post-workshop Survey</a></p>

<hr/>


{% comment %}
SCHEDULE

Show the workshop's schedule.  Edit the items and times in the table
to match your plans.  You may also want to change 'Day 1' and 'Day
2' to be actual dates or days of the week.
{% endcomment %}
<h2 id="schedule">Schedule</h2>

<div class="row">
  <div class="col-md-6">
    <h3>Saturday February 15</h3>
    <table class="table table-striped">
      <tr> <td>08:30</td> <td><a href="https://github.com/UA-Carpentries-Workshops/2019-02-23-WorkshopResources/blob/master/shell-lessons/1_intro-to-shell.md" target="_blank">Access and navigate the command line / Bash Shell</a></td> </tr>
      <tr> <td>10:30</td> <td>Coffee Break</td> </tr>
      <tr> <td>10:45</td> <td> <a href="https://github.com/UA-Carpentries-Workshops/Goat_Path_Git_Lesson" target="_blank">Manage data with git/GitHub</a></td> </tr>
      <tr> <td>12:00</td> <td>Lunch Break*</td> </tr>
      <tr> <td>13:00</td> <td>Analyze data in the Bash Shell</td> </tr>
      <tr> <td>14:45</td> <td>Coffee Break</td> </tr>
      <tr> <td>15:00</td> <td><a href="https://github.com/UA-Carpentries-Workshops/2019-02-23-WorkshopResources/tree/master/python-lessons" target="_blank">Analyze scientific data with Python </a></td> </a></tr>
      <tr> <td>17:00</td> <td>End of Day</td> </tr>
    </table>
  </div>
  <div class="col-md-6">
    <h3>Sunday February 16</h3>
    <table class="table table-striped">
      <tr> <td>08:30</td>  <td><a href="https://github.com/UA-Carpentries-Workshops/2019-02-23-WorkshopResources/tree/master/python-lessons" target="_blank">Analyze scientific data with Python </a> and <a href="http://swcarpentry.github.io/git-novice/" target="_blank">git/GitHub</a></td> </tr>
      <tr> <td>10:30</td>  <td>Coffee Break</td> </tr>
      <tr> <td>11:00</td>  <td><a href="https://github.com/UA-Carpentries-Workshops/2019-02-23-WorkshopResources/tree/master/python-lessons" target="_blank">Analyze scientific data with Python </a> and <a href="http://swcarpentry.github.io/git-novice/" target="_blank">git/GitHub</a>, cont.</td> </tr>
      <tr> <td>12:00</td>  <td>Lunch Break*</td> </tr>
      <tr> <td>13:00</td>  <td><a href="https://github.com/UA-Carpentries-Workshops/2019-02-23-WorkshopResources/tree/master/python-lessons" target="_blank">Analyze scientific data with Python </a> and <a href="http://swcarpentry.github.io/git-novice/" target="_blank">git/GitHub</a>, cont.</td> </tr>
      <tr> <td>14:45</td>  <td>Coffee Break</td> </tr>
      <tr> <td>15:00</td>  <td><a href="https://github.com/UA-Carpentries-Workshops/2019-02-23-WorkshopResources/tree/master/python-lessons" target="_blank">Analyze scientific data with Python </a> and <a href="http://swcarpentry.github.io/git-novice/" target="_blank">git/GitHub</a>, cont.</td> </tr>
      <tr> <td>17:00</td>  <td>End of Day</td> </tr>
    </table>
  </div>
</div>

<p>* <a href="http://bit.ly/37asaPD">Click for a list and map of nearby eateries.</a></p>

<p>Schedule subject to change if necessary.</p>

<hr/>

{% comment %}
Collaborative Notes

If you want to use an Etherpad, go to

http://pad.carpentries.org/YYYY-MM-DD-site

where 'YYYY-MM-DD-site' is the identifier for your workshop,
e.g., '2015-06-10-esu'.
{% endcomment %}
{% if page.collaborative_notes %}
<p id="collaborative_notes">
  We will use this <a href="{{page.collaborative_notes}}">collaborative document</a> for chatting, taking notes, and sharing URLs and bits of code.
</p>
{% endif %}

<hr/>

{% comment %}
SYLLABUS

Show what topics will be covered.

1. If your workshop is R rather than Python, remove the comment
around that section and put a comment around the Python section.
2. Some workshops will delete SQL.
3. Please make sure the list of topics is synchronized with what you
intend to teach.
4. You may need to move the div's with class="col-md-6" around inside
the div's with class="row" to balance the multi-column layout.

This is one of the places where people frequently make mistakes, so
please preview your site before committing, and make sure to run
'tools/check' as well.
{% endcomment %}

<h2 id="syllabus">Syllabus & Learning Objectives</h2>

<div class="row">
  <div class="col-md-6">
	  <h3 id="syllabus-shell">Take control with the Bash Shell (Command Line/Shell/Unix)</h3>
    <ul>
	    <li>Work <em>in</em> vs. work <em>below</em> the GUI</li>
	    <li>Navigate the shell</li>
	    <li><code>Find</code>, create, copy, move and delete folders and files</li>
	    <li>Shell over GUI: Command history and tab completion</li>
	    <li>Connect commands into workflows: pipes and redirection</li>
	    <li>Automate repetitive tasks: loops</li>
	    <li>Save and run workflows in scripts</li>
	  </ul>
	  <u>Resources:</u>
	  <ul>
		  <li><a href="{{site.swc_pages}}/shell-novice">Shell Lessons</a></li>
		  <li><a href="{{site.swc_pages}}/shell-novice/reference">Shell Quick Reference</a></li>
		  <li><a href="http://explainshell.com/" target="_blank"><em>Explain Shell</em> (Parses shell commands and shows docs about the command)</a></li>
		  <li><a href="http://www.shellcheck.net/" target="_blank"><em>ShellCheck</em> (Identifies bugs in shell scripts)</a></li>
		  <li><a href="http://man.he.net/" target="_blank"><em>Linux Man Pages Online</em> (Same content as command line man/help pages)</a></li>
	  </ul>
  </div>

  <div class="col-md-6">
	  <h3 id="syllabus-git">Collaborate with git/GitHub</h3>
    <ul>
	    <li>Access a repository and pull files</li>
	    <li>Create a repository</li>
	    <li>Record changes: <code>add</code>, <code>commit</code>, ...</li>
	    <li>View changes: <code>status</code>, <code>diff</code>, ...</li>
	    <li>Ignore files</li>
	    <li>Work on the web: <code>clone</code>, <code>pull</code>, <code>push</code>, ...</li>
	    <li>Resolve conflicts</li>
	  </ul>
	  <u>Resources:</u>
	  <ul>
		  <li><a href="{{site.swc_pages}}/git-novice">Git Lessons</a></li>
		  <li><a href="{{site.swc_pages}}/git-novice/reference">Git Quick Reference</a></li>
		  <li><a href="https://git-scm.com/book/en/v2/Git-in-Other-Environments-Git-in-Bash" target="_blank"><i>Mac/Linux:</i> Integrating Git into your shell prompt</a></li>
		  <li><a href="https://github.com/magicmonty/bash-git-prompt" target="_blank">An informative and fancy bash prompt for Git users</a></li>
		  <li><a href="https://education.github.com/pack" target="_blank">Unlimited <em>private</em> repositories for free on Github, <i>while you are a student</i></a></li>
		  <li><a href="https://git-annex.branchable.com/" target="_blank">Git for Archiving Data</a></li>
	  </ul>
  </div>

</div>

<div class="row">
<div class="col-md-6">
    <h3 id="syllabus-python">Analyse scientific data with Python</h3>
    <ul>
      <li>Use libraries</li>
      <li>Work with arrays</li>
      <li>Read and plot data</li>
      <li>Create and use functions</li>
      <li>Use loops and conditionals</li>
      <li>Use Python from the command line</li>
      <li>Defensive programming</li>
    </ul>
	  <u>Resources:</u>
	  <ul>
		  <li><a href="{{site.swc_pages}}/python-novice-gapminder">Python Lessons</a></li>
		  <li><a href="{{site.swc_pages}}/python-novice-gapminder/reference/">Python Quick Reference</a></li>
                  <li><a href="https://www.codecademy.com/learn/python" target="_blank">Codecademy: Interactive Python practice lessons</a></li>
		  <li><a href="http://rosalind.info/problems/list-view/?location=python-village" target="_blank">Rosalind Python Bioinformatics Practice</a></li>
		  <li><a href="https://www.datacamp.com/community/tutorials/tutorial-jupyter-notebook#gs.mz7KeNQ" target="_blank">Jupyter Notebook tutorial</a></li>
		  <li><a href="https://plot.ly/python/" target="_blank">Interactive plotting with Plotly (available for R and for Python)</a></li>


    </ul>
  </div>
</div>

<p>Syllabus subject to change if necessary.</p>

<hr/>

{% comment %}
SETUP

Delete irrelevant sections from the setup instructions.  Each
section is inside a 'div' without any classes to make the beginning
and end easier to find.

This is the other place where people frequently make mistakes, so
please preview your site before committing, and make sure to run
'tools/check' as well.
{% endcomment %}

<h2 id="setup">Setup</h2>

<p>
  To participate in the
  {% if site.carpentry == "swc" %}
  Software Carpentry
  {% elsif site.carpentry == "dc" %}
  Data Carpentry
  {% elsif site.carpentry == "lc" %}
  Library Carpentry
  {% endif %}
  workshop,
  you will need access to the software described below.
  In addition, you will need an up-to-date web browser.
</p>

<p>
  We maintain a list of common issues that occur during installation as a reference for instructors
  that may be useful on the
  <a href = "{{site.swc_github}}/workshop-template/wiki/Configuration-Problems-and-Solutions">Configuration Problems and Solutions wiki page</a>.
</p>

{% if site.carpentry == "swc" %}
{% include swc/setup.html %}
{% elsif site.carpentry == "dc" %}
{% include dc/setup.html %}
{% elsif site.carpentry == "lc" %}
{% include lc/setup.html %}
{% endif %}
