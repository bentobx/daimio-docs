## Daimio

create -- iterate -- collaborate

### What is Daimio?


### Medium Description

Daimio: Consolidates templating and the API to let your small web team build prototypes overnight. As your application matures, the API grows with it.

### Long Description

Daimio transcends traditional web application development frameworks - in Daimio, templating is the API that grows with your site. Daimio speeds routine development tasks, making coding fun. Using DAML, Daimio's mini-language, your small team can redline the productivity zone. Build prototypes quickly, with what Daimio gives you out of the box, then extend your application and the API with PHP phrases. 

Daimio is a PHP-based framework that allows small teams to create, iterate, and prototype web applications quickly. DAML, Daimio's domain-specific language, speeds routine development tasks. It consolidates templating, the API, and the scaffolding commands you need to be able to build web applications. 

### Design and develop at the same time

You can extend DAML by adding new commands and language constructs to encapsulate your application's logic. **While** you develop and test your models, your designer can use DAML to create web and mobile interfaces, boosting productivity. You can use Daimio's built-in concepts to speed your workflow, or define your own. It's that simple.

_Concurrent workflow diagram could go here._

### Daimio's terminal speeds learning and boosts productivity

Daimio's built-in terminal makes it easy to learn DAML and become productive quickly. When you enter text into the command line, only the options you have available to you appear below the command line. This helps users to learn DAML syntax and constructs, speeding productivity for new and experienced programmers alike. As you become comfortable with DAML, you'll be prototyping web applications in a few keystrokes. Go ahead, [kick the tires](http://daimio.org/terminal) on the terminal to see how it works.

### Open source your functionality

 Your website is really just the entry point to the services and information&#8212;the _functionality_ you offer. Daimio separates your functionality from its interfaces, allowing you to open source that functionality and release the genie for other developers to use. And, best of all, when your application is complete, its API is complete too&#8212;no API development lag time!

*   Daimio consolidates templating, the API, and scaffolding commands so you can prototype applications quickly.
*   Daimio allows concurrent design and development&#8212;boosting productivity
*   With Daimio, when your application is complete, its API is, too.

## CUDL, DAML, and Daimio

### CUDL: Commands Underlying a Design Language

_Get cozy in the application ecosystem_

There are many ways to think about a web application. One could look at it as a set of documents (<span class="caps">REST</span>), as a three-tiered system (<span class="caps">MVC</span>), as a set of objects (<span class="caps">OOP</span>), as a bunch of data, or maybe as just a big ball of mud. These architectures and philosophies are generally compatible, and most modern web applications combine aspects of several. But underneath these combinations, there's likely a central way you consider the applications you build, which can color the way you perceive applications in general. For us, an application is a set of commands.

A <span class="caps">CUDL</span>y app is a defined by set of commands which has four specific properties:

1. The command list is **complete**: it contains every action possible within the application.

*   This includes all administrative commands, such as disabling a user or adding a new content page.
*   This includes structurally significant commands, such as adding a new table to the database.
*   This also includes scaffolding commands, such generating the stub code for a new model.

2. Commands are **atomic**: each represents a single, irreducible portion of functionality. 

*   Does updating an article's publication status have a different set of constraints than those you use to update the article's text? Make one command for each task.
*   Are you required to update the date when you change the publication status? Make one command that does both.
*   Need to perform a compound operation? Issue a set of commands to be run in sequence (i.e., a subroutine).

3. Commands are **restrictable**: you can limit their use to a subset of users. 

*   Since the command set contains every atomic action, this provides granular access control.
*   All the application's commands are subject to this constraint, so the restrictions still apply, regardless of where the request originates (the primary site, external widgets, <span class="caps">REST</span>ful <span class="caps">API</span>s, mobile apps, e-mail, <span class="caps">SMS</span>, etc.).
*   Further command filtering, performed on a per-gateway basis, can limit the types of commands that can be performed with a <span class="caps">GET</span> request.

4. Commands are **discoverable**: generating a list of available commands is one of the available commands. 

*   The list generally includes a description, examples, the command's parameters, parameter descriptions, and which parameters are required.
*   This list of commands can be used to generate an interface to access the application that is specifically tuned to that particular user.

<span class="caps">CUDL</span> makes your application universally available. Your own website runs on those commands, so they are the core of your system. And that same set of commands is openly available, so third party interfaces enjoy the full power of your application. When you upgrade your site's functionality, those improved commands are discoverable the instant they go live. They're already documented, and external developers can use them immediately. There's no separate <span class="caps">API</span> system to build and support. There's no lag between primary release, <span class="caps">API</span> release, and documentation. And, there's no need to support multiple, disjointed access conventions&#8212;each with their own security concerns. Add new commands, and **they work everywhere**. It's that simple.

In a way the term API is almost a misnomer... CUDL + DAML is really a closer analogue to the role of BASH wrt the OS than it is to traditional APIs.

Once you define your application's commands, you can design and develop concurrently. Designers can build interfaces using those commands **while** the developers extend them. To speed workflow, designers will want to use a templating language containing the commands they use to build their interfaces. 

Since the command set is basically an <span class="caps">API</span> for your application, external developers will want to access it using a <span class="caps">REST</span>ful interface (or <span class="caps">SOAP</span>, or semaphores, or smoke signals) and get a response back in <span class="caps">JSON</span> (or <span class="caps">XML</span>, or <span class="caps">YAML</span>, or binary). Wouldn't it be interesting if you could embed your commands in a language that was powerful enough to template an interface, but weak enough for you to run arbitrary code provided by third parties?


<span class="caps">SIDEBAR</span>: <span class="caps">CUDL</span> in brief

*   complete
*   atomic
*   restrictable
*   discoverable
*   automatic <span class="caps">API</span>
*   fully awesome

### <span class="caps">DAML</span>: Domain-specific API Markup Language

_A language for <span class="caps">CUDL</span>ing_

Using a domain-specific language is an effective way to solve many types of problems. Creating a new language, however, requires time and testing to ensure that it is sensical, secure, complete, efficient, etc. Fortunately, most web applications tend to behave fairly similarly and solve the same general types of problems. We can extract the basic structure of a language designed to solve these problems, and extend it with commands that solve a specific problem. This alleviates the burden of creating an entirely new language while retaining the benefits of a language perfectly suited for the task at hand.

DAML's benefits:

*   <span class="caps">PHP</span> is already a good templating language. Why do we need to add a layer on top of it? Because we need something weaker (weak enough to be safe for external use). We also need something stronger than a standard <span class="caps">API</span>, so we can template with it.
 *   <span class="caps">DAML</span> gives you interoperability with every other <span class="caps">DAML</span>-speaking platform.
*   <span class="caps">DAML</span> can convert itself to a different language if you need to interact with other systems.
*   <span class="caps">DAML</span> provides a minimal language structure in which to embed your domain-specific commands. It's easy to learn, and the structure itself is consistent from project to project.

With DAML, you get all the benefits of <span class="caps">CUDL</span>:

*   Command filtering (atomic-level granularity for security)
*   Discoverability
*   Mashability
*   Completeness (every single thing your app can do is available)

You also enjoy all the advantages of language-oriented programming:

*   Concurrent design / development
*   A ubiquitous language
*   Self-documenting code
*   Separation of concerns
*   A user-enhanceable system
*   Opportunities for reuse

###  The secret sauce

External developers don't have to send <span class="caps">DAML</span> directly to your application. Using [gateways](#gateways) you can catch requests sent through any channel and convert it to a processable DAML string. The simplest and most powerful gateways accept raw <span class="caps">DAML</span> as input: These allow the external developer to request output in the format they desire. Need an <span class="caps">ATOM</span> feed from a site that doesn't provide one? If it were <span class="caps">CUDL</span>y, you could do it yourself.

### Daimio

_a framework for <span class="caps">DAML</span>ers_

A few of Daimio's many features and benefits:

*   [User management](#users) is integrated with <span class="caps">DAML</span> command filtering
*   [Gateways](#gateways) provide a way to transmit information to and from the <span class="caps">DAML</span> parser
*   [Pages](#pages) and [Content](#content) provide basic site-building structure (and output consolidation for other interfaces)
*   [Forms](#forms) allow complicated applications to be rapidly assembled
*   [Interfaces](#interfaces) provide web access to Daimio's innards
*   [Packages](#packages) wrap installable content in pretty party paper
*   [Tools](#tools) expand basic functionality
*   Integrated [Models](#handlers) are effortlessly absorbed into your app's <span class="caps">DAML</span> dialect
*   Lenses offer limited views of specific information
*   Workflows coordinate your efforts
*   Notices encapsulate real-time messaging


## Daimio development philosophy&#8212;make it fast, fun, and easy

Daimio takes the tedium out of making web applications. Because Daimio is modular, it makes coding fun, fast, and productive. Envision the functionality you want by matching it to your business logic. Daimio makes it fast and easy to create and iterate your prototype. Using PHP phrases you can extend the prototype **and the language** you're using to create it.

### Design principles

Typically, API developers allow access to only certain parts of their functionality. In Daimio, the commands you add to your application can be called by anyone, from anywhere, at any time. While this enables collaboration with other developers, it also means you have to code your models defensively to prevent unwanted side-effects. It also means the logic for preventing unwanted side-effects is in the model, where it belongs, instead of baked into your interface.
 

Subject to permission checks, gateway checks, etc. But the main user-accessible functionality of your application is out there, so your atomic actions better check all the necessary conditions because you can't rely on the client to do it for you.
</div>
<div id="usecases">

## Getting it done with Daimio

_What can you do with Daimio? Here are a few scenarios that demonstrate Daimio's features, benefits, and capabilities._

### Tracking tots in real time

The L'il Tots Daycare Center has a website. It allows parents to track their child's location in real time thanks to a <span class="caps">GPS</span> device attached to the safety wristband worn by each child. This service sets them apart from other daycares for their focus on child safety and security and has made them the number one choice for tech-savvy parents.

One of the parents is an iPhone developer. She sees an opportunity to build an iPhone app that allows her to track the location of her son during her busy day. That way, if the daycare takes a field trip to the park across from her office, she can stop in and say hello to her son. The daycare's website is built on Daimio, and its built-in <span class="caps">API</span> allows her to build that web application easily.

The iPhone app turns out to be a hit, and she starts selling it for 99c. She makes a little money from her time investment, the daycare gets an investment-free iPhone application for their website, and parents get mobile access to the daycare site's functionality. Everyone wins!

### Boosting business at the Chez Nous bed and breakfast

Chez Nous is a bed and breakfast establishment located in Newburyport MA. To boost tourism and increase his occupancy rate, the proprietor of Chez Nous wanted to offer a listing of local seasonal attractions on the Chez Nous website. The Newburyport tourism website features a widget that lists current local festivals, tours, and attractions, as well as area restaurants. Since the forward-thinking Newburyport town fathers knew the economic benefits of tourism, they had their website built on Daimio, and offered the local attractions widget free of charge to area businesses.

### AeroClip saves money with ClipTrackr

AeroClip is the world's largest supplier of clips and brackets to the aerospace industry. In 2003, their in-house web development team created ClipTrackr, a custom application to track and display production quotas and inventory levels in real-time on the company intranet.

Fast forward to the present. The global recession is forcing AeroClip to find ways to cut costs. To save money, AeroClip wanted to augment ClipTrackr to automatically release new work orders as manufacturing completed existing work orders. Automating this process allowed AeroClip to redeploy a scheduler to the finance department, to help them count the beans. Fortunately, because ClipTrackr is based on Daimio, it has a discoverable, self-documenting, <span class="caps">API</span> containing ClipTrackr's full power. Despite staff turnover over the years, it was easy for the AeroClip web team to extend ClipTrackr by building a simple gateway using a few lines of PHP, while treating its code as a black box.


to-do:

<span class="caps">SAAS </span>/ SOA / Web 2.0 / etc (DAML's command listing serves as a discoverable, extensible encapsulation of services available to other applications)

license, subscription, micropayment models are all supported here: your clients have near infinite freedom to port your services to other devices and environments (and because you're being paid for the use of your services, not the use of your site, your website itself because Just Another Interface to your services). This reflects the separation Daimio creates between your functionality and the website it's offered through.

advertising-based models (social networks, etc)

non-profits (educational systems, think tanks, government programs (WHO), etc.)

ecommerce sites
 </div>
GETTING STARTED
<div id="install">  

## Installing and configuring Daimio

### System requirements

Daimio requires MySQL and PHP5.

Be sure you have the following information handy:

*   database server
*   database name
*   database username
*   database password  

Have another username and password in mind for your first user account in Daimio. 

### Installing Daimio

Go to the directory in which you want to install Daimio. Run the following command, which downloads Daimio's files into the directory:

	svn checkout http://svn.bentobox.net/daimio/daimio5/trunk ./`</pre>  

	Enter this command next -- you'll use it to set up your Daimio install:
	   <pre>`php daimio/bin/build.php`</pre>  

	Note: if you are on a shared server you might need to modify the above command to use PHP5, e.g.: `/usr/local/php5/bin/php` instead of just `php`

	The build script will prompt you to enter the database information. If the connection to the database succeeds, it will load a fresh copy of the Daimio database into the system.

	Next, Daimio will prompt you to set up your first user account.

	Enter your admin username and password. Now you're ready to log in and build your first web application with Daimio.

	### Login to Daimio

	Now that Daimio is installed, go to `your_domain/interfaces/terminal.html` to log in and start building your first web application.

	To log in just enter the username and password you entered in the build script step above.

	You're ready to [start building](#simpleapp) your first web application!
	</div>
	<div id="simpleapp">

	## Build a simple web application with Daimio

	Are you ready to kick Daimio's tires to see what you can do with it? Here are some instructions on building a simple web application—a community recipe site. To get started, you'll need to [install Daimio](http://www.daimio.org/new#install).

	First you'll log in as the user you created in the Daimio install process. Then we'll use this user to create a second user to get you acquainted with the Terminal interface. Point your browser thingy here: 
	<pre>`yourdomain.com/interfaces/terminal.html`</pre>

	Type the following into the command line and hit Enter. Be sure to replace `yourname` with the username you want, and do the same for the password. Did you know that you can type `u` for user and hit the spacebar to put the command into the command line? (Handy, eh?)
	<pre>`user add username :yourname password :yourpassword`</pre>

	You'll may want this new user to be a wizard, which allow access to application building commands. We typically create a generic wizard user in the build process and then build a separate user for each team member. The "user wizardize" command will upgrade your new user:
	<pre>`user wizardize for :yourname`</pre>

	After you"ve upgraded your permissions, logout and log back in with your new username. Use the logout/login link at the top.

	### Making the forms

	It"s time to make some forms. Your site visitors want to submit and rate recipes, so let"s create the forms you"ll need to collect their data.

	There are two ways to get to where you need to go to make forms. From the terminal, click "change" in the header and then choose "forms", **or** go to:
	<pre>`yourdomain.com/interfaces/forms.html`</pre>

	Click on the "add another" link at the top of the page. A text box will appear. This is where you'll enter the keyword for your forms.

	First, you need to create the form users will use to enter recipes. Type "recipes" into the Keyword textbox and click "add."

	A box with your form's default settings will appear on the left. Leave the default settings as they are. On the right, a preview of your form will appear. Right now, your form preview is blank because you have yet to create some fields. You're going to do that next.

	Click the "add a field" link at the bottom of the "Form recipes" box and complete the following four steps:

1.  Enter `name` for the keyword
2.  Enter `Name` for the name
3.  Select "varchar" from the drop-down menu to set the type of field
4.  Finally, click "Add field"; 

	On the right side of the screen, you'll see a preview of this new field in your form. Repeat the add field process for each of the following keywords:

*   description (Name: Description) (Type: text)
*   servings (Name: Servings) (Type: varchar)
*   ingredients (Name: Ingredients) (Type: text)
*   instructions (Name: Instructions) (Type: text)
*   tags (Name: Tags) (Type: commatags)

	This form is done!

	Repeat this process to create another form called ratings. Create the following fields using the keywords listed. Be sure to enter the Name and the type of field:

*   recipe_id (Name: Recipe_id) (Type: hidden)
*   rating (Name: Rating) (Type: simplepulldown)
*   comment (Name: Comment) (Type: text)

	After you've created these fields, set the default value for the recipe_id field to `{#2}`. Now, when a user is rating a recipe, Daimio will automatically extract the id of the recipe from the address and insert it into the form.

	Next you need to create the options for the "rating" field. In the Options text box, type the following (be sure to include the brackets): 
	<pre>`["*****","****","***","**","*"]`</pre>

	Your form is now done!

	### Creating site pages

	Now, you'll create some webpages for your site. To do this, you need to return to the terminal. There are two ways to get there. You can select "terminal" under the "Pick an interface" drop-down menu or go to:
	 <pre>`yourdomain.com/interfaces/terminal.html`</pre>

	**Daimio tip:**_ Open up a new tab for each interface you're using or each page you want to look at._

	Type the following into the terminal's command line:
	<pre>`page add keyword :home`</pre>

	Repeat this command to add pages with the following keywords:

	**Daimio tip:** _Remember to use the up arrow for speedy command repetition._

*   addrecipe
*   list
*   recipe

	You should now have four pages. You'll need to add some content to these pages before you can actually see them. To do this, you'll use the content management interface. You can select "content" under the "Pick an interface" drop-down menu or go to:
	 <pre>`yourdomain.com/interfaces/content.html`</pre>

	Once you're there, complete the following steps:

*   Click on the "Add content" link at the top of the page. A big content box will appear. Type in some temporary copy you'd like for now (this is only a test after all).*   In the "Page" text box, type `home`.
*   In the "keyword" text box, type `copy`.
*   Click on the "Add" button.

	You should see a page called "home" appear in the list to the left of the large content box. The content item called "copy" will be listed under "home."

	Visit `yourdomain.com/home` to see your new page and your temporary copy.

	Repeat the add content procedure to make content items called "copy" for each of your other pages (addrecipe, list, and recipe).

	Next you'll add some more substantial content to your webpages.

	### The addrecipes page

	Click on "copy" under the "addrecipe" page listed on the left-hand side of the content management interface page. In the future, this content item will be referred to as _copy-on-recipes_.

	Type the following in the content box:
	<pre>`<h2> Add Your Recipe </h2>{form display for :recipes}`</pre>

	Be sure to click on the "Save" button. When the changes are saved, you'll see "value changed for: copy-on-home" in nice green letters on top of the content box. The code you typed in will display the heading and the form you created to collect recipes.

	Now, go to `yourdomain.com/addrecipe` and enter some recipes. This will give you some data to use for the testing you'll do later.

	### The list page

	Next you'll create a page to list all the recipes collected for the list page. To do this, go to the copy-on-list content item and replace your test copy with the following:
	<pre>`<h2>Recipes Galore</h2><p> We hope you find just what you're looking for!</p>{data fetch form :recipes | array create name :recipes | ""}{begin recipelist | merge with @recipes glue "<hr />"}<p> name: <a href="/recipe/{id}/{name}">{name}</a> </p> <p> description: {description} </p> <p> servings: {servings} </p> <p> ingredients: {ingredients} </p> <p> instructions: {instructions} </p> <p> tags: {tags.value | foreach string "{value}" glue ", "} </p> {end recipelist}`</pre>

	If you'd like to alphabetize the recipes, just change the ` {data fetch ... } `command to this:
	<pre>`{data fetch form :recipes order "name ASC" | array create name :recipes | ""}`</pre>

	For other ways to sort the data or more details on "merge," see the [Learn DAML](http://www.daimio.org/new#learndaml) section of Daimio documentation.

	Be sure to save your changes!

	### Adding a search bar

	You want your visitors to be able to search for recipes on the site, so you'll need to add a search bar to the header. If you put it in the header, the search bar will appear on every page you create.

	To accomplish this, go the the content item called "header" under the global section (also called header-global).

	At the bottom of the current content, add the following:
	<pre>`<form method="get" accept-charset="UTF-8" action="http://recipewranglers.bentodojo.com/list"> Search for your favorite recipes: <input type="text" name="searchtext" value="{#searchtext}"/><input type="submit" value="search" /></form><hr />`</pre>

	Notice that if you do a search right now, it will send you to the complete list of recipes and not _your_ specific search results. Go to copy-on-list and change the `{data fetch ...}` command to the following:
	<pre>`{data fetch form :recipes where {"name ~= '%{#searchtext}%' OR description ~= '%{#searchtext}%'"} order "name ASC" | array create name :recipes | ""}`</pre>

	Now Daimio will display only the results of _your_ search. Once you've saved this new copy (by clicking on the "Save" button) go ahead and take a look at the new and improved list page. You'll find it at `yourdomain.com/list`. Try some searches!

	Now that the list and addrecipe pages are set up, you can add links to them on the home page. Go to copy-on-home and replace your test copy with the following.
	<pre>`<h2>Welcome to my recipe sharing site!</h2><p> Check out all our great <a href="/list">recipes</a>! </p><p> Or maybe you'd like to <a href="/addrecipe">add</a> a recipe of your own! </p>`</pre>

	Remember to click "Save" to commit your changes.

	### The recipe page

	Notice that each of the recipes has a link to its own page. Next, you'll create the content for those pages. To do this, you'll modify the content on copy-on-recipe. Copy and paste the following code into copy-on-recipe:
	<pre>`<div>{data fetch form :recipes where "id = {#2}" | __pipe.#1 | array create name :recipe | ""}<p> name: {@recipe.name} </p> <p> description: {@recipe.description} </p> <p> servings: {@recipe.servings} </p> <p> ingredients: {@recipe.ingredients} </p> <p> instructions: {@recipe.instructions} </p> <p> tags: {@recipe.tags.value | foreach string "{value}" glue ", "} </p> </div><div>Rate this recipe! {form display for :ratings}</div><div><p> Reviews of this recipe </p>{data fetch form :ratings where "recipe_id = {#2}"| array create name :ratings | ""}{begin showratings | merge with @ratings glue "<br>"}{value}comment: {comment}{end showratings}</div>`</pre>

	This page has three sections to it. The first part takes the id number of the recipe from the link and displays all the information submitted. The second part displays the ratings form so others can rate the recipe. The final part displays any ratings submitted for this recipe. To see the fruits of your labor, just click on any of the recipe links from the list page. (The URL is `yourdomain.com/list`.) Try submitting a rating or two!

	### Adding a login feature

	You want the users of this website to have an account on the site if they are going to add or rate recipes. To do this, let's create a new content item with keyword login. (Here's a [reminder](#contentreminder) on how to create content, just in case you forgot, or need more practice.) Leave the Page section blank to create a global content item. Copy and paste the following content into the content item:
	<pre>`{begin login | if {not @MY.id}}<div class="login"><h4>Already have an account? Sign in!</h4><form method="post" accept-charset="UTF-8" name="loginForm" id="loginForm"><div class="field_line"><label for="username">Username:</label><input type="text" name="username" id="username" value="" class="text" /> </div><div class="field_line"><label for="password">Password:</label><input type="password" name="password" id="password" value="" class="text" /></div> <div class="field_line"><label><input type="checkbox" name="days" id="days" value="30" />Keep me logged in</label></div> <input type="hidden" name="commands" value="{myself authenticate username #username password #password}" /><input type="submit" name="login_form_submit" value="Sign In" id="login_form_submit" class="submit" /></form></div><div class="signup"><h4>Don't have an account yet? Sign up!</h4><form method="post" accept-charset="UTF-8" name="signupForm" id="signupForm"><div class="field_line"><label for="username">Username:</label><input type="text" name="username" id="username" value="" class="text" /></div><div class="field_line"><label for="password">Password:</label> <input type="password" name="password" id="password" value="" class="text" /></div><textarea name="commands" style="display:none">{begin verbatim | process escape}{user add username #username password #password}{myself authenticate username #username password #password}{end verbatim}</textarea><input type="submit" name="signup_form_submit" value="Sign Up" id="signup_form_submit" class="submit" /></form></div>{end login}`</pre>

	Notice that it contains one section for current users to log in and another section for new users to create an account. You added this as a global content item so it can be referenced on multiple pages. To make it display on a page, just add `{%login-global}` to the content of the page. Go ahead and add `{%login-global}` to copy-on-home and copy-on-addrecipe. Don't forget to click "Save"!

	The login will display only if the user is not logged in, which means to test it out, you'll need to add a logout feature. Let's temporarily put one on the home page by adding this to copy-on-home:
	<pre>`{begin greeting | if @MY.id}<p class="greeting">Hi, <span class="username">{@MY.username}</span>! <a href="?handler=myself&method=logout">Log out.</a></p>{end greeting}`</pre>

	Go ahead and test out the changes—logout, login. Try creating a new user. When you're done, be sure you log back in as yourself so you can go back to editing content. If in the future you ever encounter an error that says "Invalid command 'content set_value'", it's probably because you're not logged in with your username.

	A user will need to be logged in to add a recipe to the site, but the login form doesn't need to display if the user is already logged in. Change copy-on-addrecipe to the following: 
	<pre>`<h2> Add Your Recipe </h2>{begin mustlogin | if {not @MY.id}}<p> You must be logged in to add recipes.</p>{end mustlogin}{%login-global}{begin addrecipe | if @MY.id}{form display for :recipes}{end addrecipe}`</pre>

	Now the addrecipe form will display only if the user is logged in. The login/signup form will only display if the user is not logged in.

	Users also have to log in to rate recipes, so you can make a similar change on the recipe page. Replace the `{form display for :ratings}` with the following:
	<pre>`{begin mustlogin | if {not @MY.id}}<p> You must be logged in to rate this recipe.</p>{end mustlogin}{%login-global}{begin raterecipe | if @MY.id}{form display for :ratings}{end raterecipe}`</pre>

	With all this logging in, it would be nice if the logout option were also easily accessible. To accomplish this, all you need to do is add the following logout (and a simple login) to the footer-global content item. Copy and paste this code into the top of the content item:
	<pre>`<hr/>{begin greeting | if @MY.id}<p class="greeting">Hi, <span class="username">{@MY.username}</span>! <a href="?handler=myself&method=logout">Log out.</a></p>{end greeting}{begin login | if {not @MY.id}}<form method="post" accept-charset="UTF-8" name="loginForm" id="loginForm"><label for="username">Username:</label><input type="text" name="username" id="username" value="" class="text" /> <label for="password">Password:</label><input type="password" name="password" id="password" value="" class="text" /><label><input type="checkbox" name="days" id="days" value="30" />Keep me logged in<input type="hidden" name="handler" value="myself" /><input type="hidden" name="method" value="authenticate" /><input type="submit" name="login_form_submit" value="Sign In" id="login_form_submit" class="submit" /></form></div>{end login}`</pre>

	It's a bit redundant to have the logout on the home page and in the footer, so you can go ahead and delete the "greeting" from copy-on-home. Remember to save your work.

	Now that all the users are set up and ready to go, you can give users the ability to edit recipes that they've submitted. Do this on the recipe page by adding the following below the "showratings" section:
	<pre>`<div>{begin edit | if {is value @MY.id like {@recipe.user_id}}}<h3>Edit your recipe</h3><p>Need to make a change to this recipe? You can do that here: </p>{form display for :recipes row :{#2}}{end edit}</div>`</pre>

	### Adding tags

	Wouldn't it be nice if you could just click on one of the tags on the list page and have it bring up all the recipes that share that tag? All you have to do is replace the recipelist block—that's the whole bit starting with `{begin recipelist...}` and ending with `{end recipelist}`—with the following:
	<pre>`{begin recipelist | merge with @recipes }{begin tagsort | if {or ({is value #2 in tags.stripped_value} {not #2} ) }}<hr><p> name: <a href="/recipe/{id}/{name}">{name}</a> </p> <p> description: {description} </p> <p> servings: {servings} </p> <p> ingredients: {ingredients} </p> <p> instructions: {instructions} </p> <p> tags: {tags | foreach string "<a href="/list/{value.stripped_value}">{value.value}</a>" glue ", "} </p>{end tagsort} {end recipelist}`</pre>

	Each tag should now appear as a link where the URL ends with that tag (or a simplified version if the tag includes spaces or funny characters). The tagsort block will now pull that tag (or the simplified version) from the URL and display only the recipes with that tag. Of course, if there's no tag at the end of the URL, it returns the full list of recipes.

	### Organizing your data in better way 

	So far there have been no problems with the way you've organized your data. However, as your Diamio needs become more complex, it's more efficient to organize data differently to avoid data fetching complications. To do this, you'll need to create some content items called local_data on each of the pages that use data (namely, list and recipe). What should go into these new content items? Move the `{data fetch...}` command from copy-on-list to local_data-on-list. You'll do the same migration on the recipe page as well.

	Since you've deleted the `{data fetch...}` command from the copy, you're probably wondering how Daimio will find the data that it needs. You can tell Daimio about this change using the terminal. (It may have been a while since you've used the terminal. Don't forget that you can get to it via "Pick an Interface" or by visiting `yourdomain.com/interfaces/terminal.html`.)

	If you type `page fetch > tab` into the terminal, you'll see all the information about your pages. Notice that all of the pages have "data" set to "null." You need to change it so "data" is set to the new data content items you created. To do this, type the following command into the terminal:
	<pre>`page set_data for :list to :local_data-on-list`</pre>

	Repeat this activity for recipe and local_data-on-recipe. (Remember the up-arrow shortcut to repeat commands.) You can double check that the change was made using `page fetch > tab`.

	### Fixing up those comments

	Uh-oh. Did you make a typo in a comment that you left when rating a recipe? Wouldn't it be nice if you could edit your ratings? It's going to take a little bit of magic (some people call it JavaScript), but you can do it! You'll head back to the content management interface for this.

	Let's modify the header-global content item. In the end, you want it to look like this:
	<pre>`<html><head><title>{@PAGE.title}</title><script type="text/javascript" src="/interfaces/js/jquery.js"></script>{begin verbatim | process escape}<style>p {margin: 0px; padding: 5px 0px;}div {margin: 0px; padding: 10px 0px;}form div {margin: 0px; padding: 0px 0px;}</style>{end verbatim}</head><body><form method="get" accept-charset="UTF-8" action="http://recipewranglers.bentodojo.com/list"> Search for your favorite recipes: <input type="text" name="searchtext" value="{#searchtext}"/><input type="submit" value="search" /></form><hr>`</pre>

	Actually, the `<script...>` part is all you need for the comment editing fix, but you may as well add that verbatim block for some styling adjustments.

	Next, return to copy-on-recipes. At the very bottom of the showratings block (below `comments:{comments}` and above `{end showratings}`), add the following code block:
	<pre>`{begin editrating | if {is value @MY.id like user_id}}<a href="#" onclick="$('#edit_comment{id}').toggle(); return false;">Edit this comment</a> <div id="edit_comment{id}" style="display:none;">{form display for :ratings row {id}}</div> {end editrating}`</pre>

	### Making it just a little prettier

	If you are looking at a specific recipe, notice that the title of the page (up at the top of the window or in the tab) is simply "Recipe." Let's make it so that the name of the actual recipe appears. You'll do this in header-global. The first line of the content currently looks like this:
	<pre>`<html><head><title>{@PAGE.title}</title>`</pre>

	You can change it to this:
	<pre>`<html><head><title>{if {is value @PAGE.title like "Recipe"} then {@recipe.name} else {@PAGE.title}}</title>`</pre>

	Now that's _much_ better. Congratulations! You've built your first web application using Daimio.
	</div>
	<div id="complexapp">

	a complex app example
	</div>
	DAML
	<div id="primer">

	## DAML Primer

	`{-----}`
	_commands go in braces_

	`{----|-----|-----}`
	_use pipes to separate commands_

	`{begin foo} ------ {end foo}`
	_begin and end denote blocks_

	`{$foo}`
	_reference blocks with $_

	`{handler method param value}`
	_commands have four parts_

	`{handler method param1 value1 param2 value2}`
	_multiple parameters_

	`{handler method param $foo}`
	_values can be fancy_

	`{handler method param {-----}}`
	_even other commands_

	`(one two three)`
	_this is a list_

	`("one" "two" "three")`
	_a list of strings_

	`(:one :two :three)`
	_also a list of strings_

	`{variable set path :bar value (:one :two :three)}`
	_a list used as a parameter value_

	`{@bar}`
	_lists are accessed with @_

	`{(:one :two :three) | > :bar}`
	_another way to set @bar_

	`($foo @bar)`
	_list items can be fancy_

	`((:one :two) (:three :four))`
	_even other lists_

	`({-----} {-----})`
	_or commands_

	`{* (:one :1 :two :2)}`
	_this is a hash_

	`{* (:one :1 :two :2) | > :bar}`
	_this is a hash assigned to bar_

	`{@bar}`
	_reference hashes with @ too_

	`{@bar.one}`
	_this is a hash value_

	`{(@bar @hash) | > :bundle}`
	_a list of hashes is a bundle_

	`{begin block | merge with @bundle} {one} {end block}`
	_merging over a bundle_

	`{one}`
	_this is a local variable_

	`{@bar.one | is like :1}`
	_this is true_

	`{one | is like :1}`
	_within the above merge, also true_

	`{@bundle.#1.one | is like :1}`
	_references are flexible_

	`{@bundle.{@bar.one}.one | is like :1}`
	_very flexible_
	</div><div id="variables">

	## Variables

	<span class="caps">DAML</span> has two primary variable types:

*   **Static** variables store information you'll refer to later.
*   **Local** variables are dynamically generated by various commands.

	In DAML, there's no strict concept of scope, however various commands interact with local variables to add things and take them away. Placed within static variables, your data is safe from harm. Sometimes, template set up dictates placing information into special local variables to activate them. You can accomplish this manually, using the '>' shortcut, or automatically with a conveniently placed {process merge}, for example.

	You can use the '@' symbol to access different types of variables. For example, @MY contains the ID, username, and keychain of the current user. Only @STATIC and @LOCAL are editable, however.

	### Static variables

	Once you set a static variable you can reference it later within that Daimio run. Generally speaking, static variables shouldn't change once set, but they're entirely mutable if you need to change them. 

	Static variables are:

*   Set once, accessed anywhere
*   Only modified when requested
*   Used for all general data passing
*   The default for the '@' sigil

	`{:avacado | > :questionable.pizza.toppings}`
	`{@questionable.pizza.toppings}`

	The above is equivalent to:
	`{:avacado | > :STATIC.questionable.pizza.toppings}`
	`{@STATIC.questionable.pizza.toppings}`

	Which is also equivalent to:
	`{variable set value :avacado path :STATIC.questionable.pizza.toppings}`
	`{@questionable.{"pizza"}.toppings}`

	### Local variables

	Local variables are ephemeral things. Various commands create them and modify them automatically. You'll access them often, but will rarely set them directly. They're volatile in the sense that some commands set them indirectly as by-products.

	Local variables are:

*   Set by certain commands (e.g., merge, foreach)
*   Used within templates as replacement variables
*   Overwritten often, and without warning

	`{:spam | > :LOCAL.fav.pizza.toppings}` 
	`{fav.pizza.toppings}`

	The foreach command creates the 'key' and 'value' local variables for each topping and merges them with a copy of the string. 
	`{{* (:cheese "Basic necessity" :basil "Entirely mandatory" :olives "Completely optional" :capers "Perish the thought")} | > :toppings}` 
	`{foreach string "<p>{key}:{value}</p>" with @toppings}`

	### Blocks

	Use the begin-end notation to create blocks. Blocks created this way are added to @BLOCK, and can also be accessed using the $ sigil.

	Blocks are:

*   Reusable inline templates
*   Control flow providers
*   Not set directly via '>'

	`{begin pizza}is delicious and tasty{end pizza}` 
	`{$pizza}`

	Blocks also send their value through the pipe: 
	`{begin foo | if :true} Ceci n'est pas une pizza {end foo}` 
	returns ` Ceci n'est pas une pizza `

	`{begin foo | if false} This is a pizza {end foo}` 
	This, on the other hand, returns nothing.

	`{begin foo} No pizza {end foo}` 
	 This also returns nothing, because there's no piped command after `begin foo`

	You can set a block and immediately display its value with any of these:

*   `{begin foo | $foo} un slice {end foo}`
*   `{begin foo | __pipe} deux slice {end foo}`
*   `{begin foo} trois slice {end foo}{$foo}`

	### Use @ to access reams of information

	We've described STATIC, LOCAL, and BLOCK, which are all accessible using the '@' sigil. The following work the same way, but are not user-editable.

*   `@MY`: contains the id, username, and keychain of an authenticated user
*   `@SITE`: contains the protocol, domain, subdomain, path and url of the current site
*   `@PAGE`: contains the keyword, title, path, tags, and keyholes for the current page*   `@GET`: contains querystring variables and url segments
*   `@POST`: contains data delivered via POST
*   `@REQUEST`: combines `@GET` and `@POST` data
*   `@ERRORS`: contains any errors generated by Daimio
*   `@WARNINGS`: contains any warnings generated by Daimio
*   `@NOTICES`: contains any notices generated by Daimio
	</div>
	I'm removing this section for now, because A) it's wrong in a lot of places B) the examples aren't very simple C) the DAML primer does a better job of presenting the basics D) I'm not sure what to do with it. Should probably create a replacement (maybe just a set of simple examples / challenges) at some point... - dann 2010.01.30 <div id="basics">

	## DAML Basics

	### Command syntax

	Daimio commands have the following structure:
	 <pre>`{handler method param1 value1 param2 value2 ... paramN valueN}`</pre>

	For example, here's the command you would use to log in to Daimio:
	 <pre>`{myself authenticate username "fred" password "fantastic"}`</pre>

	Here are some simple code examples to help you learn the command syntax for some DAML basics: working with strings, arrays, pipes, and blocks. When you're ready, [try out the examples](http://www.daimio.org/terminal) on the terminal.

	### Strings
	<pre>`{variable set path :firstname value "Charles"}{"de Gaul" | > :lastname}{@firstname} {@lastname}`</pre>

1.  Create a string variable
2.  "de Gaul" is piped in as the value of the {variable set} command
3.  This line becomes "Charles de Gaul"

	### Arrays
	<pre>`{array create name :pets value (:Kinji :Lucy :Zirra)}{@pets}`</pre>

1.  Create an array of pet names
2.  Returns ["Kinji","Lucy","Zirra"], the JSON equivalent of @pets

	### Blocks
	<pre>` {begin mash_json} [{"name":"amelia", "home":"shack", "profession":"dentist", "car":"corvette"},{"name":"archie", "home":"mansion", "profession":"rockstar", "car":"jalopy"}]{end mash_json}`</pre>

1.  The beginning of a block
2.  A JSON array
3.  A JSON array
4.  End of the block

	### Putting them all together
	<pre>`{$mash_json | array from_json | > :mash}{begin outer_mash | foreach with @mash as :masher}{begin inner_mash | foreach with masher}{key}:{value}{end inner_mash}{end outer_mash}`</pre>

1.  The "mash_json" string variable is piped in as the value of the {array from_json} command. This value is then assigned to an array variable named mash. "array" is a shortcut for "collection" and the ">" symbol is a shortcut for "collection create name".
2.  The block value is piped in to foreach (alias for "process for_each"), which parses a copy of the template for each value of @mash aliased as local variable "masher"
3.  foreach sets the "key" and "value" local variables by default
4.  Display the key and value
5.  End of the block
6.  End of the block

	### And lastly
	<pre>` {begin @mash}name:{name} home:{home}{end @mash}`</pre>

1.  This syntax is sugar for using the {process merge} command with @mash
2.  The names and homes show up here
3.  End of the block </div>
	<div id="params">

	## Params

	### Parameter syntax

	Here's a handy reference to Daimio parameters and syntax.

*   `"value"` Text in quotation marks is interpreted as a raw string.
*   `:value` A single word beginning with a colon is treated as quoted text.
*   `path` A bare path is interpreted as a local variable.
*   `$value` A block variable.
*   `@path` A static variable.
*   `%type:path` The content item with keyword (or handle) "value."
*   `#value` Incoming request data (i.e. $_REQUEST['value']).
*   `{value}` A Daimio command will be completely processed before becoming a parameter.
*   `(value1 value2 value3)` This represents a list. Each value is interpreted as a parameter. Be sure to put your strings in quotation marks.
*   `[value]` If `value` is a valid JSON string it will be converted into an array. Note: no additional processing will take place, so `[{"key": "value"}] ` will be interpreted as JSON, not a Daimio command.

	Any processing mentioned above happens **before** the parameter is sent to the command, so $foo and {$foo} and "{$foo}" are potentially very different values.

	Note that local and global array variables accept dot-delimiters, so you can say @cities.toronto.nickname or foo.barista if you like. (See the Arrays section of the terminal ("Kick the Tires") for more information on using dots in arrays.)

	In addition to referencing request data, the hash mark is also used for accessing URL sections. Given "example.com/one/two/three", #1 equals "one", #2 equals "two", and #3 equals "three".

	### Parameter equivalencies

	Items in a list are equivalent.

*   "a_string"
*   :a_string

*   (:one :two :three)
*   ("one" "two" "three")
*   [["one","two","three"]]

*   {* (:key1 :value1 :key2 :value2 :key3 :value3)}
*   [{"key1":"value1", "key2":"value2", "key3":"value3"}]

	### Parameter naming policy

*   **For-parameter** This parameter accepts either an array of values (e.g. keywords, ids, etc) or a single scalar value. Commands that take this parameter **always** return an array of values, even if there's only one value being returned.
*   **Singular parameters** These parameters (e.g. solution, keyword, id) accept scalar values. If passed an array, they should take the first element of the array as their value.
*   **Plural parameters** These parameters (e.g. solutions, keywords, ids) take an array of values. If passed a scalar value, they will treat it as a one-element array.</div>
	<div id="pipes">

	## Pipes

	Pipes are used to link the output of one command into the input of another. So instead of doing `{page add_tag for {page pick} tag :test}` you could do `{page pick | page add_tag tag :test}`. 

	The value is assigned to the first unvalued parameter. "First" refers to the order in which the parameters are listed in the code, which is also the order in which they're listed in the terminal. Parameters tend to be listed in order of importance, with required parameters, if they exist, listed first.

	**Tip:** You'll need to remember the order of parameters (or check in the terminal) to effectively use pipes. In practice, there are generally only one or two parameters per command that you'll be piping values to, so it tends to work itself out. Combined with the shortcuts mentioned below, this allows you to do some fairly interesting things in a compact way, such as `{#2 | is like "/^\d+$/" | then :digits | else :not_digits}`.
	</div>
	<div id="blocks">

	## Blocks

	In DAML, you can set apart blocks of text. There are two types of text blocks: regular blocks and merge blocks. We use blocks to build inline templates, group sets of conditional commands, structure conditional interface elements, and encapsulate messy input, such as CSS. Blocks can be embedded in other blocks, as long as they don't have the same name. 

	#### Regular blocks

	You can establish a block of text like this:
	<pre>`{begin test1}this is a block. it can contain commands, like {page pick}{end test1}`</pre>

	This block will create a new global string variable named `$test1` which contains the unprocessed contents of the block. It will not output anything.

	The following block will create a variable named `$test2` and will output three copies of itself with descending heading levels. It sends a value to output because of the command following the pipe.
	<pre>`{begin test2 | foreach with (:1 :2 :3)}<h{value}>this is a block. it can contain commands, like {process escape string "{page pick}"}</h{value}>{end test2}`</pre>

	#### Merge blocks

	A merge block is shortcut syntax for merging an array with the contents of a block. Merge blocks do not set a global string variable, and always send their value to output regardless of whether or not there is a pipe. They are built by referencing a global array in the block name. Hence this:
	 <pre>`{begin test3 | merge with @example}{keyword}:{value}{end test3}`</pre>

	And this:
	<pre>`{begin @example}{keyword}:{value}{end @example}`</pre>

	Are identical, except that the former also sets `$test3`.
	</div>
	<div id="shortcuts">

	## Shortcuts

	Words on the left of the list below are converted to the string on the right when entered as the beginning of a command. Shortcuts are stored as .ini files in the `daimio/config/shortcuts` directory. We use them to mask awkward syntax (PHP doesn't allow methods named 'if,' for example) and to condense commonly used phrases such as with 'else.'

	You can build your own custom shortcuts for your application by creating a new .ini file in the shortcuts directory. You could also create a set of commonly used shortcuts that you install on any Daimio projects you develop. Shortcuts can also be installed via the packaging system, just like everything else in Daimio.

	Ex: `{if @cars.passengers then "fasten seatbelts"}` 
	becomes `{logic daimio_if condition @cars.passengers then "fasten seatbelts"}`

	The following shortcuts are installed with Daimio by default:

*   merge = "process merge"
*   foreach = "process for_each"
*   sub = "process substitute"
*   if = "logic daimio_if condition"
*   then = "logic daimio_if condition __pipe then"
*   else = "logic daimio_if condition __pipe then __pipe else"
*   is = "logic is"
*   equals = "logic is value __pipe like"
*   and = "logic daimio_and conditions"
*   or = "logic daimio_or conditions"
*   not = "logic daimio_not value"
*   less = "logic less"
*   array = "collection"
*   < = "collection create name"
*   * = "collection pair value"
*   use = "utility"

	[Back to the top](#learndaml)

	### Shortcut equivalencies

	Items in a list are equivalent.

*   {#foo | else :error}
*   {#foo | if #foo else :error}
*   {if #foo then #foo else :error}
*   {#foo | if __pipe then __pipe else :error}
*   {logic daimio_if condition #foo then #foo else :error}
*   {#foo | logic daimio_if condition __pipe then __pipe else :error}

*   {#foo | is like :good | then :good else :bad}
*   {if {#foo | is like :good} then :good else :bad}

*   {(:one :two) | > :array}
*   {(:one :two) | array create name :array}
*   {collection create name :array value (:one :two)}</div>
	<div id="where">

	## Where string

	The where parameter allows you to select particular elements. It's essentially a sugar-coated SQL statement, so the syntax should be familiar to SQL users. Three distinct parts make up a statement: field, operand, and value. Statements are separated from each other by parentheses and the keywords AND, OR, and NOT. The where parameter takes a set of possible names of fields, which double as translation devices. String values are quoted in single quotes within the where string.

	#### Operands

*   =
*   <
*   >
*   !=
*   <=
*   >=
*   ~= (translated to 'like')
*   !~ (translated to 'not like')
*   %= (translated to 'in')
*   !% (translated to 'not in')

	#### Values

*   `{some value}`: Brace-wrapped values are processed, then filtered as below.
*   `'some value'`: Single quotes are used within where values.
*   `(some, value)`: Parenthetical values are automatically individually quoted.
*   `value`: A single bare word value is quoted.

	[Back to the top](#learndaml)

	#### Additional syntax examples

	These are based on the following field array: 'pico' => 'de.gallo', 'bing' => 'crosby', 'tag' => 'tag'. The 'tag' field gets a bit of extra sugar, as you can see below.
	<dl><dt>pico = lovely</dt><dd>de.gallo = 'lovely'</dd><dt>pico ~= lovely</dt><dd>de.gallo LIKE 'lovely'</dd><dt>pico !~ 'lovely loverly'</dt><dd>de.gallo NOT LIKE 'lovely loverly'</dd><dt>pico %= (lovely,loverly,lordly)</dt><dd>de.gallo IN ('lovely','loverly','lordly')</dd><dt>tag = neat</dt><dd>tags LIKE '% neat %'</dd><dt>pico = lovely AND bing ~= '%armadillo%'</dt><dd>de.gallo = 'lovely' AND crosby LIKE '%armadillo%'</dd><dt>((pico = lovely) AND (bing ~= '%armadillo%'))</dt><dd>((de.gallo = 'lovely') AND (crosby LIKE '%armadillo%'))</dd><dt>((pico = 'lovely') AND (bing ~= '%armadillo%')) or (pico %= (robby, david))</dt><dd>((de.gallo = 'lovely') AND (crosby LIKE '%armadillo%')) OR (de.gallo IN ('robby','david'))</dd></dl> </div>
	<div id="notes">

	## Notes

*   If you need to pass an unprocessed command as a parameter, wrap it in quotes: `{content set_value for "foo" to "{page pick}"}`
*   The 'for' command takes a single keyword (or handle for content items), a comma-delimited keyword string, or an array of keywords (which can be given using the list parameter type, among other things).
*   Comments look like this: `{/lorem ipsum whatever}`. Daimio eats them.
*   You can use the process handler to escape and unescape braces.
*   Parameters appear in the terminal in order of importance, and also in the order in which the pipe checks them.</div>
	<div id="bnf">

	## BNF
	<pre>`<command> ::= "{" <handler> " " <method> " " <params> <ending><ending> ::= "}" | "|" {command} "}"<params> ::= "" | <pname> " " <pvalue> " " <params><pname> ::= <word><pvalue> ::= <command> | <list> | <quote> | <colonquote> | <local> | <string> | <array> | <content> | <request> | <json><list> ::= "(" <lvalue> ")"<lvalue> ::= <pvalue> | <pvalue> " " <lvalue><quote> ::= """ [^"]+ """<colonquote> ::= ":" <word><local> ::= <word><string> ::= "$" <word><array> ::= "@" <word><content> ::= "%" <word><request> ::= "#" <word><json> ::= "[" <validjson> "]"<word> ::= [a-zA-Z0-9_-]+`</pre> 

	**Note:** quotes can contain quote marks that are wrapped in brackets. Words are slightly more generous than the regex indicates but their generosity shouldn't be abused. This doesn't express begin/end blocks or shortcuts.
	</div>

	DAIMIO CONCEPTS
	<div id="concepts">

	## Daimio concepts—productivity in, tedium out

	Daimio comes with several built-in concepts that make development easier. These include handlers and some associated libraries that other handlers can draw on. Concepts are modular—just install and go! While Daimio comes with a few built-in concepts, you can use the package handler to download others.

	A concept generally includes at least a handler and a table in the database. Some concepts are loosely coupled: the Package handler, for instance, could be removed without affecting the other parts of the system. Others, like Users, are wound more tightly into the fabric of Daimio, but all of them are replaceable under the right circumstances.
	</div> 
	<div id="users">

	## Users

	Managing users in Daimio is simple. Users have an id, a username, and a keychain. This simplicity allows you to easily create custom models for specific user roles that expand on Daimio's session / cookie management, authentication features, and administrative power.

	A **wizard** is a special type of user account for building applications. Wizards don't have a keychain, but they don't need one. They can access any command, form or page, regardless of its permissions. They can also temporarily transform themselves into any normal user to test functionality or perform maintenance.

	### Why wizards?

	In earlier projects, where site-building users were called 'admins,' there was much confusion caused by conflating back-end admins with front-end admins. The 'wizard' designation doesn't intersect with business terminology, and is a natural choice, given the term's prevalence in sysadmin lore. (Plus everyone likes having magical powers.)
	commenting this out for now... should reconsider it for flavor later, maybe.

	 Long ago in the land of Daimio, wizards could attain various and diverse traits, including _powerful_, _invisible_, _invincible_, _transmutable_, etc., as well as buffs castable on unsuspecting plebs. After working with the system for awhile, we realized we didn't need some of those traits at all, and those we did need, we made universal among wizards instead of conferring them individually. And hence the Daimioverse became a much simpler — if perhaps less colorful — place.
	</div>
	<div id="pages">

	## Pages

	Most likely, you will associate your application with a website, which acts as a primary interface and a conduit for information. **Pages** allow you to map sets of urls to a particular content item. They also provide a keychain-based permission mechanism.

	 While the index.php gateway uses pages to display content when someone visits your site, pages can also be used with other gateways. For example, you might want to call a page via an AJAX request to insert some pre-generated HTML into a webpage. You can even call a page from within a content item, which can provide a level of modularity -- a dashboard page, for example, might contain calls to various report pages which could also be accessed individually.

	### Examples
	_Some examples_

	`{page add path "blog"}`

	Adds a new page, accessible at foo.com/blog. We haven't specified a layout, so this page will use the default magic layout of global:__layout.

	`{page add path "blog/__article_id" layout :article}`

	This path introduces placeholder names. The __article_id path segment matches any value, and the value of that path segment is accessible on the page as the `{#article_id}` variable. For example, the url foo.com/blog/12 would match this page, and `{#article_id}` would return '12'.

	A placeholder will match anything, including multiple path segments, so foo.com/blog/12/2009-12-24/Jingle_bells_and_stockings would also match this page, and `{#article_id}` would still return '12' (if multiple path segments are matched, the placeholder takes the value of the first one).

	`{page add path "blog/__article_id/comments/__comment_id" layout :admin}`

	Here's a more complicated path with two placeholders. Placeholders match less aggressively than regular path segments, so a url like foo.com/blog/12/comments/14 will open this page instead of the "blog/__article_id" page we added earlier, even though they both match.

	`{page set_keyholes for "blog/__article_id/comments/__comment_id" to (:admin :blogger)}`

	This adds keyholes to the page we just added, so only bloggers and admin users can access it. Pages without keyholes are accessible by anyone -- this is the opposite of commands without keyholes, which are only accessible by wizards. (Pages, being outward facing in nature, are almost always accessible by some set of non-wizard users, and typically open to anyone.)
	</div>
	<div id="content">

	## Content

	In Daimio, the content concept provides database-based revision control for textual data. Daimio tracks every edit, along with the user who made the change, and the time that the change occurred. Content is important for site-building, powering pages, views, and lenses. It also benefits your users directly: when used as a form field, it displays the revision history for blog posts, white papers, wiki articles, and more.

	### Types of content

	Content comes in a variety of types:

*   **Page** and **global** content form the skeleton of site building.
*   **Templates** store site-wide content that doesn't generally change, such as fatal errors, merging templates, etc. Daimio comes pre-installed with several customizable templates.
*   **Lens** content works with the [Lens](#lenses) concept.
*   **View** content stores specific views of data: a list of live articles, a single article displayed in full, etc.
*   **Form** content can't be searched like regular content. It's generally available only within the context of the form it's associated with.
*   **Bonus** content can't be searched either. You can ask Daimio to record changes to your auxiliary files, like js and css. See the [settings](#settings) section for information on setting this. 

	In the future types might be user-definable, with different behaviors n' stuff.


	### Accessing content

	The two defining characteristics of a content item are its _type_ and its _path_. Content type and path are combined to form a handle -- a string that uniquely identifies a single content item. Handles look like "type:path." Example handles:

	`page:about/company/copy`

	`global:__layout`

	`template:daimio/fatal_error`

	Here's how to get the value of a content item:

	`{content get_value handle "global:__layout"}`

	You can also use the shortcut glyph

	`{%global:__layout}`

	If you're on the main site, you can also access content using a partial handle, which leaves out the type and part of the path. If you're on page 'quuxberries' the command `{%copy}` first tries `{%page:quuxberries/copy}` and returns that value if it exists. If not, it then tries `{%global:copy}`.

	### Editing content

	There are two basic ways to edit content.

	#### Export

	Use the `{content export}` command to export content. This dumps a copy of the current content into the daimio/temp/content directory. Each type is a top-level directory in this hierarchy. Content paths serve as subdirectories, while the last path segment is the filename.

	The `{content import}` command imports the content, editing any existing content items and adding any new DAML files as content items. Additionally, new sub-directories in the 'page' directory are added as new pages (with the default layout of global:__layout). This allows us to edit content and pages via FTP.

	The `{content autoload turn :on}` command marks content to be automatically loaded, alleviating the need to constantly re-import your content. This should only be set on the development server, as it checks for changes each time Daimio is accessed.

	#### Content Management Interface

	Daimio has its own Content Management Interface, which allows you to view and edit content. **Note:** the Content Management Interface is incompatible with file-based content editing.

	### Examples

	`{content add type :page path "quuxberries/testimonials" value "Mmmm, tasty berries --Stanley" tags (:marketing :sidebar)}`

	`{content set_value for "page:quuxberries/testimonials" to "Quuxberries make me awesome. They're GRRRRR - wait for it - ATE. True story. --Barney"}`

	`{content get_history for "page:quuxberries/testimonials" include :values}`

	`{content rollback for "page:quuxberries/testimonials" from :1}`
	</div>
	<div id="forms">

	## Forms

	To build an application, you need to add structure to the database, input data within that structure, and then fetch that data from the database. **Forms** are the answer. In Daimio, forms glue the database and user experience together.

	Adding a form adds a new table to the database, and adding a field to that form adds a new column--generally. Your application's models can use Daimio's form libraries, FormLib and DataLib, to access the power of Daimio Forms. 

	### Anatomy of a form

*   keyword (valid table name)
*   input extensions (like unique, which limits users to a single row)
*   perms (explained below)
*   fields (explained below)

	### Anatomy of a field

*   keyword (valid column name)
*   type (explained below)
*   name, description
*   sort order
*   default value
*   input extensions (like required, truncate, or textile)
*   options
*   decorator (explained below)

	### Field types

	#### Basic fields

	Fields like text, varchar, int, and datetime map naturally to both MySQL columns and HTML inputs.

	#### Internal fields

	Fields like timestamp, creationdate, ipaddress and username attach valuable metadata to their information.

	#### Json fields

	A number of fields store their data as json strings, which are converted back into arrays on output. Often this small denormalization trick is actually more efficient than building new database structure and performing join queries.

	#### Tag fields

	The tags_simple field gives users an easy and efficient way to tag their articles, comments, or what-have-yous with simple space-delimited words. Sometimes things are more complex and you need the power of tags_comma, a three-table tagging solution.

	#### Dirty fields

	The data in these fields isn't scrubbed of HTML and DAML in the pre_input phase. Useful in combination with models or input extensions for allowing your users to enter textile or even limited raw HTML, but use with extreme caution.

	### The input cycle

	The checks below can modify data or throw errors that cancel the input.

*   check permissions
*   check form input_extensions (like unique)*   check field input_extensions (like required, truncate)*   check field pre_input: convert value, split into multiple fields, etc
*   verify field is_valid: ensure the value is acceptable
*   send input request to database
*   perform field post_input actions

	### The display cycle

	Form display involves three tiers of templates: the overall layout template, the field wrapper template, and the individual field input templates. Layout and wrapper templates can be sent with the `{form display}` command, set at the application level, or use the default. Individual fields will use the field default template unless they have a decorator.

	Data can be returned from `{form display}` instead of HTML, allowing you to modify the display inline. Individual fields or sets of fields can be displaying with the `{field display}` command.

*   check perms
*   determine field value
*   get field decorator template
*   get field data for display
*   merge field data with decorator
*   merge above with wrapper
*   merge all field data with layout template

	### The fetch cycle

	If none of the fields being fetched have pre_fetch or post_fetch actions this reduces to a simple query. Generally fields are designed to take a little more time on input and occupy a little more space in the database to obtain fast fetch results. Currently tags_comma has a pre_fetch method and the *_json, tag_*, and text_dirty fields have post_fetch methods.

*   sort out which fields we're fetching
*   perform pre_fetch actions for fields that have them (can affect where, fields, from)
*   put together the query*   fetch data<li>perform post_fetch actions for fields that have them

	### Decorators

	If the decorator value is a single word and a template of that name exists then that template is used as the decorator. Otherwise the decorator value is the template.

	### Permissions

	Destroying, Editing, Adding, and Reading data in a form are all constrained by the user's keychain. Each of these permission types can have keyholes, and a user with a matching key may access that ability.

	The regular magical keys of __world (anyone) and __member (registered users) can be used for form permissions, and there is an additional magical key that can *only* be used here: __owner, which unlocks rows for their creator.

	### Security

	Fields not of the *_dirty type are scrubbed of HTML and DAML on input. Be very careful about deploying dirty fields, and test them thoroughly to ensure that your cleansing techniques are satisfactory for removing the blight of XSS and related ailments.

	### Form Extensions

	The **sendemail** extension is an interesting example of what can be done with form input extensions. It allows you to send the input of a form to an email address. You can customize the email using the {daimio set_setting} command. Suppose our form is called _contact_. Here's how you would use it:

*   Attach the form extension to the form: {form set_input_extensions for :contact to :sendemail}  
*   Set the recipient: {daimio set_setting type :form_sendemail item :contact name :recipient value "email@domain.com"}  
*   Set the from address: {daimio set_setting type :form_sendemail item :contact name :from_address value "donotreply@site.com"}  
*   Set the subject: {daimio set_setting type :form_sendemail item :contact name :subject value "A new email for you"}  
*   Set the template: {daimio set_setting type :form_sendemail item :contact name :template value "Hello! {name} would like to meet you! Please call {phone}."}

	### Try it out:

*   add a field with a decorator
*   add a field with an input extension
*   add a dirty field with decorator and ' clean textile '
*   display fields with modified wrapper
*   modify global wrapper
*   modify global layout</div><div id="lenses">

	## Lenses

	#### The problem

	Daimio's [CUDLy](philosophy) roots means you can easily restrict a command to be usable by a subset of users. This operation, however, is a binary thing -- either you can use a command completely, or not at all. What if you need to restrict a command based on its parameter values?

	#### An example

	You've installed the Yari blogging package, which creates a form for storing articles and uses {data fetch} to access them. You've posted some draft articles. How can you let anonymous users access your published articles but keep them from viewing the draft ones?

	#### A partial solution

	At first blush it seems obvious that we should push all of these restrictions into the Articles model, and use that to wrap the {data fetch} call. There's some issues with this, though:

*   Some projects have a *lot* of different viewing restrictions, that take effect under different circumstances and affect different user groups. Not only does this bloat the model code, but those checks have to be run every time you access the model, whether they apply or not.
*   Putting the restrictions in the model code doesn't help the DAML users, who need to encode those finicky restrictions into their model call each time they request data.
*   Only a programmer can change the restrictions. There's no facility for a designer / IA / business user to change who can see what when. This isn't really the programmers purview -- passing that control up the chain is a good thing.
*   Suppose a tool exists to automatically generate viewing restrictions based on documentation. If the effect of this tool was to create or modify PHP code within models on the server it potentially opens up a enormous security hole. A single bug or overlooked input pattern could allow an attacker to run arbitrary code on the server. If the tool generates DAML, however, then there's no need to worry: DAML is designed to run.

	#### The Lens solution

	Lenses allow you to build DAML subroutines, save them as a content item, and then allow certain users to run that content item with elevated permissions. So you can block access to {data fetch} or even just a particular form, and then encapsulate all the calls to {data fetch} with lenses. You then dole out the permission to use those lenses as needed.

	#### Lens example

	As mentioned above, if users have read access to `{data fetch form :articles}` they can see all of your articles, including the draft articles that aren't live. You can put `{data fetch form :articles where "status = live"}` in your template code, but that doesn't stop a wily user from going to the terminal and running `{data fetch form :articles where "status = draft"}`.

	We'll take the following steps to prevent the wily user from seeing draft articles:

1.  Set the read keyhole on the articles form to __lens
2.  Make a new `lens:yari/articles/live` content item
3.  Add a new lens called live_articles

	Let's explore each of these steps in detail.

	##### Lens permissions

	When a lens is activated it first adds the __lens keyhole to the current user's keychain. It then runs the DAML code within the content item the lens is linked to, and finally removes the __lens keyhole from the user's keychain. 

	Setting the keyhole of a command (or a form, in this case) to __lens allows lenses to run that command, even if the user doesn't have permission to do so directly. Setting the keyholes on a lens limits the users who can run that lens. So we can set up different lenses that are usable by different users which all call the same command with different parameters, which the lens runs for the user by proxy. Simple, eh?

	##### Lens content

	[Content](#content) comes in many flavors. Lens content doesn't have any special properties, it's just a convenience flavor. Using a global or template content item as a lens would work just fine.

	Lens content typically follows the same pattern: do a bunch of things inside a block, set some data into a return variable, then return that variable. A lens can either return a string or an array, but not both. You'll almost always want to return an array, so it's important to avoid having any string output. Here's what this looks like for live articles in yari:

	<pre>`{begin nullblock | process consume | @return}{data fetch form :articles where "status = live" order "publish_date DESC" limit {limit | else :20} | > :return}{end nullblock}`</pre>

	The first line sets up a block, processes everything within, and then gives back the return array. The Lens handler returns that array as the value of this lens, so in this case it's returning an array of articles.

	The second line fetches data from the articles table. The status of all articles returned is 'live'. Note the local variable 'limit' -- we'll be setting that up later. 

	##### Lens creation

	We can add the lens with the following command:<pre>`{lens add keyword :live_articles content :lens:yari/articles/livekeyholes :__world params {* (:limit "Number of articles returned, defaults to 20")} apropos "Fetch live articles"description "Fetches articles with a status of live in reverse chronological order."}`</pre>

	Most of the above is explained in the terminal help, but lens parameters deserve further explanation. Also note that setting the keyholes to __world makes this lens accessible to anyone.

	##### Lens parameters

	Parameters are passed in to the lens as local variables. In the above example `{limit | else :20}` returns the value of limit param if it is set, or 20 if it isn't.

	The 'params' param of the `{lens add}` command requires a hash, with the parameter name as the key and the parameter description as the value. The easiest way to provide a hash in Daimio is using the `{collection pair}` command, which has a convenient shortcut in '*'.

	The pair command takes the first element in a list and makes it the key for the second element. It does the same thing for the third and fourth, fifth and sixth, and so on. So our two element array `["limit", "Number of articles returned, defaults to 20"]` (in JSON) becomes the one element hash `{"limit": "Number of articles returned, defaults to 20"}` (also JSON).

	The `{lens add}` command also takes the 'required' param, which is an integer determining the number of required parameters. If you create a lens with four params and required is set to 2, the first two params are required and the second two are not.

	<pre>`{lens add keyword :param_test content :lens:param/test keyholes :__world params {* (:one "one help" :two "two help" :three "three help" :four "four help")} required :2}`</pre>

	You'd call the above lens like this:`{lens param_test}`

	But that would fail because it requires the first two parameters. This would work:`{lens param_test one :value1 two :value2}`
	</div><div id="packages">

	## Packages

	Adding functionality to your Daimio install is easy, fun, and dangerous. Kids, never install a package from an untrusted source.

	### Installing a package

	Run `package fetch > tab` in the terminal. This opens a new tab with a list of the packages found at daimio.org. You can use the 'from' param to fetch a list of packages kept at a different domain.

	Run `package download keyword :textile` in the terminal. This downloads the textile.zip file from daimio.org into the `daimio/temp/downloads` directory. It then unpacks the zip file into the `daimio/temp/packages` directory so you can examine it.

	Run `package install keyword :textile` in the terminal. This installs everything found in `daimio/temp/packages/textile`.

	Refetch the terminal commands. Run `string textile on :x`.

	### Anatomy of a package

	#### Files

	Examine the `daimio/temp/packages/textile` package. Everything within the `files` directory gets copied into the local file system. If you run `{package install}` with the `and :overwrite` option this process overwrites existing files.

	#### Content

	The package can also contain a `content` directory. Everything within the content directory is imported just like regular [content](#content). Note that this allows new pages to be created as well.

	#### Commands

	Advanced packages often contain a `command` directory. Files within are processed as DAML strings, one at a time, in alphabetical order. This allows the package to build new forms, set parameters for pages, install dependancies (packages can install other packages), show notices, and do anything else they desire. The Yari package has some good examples of these advanced techniques.

	### Creating a package

	Suppose you've developed a new package 'singularity'. It is a directory containing at least one of the files, content, or commands directories mentioned above. 

*   Zip the singularity directory into singularity.zip
*   Create a new /packages directory at the base level of your Daimio install
*   Copy singularity.zip into /packages
*   Run `package add keyword singularity description "Enables recursive self-improvement"` in the terminal.

	You've now added the singularity package to your system. It can be externally discovered by running `{package fetch from :your_domain}` and downloading using `{package download keyword :singularity from :your_domain}`.

	If future events necessitate disabling the singularity you can run `{package remove keyword :singularity}`.
	</div>
	<div id="tools">

	## Tools
	Note: This is the old copy for this section. It's too wordy and doesn't have enough examples, so I rewrote it.

	Most handlers contain a set of methods that work together to provide a complete basis for managing the underlying concept, but sometimes it’s hard to know when’s enough. Take the Math handler, for instance. Out of the box Daimio provides the four basic arithmetic operations, but what if you need exponentiation? We could include that in the base deploy, of course, but that just begs the question: what to do if you need factorials? Or the gamma function? Or the Riemann zeta function? 

	You could add the functions to the Math handler yourself, of course, but what happens when you want to download a package containing more math functions, all conveniently wrapped in a modified version of the Math handler? Now you need to manually merge your handler with the packaged one, and so on for every new Math package you download. There has to be a better way.

	The `daimio/tools` directory allows you to split methods out into individual files. The handler is then constructed from these methods when `{daimio freshen_commands}` is called. This allows you to expand general handlers like Math and String using the package system. 


	Tools present a solution to the problem of distributing new methods to handlers.

	Problem: You need to install Textile for a project. Later on you also need to install Markdown, AsciiDoc, Haml and Sass. When you're done you'd like to distribute the wrapper methods you've created as packages so you can easily install them in the future.

	Solution 1:Put each markup language in its own handler. This is good, because they can be easily packaged up for distribution, but it also pollutes the top-level namespace with one-method handlers.

	Solution 2:Pack the methods for each language into a common handler, like String. This limits the number of handlers, but if you package up the whole String handler it will collide with anyone else's String handler, destroying their methods and making a mess.

	Solution 3:Pack the methods for all the languages into a new handler called Markup and distribute that as a package. Later someone else distributes a different combination of markup languages as a package, but to avoid conflict they call the handler Newmarkup or Tomsmarkup or Asdfmarkup. Zoiks.

	We can avoid all these problems using tools. Daimio comes with four regular tool-based handlers out of the gate: Math, String, Collection, and Utility. Each of these can be extended directly or via packages quite easily.

	### Adding a tool

	Let's add a lowercasing method to the String handler.

	1. Create a file named `lowercase.php` in the `daimio/tools/string` directory.

	2. Paste this into the lowercase.php file:<pre>`/** * Convert a string to lowercase ** Note that the characters to be converted are dependant on the current locale settings.* * @example {"SOME OLD COMPUTERS ONLY HAD CAPITAL LETTERS" | string lowercase}** @param string Value to lowercase* @return string * @key __world*/ static function lowercase($value){return strtolower($value);}`</pre>

	3. Run `{daimio freshen_commands}` in the terminal.

	4. Click the 'refetch commands' button. Note the help and examples. Start lowercasing!

	### Create a new tool-based handler

	It’s fairly simple to create your own tool-driven handler. Let’s make one for expanding on the built-in array commands. We’ll call it Vector.

	Step 1:Add a new directory: `daimio/tools/vector`

	Step 2:Add a new file: `daimio/config/activate_on/freshen/create_vector.php`

	Step 3:Paste the following into the create_vector file:<pre>`<?phpFileLib::create_tool_handler('vector', 'Magnitude and direction -- who could ask for anything more?');// EOT`</pre>
	?> this fixes my syntax highlighting

	Our new handler is all set up. Now we just need to add some methods.

	#### Method 1: Sum of vectors

	- create a new file `sum.php` in the `daimio/tools/vector` directory- paste the following into it:<pre>`/** * Sum over a list of vectors ** A vector is just a list of numbers. A list of vectors looks like ((:1 :2) (:3 :4) (:5 :6)).* * @example {((:1 :2) (:3 :4) (:5 :6)) | vector sum}** @param string List of vectors to sum* @return array* @key __world*/ static function sum($values){foreach($value as $vector)foreach($vector as $key => $value)$sum[$key] += $value;return $sum;}`</pre>

	#### Method 2: Dot product

	- create a new file `dot.php` in the `daimio/tools/vector` directory- paste the following into it:<pre>`/** * Take the dot product of two vectors ** The dot product yields a real number with interesting geometric properties.* * @example {vector dot left (:1 :2 :3) right (:4 :5 :6)}** @param string First vector* @param string Second vector* @return string* @key __world*/ static function dot($left, $right){foreach($left as $key => $value)$dot += ($value * $right[$key]);return $sum;}`</pre>

	- add random math tool- create random vector sub- add shortcuts (v+ v.)- long version- short version

	The punchline, after creating some Vector functions and shortcuts, is "It's not exactly APL, but it ain't crap either." </div>
	SPECIFICS <div id="settings">

	## Settings

	Each Daimio installation has an internal settings variable that stores information relevant to that particular install. It is never exposed to the end user and can be used to securely store information and configuration options for your models. You can access various settings in your models using the `$GLOBALS['X']['SETTINGS']` variable.

	There are three sources for values in `$GLOBALS['X']['SETTINGS']`. The first is set through the `{daimio set_setting}` command. The second is through the daimio/config/settings directory. Daimio also sets a few settings itself during bootup.

	### Setting a setting

	When you use `{daimio set_setting}` to set a setting the setting you set is stored in the metadata table with a type of 'daimio' and the item set to 'daimio'. The only essential setting of this type has a name of 'commands', and is set by the `{daimio freshen_commands}` command. All of the other metadata settings are optional.

	#### Optional settings
	<dl><dt>subdirectory</dt><dd>This is set by [build.php](#install) if you install Daimio into a subdirectory.</dd><dt>log_*</dt><dd>These are set by `{daimio logging}` and control what is appended to log.txt</dd><dt>bonus_dirs</dt><dd>Manually set using `{daimio add_setting}`, this is a list of directories that will be imported as [bonus content](#content) on autoload.</dd></dl>

	### daimio/config/settings

	All .ini files in daimio/config/settings are parsed and importing into $GLOBALS['X']['SETTINGS'] as arrays. For example: 

	`aliases.ini`:<pre>`backbacon => "canadian bacon"naffle => "pine apple"cucu => "queue cumber" 

Now you can access `$GLOBALS['X']['SETTINGS']['aliases']['cucu']` from inside your models. Since this information is not available on the public side of the command membrane, you can hide private data like API keys here. Specifically, Daimio keeps its MySQL settings here via the daimio/config/settings/db.ini file.

Notes:

*   Don't delete the db.ini file! It is essential to the survival of your Daimio install.
*   Some file names are reserved: site_*, log_*, commands, shortcuts and db.

### includer.php

The includer imports the metadata and config settings mentioned above. It also creates a few additional entries in the `$GLOBALS['X']['SETTINGS']` array.
<dl><dt>site_directory</dt><dd>The server path to the current install, determined dynamically at boot time.</dd><dt>shortcuts</dt><dd>All .ini files in the daimio/config/shortcuts directory are merged into the [shortcuts](#shortcuts) entry.</dd></dl></div><div id="command_permissions">

## Command Permissions

Visitors to your site have `keys` that they carry around with them in their `keychain`. Every visitor receives the `__world` key, and registered users also obtain the `__member` key. You can assign other keys to users based on their various roles.

Commands have `keyholes` that are used to open them. Many basic commands have the `__world` key, so they're usable by anyone. The Myself handler is for registered users, so most of its commands have the `__member` key.

If you were building an application for a school, you might have a Report model. The `{report fetch}` command, which allows you to access to any report, might have 'teacher' and 'admin' as its two keyholes. The `{report view}` command, which returns your own report if you are a student, would have the 'student' keyhole.

Commands without keyholes are only accessible by `wizards`. Read more about wizards in the [Users](#users) section.
</div><div id="magic_words">

## Magic words

Most situations in Daimio are understandable using the few simple rules outlined in this guide. Occasionally, however, you need a little magic. Anywhere an ordinary word acts in an extraordinary fashion we prefix that word with a double underscore ('__'). All such names are reserved.
If you write a package that creates new magic words you should use the magic prefix for them. In the future there might be a central registrar for new magic words. Don't use them anywhere they're not absolutely necessary, and never use the magic prefix on anything that isn't magical.

Current magic words in Daimio:

*   **__pipe**: The value of the last command.
*   **__world**: A magic key given to every visitor.
*   **__member**: A magic key given to authenticated users.
*   **__owner**: A magic keyhole for form permissions which grants the creator of a row access to it.
*   **__layout**: The default page layout content item is global:__layout. 

The magic character ('__') is also prefixed to page path segments to convert them into wildcards. See [Pages](#pages) for more info.
</div>
<div id="security">

## Security in Daimio

Here's some important information on how Daimio handles security.

### XSS Vector

Use the `{string sanitize}` command to escape content. It converts characters in the input that have HTML entity equivalents into those entities (e.g. '<' becomes '&lt;') and then escapes curly braces (e.g. '{' becomes '\{').

Form input is generally sanitized on output, but be aware of the following points:

*   Form output sanitization can be manually overridden by calling `DataLib` directly within a model
*   `DataLib` doesn't escape fields that return array data -- the field itself is responsible for the escaping. The `commatags` field type sanitizes itself, but the `json` field type, for example, doesn't.
*   The `@REQUEST` array and hash tags (like `#foo`) are not automatically sanitized. If you plan to output those within HTML you'll need to sanitize them manually, like so: `{#foo | string sanitize}`.
*   the `@ERRORS`, `@WARNINGS`, and `@NOTICES` arrays may contain a copy of user entered parameter values (e.g. "The keyword '<foo>' is invalid") and you should also escape it on output.

### CSRF Vector

Daimio filters `GET` requests at the gateway level to strip out non-passive commands. This closes a CSRF hole, but someone could still rig a `POST CSRF`. Doing so would require a user to submit a form from the malicious site to your site -- this doesn't happen passively and silently like the `GET` version.

Checking the HTTP_REFERER value is an option to close this security loophole, although this can cut off legitimate uses as well, e.g. those users on non-standard systems, behind firewalls and proxies, etc., and could still potentially be circumvented. You can easily add referrer checking code (or code for checking other headers) to Daimio's gateways if your application requires it.

See [Command Set Filtering](#CSF) for more information on this approach. 

### Session Fixation Vector

Daimio regenerates the session id on login, which helps prevent attacks along this vector.

The "session.use_only_cookies = 1" php.ini directive should probably be set at the server level to close off another vector. For more information check out [Wikipedia's entry on Session Fixation](http://en.wikipedia.org/wiki/Session_fixation).

You may also consider using `HttpOnly` cookies to ward against session hijacking, although:

*   it seems to cause problems of its own in certain situations, and
*   it does nothing to prevent XSS attacks, which seems to be the [most common means of obtaining said cookies](http://www.gnucitizen.org/blog/why-httponly-wont-protect-you).

### SQL Injection Vector

Daimio includes a library named `QueryLib`, which encapsulates some common queries: get a single value, get a single row, get some matching rows, etc.

Daimio uses `mysql_real_escape_string` to escape the parameters for these queries. We use a simple regular expression (/[^a-zA-Z0-9_]/ → '') to escape table names and field names.

Should your models contain hand-coded SQL queries you'll need to manually escape incoming parameters. You can use the quote_smart and scrub_string functions for this, both of which live inside `QueryLib`. If you're using `FormLib` and `DataLib` in your models the parameters you send are scrubbed for you.

### Command Set Filtering

During the bootstrapping process Daimio generates an array of accessible commands for the current user. This command array can be filtered before the processor is invoked to limit access through a particular gateway. The `white_filter` and `black_filter` functions found in daimio/config/input_filters.php show the standard implementation of this technique.

You'll want to apply these filters on requests coming in to your gateways via `GET` &#8212;to partially close the CSRF security hole, and also just because it's good policy&#8212; as well as any other time you don't want the full command set to be accessible. (Perhaps an application has been granted access via `OAuth` to a subset of a user's available commands, for example.)
</div>
<div id="testing">

## Testing in Daimio
[use standard unit testing tools for libraries][use standard interface testing tools for interfaces]

DAML makes it easy to set up test suites! To test your new commands, send DAML through the processor and set an expected result, either in plain text or by using a regular expression. Tests that don't return the expected result are displayed along with any errors, warnings, or notices they've generated.

Using the test suites you build for your application's language, you can test your application's entire process cycle quickly and easily. For example, if you were building a blogging application the following might be part of your test suite:

*   Authenticate as a powerful user
*   Create a new blog user
*   Authenticate as the blog user
*   Post a few test blog posts
*   Fetch those test posts using a variety of techniques, including tags, title search, or date filter&#8212;whatever your application supports
*   Edit posts and refetch to confirm edits
*   Log out
*   Sign up as a new commenter
*   Post some comments
*   Fetch the posts and comments
*   Authenticate as the blog user
*   Destroy the comments
*   Destroy blog posts
*   Authenticate as the powerful user
*   Destroy the commenter
*   Destroy the blogger

Running this test simulates user behavior and is a huge time saver, compared to manually testing each time you make changes. It can also be much more comprehensive than the spot-checking developers usually do after making changes. Of course, this tests only your **application code**. It doesn't test your application's **interface**, which may contain typos or bad logic&#8212;but you'll feel secure knowing that your API is functioning as intended, and that it can use the standard tools for debugging any interfaces you're directly supporting.
</div>
<div id="trouble">

## Troubleshooting techniques

Here are some tips and suggestions on what to do if you're having trouble.

*   If the page is totally blank and has no source, check `log.txt`. A fatal error may have occurred.
*   If you've modified your models or added a new handler and things don't work as expected, issue the `{daimio freshen_commands}` command. This will import the new commands into the system.
*   After you authenticate, always remember to "refetch commands" using the link in the Daimio terminal.
*   If commands that should work don't work as expected, try them in the Daimio terminal. If you receive an "Invalid command" error, use the `{user whoami}` command to verify that you're logged in as the user you think you are.
*   Remember to escape JS and CSS (or anything else that contains curly braces). The easiest way is to use an escape block:

	`{begin verbatim | process escape}// js code or stuff{end verbatim}`

If Daimio seems particularly slow:

*   Make sure `{content autoload}` is turned off, as it reloads all the content each time Daimio boots up. (The preceding command tells you the state; use `{content autoload turn :off}` to turn it off.)
*   Make sure all fancy logging is turned off&#8212;some of the logging types generate **massive** amounts of data. 'Traces' in particular will bring your system to its knees. On the other hand, 'errors' is usually fine even for production sites.</div>
<div id="issues">

## Known issues

Here are some things to remember:

*   Quotes don't always nest nicely and can't be escaped (though quotes nested in {} or () or [] will be properly handled). If your unnested string doesn't include any spaces (such as selected="selected") you can use quotes around it, but this not recommended.
*   Unpaired braces, inside quotes, inside braces likely won't do what you expect.</div>
FUNDAMENTALS
<div id="daml_processor">

## The heart of Daimio: the DAML processor

The processor is responsible for: finding DAML commands; sorting out parameter values, shortcuts, pipes, and other fun; passing commands to the appropriate handler; and integrating the reply into the text being processed. During the bootstrapping process an array of permissible commands is created, which the processor uses to determine what gets sent to the handlers. 
</div><div id="architecture">

## Daimio's architecture
![Daimio Architecture Overview](http://www.daimio.org/images/daimio_architecture_overview.gif) </div><div id="gateways">

## Gateways

Gateways are the portal between Daimio and the outside world. They do four things: 

1.  Call includer.php, which sets up the required information for Daimio
2.  Collect input from somewhere: a web server, the shell command line, a file, etc.
3.  Send input to the Daimio processor
4.  Do something with the output

Usually, gateways will notify you when the processor generates any errors, warnings, and notices. They're courteous that way. It's how they roll. 

Daimio comes with five gateways that interface with the webserver and the shell in various ways: 

*   **homunculus.php** executes commands (passed through the 'commands' field) and returns the results as raw text.
*   **hermes.php** executes commands and returns the results along with any errors, warnings, or notices, in a JSON array.
*   **index.php** is the main website gateway. First, it executes commands (though it discards any output). Then, it finds a "Page" based on the current URL and displays it.
*   **run.php** executes commands from the shell.
*   **brun.php** is the interactive, shell-based Daimio processor.

You can also build your own custom interfaces to connect to email, SMS, serial ports, or to add another layer of access control. The [Daimio philosophy](#philosophy) discourages limiting how your application can be accessed, but recognizes that sometimes such things are necessary.
</div><div id="interfaces">

## Daimio interfaces

Interfaces simplify administrative tasks and provide custom web pages for interacting with particular concepts.

##### terminal.html

Using the terminal, you'll send commands directly to the [DAML processor](#daml_processor). The Daimio terminal lists only the options you have available to you to help you select the handler, method, or parameter you need. Tabs provide easy access to large arrays and content items. Go ahead, [try it out](http://www.daimio.org/terminal)!

##### content.html

The content interface helps you [manage content](#content). You can add and edit content and track changes between versions. Anything you do with content.html, can be done through the terminal, but sometimes it's more convenient to have a dedicated interface.

##### forms.html

The forms interface helps you [manage forms](#forms). You can add and edit forms and fields, and preview your changes for real-time feedback. Anything you do with forms.html can be done through the terminal, but sometimes it's more convenient to have a dedicated interface.
</div><div id="handlers">

## Handlers

Daimio comes with several prepackaged handlers, which are non-application specific collections of DAML commands. You can extend Daimio's language by adding new handlers. You can also extend it with models, which are identical to handlers except they live in a different directory, and they contain your application's logic.

*   The **Collection handler** has methods for handling arrays.
*   The **Daimio handler** controls low-level aspects of the Daimio install, including site settings, logging, command permissions, etc.
*   The **Logic handler** provides methods for basic logic operations (and, or, not...) and comparison operations.
*   The **Package handler** allows you to install third-party packages. The package handler also provides controls for your own package repository, if you've set one up.
*   The **Process handler** has core DAML processing methods, API-discovery methods, and command escaping methods.
*   The **String handler** gives methods for handling strings.*   The **Time handler** contains methods for handling dates and times. </div><div id="bootstrapping">

## Bootstrapping

The file includer.php is the bootstrap file for Daimio. When the gateway calls it, it does the following, in approximately this order:

1.  establishes the `__autoload` function
2.  fiddles with the error reporting settings and registers a custom shutdown function (this logs fatal errors whenever possible)
3.  imports ini files in the daimio/config/settings dir
4.  initializes the db connection
5.  sets up some constants and the global settings array
6.  includes any .php files in the daimio/config/activate_on/preload directory (handles session management, e.g.)
7.  builds the command array
8.  imports content, if needed
9.  builds the shortcut array
10.  sets up some user accessible globals including request arrays and the site array</div><div id="directory_structure">

## Daimio's directory structure

The following are directories in `daimio/`:

#### bin/

Command line utilities

*   brun.php: An interactive shell-based Daimio processor.
*   build.php: Installer script for Daimio.
*   deployer.php: Installer script for Daimio.
*   run.php: Executes commands from the shell.

#### config/

The config/ directory contains configuration files and special directories

##### config/activate_on

All .php files in these subdirectories are included upon activation of corresponding event.

*   freshen: Activated by the {daimio freshen_commands} command.
*   preload: Activated by includer.php during Daimio bootstrapping.

##### config/clean.sql

A pristine Daimio database used by build.php to create a new Daimio install.

##### config/custom/templates

##### config/default/templates

Templates stored in custom will override the default templates that come with Daimio.

##### config/htaccess.default

Default htaccess file used by build.php to create a new Daimio install.

##### config/input_filters.php

A pair of input filters for gateways to scrub viable commands.

##### config/settings

All .ini files in daimio/config/settings are parsed and importing into $GLOBALS['X']['SETTINGS'] as arrays. See the [Settings](#settings) section for more information.

##### config/shortcuts

Any .ini files in here are imported during bootstrapping as command shortcuts. The native.ini file contains default Daimio shortcuts.

#### core/

The core/ directory contains the libraries that are essential to Daimio:

*   DBLib: This is a thin wrapper for PHP's MySQL commands. It could be modified to use a different database.
*   ErrorLib: This library sets error, warnings, and notices, and writes to the log.txt file.
*   FileLib: This library makes files.
*   Handler: Here, you'll find convenience methods for handlers and models.
*   Metadata: This offers access to system metadata.
*   MixMaster: This gives you access to mixins.
*   Processor: Here's where the core DAML processing code lives.
*   QueryLib: This library offers convenience methods for making database queries.

#### handlers/

Daimio's handlers live here.

#### libs/

The libs/ directory contains the libraries that support handlers and models.

#### log.txt

Created by Daimio if you've asked it to log various events. Useful for tracking errors and debugging problems.

#### models/

Your application models live here.

#### mixins/

Subdirectories contain 'mixins' - bits of code that provide extra functionality to handlers and models.

#### temp/

Daimio stores temporary files here. Currently content, downloads, packages, and destroyed subdirectories are created as needed.

#### tests/

The tests/ directory contains a set of tests that can be performed on Daimio's basic functions and pre-packaged handlers.

#### tools/

Tools are dynamically generated handlers. The Math handler, for example, is made up of the php files in the daimio/tools/math directory.

### [Daimio Documentation](#)

*   [About](#)(#about)

*   [What is Daimio?](#)(#description)
*   [CUDL, DAML, and Daimio](#)(#philosophy)
*   [Getting it Done with Daimio](#)(#usecases)
*   [Get Started](#)(#getstarted)

*   [Installing Daimio](#)(#install)
*   [Build a Simple App](#)(#simpleapp)

*   [Build a Complex App](#)(#complexapp)
*   [DAML](#)(#daml)

*   [DAML](#)(#)

*   [DAML Primer](#)(#primer)
*   [Variables](#)(#variables)
*   [Params](#)(#params)
*   [Pipes](#)(#pipes)
*   [Blocks](#)(#blocks)
*   [Shortcuts](#)(#shortcuts)
*   [The where param](#)(#where)
*   [Notes](#)(#notes)
*   [BNF](#)(#bnf)
*   [Concepts](#)(#concepts)

*   [General](#)(#concepts)
*   [Users](#)(#users)
*   [Pages](#)(#pages)
*   [Content](#)(#content)
*   [Forms](#)(#forms)
*   [Lenses](#)(#lenses)
*   [Packages](#)(#packages)
*   [Tools](#)(#tools)
*   [Specifics](#)(#specifics)

*   [Settings](#)(#settings)
*   [Command Permissions](#)(#command_permissions)
*   [Magic Words](#)(#magic_words)
*   [Security in Daimio](#)(#security)
*   [Testing in Daimio](#)(#testing)
*   [Troubleshooting](#)(#trouble)
*   [Known Issues](#)(#issues)
*   [Fundamentals](#)(#fundamentals)

*   [DAML Processor](#)(#daml_processor)
*   [Architecture](#)(#architecture)
*   [Gateways](#)(#gateways)
*   [Interfaces](#)(#interfaces)
*   [Handlers](#)(#handlers)
*   [Bootstrapping](#)(#bootstrapping)
*   [Directory Structure](#)(#directory_structure)
*   [Terminal trainer](#)(http://www.daimio.org/terminal)
