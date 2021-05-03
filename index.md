---
layout: workshop      # DON'T CHANGE THIS.
root: .               # DON'T CHANGE THIS EITHER.  (THANK YOU.)
country: "nz"      # lowercase two-letter ISO country code such as "fr" (see https://en.wikipedia.org/wiki/ISO_3166-1)
language: "en"     # lowercase two-letter ISO language code such as "fr" (see https://en.wikipedia.org/wiki/ISO_639-1)
humandate: "4, 5, 11, 12, 18, 19, 25, and 26 May 2021"    # human-readable dates for the workshop (e.g., "Feb 17-18, 2020")
humantime: "1:00 pm - 3:00pm NZST"    # human-readable times for the workshop (e.g., "9:00 am - 4:30 pm")
startdate: 2021-05-04      # machine-readable start date for the workshop in YYYY-MM-DD format like 2015-01-01
enddate: 2021-05-26        # machine-readable end date for the workshop in YYYY-MM-DD format like 2015-01-02
instructor: ["Megan Guidry", "Murray Cadzow", "Arindam Basu", "Mik Black"] # boxed, comma-separated list of instructors' names as strings, like ["Kay McNulty", "Betty Jennings", "Betty Snyder"]
helper: [""]     # boxed, comma-separated list of helpers' names, like ["Marlyn Wescoff", "Fran Bilas", "Ruth Lichterman"]
contact: ["megan.guidry@nesi.org.nz", "murray.cadzow@otago.ac.nz"]    # boxed, comma-separated list of contact email addresses for the host, lead instructor, or whoever else is handling questions, like ["marlyn.wescoff@example.org", "fran.bilas@example.org", "ruth.lichterman@example.org"]
etherpad:  https://pad.carpentries.org/2021-05-04-ttt-online-NZST           # optional: URL for the workshop Etherpad if there is one
eventbrite:           # optional: alphanumeric key for Eventbrite registration, e.g., "1234567890AB" (if Eventbrite is being used)
locations:
  - venue: "Online"
    address: "Will be emailed to participants."



---

<!-- See instructions in the comments below for how to edit specific sections of this workshop template. -->

<!--
  HEADER

  Edit the values in the block above to be appropriate for your workshop.
  If the value is not 'true', 'false', 'null', or a number, please use
  double quotation marks around the value, unless specified otherwise.
  And run 'tools/check' *before* committing to make sure that changes are good.
-->

<!--
  EVENTBRITE

  This block includes the Eventbrite registration widget if
  'eventbrite' has been set in the header.  You can delete it if you
  are not using Eventbrite, or leave it in, since it will not be
  displayed if the 'eventbrite' field in the header is not set.
-->
{% if page.eventbrite %}
<iframe
  src="https://www.eventbrite.com/tickets-external?eid={{page.eventbrite}}&ref=etckt"
  frameborder="0"
  width="100%"
  height="248px"
  scrolling="auto">
</iframe>
{% endif %}

<h2 id="general">General Information</h2>

<!--
  INTRODUCTION

  Edit the general explanatory paragraph below if you want to change
  the pitch.
-->

<p>
  The course is aimed at everyone who is
  interested in becoming a better teacher. In particular, this training
  is aimed at those who want to become <a href="{{ site.swc_site }}">Software Carpentry</a>,
  <a href="{{ site.lc_site }}">Library Carpentry</a>, and <a href="{{ site.dc_site }}">Data Carpentry</a>
  Instructors, run workshops and contribute to The Carpentries training
  materials. You don't currently have to be an instructor or a
  teacher to attend this workshop, but you do need to be willing and
  committed to becoming one and to improving your teaching techniques.
</p>

<p>
  <a href="{{ site.swc_site }}">Software Carpentry</a>,
  <a href="{{ site.dc_site }}">Data Carpentry</a>, and 
  <a href="{{ site.lc_site }}">Library Carpentry</a>'s mission is to
  help scientists, researchers, and librarians get more research done in less time
  and with less pain by teaching them basic lab skills for scientific
  computing.  This hands-on two-day workshop covers the basics of
  educational psychology and instructional design, and looks at how to
  use these ideas in both intensive workshops and regular classes.
