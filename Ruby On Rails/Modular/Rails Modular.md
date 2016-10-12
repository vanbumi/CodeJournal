# Modular	Rails

## Complete	Guide To Modular Applications

by Thibault	Denizet

### Introduction

Building	modular	Rails	application	means	that	you will	build	a	set	of	reusable	modules,	a	bit	like	libraries,	some	with	very	specific functionalities. 	Then	you	will	just	assemble	them,	just	like	bricks,	and	build	your application.

Building	modular	applications	is	hard. 	You	won’t	be	building	your	web	application	like
everyone	else	and	finding	help	is	not	easy. 	There’s	not	much	documentation	either,	but
with	this	book	you	will	be	able	to	learn	a	lot. 	I	will	also	help	you	if	you	still	have questions	after	reading	it!

I	think	every	Ruby	on	Rails	developer	should	read	this	book	or	at	least	give	it	a	try. It’s not	super	long	but	comes	with	a	lot	of	‘underground’	information	about	engines. 	If	you’re about	to	write	a	modular	application,	then	you	should	definitely	read	it. The	goal	is	to	teach	you	how	to	build	your	own	modules	and	at	the	end	of	the	road,	create complete	modular	applications.

This	book	will	probably	be	more	useful	to	web	agencies	and	freelancers,	or	anyone	who
ends	up	building	the	same	thing	over	and	over	again.

### The	Modular	Way

Let’s	start	by	defining	the	concept. Maybe	you	don’t	know	what	modularity	means	or	what	is	a	modular	architecture. 	Or maybe	you	have	a	vague	idea	of	what	it	represents,	but	no	concrete	example	in	mind. 
That’s	okay,	I’m	here	to	help.

This	first	chapter	will	take	you	from	knowing	nothing	about	modularity	to	having	a	clear
idea	of	what	it	is	and	how	it	can	serve	you.

#### 2.1	 What	is	modularity

I	believe	that	to	understand	something	you	need	to	understand	its	origin. 	Module	find	its source	in	Latin	as	‘modulus’	meaning	‘a	small	measure’. 	By	extension,	modular	means
‘composed	of	interchangeable	units’. 	The	antonym	of	modular	is	monolithic	which
originally	was	a	‘column	consisting	of	a	single	large	block	of	stone’. 	We	will	see	both	of these	terms	throughout	the	book	so	it	is	important	that	you	remember	them.

As	you’ve	probably	already	understood	it,	something	modular	is	built	from	a	set	of
smaller,	interchangeable	pieces. 	On	the	other	side,	we	have	monolithic	things	which	are
only	composed	of	one	element.

For	example,	we	could	say	a	computer	is	a	modular	object. 	It	is	composed	of	various
pieces,	such	as	the	CPU,	GPU,	RAM	and	so	on,	that	all	fit	together	to	deliver	us
indispensable	platforms	like	Reddit	and	Facebook. 	Most	components	in	a	computer	can
be	changed,	one	at	a	time,	without	impacting	the	normal	function,	except	by	improving	or
reducing	the	computing	capacities. 	When	choosing	parts	for	a	computer,	the	main	thing	to
pay	attention	to	is	that	the	parts	work	together. 	They	need	to	be	able	to	talk	to	each	other through	common	interfaces.

#### 2.2	 Modularity	in	programming

Let’s	focus	on	programming	now	since	that’s	why	you’re	here. What’s	modularity	in programming?

> Modular	programming	is	a	software	design	technique	that	emphasizes	separating	the
functionality	of	a	program	into	independent,	interchangeable	modules,	such	that	each
contains	everything	necessary	to	execute	only	one	aspect	of	the	desired	functionality.
Conceptually,	modules	represent	a	separation	of	concerns,	and	improve
maintainability	by	enforcing	logical	boundaries	between	components. 	—	Wikipedia

So	modularity	is	all	about	isolating	the	functionalities	of	your	application	into	independent and	interchangeable	components.

But	what	does	that	means	exactly? 	I	think	the	best	way	to	understand	this	is	with	an
example,	and	what	better	example	than	the	Ruby	on	Rails	framework	itself! 	Ruby	on
Rails	used	to	be	monolithic	but	that	all	changed	when	Rails	3	was	published,	after	merging
with	Merb. 	Indeed,	Rails	became	modular.

Rails	is	now	composed	of	a	set	of	modules	:

+ Active	Record
+ Active	Model
+ Active	Support
+ Action	View
+ Action	Pack
+ Action	Mailer
+ And	more	recently:	 Active	Job

