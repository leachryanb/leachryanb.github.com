---
layout: default
title: NFJS - Modeling Resources
---

# Modeling Resources
## Brian Sletten - @bsletten

### REST & Hypermedia

RESTful JSON is not the end of the story

## Identity
Web is not about documents its about resources

what we get back is a representation of an identity

### Information Resources
* Document
* Data set
* Data element
* Semi-private data
  * Just because something has identity, doesn't mean that it can't be protected
* Not proscribing the workflow
* REST - The result of invoking a service
* Data, Documents, Services

### Non-Information Resources
* You
* Your organization
* The concept 'puppy'
* My dog

* I have a page, but I am not a webpage
* For non-networkable addressable resources, W3C says return 303 redirect
* Valid request, but go here
* REST is about resources - Identity, not services
* The function of a name is to facilitate sharing
* Naming schemes don't scale
* The name of the technology should not be part of its identifier
  * URLs have not been stable
* URL, URN, URI
  * URI - General Scheme

### Information Space
* Provide myltiple Aliases to the same identity
* Findability of resource
* Sets of information with partition schemes
* Need conceptual partitioning

### Canonical vs Historical
* versioned/non-versioned
* latest and greatest vs historical/specific

### URI
* Cool URIs don't change

### Things to avoid
* Author name
* Subject
* Status
* File name extension
* Software mechanism

## Interaction
* Structuring the returned information on the 80/20 rule
  * lint out to more detail
* Hierarchy matters
* Ad Hoc filtering
* Matrix-uri form: Semi-colon key-value pairs

### The API is a first class citizen
* Make choices that make sense for the domain
* Change the backend to support the API

### The Verbs
* The verbs matter.  Use the right one
* Itempotent - does it mutate the resource
* POSTs intent was create a resource on my behalf and I will send you a reference to it so you can do a get for it.
  * We abuse POST by sending the resource back instead of the reference
* PUT has a specific meaning: Update or Overwrite
* DELETE - itempotent. not used much due to security
* GET - itempotent - can ask as many times as you want.  Doesn't mutate anything
* POST - not itempotent - who knows what you're doing.  No semantics
* PUT - IS itempotent
* HEAD - Don't do it, but send me meta about the transaction
* OPTION - discovery
* PATCH - Partial update
  * Modify resources without caring what it is
  * Just needs ID
  * Patch formats - options with E-Tag
  * Concept is key to understanding REST

* Combined with Response Codes you can have a very rich conversation

## Representation

### Content Negotiation
* Formats
  * Generally solved by using extensions: .html, .xml, etc, but prefer
  * Link header RFC
  * If you are passing around the ref pass around the logical ref (no extension)
  * Accept: Mime-types
  * Biggest problem with a logical ref and different return type is proxies and cache
    * Use the Vary: Accepts header in the response

### Hypermedia

* Templated Links
* HTML doesn't support itempotent links: PUT, PATCH and DELETE from forms
  * Need to use JavaScript
* <x:include


Book: Hypermedia APIs with HTML5 & Node