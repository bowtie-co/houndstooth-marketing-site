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
<p><span style="font-size: 12pt; font-family: arial, helvetica, sans-serif;">Houndstooth is a web editor for your Github project. </span></p>
<p><span style="font-size: 12pt; font-family: arial, helvetica, sans-serif;">It allows you to create, update, or remove content on your github repo site from any browser. It has two modes: a structured content editor, and a file editor. </span></p>
<p><span style="font-size: 12pt; font-family: arial, helvetica, sans-serif;">The content editor is designed for use with <a href="https://jekyllrb.com/">Jekyll</a>. It's ideal for content that changes often, marketing copy, blog posts, and content with a similar format that is frequently repeated. The file editor allows for more advanced formatting with HTML or Markdown. </span></p>
<p><span style="font-size: 12pt; font-family: arial, helvetica, sans-serif;">Similar to other Jekyll collection editors, Houndstooth uses collections to make it easy for web developers to customize the editing interface for clients and non-technical collaborators. </span></p>
<p><span style="font-size: 12pt; font-family: arial, helvetica, sans-serif;">This guide will show you how to do structure your Jekyll project for use with the Content Editor, and access the File Editor.</span></p>
<h2><span style="font-family: arial, helvetica, sans-serif;"><strong>How it Works</strong></span></h2>
<hr />
<p><span style="font-family: arial, helvetica, sans-serif; font-size: 12pt;">Houndstooth will detect any valid collection defined in your site <code>_config.yml</code> file and make it editable from your Houndstooth dashboard. Markdown files can be modified using an intuitive markdown editor. Or, you can use the collection editor to create and edit templated content using a form-based interface. </span></p>
<p><span style="font-family: arial, helvetica, sans-serif; font-size: 12pt;">Changes made in your browser are saved as git commits, and will trigger a new site build on the Houndstooth server, making it easy to collaborate with less technical users while maintaining a git workflow.</span></p>
<h4><span style="font-family: arial, helvetica, sans-serif; font-size: 12pt;"><strong>Content Editor</strong></span></h4>
<p><span style="font-family: arial, helvetica, sans-serif;"><img src="https://raw.githubusercontent.com/bowtie-co/houndstooth-marketing-site/master/upload/Screen%20Shot%202019-02-08%20at%203.26.23%20PM.png" /></span></p>
<h2><span style="font-family: arial, helvetica, sans-serif;"><strong>Getting Started:</strong></span></h2>
<p><span style="font-family: arial, helvetica, sans-serif; font-size: 12pt;">In order to use this feature, your site must be made with Jekyll and use Jekyll collection objects (including the default Jekyll <em>Posts</em> and <em>Drafts</em> collections).</span></p>
<h4><span style="font-family: arial, helvetica, sans-serif; font-size: 12pt;"><strong>Step 1: Defining a Collection</strong></span></h4>
<pre><span style="font-family: arial, helvetica, sans-serif; font-size: 12pt;">To define a collection, include it in your <code>_config.yml</code> as shown below. For more information on Jekyll collections, <a href="https://jekyllrb.com/docs/collections/">see their docs</a>. <code>
<br />  collections:
    lander-1-col:
      output: true
    services:
      output: false<br />
</code> Once a collection has been defined, it will appear in the Houndstooth dashboard. Houndstooth will respect and recognize custom collection directory locations if a <code>collection_dir:</code> is set in your <code>config_yml .</code></span></pre>
<h4><span style="font-family: arial, helvetica, sans-serif; font-size: 12pt;"><strong>Step 2: Set up the form defaults</strong></span></h4>
<p><span style="font-family: arial, helvetica, sans-serif; font-size: 12pt;">Building a custom form for content or post front matter is easy. The collection editor will generate a dynamic form from a <code>_fields.md</code> file in the root of the collection. Entry type and defaults are specified in yaml front matter. You can configure the form for strings, dates, timestamps, file uploads, color pickers, and more.</span></p>
<h4><span style="font-family: arial, helvetica, sans-serif; font-size: 12pt;"><strong>Example '_fields.md' File</strong></span></h4>
<pre><span style="font-family: arial, helvetica, sans-serif; font-size: 12pt;"><code>
  - - -
  name: null
  members_only: true
  date:
  ending_on:
  starting_at:
  featured_img_path:
  header_color:
  - - -
  Add text or liquid includes here.<br />