</p>
<p>
  The workshop is a mix of lectures and hands-on lessons where you
  practice giving a short lesson using approaches learned and
  implement some of the teaching techniques which we will discuss.
  This is training for teaching, not technical training; you do not
  need any particular technical background, and we will not be
  teaching that. This workshop is based on the constantly revised and
  updated
 <a href="{{ site.training_site }}">curriculum</a>.
</p>

<!--
  LOCATION

  This block displays the address and links to maps showing directions
  if the latitude and longitude of the workshop have been set.  You
  can use http://itouchmap.com/latlong.html to find the lat/long of an
  address.
  -->
<h3 id="where">Where</h3>

{% assign inperson = "false" %}
{% for loc in page.locations %}

{% capture online %}{{ loc.venue | downcase }}{% endcapture %}

<h4>{{ loc.venue }}</h4>

{% if online == "online" %}

This is an online event. We will meet using the online videoconference software Zoom. You will need to <a href="https://zoom.us/download">download and install their client</a> to connect with your instructors. The link to use for this event is <{{ loc.address }}>.

{% else %}
{% assign inperson = "true" %}
{{ loc.address }} {% if loc.latlng %} Get directions with
    <a href="//www.openstreetmap.org/?mlat={{loc.latlng | replace:',','&mlon='}}&zoom=16">OpenStreetMap</a>
    or
    <a href="//maps.google.com/maps?q={{loc.latlng}}">Google Maps</a>. {% endif %}

{% endif %}
{% endfor %}

{% if inperson == "true" %}

<h4 id="accessibility">Accessibility</h4>

We are committed to making this workshop
accessible to everybody.
The workshop organisers have checked that:

<ul>
  <li>The room is wheelchair / scooter accessible.</li>
  <li>Accessible restrooms are available.</li>
</ul>

Materials will be provided in advance of the workshop and
large-print handouts are available if needed by notifying the
organizers in advance.  If we can help making learning easier for
you (e.g. sign-language interpreters, lactation facilities) please
please get in touch (using contact details below) and we will
attempt to provide them.

{% endif %}

<h3>Requirements</h3>

Participants should bring a laptop that is Internet connected and has a
functioning browser. If you have it, a device for recording audio and video
(mobile phones and laptops are OK) is useful as throughout the two days, we
are going to record one another teaching in pairs or threes. It does not have
to be high-quality, but it should be good enough that you can understand what
someone is saying.

Please note that after this course is over, you will be asked to do
three short follow-up exercises online in order to finish qualifying
as an instructor: the details are available at
<a href="{{ site.training_site }}/checkout/">{{ site.training_site }}/checkout/</a>.
If you have any questions about the workshop, the reading material,
or anything else, please get in touch.


<h3>Code of Conduct</h3>

All participants are required to abide by The Carpentries <a href="{{
site.swc_site }}/conduct/">Code of Conduct</a>.



<h3 id="contact">Contact</h3>
<p>
Please email
{% if page.contact %}
  {% for contact in page.contact %}
    {% if forloop.last and page.contact.size > 1 %}
      or
    {% else %}
      {% unless forloop.first %}
      ,
      {% endunless %}
    {% endif %}
    <a href='mailto:{{contact}}'>{{contact}}</a>
  {% endfor %}
{% else %}
  to-be-announced
{% endif %}
for more information.
</p>

<hr/>

<h2 id="preparation" name="preparation">Preparation</h2>

<p>
  Please read the following before the workshop begins:
</p>
<ol>
  <li><a href="{{ site.training_site }}/papers/science-of-learning-2015.pdf">The Science of Learning</a></li>
  <li><a href="https://carpentries.org/files/reports/TheCarpentries2019AnnualReport.pdf">The Carpentries 2019 Annual Report</a></li>
</ol>
<p>
  Please also read through <em>one</em> episode of one of The Carpentries lessons below   
  carefully, so that you can do some exercises based on it on the
  first day of the class.  An episode is one page of a lesson.
</p>

  <ul>
  <li><a href="{{ site.swc_site }}/lessons">Software Carpentry Lessons</a></li>
  <li><a href="{{ site.dc_site }}/lessons">Data Carpentry Lessons</a></li>
  <li><a href="{{ site.lc_site }}/lessons">Library Carpentry Lessons</a></li>
  </ul>
  

