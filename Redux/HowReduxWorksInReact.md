# How Redux Works In React App



Let's go over redux and how the technology can help our ReACT applications manage this state as they

become really large let's start by looking at the problem that read assault in the first place and it's

a problem that was actually present in the last application we built music master.

So let's break down the architecture of music master primarily music master consists of four components

one D search component it's allows a user to enter the name of the artists they want to look up the

top tracks for Then too there's the artist component this displays the info about the artist that the

user searched once that info is available.

The third one is the tracks component and this shows a list of playable track objects that actually

outputs audio for the user funnily.

The fourth component is the main at component is actually grouped together.

Each of the previous components enticing music matches your application together.

It's arguably the most important component since it has the search artist functionality to hit the Spotify

API and it also contains the main data for the overall application.

So all the data for what the user has typed in the fetch artist and their top tracks.

It gets stored in the App State so it's up to the app component to pass this data down to the artist

in tracks component.

So this information can be displayed.

But not only that in addition to passing down data the main app has also passed down the search artist

function as a callback through prompts that we the search artist component can attach its button to

the search artist's method originally defined within app.

Now this approach is in horrible when a method is only passed down once for smaller react applications

passing down props is an effective way to pass data and that it's from a paired component to charred

ones.

But what if there are even more components than this in the overall application.

Hypothetically that such component could have been split up into separate custom input and button components

and now all of a sudden the search artist's method needs to be passed down one more time to the button

component.

Three levels are passing down a method also that a button can trigger a method that changes a state

in the main app component so it's not the cleanest situation.

And this is the exact situation that redux hopes to address instead of this approach.

A building state in many different components and passing dumb methods that change components state

retakes can be used as an alternative since redux is a state management technology.

It lets components do what they do best display data and user interfaces and then redux does a job of

handling all the underlying data.

There are three main aspects to redux.

First there is the global store the global sort collects all the state for the entire react application.

That's right.

The entire react app.

For example if we read x5 music master the global store would include the user entered artist query

the fetched artist object result and the tracks array result as well.

Next to the store we have reduces reduces describes certain sections of the store and how they should

update.

For example in a redux version of music master again there would be a reducer for the artist query.

Another reducer for the fetch artist object and then another one for the tracks put together these reducer

is composed compose the overall store third there are actions actions are objects that contain data

that should end up in the store.

Again looking back at the example of music master in the Redux version there would be action objects

for the fetched artists and tracks these action objects will end up containing the data relevant to

the fetch artist and tracks to then put in the store.

Now these concepts are better understood when you look at how they fit together from a zoomed out perspective

a redux.

All right so there's the global store which contains the data for the react app.

Then there are various action objects these action objects are full of data that will end up within

the overall store and then reduces describe how certain sections of the store should be updated composed

altogether they comprise the store one key aspect of redux is that the producers listen to every single

action however they're only going to be configured to respond to certain action objects.

In other words they're only going to take the data from a few action objects to update their section

of the store.

Now there's the next question of who is actually sending out these action objects or to use a terminology

of redux who is dispatching these action objects.

Well that would be the components the rock components will have the ability to connect their elements

like buttons and input fields to functions that can create action objects and dispatch them to the producers

the components.

Also had the ability to read the data for any part of the reader's store that way they can use data

to display something to the user overall.

That's how redux works now.

How does a system fix the messy situation a passing down state did it in callbacks.

The many components while the beauty of this read its implementation is that you end up with a unique

directional flow of data.

In other words the data flows one way from the store and down to all the components the arc callbacks

going down through components in order to set the state of a paired component in a grandchild component

the store is like a well-defined and predictable function that is split up by its reduces and the action

objects are the inputs for that function.

Giving it new data that will adapt the stores overall output overall.

This is why redux is using react applications unidirectional flow of data eliminates the potential for

messy situations where a ton of data and callback methods are being passed down through prompts.

Okay with that.

Let's reinforce these concepts by actually exporting redux by building a redux application.



My kesimpulan

Redux adalah state management -> sistem yang mengatur penggunaan state di dalam aplikasi (React).

Struktur Organisasi Redux dalam aplikasi React terdiri dari STORE, REDUCER, DISPATCH, ACTION, ACTION CREATOR, STATE dan COMPONENT.

 

