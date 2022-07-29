## Oracle ATG - Information - Q and A

Hey Reader!!!!

You're here and you want to know more about the technical concepts.

# Contents of the blog include:

- Basics of Oracle ATG 


![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1642830447435/1X3x3ZM31.png)

1.	ATG is a framework for creating web applications using **J2EE** standards.

2.	**DAF** [ Dynamo Application Framework] is the core platform which implements a component development model based on Java Server Pages [JSP] and Java Beans

3**.	What is Droplet in ATG?**

1. Droplet is an ATG’s custom servlet, which has some atg’s specific customization. It is similar to J2EE’s HttpServlet,

2. Here we use DynamoServlet which implements javax.servlet.Serlvet interface

3.	Droplets are mainly used to write the business logic out for server side code.

4.	Default scope of droplet is GLOBAL

5.	Droplet is stateless – can be used by many different request\ users at a time so there is no reason to make droplet as request scope

6.	Droplet have request, session and global scopes

7.	There is layer Generic service between Servlet and DynamoServlet to provide with some nucleus component.

8.	To create a droplet we extend DynamoServlet and override its service() method to run our code.

9.	Droplets are invoked from JSP’s
 [Whenever, we are writing JSPs, we make sure that we do not add any "logic" in JSPs. If we want some of the content to be dynamically displayed using a logic, we use a droplet!]

10.	<dsp:droplet name="{YOUR_DROPLET_COMPONENT_PATH}"> </dsp:droplet>

4. **What is a Component in ATG?
**
1.	Component is nothing but a configuration file with .properties extension which uses a java class
2.	To create a component we need Java class and configuration file

**GenericService**

1.	Is a basic implementation of the service Interface.
2.	Services written from scratch should extend this class to take advantage of all the facility it provides
3.	Provides two methods
1.	doStartService() - this is called after the service has been created. Service should use this method to start any processes required for its operation.
2.	DoStopService() - this is called when a nucleus determines when that a service should shut down. It may happen because of explicit command, or if nucleus is shutting down.


**Nucleus in ATG
**	
1.	Nucleus is referred to the ATG container for components.
2.	It provides hierarchical name space to component.
3.	It serves 2 purpose – it is the root of nameContextHierarchy and implement the policies for resolving name hierarchy
4.	its absolute name is “/”
5.	nucleus properties are processed by using the $ sign in the configuration files.

**How JSP is processed in ATG
**	
- type a URL and send a request for a jsp to ATG application
- ATG application receives the request for JSP file you requested for.
- once the JSP is found it is compiled into java code
- when all the content is fetched by java code, the end result is converted into plain HTML
- this HTML is sent back to the browser

**ATG Servlet Pipeline
**
- pipeline is a series of actions to be execute
- each request is rendering through DAF pipeline in ATG
DAF pipeline – handles JSP request, pipeline is invoked by Pagefilter
DAS pipeline – handles JHTML request, are usually dyn/admin pages

![image.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1642830161965/vcmB3sOps.png)


- DynamoHandler is the first servlet in the request servlet pipeline chain. PageFilter will start DAF servlet pipeline by calling DynamoHandler. PageFilter is configured in web.xml to handle jsp request

<filter>
     <filter-name>PageFilter</filter-name>
     <filter-class>atg.filter.dspjsp.PageFilter</filter-class>
</filter>
     <filter-mapping>
        <filter-name>PageFilter</filter-name>
        <url-pattern>*.jsp</url-pattern>
     </filter-mapping>

- DynamoHandler converts HttpRequest and HttpResponse to DynamoHttpRequest and DynamoHttpResponse.

**SiteContextPipelineServlet**
- evaluate the site identity in multisite environment
- it site is not multisite, set SiteContextPilelineServlet.enabled=false

	 For Multisite, SiteContextPilelineServlet  performs below tasks :

- Derives a siteId from request URL
- Determines site information is available for request
- Passes site id to SiteContextManager and SiteSessionManager

**PathAuthenticationServlet** : provides username and password authentication for authenticators path.

Example : For getting access of /File/Location, We need to provide TestUser as username and TestPassword as password.

          enabled=true
          authenticators=\
                  /File/Location=/application/auth/TruthPassword
 
         TruthPassword.properties
                $class=atg.servlet.pipeline.BasicAuthenticator
                passwords=\
                       TestUser=TestPassword

**DynamoServlet** : Sets various properties to DynamoHttpServletRequest.

**ProtocolSwitchServlet** :

- perform switching between a secure and non secure server.
-  It is having secureList and ignoreList.
- Contains URL Mapping.
- Getting secureHostName and nonSecureHostName from /atg/dynamo/Configuration.

**ProfileRequestServlet** :

- creates an instance of the atg/userprofiling/Profile component.
- If profile doesn't exits, It creates a transient RepositoryItem.
- To presists anonymous profiles in DB, set  ProfileRequestServlet.persistentAnonymousProfiles=true

**ProfilePropertyServlet** :
- Sets properties on profile.
- Default property sets are :
				/atg/userprofiling/SiteProfilePropertySetter
				/atg/userprofiling/CatalogProfilePropertySetter
				/atg/userprofiling/PriceListProfilePropertySetter

**SessionEventTrigger**:
- determines the session.
- If New, fires a StartSession event.
- If Expired, fires a EndSession event.
- Registers itself as a listener in the SessionManager, nameContextBindingListeners property.
- Session Expire Time is set to the sessionInvalidationTime property of /atg/dynamo/servlet/session/SessionManager.
- By Default it is 30 minutes.

To avoid these session expiration errors, We used the CheckSessionExpiration servlet, an instance of the class atg.projects.b2bstore.servlet.WACheckSessionExpiration.
- It passes the expired session user to the URL set to relativeExpirationURL property.

**AccessControlServlet** : verifies profiles is permitted or not to view requested URL.

**DAFDropletEventServlet** : responsible to call setXXX / handleXXX in case of form is submitted.

**TailPipelineServlet** : Last servlet in request servlet pipeline.  It is responsible for calling FilterChain.doFilter(), which invokes the next filter defined in web.xml.

Thank you for reading, Please like the article, It will encourage me to write more such articles. Do share your valuable suggestions, I appreciate your honest feedback!!