You	will	usually	use	all	of	them	in	a	standard	Ruby	on	Rails	application	but	you	could
also	build	a	Ruby	program	with	just	Active	Record. That	would	allow	you	to	easily	build
a	Ruby	application	that	can	talk	with	all	kinds	of	databases. As	you	can	guess	from	the
names,	each	module	in	the	Rails	framework	encapsulates	a	specific	feature. Active
Record	contains	everything	you	need	to	map	Ruby	classes	to	a	database	tables.
Rails	modules	are	obviously	highly	reusable	since	they	lay	the	groundwork	for	any	web application	you’d	like	to	build. 	What	we	will	see	in	this	book	is	a	way	to	build	Ruby	on Rails	applications	on	top	of	these	modules	by	using	the	same	principles:	Re-usability and functionality	encapsulation.

### 2.3	 Advantages	and	Drawbacks

As	we	already	said,	modularity	comes	with	2	major	advantages,	the	re-usability	of	the
components	and	the	encapsulation	of	features	into	independent	chunks	of	code	called
modules. 	There	are	actually	more	advantages!

#### 2.3.1	Advantages

The	fact	that	each	module	is	independent	(but	a	module	can	be	built	on	top	of	another	one) makes	the	coordination	and	cooperation	of	different	teams	much	easier. If	two	teams	are building	2	completely	different	features	on	top	of	a	shared	 Core ,	even	without
communication,	there	won’t	be	a	lot	of	conflicts. 	Why? 	Simply	because	they	are	working
on	the	equivalent	of	2	distinct	projects.

Let’s	say	now	that	you’re	working	for	a	company	building	complex	web	applications.
These	applications	will	always	require	users,	authentication	and	authorization. 	So	why	not build	it	one	time	and	re-use	it	everywhere? 	We	can	build	a	 Core 	module	which	will	handle the	users’	CRUD,	the	way	they	can	login	and	what	they	can	do. 	Once	it’s	done,	you	can simply	reuse	it	in	every	future	web	application	produced	by	your	company,	simply	by adapting	the	style.

Finally,	I’d	like	to	talk	about	tests. 	Automated	testing	is	an	important	part	of	software creation,	be	it	for	web,	desktop	or	mobile. 	Since	features	are	encapsulated,	you	can	easily write	tests	that	run	in	isolation. 	You	can	also	add	tests	at	the	top	level	of	your	application to	ensure	that	everything	is	working	well	together. 	It’s	just	like	the	way	libraries	are	tested to	be	sure	that	what	they	provide	is	working. 	Then,	you	test	the	code	where	you	use	those libraries	to	be	sure	you	are	getting	the	behavior	you	want. Just	like	everything,	modularity	comes	with	some	drawbacks	too.

#### 2.3.2 Drawbacks

One	of	the	main	drawbacks	of	modular	applications	is	that	it	can	get	quite	time-
consuming. 	Indeed,	you	are	not	dealing	with	one	application	and	one	repository. 	Instead,
you	will	work	with	a	set	of	repositories,	each	containing	the	source	code	for	a	specificfunctionality. 	Depending	on	the	technology	used,	you	will	have	to	update	the	module,	test it,	push	the	source	code,	then	link	it	to	the	main	application,	re-test	it	and	then	push	it.
Now,	imagine	if	you	have	3,	4	or	more	modules	to	update.

That’s	a	longer	process	than	simply	making	the	change	and	pushing	it	live	but	it’s	totally worth	it! 	Finally,	since	we	have	a	lot	of	different	mini-projects,	we	need	to	keep	track	of their	version. 	What	is	currently	used	in	production,	in	staging,	which	versions	are	ready for	testing,	etc. 	The	best	way	I’ve	found	to	deal	with	that	is	simply	a	Google	Doc Spreadsheet. 	It	allows	you	to	see	what	is	where	and	is	easy	enough	to	update.

Now	you	know	that	modularity	comes	with	some	stuff	that	you	will	need	to	deal	with	if
you	want	to	use	it	in	the	best	way. 	Before	we	see	more	about	modular	web	applications
built	with	Ruby	on	Rails,	I	want	to	tell	you	about	a	few	case	scenarios	where	you	might
want	to	build	a	modular	application	and	when	you	should	simply	avoid	it.

### 2.4	 When	should	you	build	modular web	applications?

A	good	example	of	when	to	create	modular	applications	is	the	one	I	talked	about	above. 	If you	are	a	web	agency,	or	a	freelancer,	and	you’d	like	to	reuse	some	code	between	clients, then	go	for	modular	applications. 	As	a	web	agency,	you	probably	build	a	lot	of	web applications,	a	lot	have	commons	features. 	A	way	for	people	to	create	accounts,	login,
access	some	parts	of	the	application	and	so	on. 	You	will	also	often	want	an	Admin	panel to	administrate	the	application. 	Then	you’ll	probably	have	some	specific	code	to	add	for each	client,	depending	on	their	needs. 	But	still,	you	just	saved	a	lot	of	time	reusing	an existing	module. Imagine	all	the	time	you	can	save	through	10	or	100	projects!

