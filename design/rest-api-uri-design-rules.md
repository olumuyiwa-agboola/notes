# REST API URI Design Rules
## Clarifying Some Buzz Words
- ***Web server*** is a term used to refer to software programs that accept, process and respond to HTTP (or its secure variant HTTPS) requests, as well as the underlying hardware (i.e. the physical machine) that makes this possible. 
- A ***web service*** is a purpose-built web server that provides functionalities and access to resources that support the needs of a site or any other application.
- An ***application programming interface (API)***, or more specifically a ***web API***, is the face of a web service, facilitating communication between client programs and the web service.
- A web API that conforms to the **Representational State Transfer (REST)** architectural style is a called a ***REST API***.
- When the web API that exposes a web service conforms the REST architectural style (i.e. it is a REST API), the web service is said to be a ***RESTful service***.

## A Little Bit of History
In 1993, Roy Fielding and others proposed a set of constraints grouped into six categories and collectively referred to
as the **Web's architectural style**. The six categories are:
1. Client-server
2. Uniform interface
3. Layered system
4. Cache
5. Stateless
6. Code-on-demand

In 2000, Fielding named and described the Web’s architectural style in his Ph.D. dissertation, giving it the name **Representational State Transfer (REST)**.

In the **uniform interface** category, one of the four constraints Fielding named is the ***identification of resources***, which is the idea that each distinct Web-based concept (i.e. resource) should be addressed by a unique identifier, one of which is a ***uniform resource identifier (URI)***.

In this context, a ***uniform resource identifier*** is a unique sequence of characters that identifies a Web-based concept or resource. REST APIs use URIs to address resources.

## Format of a URI
The image below shows the generic syntax of a URI:

![Generic syntax of a URI as defined in RFC 3986](uri-syntax.png)

Of the five URI segments, three (authority, path and query) will be dicussed in this note.

# URI Design Rules

## 1. General URI Design Rules
1. Forward slash separator (/) *must* be used to indicate a hierarchical relationship between resources.
2. A trailing forward slash (/) *should* not be included in URIs. As the last character within a URI’s path, a forward slash (/) adds no semantic value and may cause confusion. REST APIs should not expect a trailing slash and should not include them in the links that they provide to clients.
3. Hyphens (-) *should* be used to improve the readability of URIs. Anywhere you would use a space or hyphen in English, you should use a hyphen in a URI.
4. Underscores (\_) *should* not be used in URIs. Depending on the application’s font, the underscore
(\_) character can either get partially obscured or completely hidden by this underlining. To avoid this confusion, use hyphens (-) instead of underscores.
5. Lowercase letters *should* be preferred in URI paths. When convenient, lowercase letters are preferred in URI paths since capital letters can sometimes cause problems.
6. File extensions *should* not be included in URIs. A REST API should not include artificial file extensions
in URIs to indicate the format of a message’s entity body. Instead, they should rely on the media type, as communicated through the Content-Type header, to determine how to process the body’s content. 

## 2. URI Authority Design Rules
7.  Consistent subdomain names *should* be used for your APIs. The top-level domain and first subdomain names of an API should identify its service owner. The full domain name of an API should add a subdomain named `api`.
8. Consistent subdomain names *should* be used for your client developer portal. If an API provides a developer portal, by convention it should have a
subdomain labeled `developer`.
## 3. URI Path Design Rules
### Resource Models

## 4. URI Query Design Rules

## Sources
- Massé, Mark. REST API Design Rulebook. O'Reilly Media, 2012.
- Wikipedia. "Web Server." Accessed July 25, 2025. https://en.wikipedia.org/wiki/Web_server.
- Wikipedia. "Uniform Resource Identifier." Accessed July 25, 2025. https://en.wikipedia.org/wiki/Uniform_Resource_Identifier.
- Berners-Lee, Tim, Roy Fielding, and Larry Masinter. "Uniform Resource Identifier (URI): Generic Syntax." RFC 3986. Internet Engineering Task Force, January 2005. https://www.rfc-editor.org/rfc/rfc3986.txt.