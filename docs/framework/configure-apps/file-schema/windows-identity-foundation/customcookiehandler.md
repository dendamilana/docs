---
title: "<customCookieHandler>"
ms.date: "03/30/2017"
ms.assetid: a03b153d-5ec6-4915-9031-6f0c3fd348be
author: "BrucePerlerMS"
---
# \<customCookieHandler>

Sets the custom cookie handler type. This element may only be present if the `mode` attribute of the `<cookieHandler>` element is "Custom". The custom type must be derived from the <xref:System.IdentityModel.Services.CookieHandler> class.  
  
[**\<configuration>**](../configuration-element.md)\
&nbsp;&nbsp;[**\<system.identityModel.services>**](system-identitymodel-services.md)\
&nbsp;&nbsp;&nbsp;&nbsp;[**\<federationConfiguration>**](federationconfiguration.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;[**\<cookieHandler>**](cookiehandler.md)\
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;**\<customCookieHandler>**  
  
## Syntax  
  
```xml  
<system.identityModel.services>  
  <federationConfiguration>  
    <cookieHandler mode="Custom">  
      <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" >  
      </customCookieHandler>  
    </cookieHandler>  
  </federationConfiguration>  
</system.identityModel.services>  
```  
  
## Attributes and Elements  

 The following sections describe attributes, child elements, and parent elements.  
  
### Attributes  
  
|Attribute|Description|  
|---------------|-----------------|  
|type|Specifies a custom type that derives from the <xref:System.IdentityModel.Services.CookieHandler> class. For more information about how to specify the `type` attribute, see [Custom Type References](../windows-workflow-foundation/index.md).|  
  
### Child Elements  

 None  
  
### Parent Elements  
  
|Element|Description|  
|-------------|-----------------|  
|[\<cookieHandler>](cookiehandler.md)|Configures the <xref:System.IdentityModel.Services.CookieHandler> that the <xref:System.IdentityModel.Services.SessionAuthenticationModule> uses to read and write cookies.|  
  
## Remarks  

 When you specify a custom cookie handler by setting the `mode` attribute of the `<cookieHandler>` element to "Custom", you must specify the type of the custom cookie handler by including a `<customCookieHandler>` child element that references the cookie handler type. This element cannot be specified when the `mode` attribute is set to "Chunked" or "Default". Custom cookie handlers must derive from the <xref:System.IdentityModel.Services.CookieHandler> class.  
  
 The `<customCookieHandler>` element is represented by the <xref:System.IdentityModel.Configuration.CustomTypeElement> class.  
  
## Example  

 The following example configures the SAM to use a custom cookie handler of type `MyNamespace.MyCustomCookieHandler`.  
  
```xml  
<cookieHandler mode="Custom">  
    <customCookieHandler type="MyNamespace.MyCustomCookieHandler, MyAssembly" />  
</cookieHandler>  
```  
  
## See also

- <xref:System.IdentityModel.Services.CookieHandler>