Another	good	case	scenario	for	modularity	is	a	startup	creating	some	kind	of	generic
application	with	a	layer	of	configuration. 	That	might	sounds	abstract	so	let	me	give	you an	example	of	such	an	application. 	Take	the	Stack	Exchange	network. 	If	you’re	looking to	build	something	like	that,	then	modularity	is	your	best	friend. 	You	would	probably have	a	set	of	modules	present	in	every	application	in	your	network. 	Then,	you’d	have some	specific	modules	added	on	top	of	them	to	customize	the	application	to	a	specific
niche. 	Maybe	for	one	application,	you	want	a	rating	system,	for	another	one	you	want	to
have	commentable	questions	and	answers. 	All	that	can	be	achieved	by	building	modular
applications.

You	may	have	heard	about	Spree	Commerce. 	Spree	is	a	complete	open	source	e-commerce	solution	built	with	Ruby	on	Rails. 	Spree	is	completely	modular	and	is composed	of	6	modules. 	Spree	was	one	of	my	main	example	when	I	first	started	to	create modular	applications	and	I’d	like	to	thank	them	for	the	great	work	they	did. 	If	you’re
looking	for	an	ecommerce	solution,	take	a	look	at	what	they	offer,	it’s	very	nice!

### 2.5	 There’s	no	need	to	go	All-In

With	this	book,	you	will	learn	**how	to	build	modular	web	applications	with	Ruby	on	Rails**. I	will	present	you	fully	modular	application	but	you	don’t	have	to	go	to	that	extend	if	you don’t	want. Hybrid	applications	are	also	great. 	The	idea	is	to	use	a	few	modules	and	build a	standard	Rails	application	with	them. 	I	will	talk	more	about	this	approach	in	the	next chapter,	after	we’ve	talked	about	architecture.

## Chapter	3 Modular	Rails:	The	Basics

In	this	chapter	we’ll	first	see	what	makes	Ruby	on	Rails	such	a	good	solution	to	build
modular	applications. We	will	learn	about	Rails	engines,	how	they	work	and	how	we	can
use	them	as	modules. Then	we’ll	study	different	modular	architectures	before	picking	one
and	sticking	with	it	for	the	entire	book. Finally,	I	will	talk	about	the	modular	web
application	that	we	will	create	in	the	next	chapters.

### 3.1	 Ruby	on	Rails	Magic

In	this	first	part,	I	want	to	share	with	you	a	few	of	the	things	that	makes	it	easy	to	create modular	application	with	Ruby	on	Rails.

#### 3.1.1 Interpreted	Language

Since	Ruby	is	an	interpreted	programming	language,	there	are	a	few	things	that	we	can	do
super	easily. For	example,	re-opening	classes	and	extending	them	to	add	more	logic.

Before	we	continue,	I	want	to	show	you	how	important	this	is,	so	here	is	a	simple
example. Let’s	say	we	have	two	modules	(not	the	ruby	ones),	X	and	Y.	We	define	a	User
model	in	X	and	we	want	to	extend	that	model	in	Y.	All	we	need	to	do	is	create	a	decorator for	the	 User model	inside	Y	and	use	something	like	class_eval to	add	some	methods	or associations	to	it. By	doing	that	inside	the	Y	module,	the	X	module	can	stay	independent and	does	not	care	about	Y.	X	can	run	on	its	own	but	will	have	more	features	if	we	add	Y. Obviously,	since	Y	is	extending	X,	it	will	comes	with	a	dependency	on	X.
This	is	one	of	the	basic	requirements	for	modularity	and	this	is	all	possible	thanks	to	Ruby.

#### 3.1.2	Bundler

Bundler	is	a	great	dependency	management	tool. A	quick	 **bundle	install** 	will	download	all	the	dependencies	required	by	your	application and	your	gems	dependencies. 	A	good	dependency	resolver	is	required	to	create	modular applications	since	we	will	create	our	modules	as	libraries. 	We	need	to	be	able	to	easily	get them	and	their dependencies.

In	the	kind	of	modular	applications	I	am	going	to	show	you,	the	parent	application
(containing	the	modules)	is	mostly	empty. 	It’s	just	a	shell	containing	a	set	of	engines
which	contains	all	the	logic. 	As	we	will	see	in	a	minute,	we	will	be	using	Rails	engines	as modules. The	good	news	is	that	we	can	package	those	as	gems	and	use	Bundler	to	handle them	for	us. That’s	why	Bundler	is	a	great	companion	for	anyone	looking	to	create	a modular	application.