<hr/>

<h2 id="materials" name="materials">Training Materials and Schedule</h2>
<!--
<p>
  Please see <a href="{{ site.training_site }}">this site</a> for course material and tentative schedule.
</p>


<hr/>
-->

<p> 
  Please see below for a tentative schedule:
</p>

<div class="row">
  <div class="col-md-12">
    <h3>Sample Schedule</h3>
    <table class="table table-striped">
      <tr> <td> </td> <td> <a href="https://carpentries.github.io/instructor-training/setup.html">Setup</a> </td> <td>Download files required for the lesson</td> </tr>
      <tr> <td> </td> <td> <a href="https://www.surveymonkey.com/r/instructor_training_pre_survey?workshop_id=2021-05-04-ttt-online-NZST">Pre-training survey</a> </td> <td>Please fill out our pre-training survey before the start of the course.</td></tr>
      <tr> <td>Day 1</td> <td>1. <a href="https://carpentries.github.io/instructor-training/01-welcome/index.html">Welcome</a> </td> <td>Who are we and how do we approach teaching?<br>What should you expect from this workshop?</td> </tr>
      <tr> <td> </td> <td>2. <a href="https://carpentries.github.io/instructor-training/02-practice-learning/index.html">Building Skill with Practice </a> </td> <td>How do people learn?<br>Who is a typical Carpentries learner?<br>
