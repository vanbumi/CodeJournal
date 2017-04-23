#### warning: constant ::Fixnum is deprecated & warning: constant ::Bignum is deprecate

	Replace references to Fixnum with Integer, to fix the existing deprecation warning:

or

	You can fix the error by either upgrading your Rails installation (gem 'rails', '5.0') or downgrading to an older version of Ruby with a version manager (e.g. $ rvm install 2.3.0; rvm use 2.3.0).	

Came with this message:

	You have requested:
	  rails = 5.0.0

	The bundle currently has rails locked at 4.2.4.
	Try running `bundle update rails`

	If you are updating multiple gems in your Gemfile at once,
	try passing them all to `bundle update`	

Solution	

	running `bundle update rails`
	bundle update

Done!	