Once	your	engines	are	packaged	as	gems	(we’ll	see	that	in	the	last	chapter),	getting	your modular	application	together	will	be	as	simple	as	requiring	your	modules	in	the	 Gemfile .

	gem	'module1',	'1.0.0'
	gem	'module2',	'1.0.0'

#### 3.1.3	Deface

Deface	is	a	neat	**little	gem**	that	will	allow	us	to	extend	Rails	views. 	I	don’t	want	to	say	too much	yet,	but	you	will	learn	very	soon	how	it	works	and	how	to	use	it. 	This	is	one	of	the **pillars	of	modularity**.

#### 3.1.4	Rails	engines

We	will	be	using	Rails	engines	as	the	bricks	of	our	application. 	Let’s	see	what	are	they
and	how	to	use	them.

### 3.2	 Rails	Engines

With	Rails	3,	a	new	feature	came	out. 	Rails	Engines. 	They	are	just	like	regular	Ruby	on
Rails	applications	but	can’t	actually	live	on	their	own,	they	need	a	regular	Rails
application	to	run	from. 	Engines	and	regular	Rails	applications	have	actually	a	lot	in
common. 	First	of	all,	they	share	the	same	structure.

You	will	find	the	following	elements	in	both:

* Models
* Controllers
* Views
* Assets
* Tests

The	nice	thing	about	engines	is	that	you	can	integrate	them	to	any	Ruby	on	Rails
application. 	Once	an	engine	is	ready	to	be	deployed,	it	can	be	encapsulated	as	a	gem	and pushed	to	RubyGems	if	you	want	to	share	it	with	the	community. 	You	can	also	keep	it private	and	we	will	see	how	later.

#### 3.2.1	Quick	overview	of	Rails	engines

Engines	are	basically	miniature	Ruby	on	Rails	applications	that	can	provide	new
functionalities	to	the	parent	application	including	them. 	The	class	defining	a	Ruby	on
Rails	application	is	**Rails::Application** which	inherits	a	lot	of	its	behavior	from
**Rails::Engine** which	defines	an	engine. A	Ruby	on	Rails	application	is	just	a	bit	more
than	a	Rails	engine,	coming	with	the	logic	required	to	run	on	its	own.

#### 3.2.2	Creating	an	engine

Engines	are	also	closely	related	to	plugins. 	Plugins	are	not	really	used	anymore	since
Rails	3.0	but	the	command	to	generate	an	engine	is	actually	the	same	used	to	generate	a plugin. We	will	see	how	to	generate	an	engine	in	the	next	chapter	when	we	start	working on	our	modular	application.

#### 3.2.3	Mounting	an	engine

An	engine	cannot	live	on	its	own,	before	you	can	use	it	you	need	to	integrate	it	inside	a Rails	application. There	are	actually	two	ways	to	do	this	but	the	one	that	interests	us	is this	one:

	Rails.application.routes.draw	do
		mount	Samurails::Core::Engine,	at:	'/',	as:	'samurails'
	end

In	this	example,	we	mounted	the	Core	engine	at	the	root	of	a	Rails	application. If	there	is nothing	inside	your	parent	application,	that’s	the	easiest	way.
However,	if	your	Rails	application	has	some	content	you	probably	want	to	do	the
following:

	Rails.application.routes.draw	do
		mount	Samurails::Forum::Engine,	at:	'/forum',	as:	'forum'
	end

Now	the	 Forum 	engine	can	be	accessed	by	going	to	 /forum 	and	the	root	can	be	used	by the parent	application.

#### 3.2.4	Namespacing

Engines	can	and	should	be	namespaced. That	means	that	**two	models	with	the	same	name**,
one	in	an	engine	and	one	in	the	host	application,	won’t	clash. When	generating	an engine, everything	is	automatically	namespaced:	tables,	models,	controllers. If	you	generate	an engine	named	**Core** and	a	**User** 	model,	the	generated	table	will	be	**core_users** and	your model	will	be	**Core::User**.

Throughout	this	book,	I	recommend	going	one	step	further	and	adding	another	level	of
namespacing. If	you	plan	to	create	a	lot	of	engines	and	want	to	avoid	any	future	conflict, you	can	just	namespace	all	your	engines	with	your	project	or	with	your	company	name.
Instead	of	having:

	module	ModuleName
			class	ModelName	<	ActiveRecord::Base
			end
	end

