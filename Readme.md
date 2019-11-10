## Project XanaDown
An attempt to make a fuctional Xanadu client/server implementation

# [Demo Here](http://lain.gboards.ca)

# What is Xanadu?
Xanadu is the brainchild of Ted Nelson, a interconnected document storage/hypermedia system before the 
WWW. The main features are direct reXanadu was never or functional outside of a lab. It has some caveats though

- Requires a centralised document store with versioning
- Based on txt files with no markup
- Provides inlining with source defences (Transclusions)
- Provides hyperlinks with Spans
- Links against a static version of the document

# Why is this cool?
As opposed to the fragmented nature of the network currently, Xanadu removes any possibility of bitrot and provides
a clean and efficent way to browse information and navigate resources. Styling is handled entirely by the client and
content is entirely seperate. Because of versioning a static net of links is created  more accurately connecting the
knowledge/exploration of such.

# What is XanaDown
XanaDown is a modern implementation of Project Xanadu, while making some concessions
- Uses decentralized git repositories for storage/versioning
- Markdown syntax with addition for spans/transclusions
- Backend written in Golang + gitfs
- Frontend written in React

# Todo:
- Dockerize the whole thing for easy deployment
- Fallback/Automatic backup to a centralized store (Internet Archive)
- Write converter for traditional information sources (Wikipedia)
- IFrame for traditional web content
