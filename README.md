# Social-Single-Sign-SSO-Authentication-in-Oracle-APEX
for video help go to this link : https://youtu.be/YU8li4lpZcs
#follow these steps
--1
 google cloud console
--2
 left navigation menu
   >>> API & Services
    >>> Credentials
	  >>>OAuth 2.0 Client IDs
	      >>> Authorized redirect URIs https://oracleapex.com/ords/apex_authentication.callback
DECLARE
  l_callback VARCHAR2(4000);
BEGIN
  l_callback := apex_authentication.get_callback_url;
  dbms_output.put_line(l_callback);
END;

--3 Branding
>>App domain 
 >>https://oracleapex.com/ords/r/sales_se/single-sign-on-sso-app/home
    >>>Authorized domains
      >>oracleapex.com
--4 Web Credentials
    name>>Google Authentication
	static id>>google_authentication
	Authentication Type>>OAuth2 Client Credentials
	scope>> email.profile
	<client id & Sceret>
--5 APEX Authentication Scheme
  >>Settings
   >>web credential
     Auth Provider>> google
	         scope >> profile,email 
	               Username>> email
	  