You	would	have:

	module	GlobalModuleName
			module	ModuleName
					Class	ModelName	<	Activerecord::Base
					end
			end
	end

With	this	system,	you	can	keep	your	engines	organized	under	a	common	namespace. You
can	rest	assured	that	you	won’t	get	any	problems	when	adding	external	engines	to	your
application.

A	special	thanks	to	James	Adam,	Piotr	Sarnacki,	the	Rails	Core	Team,	and	a	number
of	other	people	for	their	awesome	work	on	the	Rails	Engines!

#### 3.2.5	Extending	an	engine

We	already	talked	a	bit	about	extending	an	engine	and	we	will	get	into	the	coding	part	in the	fourth	chapter. There	are	basically	three	things	to	extend	inside	a	Ruby	on	Rails application.

+ Models

Can	be	extended	using	decorator	and	class_eval or	other	similar	method.

+ Views

Can	be	extended	with	the	 Deface 	gem.

+ Controllers

Can	be	extended	just	like	models:	decorator	and	**class_eval**.
There	is	actually	a	fourth	entity	that	we	will	have	to	extend	and	we	will	see	how	later.

#### 3.2.6	Engines	in	the	wild!

Even	if	you’ve	just	discovered	Rails	Engines,	you’ve	probably	been	using	them	for	a
while. 	One	of	the	most	famous	**authentication	gems**	is	actually	an	engine. Of	course,	I’m	talking	about	Devise! Basically,	any	gem	that	will	provide	you	with	some
Rails-related	component	such	as	migrations,	controllers,	views	or	models	is	not	just	a
gem. 	**It’s	actually	an	engine	packaged	as	a	gem**.

A	few	examples	of	famous	engines:

* Forem
Forem	is	an	engine	for	Rails	that	aims	to	be	the	best	little	forum	system	ever. The
end	goal	is	to	have	an	engine	that	can	be	dropped	into	an	application	that	provides	the basic	functionality	of	forums,	topics	and	posts.

* Devise
Devise	is	a	Rack	Based	engine	that	provides	a	complete	authentication	system	for
any	Ruby	on	Rails	application.

* Spree	Ecommerce
Spree	is	a	complete	open	source	e-commerce	solution	built	with	Ruby	on	Rails	as	set
of	engines. 	Spree	actually	consists	of	several	different	gems,	each	of	which	are
maintained	in	a	single	repository	and	documented	in	a	single	set	of	online
documentation.

### 3.3	 Modular	Architectures

Creating	a	modular	application	is	quite	different	from	creating	a	regular	monolithic
application. In	this	section,	I	want	to	go	over	the	different	architectures	that	you	can	use	to build	a	modular	application	with	Ruby	on	Rails.

#### 3.3.1	What	is	a	monolithic	application?

Regular	Ruby	on	Rails	applications	are	monolithic	applications. 	They	are	self-contained
applications	that	will	do	what	you	programmed	them	for. 	Note	that	this	is	not	a	bad	thing.
Ruby	on	Rails	is	known	for	its	fast	prototyping	that	will	let	you	create	an	MVP	(Minimum
Viable	Product)	easily.

> In	software	engineering,	a	monolithic	application	describes	a	software	application
which	is	designed	without	modularity. -Wikipedia

So	that’s	exactly	what	we	are	trying	to	avoid	by	building	modular	applications.
Monolithic	have	their	place,	just	not	in	this	book!

Note	that	I	don’t	recommend	creating	only	modular	applications. I	still	create	and
maintain	monolithic	applications	because	I	don’t	always	need	the	modular	side. Regular
applications	are	also	easier	to	work	with. It’s	all	about	picking	the	right	tool	for	the	right job.

#### 3.3.2	What’s	a	modular	application?

Now,	let’s	talk	about	modularity.

There	is	not	just	one	way	to	organize	your	code. Here,	I’ll	go	over	three	ways	that	I’ve personally	played	with. I’m	sure	there	are	more	and	if	you	have	any	suggestions,		would be	happy	to	talk	about	them	with	you.

As	we	said	earlier,	we	are	going	to	cut	our	monolithic	application	in	small	modules. 	But what	should	we	put	in	these	modules? 	Since	we	will	be	using	Rails	engines,	we	can	put models,	controllers,	views,	migrations,	tests	and	so	on. Basically	everything	that	you	will find	inside	a	Ruby	on	Rails	application.

So	how	do	we	organize	all	that? 	Should	one	module	have	all	the	models? 	Or	should	one module	have	a	model-view-controller	silo?

#### 3.3.3	 Understand	the	difference	between	Core	and	Feature engines

