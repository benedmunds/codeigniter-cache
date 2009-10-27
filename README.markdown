CodeIgniter-Cache
=================

CodeIgniter-Cache is a partial caching library for CodeIgniter. It allows you to write and get chunks
of data to and from the filesystem. By storing complex or large chunks of data in serialized form 
on the file system you can relieve stress from the database or simply cache Twitter calls.

Usage
-----

	// Uncached model call
	$this->blog_m->getPosts($category_id, 'live');

	// cached model call
	$this->cache->model('blog_m', 'getPosts', array($category_id, 'live'), 120); // keep for 2 minutes 
	
	
	$this->cache->library('some_library', 'calcualte_something', array($foo, $bar, $bla)); // keep for default time (0 = unlimited)
	
	$this->cache->write($data, 'cached-name');
	$data = $this->cache->get('cached-name');
	
	$this->cache->delete('cached-name');


Installation
------------

Permission your cache folder to be writeable by the web server.


Requirements
------------

Only CodeIgniter


Extra
-----

If you'd like to request changes, report bug fixes, or contact
the developer of this library, email <email@philsturgeon.co.uk>