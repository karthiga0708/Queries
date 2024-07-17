# Questions

## seperate data will store as entity or not
  Yes, we can seperate a data or information from the file which we stored as entity in XML file. 

    from defusedxml.ElementTree import parse, fromstring

      xml_data = """<?xml version="1.0"?>
      <!DOCTYPE root [
          <!ENTITY exampleEntity SYSTEM "file://path/to/entity.xml">
      ]>
      <root>
          <content>&exampleEntity;</content>
      </root>
      """
      
      try:
          root = fromstring(xml_data)
          content = root.find('content').text
          print(f"Content: {content}")
      except Exception as e:
          print(f"Error: {e}")


## What is xml parser
  - XML parser is a software library that reads XML documents and provides access to their structure and content for processing.
  - XML parsers are used to transform XML data into a format that applications can use, such as objects or data structures.
## How XML parser works
   An XML parser works by reading an XML document and converting it into a structure that a computer program can manipulate. 
Steps of XML Parsing

      Loading the Document
      Lexical Analysis (Tokenization)
      Syntax Analysis
      Building the Data Structure
      Validation (Optional)
      Providing Access to the Data
      
## why to disallow custom DTD in xml parser

## Where did we use session id?
  - Session id is also known as session tokens, It is piece of code (unique identifier) that a web server assigns a user when they login. A session is a finite period of interaction between a client and server.
  - Sessions and session IDs provide a mechanism for requests together, making it easier to carry out tasks such as filling out multipage forms or tracking items in an online-shopping cart.
  - Web servers that issue session IDs use various methods to persist the IDs throughout the life of the session.
  - The most common approach is to store the session ID as a cookie on the user's browser.
  - A cookie is a small amount of data that contains information about the user, session, environment or user's activity.
  - A cookie that holds a session ID is typically deleted after the session has been terminated

## What is poor management?
  - Poor session management refers to the mishandling of user sessions in a web application, which can lead to various security vulnerabilities and usability issues.
  - A user session typically starts when a user logs into a web application and ends when they log out.
  - Effective session management ensures that the user's session is secure and properly tracked.

## Types of anti-CSRF
Anti-CSRF includes authentication fundamentals
  -  Cookie-based authentication
  -  Token-based authentication
Antiforgery in ASP.NET Core
Antiforgery with AddControllers
Configure antiforgery with AntiforgeryOptions
Generate antiforgery tokens with IAntiforgery

  Link for more - (https://learn.microsoft.com/en-us/aspnet/core/security/anti-request-forgery?view=aspnetcore-8.0#antiforgery-in-aspnet-core)
  
### CSRF protection with custom headers 
      X-XSRF-Token
      Access-Control-Allow-Credentials 
      Access-Control-Allow-Origin

## same-origin policy in detail?(best practices, sytax)
  - The Same-Origin Policy (SOP) is a security measure implemented in web browsers to prevent malicious scripts on one page from accessing data on another page unless they share the same origin.
  - This policy helps protect the confidentiality and integrity of information by restricting how documents or scripts loaded from one origin can interact with resources from another origin.

### Key Areas Affected by SOP

      DOM Access: A script can only read properties of windows and documents that have the same origin
      Cookies: Cookies are accessible only to the origin that set them.
      XMLHttpRequest: An XMLHttpRequest can only make network requests to the same origin unless CORS (Cross-Origin Resource Sharing) is used.
      Web Storage: Local storage and session storage are origin-specific.

### Syntax
      var xhr = new XMLHttpRequest();
      xhr.open('GET', 'http://example.com/data', true); // This will work if the request is to the same origin.
      xhr.onload = function() {
        if (xhr.status === 200) {
          console.log(xhr.responseText);
        }
      };
      xhr.send();


### Best practice
  - Use CORS Properly: When cross-origin requests are necessary, configure CORS on the server side to allow specific origins, methods, and headers.

    ### Syntax
        Access-Control-Allow-Origin: https://anotherdomain.com
        Access-Control-Allow-Methods: GET, POST
        Access-Control-Allow-Headers: Content-Type

  - Validate and Sanitize Data: Always validate and sanitize data on the server side to prevent cross-site scripting (XSS) and other attacks.

  - Use Secure Cookies: Set the SameSite attribute for cookies to Strict or Lax to control how cookies are sent with cross-site requests.
    ### Syntax
        Set-Cookie: sessionId=abc123; SameSite=Strict; Secure; HttpOnly

  - Adopt Secure Protocols: Use HTTPS to ensure data integrity and confidentiality in transit.

  - Content Security Policy (CSP): Implement CSP headers to restrict the sources from which resources can be loaded.

    ### Syntax
        Content-Security-Policy: default-src 'self'
  

## CMS doc(why and how it used) and architecture
  - Content Management Systems (CMS) are software applicatio that allow users to create, manage, and modify content on a website without needing specialized technical knowledge.
  - It hosted either in the cloud as a SaaS product or on- premise.
  - They provide an intuitive interface and various tools that simplify content creation, storage, editing, and publishing.
  - Without a content management system, you’d need to write a static HTML file and upload it to your server
  - With a content management system like WordPress, you can just write your content in an interface

### CMS Architecture
  - CMS architecture refers to the design and implementation of frontend and backend processes within CMS systems.
  - CMS architecture defines the relationship between the tools used to publish and manage posts and pages with those used to create and edit them — the frontend and the backend.

CMS Architecture include

        Content Repository
        Content Management Application (CMA)
        Content Delivery Application (CDA)
        Templates/Themes
        Plugins/Extensions
        API Layer
        User Interface
        Security Layer
        
### Types of CMS Architecture

There are five basic types of CMS architecture:

    Coupled (also called traditional)
    Decoupled
    Headless
    Hybrid
    SaaS

Reference: https://blog.hubspot.com/website/cms-architecture
  
## SSTI

## Arbitrary code and obfuscated code (diff)
### Arbitrary code
  - Arbitrary code refers to computer code or instructions that can be executed on a machine without any restrictions.
  - When someone says they can execute "arbitrary code," it typically means they have the ability to run any command or code they choose on a system, which can lead to various outcomes depending on the intent of the person executing it.
  - the ability to execute arbitrary code is often associated with vulnerabilities or exploits.


### obfuscated code
  - Is used to make something harder to understand and also for more difficult to attack.
  - Obfuscation of source code is harder to replicate product if it is reverse engineered. It is not a strong control.
  - It is an obstracle like encoding & often reversed by the same technique.

## where serialization is used & how, why

## SSRF & Types of SSRF blind, semi blind, non-blind