In	the	following	section	and	in	the	future	chapters,	I	will	sometimes	talk	about	 **Core
engines**	and	 **Feature 	engine**. When	building	a	modular	application,	you	need	at	least	one **Core 	engine**. This	engine	will	contains	things	like	the	configuration	and	the	basic functionalities. **Feature engines**	extend	the	 Core(s) and	provide	specific	features.

The	best	way	to	understand	the	difference	is	by	reading	the	following	chapters	where	we
will	build	a	**Core engine**	followed	by	two	**Features engines**.

#### 3.3.4	Approach	1	–	Three	Tier	Modules

You	should	be	familiar	with	the	three	tier	architecture. 	If	not,	here’s	a	definition.

> Three-tier	architecture	is	a	client–server	architecture	in	which	the	user	interface
(presentation),	functional	process	logic	(“business	rules”),	computer	data	storage	and
data	access	are	developed	and	maintained	as	independent	modules,	most	often	on
separate	platforms.	—	Wikipedia

Since	the	views	are	so	tied	to	the	rest	of	the	application	in	Ruby	on	Rails,	a	good	way	to follow	this	pattern	is	*by	creating	an	API	and	a	Javascript	frontend	application*.
The	idea	is	to	separate	the	application	into	the	following	modules/engines:

+ Engine	1	-	Data	Engine
This	engine	contains	the	data	layer:	models,	migrations	and	models	specs.

+ Engine	2	-	API
This	engine	contains	an	API	allowing	external	applications	to	connect	to	it	through
RESTful	URLs. This	engine	depends	on	the	Engine	1.

+ Engine	3	-	Javascript	applicationThe	Javascript	application	should	be	built	with	the	help	of	a	frontend	Javascript framework	such	as	Angular.js. The	code	can	be	contained	inside	a	Rails	engine	and included	inside	the	parent	application. 	Another	way,	which	I	personally	prefer,	is	to create	the	Javascript	application	as	a	standalone	by	using	tools	like	Yo,	Grunt	and Bower.

Here	is	a	diagram	representing	this	architecture. 	Figure	3.1

