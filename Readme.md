# Project XanaDown
An attempt to make a fuctional Xanadu client/server implementation

## [Demo Here](http://lain.gboards.ca)

## What is Xanadu?
Xanadu is the brainchild of Ted Nelson, a interconnected document storage/hypermedia system before the 
WWW. The main features are direct reXanadu was never or functional outside of a lab. It has some caveats though

- Requires a centralised document store with versioning
- Based on txt files with no markup
- Provides inlining with source defences (Transclusions)
- Provides hyperlinks with Spans
- Links against a static version of the document

## Why is this cool?
As opposed to the fragmented nature of the network currently, Xanadu removes any possibility of bitrot and provides
a clean and efficent way to browse information and navigate resources. Styling is handled entirely by the client and
content is entirely seperate. Because of versioning a static net of links is created  more accurately connecting the
knowledge/exploration of such.

## What is XanaDown
XanaDown is a modern implementation of Project Xanadu, while making some concessions
- Uses decentralized git repositories for storage/versioning
- Markdown syntax with addition for spans/transclusions
- Backend written in Golang + gitfs
- Frontend written in React

## Todo:
- Dockerize the whole thing for easy deployment
- Fallback/Automatic backup to a centralized store (Internet Archive)
- Write converter for traditional information sources (Wikipedia)
- Transclusion selector
- Version browser!
- IFrame for traditional web content

## Server API
It's pretty simple, it mostly acts a proxy for remotes!

### /doc
#### params:
?loc=[URL]		// The resource to request

#### url format
// Get latest revision

[repo]/current/[path to file]


// Get specfic revision

[repo]/history/[day]/[time+hash]/[path to file]

- https://github.com/germ/germ.xan.git/current/index.md
- https://github.com/germ/germ.xan.git/history/2019-11-10/06-35-34-9eec078fbe/index.md

#### Response
JSON Object describing the resource

    type DocReq struct {
	    Doc       string		// The Raw document (if text)
      IsLatest  bool			// Does a newer version exist?
      LatestUrl string		// Where the newest version is (permalink)
	    Url       string		// Link to the document
    }
