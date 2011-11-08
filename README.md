# CodeIgniter-Cache

CodeIgniter-Cache is a partial caching library for CodeIgniter. It allows you to write and get chunks
of data to and from the filesystem. By storing complex or large chunks of data in serialized form
on the file system you can relieve stress from the database or simply cache Twitter calls.

## Requirements

1. PHP 5.2.x
2. CodeIgniter 2.0.x to 2.1.0

## Usage

	// Uncached model call
	$this->blog_m->getPosts($category_id, 'live');

	// cached model call
	$this->cache->model('blog_m', 'getPosts', array($category_id, 'live'), 120); // keep for 2 minutes

	// cached library call
	$this->cache->library('some_library', 'calcualte_something', array($foo, $bar, $bla)); // keep for default time (0 = unlimited)

	// cached array or object
	$this->cache->write($data, 'cached-name');
	$data = $this->cache->get('cached-name');

	// Delete cache
	$this->cache->delete('cached-name');

	// Delete all cache
	$this->cache->delete_all();

	// Delete cache group
	$this->cache->write($data, 'nav_header');
	$this->cache->write($data, 'nav_footer');
	$this->cache->delete_group('nav_');

	// Delete cache item
	// Call like a normal library or model but give a negative $expire
	$this->cache->model('blog_m', 'getPosts', array($category_id, 'live'), -1); // delete this specific cache file

## Installation

Permission your cache folder to be writeable by the web server.