![Three	Tier	Modules.](http://res.cloudinary.com/medio/image/upload/v1471573555/engineArchitecture_oproul.png)

Figure	3.1:	Three	Tier	Modules.

This	architecture	can	be	optimized	based	on	your	needs. For	example,	you	could	put	the
Engine	2′s	logic	directly	inside	the	parent	application. 	You	could	also	separate	the	Engine 1	into	smaller	engines. Keep	reading	to	learn	more	about	other	architectures	to	find	the perfect	one	for	your	needs!

#### 3.3.5	Approach	2	–	Hybrid	Component	Based

This	approach	is	the	first	one	I	tried	when	I	started	to	work	on	modular	applications. 	With time,	I	realized	that	it’s	not	the	best	solution. The	idea	is	to	have	a	couple	of	engines representing	the	minimal	logic	of	your	application. On	this	set	of	engine,	you	can	later add	new	features	encapsulated	inside	new	engines.

With	this	architecture,	the	‘core’	of	your	application	will	be	composed	of	at	least	two engines:

+ Core	Engine	1:	Models	&	Migrations	engine
+ Core	Engine	2:	Controllers	&	Views	engine

Now,	you	can	start	adding	more	modules	which	will	depends	on	this	‘core’.

+ Feature	1	engine	(models	+	controllers	+	views)
+ Feature	2	engine	(models	+	controllers	+	views)
+ Feature	3	engine	(models	+	controllers	+	views)

That	might	look	abstract	so	to	give	you	something	more	concrete	here’s	how	your	 Gemfile might	look	like	with	this	architecture:

	gem	'core_data',	'1.0'
	gem	'core_view',	'1.0'
	gem	'feature_1',	'1.0'
	gem	'feature_2',	'1.0'
	gem	'feature_3',	'1.0'

![hybrid component base](http://res.cloudinary.com/medio/image/upload/v1471574292/hybrid_tfw6je.png)

Figure	3.2:	 Hybrid	Component	Based.

#### 3.3.6 Approach	3	–	Full	Component	Based

The	Full	Component	Based	architecture	is	a	refined	version	of	the	previous	example. In
this	one,	we	remove	the	‘core’	engines	and	the	separation	of	the	models,	views	and
controllers	into	different	engines. Instead,	each	engine	encapsulates	all	the	components required	to	make	it	work. That	means	each	engine	is	a	micro	Rails	application	containing
models,	controllers,	views	and	specs.

+ Core	(models	+	controllers	+	views)
+ Feature	1	(models	+	controllers	+	views)
+ Feature	2	(models	+	controllers	+	views)

![Full	Component	Based](http://res.cloudinary.com/medio/image/upload/v1471574640/full_component_base_s99wfs.png)

Figure	3.3: Full	Component	Based.

In	this	case,	the	 Core could	be	run	alone	inside	the	containing	application	but	would	offer only	limited	features. For	example,	we	could	simply	include	the	minimum	code	for	users to	be	able	to	login	and	access	an	empty	dashboard. 	We	can	then	add	competently
encapsulated	features	to	the	core	to	improve	our	application.

This	is	a	very	good	solution	to	build	modular	applications	with	Ruby	on	Rails	which	is
why	we	will	pick	this	architecture	to	build	our	modular	application. By	using	layers	like
this,	we	can	easily	and	completely	encapsulate	one	specific	feature	inside	one	engine.
Each	engine	can	also	be	independant	from	the	others,	except	for	their	dependency	on	the
Core.

### 3.4	 Build	a	modular	CRM

The	best	way	to	learn	something	is	by	doing	it.
As	French	people	like	to	say:

It	is	by	forging	that	one	becomes	a	blacksmith. 	—	French	people

So	we’re	going	to	build	a	little	modular	application. 	I	want	to	show	you	how	to	create
your	own	modular	application	by	using	the	various	techniques	I	learned	the	hard	way.

#### 3.4.1	The	Idea

We’re	going	to	make	a	CRM,	or	**Customer	Relationship	Management**,	and	we’re	going	to
call	it	**SamuraiCRM**	because	that’s	an	amazing	name. CRM	are	usually	used	by
salespeople	in	companies	to	keep	track	of	their	contacts,	meetings,	calls	and	so	on. So
what	should	we	put	inside	SamuraiCRM?

#### 3.4.2	SamuraiCRM

Our	CRM	will	be	composed	of	the	following:

+ The	Parent	Application
This	will	be	an	almost	empty	Ruby	on	Rails	application	that	will	contain	all	the
engines. 	This	will	be	the	container	for	all	the	engines.

+ The	 Core 	Module
This	engine	will	put	the	foundations	of	our	CRM	in	place. 	We	will	include
everything	related	to	users:	login,	authentication,	authorization,	administration. We
will	also	define	the	style	for	the	application	and	create	the	dashboards	that	will	be
extended	by	the	modules	later.

+ The	 Contacts 	Module
A	basic	CRUD	for	contacts	that	will	extend	the	 Core 	module.

+ The	 Tasks 	module
A	basic	CRUD	for	tasks	that	will	extend	the	 Core 	and	 Contacts 	modules.

Let’s	code!

## Chapter	4 Building	SamuraiCRM	:	the	core

That’s	it,	you’re	about	to	create	your	first	module. Feeling	excited? You	should!

### 4.1	 What’s	the	core	module	?

Before	we	dive	in	the	code,	let’s	define	what	is	the	Core module. 	**This	module	sets	the foundations	of	our	application**. The	other	engines	will	be	built	on	top	of	it	by	extending	its very	basic	functionalities.

**The	 Core 	will	include**:

+ The	dashboard
The	dashboard	is	the	first	thing	a	user	sees	after	logging	in. In	the	 Core ,	it	will	be
pretty	much	a	blank	screen. But	in	the	next	chapters	we	will	add	hooks	to	it	to	allow
other	modules	to	extend	it. This	way,	we	will	be	able	to	fill	the	dashboard	a	little	bit in	each	module.

+ The	admin	panel
The	admin	panel	is	an	important	part	of	any	CRM	(Customer	Relationship Management). We	will build	**a	basic	admin	panel**	in	the	Core which	will	allow	us	to manage	 Users. We	will	make	it	extendable	in	the	future	so	other	modules	can	also 
integrate	themselves	in	this	panel.

+ Authentication
Since	we	are	lazy	developers,	we	will	be	using	the	great	Devise	gem	to	handle
Authentication. Devise	being	an	engine,	we	will	meet	a	few	problems	while	using	it
inside	another	engine. Do	not	worry,	I	will	show	you	how	to	make	everything	work
together!

+ Authorization
Authorization	will	be	achieved	by	using	CanCan. In	future	chapters,	we	will	see	how
to	extend	CanCan	abilities	in	other	modules.

+ Specs
The	Core module	will	come	with	a	set	of	tests	to	ensure	that	it’s	working	correctly. 	I
will	keep	the	code	and	tests	simple	so	you	can	focus	your	attention	on	the	modular
side. We’ll	be	using	Rspec	and	Factory	Girl.

+ Modularity
Modularity	principles	will	be	explained	while	building	the	application	and	summed up	at	the	end	of	the	chapter.

Now,	it’s	time	to	start	building	it!

### 4.2	 Build	it

The	Build	it	section	is	where	we	actually	play	with	some	code. You	will	find	one	in	each of	the	following	chapters.

#### 4.2.1	Part	1:	Setup	the	Rails	app

Before	we	actually	work	on	the	 Core engine,	we	need	a	parent	application. 	Let’s	generate one	and	create	our	first	engine!

Note	that	this	book	was	written	with	Ruby	version	2.2	and	Rails	version	4.2.

##### Step	1:	Generate	the	app

Fire	up	a	terminal	and	navigate	to	your	workspace	before	running	the	following:

	rails	new	SamuraiCRM	--skip-test-unit

##### Step	2:	Go	inside	your	new	application	folder	and	generate	a	mountable	engine

	cd	SamuraiCRM	&&	rails	plugin	new	core	--mountable	--skip-test-unit	

##### Step	3:	Create	an	‘engines’	folder	and	move	the	Core	inside

	mkdir	engines	&&	mv	core	engines/ 

All	our	engines	will	go	inside	this	folder.

##### Step	4:	Add	one	more	namespace	level

By	default,	everything	inside	an	engine	will	be	namespaced	based	on	the	name	you	gave
it. Since	we	are	building	a	modular	application	and	a	set	of	engines	that	are	supposed	to
work	together,	**I	recommend	adding	one	more	namespace**. For	this	application,	I	will	use the	namespace	Samurai. It	will	be	the	global	namespace	containing	all	the	engines. For	now,	let’s	focus	on	the	lib	folder	located	at	 SamuraiCRM/engines/core/lib. In	this
folder,	we’ll	find	the	heart	of	our	engine	but	first,	we	have	to	do	a	bit	of	reorganization.

Rearrange	the	lib	folder	until	you	have	the	following	structure	or	run	the	command	below.

	SamuraiCRM/engines/core/
		lib/
				samurai_core.rb
				samurai/
						core.rb	
						core/
								engine.rb
								version.rb

Here’s	a	command	to	achieve	this	result. 

Run	it	from	 SamuraiCRM/engines/core/ .

	cd	lib	&&	mkdir	samurai	&&	mv	core	core.rb	samurai/	&&	touch	samurai_core.rb

Let’s	open	these	files	and	fill	them	a	bit.

##### Step	5:	samurai_core.rb	and	core.rb

This	file	is	a	very	simple	file	that	is	going	to	make	the	link	between	our	engine	and	the parent	application. 	How? 	By	requiring	the	right	files!

	#	SamuraiCRM/engines/core/lib/samurai_core.rb
	require	"samurai/core"
	require	"samurai/core/engine"

And	this	one	is	where	we	load	our	modules	for	the	first	time,	before	the	engine	gets
loaded.

	#	SamuraiCRM/engines/core/lib/samurai/core.rb
	module	Samurai
		module	Core
		end
	end

##### Step	6:	Define	a	version

Since	the	Core module	will	be	released	as	a	gem,	we	need	to	give	it	a	proper	version	and add	our	top-level	namespace	 Samurai.

	#	SamuraiCRM/engines/core/lib/samurai/core/version.rb
	module	Samurai
		module	Core
			VERSION	=	"0.0.1"
		end
	end

##### Step	7:	The	Engine	file

Each	Ruby	on	Rails	engine	comes	with	a	file	named	 engine.rb. This	is	really	the	heart	of the	engine. We	need	to	add	our	new	namespace	to	it. Note	that	we	are	also	removing
Core 	from	 isolate_namespace. We	won’t	namespace	our	models	and	controllers	with
Core 	in	the	 Core 	module. You	will	understand	why	in	the	next	chapter,	but	for	now,	you should	know	that	it	makes	extending	the	 Core 	much	easier.

	#	SamuraiCRM/engines/core/lib/samurai/core/engine.rb
	module	Samurai
			module	Core
					class	Engine	<	::Rails::Engine
							isolate_namespace	Samurai
					end
			end
	end

What	is	**isolate_namespace** ? The	isolate_namespace method	is	here	**to	mark	a	clear
separation	between	the	engine	controllers,	models	and	routes	and	the	parent	application’s content**. Without	it,	we	might	have	unwanted	conflicts	or	overrides.

##### Step	8:	Gemspec

Next,	we	need	to	give	some	proper	details	about	our	engine	inside	the	 gemspec 	file. 	Head over	to 	SamuraiCRM/engines/core/core.gemspec . 	First,	you	will	want	to	rename	the
file	to	 samurai_core.gemspec 	to	match	the	namespaces	we	are	now	using. 	Here’s	the	file
with	the	changes.

