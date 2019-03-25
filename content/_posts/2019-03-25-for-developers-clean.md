---
layout: post
title: Houndstooth for Developers
subtitle_body: Building a Jekyll Site for Use with the Houndstooth Editor
_date: 02/20/2019
posted_at: null
permalink: /docs/
masthead:
  img_path: null
  pat_path: /assets/images/backgrounds/houndtooth-pat-dark.png
  overlay: true
categories: []
elsewhere:
  name: null
  url: null
comments: false
share: false
seo:
  title: Configuring Houndstooth for Developers
  description: Setting up a Jekyll website to use the Houndstooth Editor
  canonical: null
  noindex: false
social:
  title: null
  description: null
  img_path: /upload/image/png/1553544729906_img_path_Houndstooth_markdown.png

---

Houndstooth is a web editor for your Github project.
It allows you to create, update, or remove content on your github repo site from any browser. It has two modes: a structured content editor, and a file editor.

The content editor is designed for use with <a href=https://jekyllrb.com/>Jekyll</a>. It's ideal for content that changes often, marketing copy, blog posts, and content with a similar format that is frequently repeated. The file editor allows for more advanced formatting with HTML or Markdown.

Similar to other Jekyll collection editors, Houndstooth uses collections to make it easy for web developers to customize the editing interface for clients and non-technical collaborators.

This guide will show you how to do structure your Jekyll project for use with the Content Editor, and access the File Editor.

<h2><b>How it Works</b></h2>
<hr />
Houndstooth will detect any valid collection defined in your site <code>_config.yml</code> file and make it editable from your Houndstooth dashboard. Markdown files can be modified using an intuitive markdown editor. Or, you can use the collection editor to create and edit templated content using a form-based interface.

Changes made in your browser are saved as git commits, and will trigger a new site build on the Houndstooth server, making it easy to collaborate with less technical users while maintaining a git workflow.

<h4><b>Content Editor<b></h4>

<img src="https://raw.githubusercontent.com/bowtie-co/houndstooth-marketing-site/master/upload/Screen%20Shot%202019-02-08%20at%203.26.23%20PM.png" />

<h2><b>Getting Started:</b></h2>

In order to use this feature, your site must be made with Jekyll and use Jekyll collection objects (including the default Jekyll Posts and Drafts collections).

<h4><b>Step 1: Defining a Collection<b></h4>

To define a collection, include it in your <code>_config.yml</code> as shown below. For more information on Jekyll collections, see their docs.

<code>
  collections:
    lander-1-col:
      output: true
    services:
      output: false
</code>


Once a collection has been defined, it will appear in the Houndstooth dashboard. Houndstooth will respect and recognize custom collection directory locations if a <code>collection_dir:</code> is set in your <code>config_yml</code>

<h4><b>Step 2: Set up the form defaults<b></h4>

Building a custom form for content or post front matter is easy. The collection editor will generate a dynamic form from a <code>_fields.md</code> file in the root of the collection. Entry type and defaults are specified in yaml front matter. You can configure the form for strings, dates, timestamps, file uploads, color pickers, and more.

<h4><b>Example '_fields.md' File<b></h4>
<code>
  - - -
  name: null
  members_only: true
  date:
  ending_on:
  starting_at:
  featured_img_path:
  header_color:
  - - -
  Add text or liquid includes here.
</code>



<h4><b>Generated Form:</b></h4>
<img src=<img src="https://lh5.googleusercontent.com/nK4iOVp4bx7Te7b0chKA5r_nP08ykKy807lstG34odreJ8yp4SGCTPYA7SX1gr2VOtPAgqMx4pfVE-LazUvL9MwfMrnY1CsixCZUvS_nqkaBddi3DcEfeWyR_ByCEVti33nSHgxF" />

Each form field is defined from a key/value pair in the front matter of the <code>_fields.md</code> file. Read on for a full list of options.

<h4><b>Step 3. Provide Access</b></h4>

If you are providing access to a client or collaborator, please add that person with write access on your GitHub repo and then visit the “Users” page found on the left sidebar to view the users and access type.



<h2><b>Field conventions:</h2><b>
Any text you enter as a value in the <code>_fields.md</code> file will be used as a default. We recommend wrapping text in quotes (e.g. "Jack Dorsey"). A blank value, or the use of 'null' will render the option null.

Keys unique to a collection item and not present in the <code>fields.md</code> will only appear in new items cloned from the item containing the unique values.

Strings:

Most key/value pairs will render simple string variables you can use in your templates (e.g. name: "value" ). This will produce a text input in your form:
<code>
  - - -
  name: "Jack Dorsey"
  address: null
  - - -
</code>


<img src="https://lh6.googleusercontent.com/duJtRamYxxKo5ANa3_FgESbtWySaWMCMCXRFdao2mbq413U8pEIClqbwAHW8fTJ754jPiMU3qUEI-mC-cyD61yANlI_D2hbY4COR8pfzG3erUhBfY42wZ3b7nF2BhHI03mZRqsAC" />


<h4><b>Array:</h4><b>