How can we help novices become competent practitioners?</td> </tr>
      <tr> <td> </td> <td>3. <a href="https://carpentries.github.io/instructor-training/06-feedback/index.html">Building Skill with Feedback </a> </td> <td>How can I get feedback from learners?<br>How can I use this feedback to improve my teaching?</td> </tr>
      <tr> <td> </td>  <td>Finish</td> <td> </td> </tr>
      <tr> <td>Day 2</td> <td>4. Welcome</td><td>Who are we and how do we approach teaching?<br>What should you expect from this workshop?</td> </tr>
      <tr> <td> </td> <td>5. <a href="https://carpentries.github.io/instructor-training/03-expertise/index.html">Expertise and Instruction </a> </td> <td>What type of instructor is best for novices?<br>How are we (as instructors) different from our learners and how does this impact our teaching?</td> </tr>
      <tr> <td> </td> <td>6. <a href="https://carpentries.github.io/instructor-training/09-mindset/index.html">Mindset </a> </td> <td>How does mindset influence learning?<br>How should we praise our learners?<br>How should we talk about errors?<br>What are successful habits of lifelong learners?</td></tr>
      <tr> <td> </td> <td>Finish </td> <td> </td> </tr>
      <tr> <td>Day 3</td> <td>7. Welcome </td> <td> </td> </tr>
       <tr><td> </td> <td>8. <a href="https://carpentries.github.io/instructor-training/11-practice-teaching/index.html">Teaching Is a Skill </a> </td> <td>How can I improve my teaching?</td> </tr>
      <tr><td> </td> <td>9. <a href="https://carpentries.github.io/instructor-training/18-management/index.html">Managing a Diverse Classroom </a> </td> <td>How can I prepare for effective co-teaching?<br>What are the challenges of managing a heterogeneous classroom?<br>What do I do if there is a Code of Conduct violation?</td></tr>
      <tr> <td> </td> <td>Finish </td> <td> </td> </tr>
      <tr> <td>Day 4</td> <td>10. Welcome </td> <td>Who are we and how do we approach teaching?<br>What should you expect from this workshop?</td></tr>
      <tr><td> </td> <td>11. <a href="https://carpentries.github.io/instructor-training/05-memory/index.html">Memory and Cognitive Load </a> <td>What is cognitive load and how does it affect learning?<br>How can we design instruction to work with, rather than against, memory constraints?</td> </td> </tr>
      <tr> <td> </td> <td>12. <a href="https://carpentries.github.io/instructor-training/15-lesson-study/index.html">Preparing to Teach </a> </td> <td>How should I prepare to teach?</td> </tr>
      <tr><td> </td> <td>13. <a href="https://carpentries.github.io/instructor-training/08-motivation/index.html">Motivation and Demotivation </a> </td> <td>Why is motivation important?<br>How can we create a motivating environment for learners?</td> </tr>
      <tr> <td> </td>  <td>Finish </td> <td> </td> </tr>
      <tr> <td>Day 5</td><td>14. Welcome </td> <td>Who are we and how do we approach teaching?<br>What should you expect from this workshop? </td> </tr>
       <tr><td> </td> <td>15. <a href="https://carpentries.github.io/instructor-training/14-live/index.html">Live Coding Is a Skill </a> </td> <td>Why do we teach programming using participatory live coding?</td> </tr>
      <tr> <td></td> <td>Finish </td> <td> </td> </tr>
      <tr> <td>Day 6</td> <td>16. Welcome </td> <td>Who are we and how do we approach teaching?<br>What should you expect from this workshop?</td> </tr>
      <tr> <td> </td> <td>17. <a href="https://carpentries.github.io/instructor-training/20-checkout/index.html">Checkout Process </a> </td> <td>What do I need to do to finish certifying as a Carpentries Instructor?</td></tr>
      <tr> <td> </td><td></td> <td>Finish </td> <td> </td></tr>
      <tr> <td>Day 7</td> <td>18. Welcome </td> <td> Who are we and how do we approach teaching?<br>What should you expect from this workshop?</td> </tr>
       <tr> <td> </td><td>19.</td> <td><a href="https://carpentries.github.io/instructor-training/17-performance/index.html">More Practice Live Coding </a> </td> </tr>
      <tr> <td> </td> <td>20. <a href="https://carpentries.github.io/instructor-training/21-carpentries/index.html">The Carpentries: How We Operate </a> </td> <td>How is The Carpentries organized and run?<br>What is the difference between SWC, DC, and LC workshops? <br>How do you run a Carpentries workshop?</td> </tr>
      <tr> <td> </td><td></td> <td>Finish </td> <td> </td> </tr>
      <tr> <td>Day 8</td><td>21. Welcome </td> <td>Who are we and how do we approach teaching?<br>What should you expect from this workshop?</td></tr>
      <tr> <td> </td> <td>22. <a href="https://carpentries.github.io/instructor-training/24-practices/index.html">Putting it Together </a> </td> <td>How are the teaching practices we have learned used in our workshops?</td> </tr>
      <tr> <td> </td> <td>23. <a href="https://carpentries.github.io/instructor-training/23-introductions/index.html">Workshop Introductions </a> </td> <td>How do you actually start a workshop?</td></tr>
      <tr> <td> </td> <td>24. <a href="https://carpentries.github.io/instructor-training/25-wrap-up/index.html">Wrapping Up </a> </td> <td>What can we improve in this training?</td> </tr>
       <tr> <td> </td> <td><a href="https://www.surveymonkey.com/r/instructor_training_post_survey?workshop_id=2021-05-04-ttt-online-NZST">Post-Training Survey </a> </td> <td>Please fill out our post-training survey after the course.</td> </tr>
      <tr> <td> </td><td></td> <td>Finish </td> <td> </td> </tr>
    </table>
  </div>
</div>



<!--
  ETHERPAD

  At `_misc/etherpad.txt` you will find a template for the etherpad.

  Display the Etherpad for the workshop.  You can set this up in
  advance or on the first day; either way, make sure you push changes
  to GitHub after you have its URL.  To create an Etherpad, go to

      http://pad.software-carpentry.org/YYYY-MM-DD-site

  where 'YYYY-MM-DD-site' is the identifier for your workshop,
  e.g., '2015-06-10-esu'.
-->
{% if page.etherpad %}
<hr/>

<p id="etherpad">
  <strong>Etherpad:</strong> <a href="{{page.etherpad}}">{{page.etherpad}}</a>.
  <br/>
  We will use this Etherpad for chatting, taking notes, and sharing URLs and bits of code.
</p>

{% endif %}

<h2 id="pre_workshop_survey">Surveys</h2>

<p>
  Before attending the workshop, please fill out <a href="{{ site.instructor_pre_survey }}{{ site.github.project_title }}">our pre-training survey</a>.
</p>


<p>
  After the workshop, please fill out <a href="{{ site.instructor_post_survey }}{{ site.github.project_title }}">our post-training survey</a>.
</p>
