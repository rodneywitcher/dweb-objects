# DwebObjects
Object library for higher level Decentralized Web concepts.  Builds on dweb-transports.

## Background
This library is part of a general project at the Internet Archive (archive.org) 
to support the decentralized web.  

## Goals
* to allow a API that can be used to build functionality in the Dweb easier.

## Installation and usage in the Browser

* Install npm & node
* Clone this repo and cd to it.
* `npm build` will create dist/dweb-transports-bundle and dweb-objects-bundle.js
* `npm setuphttp` will setup some links we haven't persuaded webpack to do!


### Running the examples in the Browser
The examples can run either from the [dweb.me/examples](https://dweb.me/examples) server, 
or once the source is checked out, locally from your file system.

By default each of these examples runs multiple transports, and is smart if it cannot connect to one or the other.

- Simple text creation and retrieval: [example_block.html](https://dweb.me/examples/example_block.html)
- Simple dict creation and retrieval: [example_smartdict.html](https://dweb.me/examples/example_smartdict.html)
- List creation and retrieval: [example_list.html](https://dweb.me/examples/example_list.html)
- UI for Academic docs - centralised search; decentralized retrieval: []example_academic.html](https://dweb.me/examples/example_academic.html)
- Authentication: Managing locks and keys [example_keys.html](https://dweb.me/examples/example_keys.html)
- Versions of a single document: [example_versions.html](https://dweb.me/examples/example_versions.html)
- [objbrowser.html](https://dweb.me/examples/objbrowser.html)

**Browser Support**: This should work on Chrome and Firefox (Safari doesn't support many newer features but appears to work), 

**Transport choice**: You can deselect transports by clicking the Green indicator on an example. 
To prevent it connecting in the firstplace, you can supply paused=HTTP or paused=IPFS or paused=WEBTORRENT or paused=YJS to the url.

**Verbosity**: You can get debugging output by setting localStorage.debug=("dweb-objects:* dweb-transports:*") in your javascript console, you should only have to set this once.

### Adding to a HTML application
* Add to your `<HEAD>`

```
<SCRIPT type="text/javascript" src="dweb-transports-bundle.js"></SCRIPT>
<SCRIPT type="text/javascript" src="dweb-objects-bundle.js"></SCRIPT>
```

See the examples in the dist directory of this repo for some example code. 

See [API.md](./API.md) for the detailed API.

## Node Installation
* Clone this repo. 

### Incorporation in a Node application

Add to `package.json` in the `dependencies` section.
```
"@internetarchive/dweb-transports": "latest",
"@internetarchive/dweb-objects": "latest",
```

* `npm install`  will then install `dweb-objects` and `dweb-transports` which currently includes `IPFS`, `WebTorrent`, `Gun`, `YJS`

In your application javascript, in this order.
```
const DwebTransports = require('@internetarchive/dweb-transport') #adds the transports
const DwebObjects = require('@internetarchive/dweb-objects;)      #adds the object library
```

* TODO writeup how to require only some of the transports.
* Then see usage API below


## See also
See [Dweb document index](https://github.com/internetarchive/dweb-transports/blob/master/DOCUMENTINDEX.md) for a list of the repos that make up the Internet Archive's Dweb project, and an index of other documents. 