</code></span></pre>
<h4><span style="font-family: arial, helvetica, sans-serif; font-size: 12pt;"><strong>Generated Form:</strong></span></h4>
<p><span style="font-family: arial, helvetica, sans-serif;"><img src="https://lh5.googleusercontent.com/nK4iOVp4bx7Te7b0chKA5r_nP08ykKy807lstG34odreJ8yp4SGCTPYA7SX1gr2VOtPAgqMx4pfVE-LazUvL9MwfMrnY1CsixCZUvS_nqkaBddi3DcEfeWyR_ByCEVti33nSHgxF" /> </span></p>
<p><span style="font-family: arial, helvetica, sans-serif;"><span style="font-size: 12pt;">Each form field is defined from a key/value pair in the front matter of the <code>_fields.md</code> file. Read on for a full list of options.</span></span></p>
<h4><span style="font-family: arial, helvetica, sans-serif; font-size: 12pt;"><strong>Step 3. Provide Access</strong></span></h4>
<p><span style="font-family: arial, helvetica, sans-serif; font-size: 12pt;">If you are providing access to a client or collaborator, please add that person with write access on your GitHub repo and then visit the &ldquo;Users&rdquo; page found on the left sidebar to view the users and access type.</span></p>
<h2><span style="font-family: arial, helvetica, sans-serif;"><strong>Field conventions:</strong></span></h2>
<p><span style="font-family: arial, helvetica, sans-serif;"><span style="font-size: 12pt;">Any text you enter as a value in the <code>_fields.md</code> file will be used as a default. We recommend wrapping text in quotes (e.g. "Jack Dorsey"). A blank value, or the use of 'null' will render the option null. </span></span></p>
<p><span style="font-family: arial, helvetica, sans-serif;"><span style="font-size: 12pt;">Keys unique to a collection item and not present in the <code>fields.md</code> <em>will only appear in new items cloned from the item containing the unique values. </em></span></span></p>
<h4><strong><span style="font-family: arial, helvetica, sans-serif;"><span style="font-size: 12pt;">Strings:</span></span></strong></h4>
<p><span style="font-family: arial, helvetica, sans-serif;"><span style="font-size: 12pt;"> Most key/value pairs will render simple string variables you can use in your templates (e.g. name: "value" ). This will produce a text input in your form: <code>
  - - -
  name: "Jack Dorsey"
  address: null
  - - -
</code></span> <img src="https://lh6.googleusercontent.com/duJtRamYxxKo5ANa3_FgESbtWySaWMCMCXRFdao2mbq413U8pEIClqbwAHW8fTJ754jPiMU3qUEI-mC-cyD61yANlI_D2hbY4COR8pfzG3erUhBfY42wZ3b7nF2BhHI03mZRqsAC" /></span></p>
<h4><span style="font-size: 12pt; font-family: arial, helvetica, sans-serif;"><strong>Array:</strong></span></h4>
<p><span style="font-family: arial, helvetica, sans-serif;"><span style="font-size: 12pt;">To produce an editable array of strings, simply nest the variables in your front matter as show below. This will output an editable list of variables in the form: <code>
  - - -
  categories:
    - Hello World
    - BowTie
  - - -
</code></span> <img src="https://lh6.googleusercontent.com/bP_wI_hYaUOoxopXXvRYp5OaskXjDCBA1dqgUFg7P8tnCUUJCKpBP2UBErnTSe8tdg7FltOoapIRt2VdyPOFsziULC7qn2pwk_NEtW-Yrn2z3QH6Sniz0Bfi-nku7Wmyjsy9jJEq" /></span></p>
<h4><span style="font-size: 12pt; font-family: arial, helvetica, sans-serif;"><strong>Boolean values:</strong></span></h4>
<p><span style="font-family: arial, helvetica, sans-serif;"><span style="font-size: 12pt;">Adding a value of <code>true</code> or <code>false</code> following the key in the yaml will produce a checkbox. <code>
  - - -
  pattern: false
  parallax: true
  - - -
</code></span> <img src="https://lh4.googleusercontent.com/39WbGS2YUqd3eisHbom8aD_wo21STyx1JiPW-tmKxbqyXncgnFFOe1n3p1vDbv-MKgk30L1hJGG0DAWS8SHwcrXx6NC6N6JH_ajUC_SIZbSnG5R9TSjCJhCwcWttwbqwzDjrxeQF" /></span></p>
<h4><span style="font-family: arial, helvetica, sans-serif; font-size: 12pt;"><strong>Date entry:</strong></span></h4>
<p><span style="font-family: arial, helvetica, sans-serif;"><span style="font-size: 12pt;">Using a key of <code>date:</code>, or appending <code>_on&rsquo;</code> to the end of a key will add a datepicker to the form. Additionally, using <code>date:</code> as a key value will add a time-stamp entry field. Using <code>_on</code> alone will produce the datepicker only (e.g. registered_on: "" ). <code>
  - - -
  date:
  - - -
