The workflow for a semi-automated resume to job application is done via this workflow

1. Write a large master resume and cover letter in markdown. This is your template.
2. Clone the two files to create a sub template targeting a specific industry.
3. Get this resume generator: https://github.com/mofosyne/resume which is a fork of https://github.com/mwhite/resume
  - The mofosyne fork contains various fixes to make it work with the new pandoc version
4. For each company job listing, you get the subtemplate for the target company and customise it for each company quickly. Then run the `make` command to generate a .pdf of both the resume and cover letter. (Remember to backup old coverletters to avoid cluttering up the root folder).
5. Send the application via seek, or other job services that jobactive support auto filling by email.
6. Install the gscript that processes and updates the email to fit the jobactive email autofilling process. This cuts down the time, since it means you don't have to head to email to adapt and forward the email. Thus you can immediately send the next coverletter to the next company.

-----------

# Pain points:

* The resume template generation system is based off mwhite, which while is quite effective when adapted, is not easy to setup. And is still quite manual in editing the text. Using markdown is very effective for low maintainance editing, but we need an additional layer to allow for more automated resume and coverletter adaption. (e.g. a preprocessor language)
* Is dependent on the jobactive api support. This locks us to only a few websites.
* Require gmail scripting, so not as portable, and also additonal friction in implementation.

# Ideal to making this more automated:
* Have a way of "hash tagging" section of the resume to allow for preprocessing the master resume to something smaller. Commonmark is coming to a sorta of standard of using `{ metadata }` to deal with this portability. Should probably check with them to ensure portability.
* Have a Q/A section to allow for customising the coverletter in a structured way, but that is still somewhat human (e.g. mix of new hard to automate sentence (describe the company), and template section (describe your skill)).
* Maybe a way to extract key points from job listings, if we are trying to avoid using the big job sites.
* Perhaps a software that directly communicates to a jobactive browser session, and is smart enough to navigate and fill in the form (you will have to, since the job seeker will have to log in anyway) (plus its a security risk if it can just log in without human intervention). Must however be aware of changes to the site layout (e.g. check for successful application). 
  - Encourage the jobactive website to expose a proper api?