To produce an editable array of strings, simply nest the variables in your front matter as show below. This will output an editable list of variables in the form:

<code>
  - - -
  categories:
    - Hello World
    - BowTie
  - - -
</code>


<img src="https://lh6.googleusercontent.com/bP_wI_hYaUOoxopXXvRYp5OaskXjDCBA1dqgUFg7P8tnCUUJCKpBP2UBErnTSe8tdg7FltOoapIRt2VdyPOFsziULC7qn2pwk_NEtW-Yrn2z3QH6Sniz0Bfi-nku7Wmyjsy9jJEq" />


<h4><b>Boolean values:<b></h4>

Adding a value of <code>true</code> or <code>false</code> following the key in the yaml will produce a checkbox.

<code>
  - - -
  pattern: false
  parallax: true
  - - -
</code>

<img src="https://lh4.googleusercontent.com/39WbGS2YUqd3eisHbom8aD_wo21STyx1JiPW-tmKxbqyXncgnFFOe1n3p1vDbv-MKgk30L1hJGG0DAWS8SHwcrXx6NC6N6JH_ajUC_SIZbSnG5R9TSjCJhCwcWttwbqwzDjrxeQF" />

<h4><b>Date entry:</b></h4>

Using a key of <code>date:</code>, or appending <code>_on’</code> to the end of a key will add a datepicker to the form. Additionally, using <code>date:</code> as a key value will add a time-stamp entry field. Using <code>_on</code> alone will produce the datepicker only (e.g. registered_on: "" ).

<code>
  - - -
  date:
  - - -
</code>

<img src="https://houndstootheditor.co/upload/Screen Shot 2019-02-14 at 10.35.36 AM.png" />

<h4><b>Time:</b></h4>

Appending <code>_at:</code> to the end of a key will create a time selector (e.g. starting_at: "").


<code>
  - - -
  start-time_at:
  - - -
</code>


<img src= "https://houndstootheditor.co/upload/Screen Shot 2019-02-14 at 10.35.42 AM.png" />

<h4><b>File uploads:</b></h4>

If you want to produce a file upload interface, append ‘_path’ to the key value (e.g. featured_img_path: "" ). This will provide a file upload interface. Most image files will preview for your end user once uploaded. Files too large to preview (over 2MB), and nonimage files will render an icon.

<code>
  - - -
  avatar_path:
  - - -
</code>



Image files will generate a preview:


<img src="https://lh3.googleusercontent.com/P2iXI-RDHUCwCj4L906oFBL7O8pQO8k8Ke3c6aKWBqcrAMsT-UH4pcIqWnPUTgNxnkYxe5T91AeRAhg2i2hvswKgq6CND8jyrFa4e2CzXmqvMbNuNmnh1GEXMVO8NJsQZKaXy57f" />


<h4><b>Color picker:</b></h4>

To provide a color picker interface in your form append <code>_color:</code> to the key (e.g. header_color: "" ). Selections are returned as six character hex values.

<code>
  - - -
  section_color:
  - - -
</code>

<img src="https://lh4.googleusercontent.com/d1HhzU5x5E9UrcAS9wnOCkOt9HvFysvfnxmMbsH3juiuA6SvlujiSb3JUuIUahHHMO55dMN3MPRsjT9VuFi1vCBT1bJahH3dxRu3YOJgiQKz0Y0kYOLZqApa6NWUeX-gEXdwVp1o" />



<h4><b>Text Areas:</b></h4>

For longer format text based fields, you may want to provide a scalable textarea in your form. To provide a text area instead of a string, use the key `content` or append ‘_content’ ‘_body’ ‘_textarea’ to your key (e.g. header_color: "" ). Selections are returned as six character hex values.

<code>
  - - -
  subtitle_body:

  - - -
</code>



<img src="https://houndstootheditor.co/upload/text-area-houndstooth.png" />







<h2><b>Other Editing Options:</b></h2>
<h4><b>File Editor</b></h4>
For more advanced cloud editing, you can leverage the buit in File Editor interface to access and modify every file in your repository. The file editor will recognize formatting using HTML or Markdown, while the collections editor will not.
<img src="https://houndstootheditor.co/upload/file-tree.png" />


The File Editor is built using Ace Editor. The workflow is a simplified git workflow. Each edit will be staged, until commited to the repo using the Commit button.

Updated (saved) files will be highlighted with a red indicator. Additionally, the 'Commit Changes' button will appear and show the number of staged edits to be committed.


<img src="https://houndstootheditor.co/upload/commit-button.png" />

You can also leverage the File Editor to drag and drop images into your Github repository. Please note: these files will post to GH via the API, so they do not respect LFS if enabled.

<img src="https://houndstootheditor.co/upload/making-commit-houndstooth.png" />




<h4><b>Working locally</b></h4>
Additionally, you can configure your website to use Houndstooth locally using the editor of your choice. Simply clone your repo, add the appropriate <code>_fields.md</code> files and key variables, and push commits via git. Once the remote updates, Houndstooth will load the collections as configured.