</code> </span><img src="https://houndstootheditor.co/upload/Screen Shot 2019-02-14 at 10.35.36 AM.png" /></span></p>
<h4><span style="font-family: arial, helvetica, sans-serif; font-size: 12pt;"><strong>Time:</strong></span></h4>
<p><span style="font-family: arial, helvetica, sans-serif;"><span style="font-size: 12pt;">Appending <code>_at:</code> to the end of a key will create a time selector (e.g. starting_at: ""). <code>
  - - -
  start-time_at:
  - - -
</code></span> <img src="https://houndstootheditor.co/upload/Screen Shot 2019-02-14 at 10.35.42 AM.png" /></span></p>
<h4><span style="font-size: 12pt; font-family: arial, helvetica, sans-serif;"><strong>File uploads:</strong></span></h4>
<p><span style="font-family: arial, helvetica, sans-serif;"><span style="font-size: 12pt;">If you want to produce a file upload interface, append &lsquo;_path&rsquo; to the key value (e.g. featured_img_path: "" ). This will provide a file upload interface. Most image files will preview for your end user once uploaded. Files too large to preview (over 2MB), and nonimage files will render an icon. <code>
  - - -
  avatar_path:
  - - -
</code> Image files will generate a preview:</span> <img src="https://lh3.googleusercontent.com/P2iXI-RDHUCwCj4L906oFBL7O8pQO8k8Ke3c6aKWBqcrAMsT-UH4pcIqWnPUTgNxnkYxe5T91AeRAhg2i2hvswKgq6CND8jyrFa4e2CzXmqvMbNuNmnh1GEXMVO8NJsQZKaXy57f" /></span></p>
<h4><span style="font-size: 12pt; font-family: arial, helvetica, sans-serif;"><strong>Color picker:</strong></span></h4>
<p><span style="font-family: arial, helvetica, sans-serif;"><span style="font-size: 12pt;">To provide a color picker interface in your form append <code>_color:</code> to the key (e.g. header_color: "" ). Selections are returned as six character hex values. <code>
  - - -
  section_color:
  - - -
</code></span> <img src="https://lh4.googleusercontent.com/d1HhzU5x5E9UrcAS9wnOCkOt9HvFysvfnxmMbsH3juiuA6SvlujiSb3JUuIUahHHMO55dMN3MPRsjT9VuFi1vCBT1bJahH3dxRu3YOJgiQKz0Y0kYOLZqApa6NWUeX-gEXdwVp1o" /></span></p>
<h4><span style="font-size: 12pt; font-family: arial, helvetica, sans-serif;"><strong>Text Areas:</strong></span></h4>
<p><span style="font-family: arial, helvetica, sans-serif;"><span style="font-size: 12pt;">For longer format text based fields, you may want to provide a scalable textarea in your form. To provide a text area instead of a string, use the key <code>content</code> or append &lsquo;_content&rsquo; &lsquo;_body&rsquo; &lsquo;_textarea&rsquo; to your key (e.g. header_color: "" ). Selections are returned as six character hex values. <code>
  - - -
  subtitle_body:

  - - -
</code></span> <img src="https://houndstootheditor.co/upload/text-area-houndstooth.png" /></span></p>
<h2><span style="font-family: arial, helvetica, sans-serif;"><strong>Other Editing Options:</strong></span></h2>
<h4><span style="font-family: arial, helvetica, sans-serif;"><strong>File Editor</strong></span></h4>
<p><span style="font-family: arial, helvetica, sans-serif;"><span style="font-size: 12pt;">For more advanced cloud editing, you can leverage the buit in File Editor interface to access and modify every file in your repository. The file editor will recognize formatting using HTML or Markdown, while the collections editor will not.</span> <img src="https://houndstootheditor.co/upload/file-tree.png" /> <span style="font-size: 12pt;">The File Editor is built using Ace Editor. The workflow is a simplified git workflow. Each edit will be staged, until commited to the repo using the Commit button. Updated (saved) files will be highlighted with a red indicator. Additionally, the 'Commit Changes' button will appear and show the number of staged edits to be committed.</span> <img src="https://houndstootheditor.co/upload/commit-button.png" /> <span style="font-size: 12pt;">You can also leverage the File Editor to drag and drop images into your Github repository. Please note: these files will post to GH via the API, so they do not respect LFS if enabled.</span> <img src="https://houndstootheditor.co/upload/making-commit-houndstooth.png" /></span></p>
<h2><span style="font-family: arial, helvetica, sans-serif;"><strong>Working Locally</strong></span></h2>
<p><span style="font-family: arial, helvetica, sans-serif; font-size: 12pt;">Additionally, you can configure your website to use Houndstooth locally using the editor of your choice. Simply clone your repo, add the appropriate <code>_fields.md</code> files and key variables, and push commits via git. Once the remote updates, Houndstooth will load the collections as configured.</span></p>
