## Open Graph Protocol

OGP enables any web page to become a rich object in a social graph. For instance, this is used on Facebook to allow any web page to have the same functionality as any other object on Facebook.

#### Basic Metadata

  To turn your web pages into graph objects, you need to add basic metadata to your page. We've based the initial version of the protocol on RDFa which means that you'll place additional <meta> tags in the <head> of your web page. The four required properties for every page are:


  `og:title` - The title of your object as it should appear within the graph, e.g., "The Rock".
  
  `og:type` - The type of your object, e.g., "video.movie". Depending on the type you specify, other properties may also be required.
  
  `og:image` - An image URL which should represent your object within the graph.
  
  `og:url` - The canonical URL of your object that will be used as its permanent ID in the graph, e.g., "http://www.imdb.com/title/tt0117500/".

  
  #### Example

  ```html
  <html prefix="og: http://ogp.me/ns#">
  <head>
  <title>The Rock (1996)</title>
  <meta property="og:title" content="The Rock" />
  <meta property="og:type" content="video.movie" />
  <meta property="og:url" content="http://www.imdb.com/title/tt0117500/" />
  <meta property="og:image" content="http://ia.media-imdb.com/images/rock.jpg" />
  ...
  </head>
  ...
  </html>
  ```


#### Resources

http://ogp.me/
