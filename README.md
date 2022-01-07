[comment]: # "Auto-generated SOAR connector documentation"
# Check Point Reputation Service

Publisher: Splunk Community  
Connector Version: 2\.0\.1  
Product Vendor: Check Point Software Technologies  
Product Name: Check Point Reputation Service  
Product Version Supported (regex): "\.\*"  
Minimum Product Version: 4\.9\.39220  

Queries Check Point Reputation Service for IOC reputation

### Configuration Variables
The below configuration variables are required for this Connector to operate.  These variables are specified when configuring a Check Point Reputation Service asset in SOAR.

VARIABLE | REQUIRED | TYPE | DESCRIPTION
-------- | -------- | ---- | -----------
**api\_key** |  required  | password | API key

### Supported Actions  
[test connectivity](#action-test-connectivity) - Validate the asset configuration for connectivity using supplied configuration  
[url reputation](#action-url-reputation) - For a domain/URL returns the classification and risk in accessing the resource  
[ip reputation](#action-ip-reputation) - For an IP address returns its classification and risk in accessing a resource hosted on it  
[file reputation](#action-file-reputation) - For a file digest \(md5/sha1/sha256\) returns the risk in downloading the file without the need to scan it  

## action: 'test connectivity'
Validate the asset configuration for connectivity using supplied configuration

Type: **test**  
Read only: **True**

#### Action Parameters
No parameters are required for this action

#### Action Output
No Output  

## action: 'url reputation'
For a domain/URL returns the classification and risk in accessing the resource

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**resource** |  required  | URL | string |  `url`  `domain` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.resource | string |  `url`  `domain` 
action\_result\.data\.\*\.resource | string |  `url`  `domain` 
action\_result\.data\.\*\.risk | numeric | 
action\_result\.data\.\*\.status\.code | numeric | 
action\_result\.data\.\*\.status\.label | string | 
action\_result\.data\.\*\.status\.message | string | 
action\_result\.data\.\*\.reputation\.classification | string | 
action\_result\.data\.\*\.reputation\.severity | string | 
action\_result\.data\.\*\.reputation\.confidence | string | 
action\_result\.data\.\*\.context\.malware\_family | string | 
action\_result\.data\.\*\.context\.protection\_name | string | 
action\_result\.data\.\*\.context\.vt\_positives | numeric | 
action\_result\.data\.\*\.context\.malware\_types\.\* | string | 
action\_result\.data\.\*\.context\.redirections\.\* | string | 
action\_result\.data\.\*\.context\.categories\.\*\.id | numeric | 
action\_result\.data\.\*\.context\.categories\.\*\.name | string | 
action\_result\.data\.\*\.context\.indications\.\* | string | 
action\_result\.data\.\*\.context\.related\_ips\.\*\.ip | string |  `ip` 
action\_result\.data\.\*\.context\.related\_ips\.\*\.classification | string | 
action\_result\.data\.\*\.context\.related\_ips\.\*\.confidence | string | 
action\_result\.status | string | 
action\_result\.message | string | 
action\_result\.summary | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'ip reputation'
For an IP address returns its classification and risk in accessing a resource hosted on it

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**resource** |  required  | IP address | string |  `ip` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.resource | string |  `ip` 
action\_result\.data\.\*\.resource | string |  `ip` 
action\_result\.data\.\*\.risk | numeric | 
action\_result\.data\.\*\.status\.code | numeric | 
action\_result\.data\.\*\.status\.label | string | 
action\_result\.data\.\*\.status\.message | string | 
action\_result\.data\.\*\.reputation\.classification | string | 
action\_result\.data\.\*\.reputation\.severity | string | 
action\_result\.data\.\*\.reputation\.confidence | string | 
action\_result\.data\.\*\.context\.asn | numeric | 
action\_result\.data\.\*\.context\.as\_owner | string | 
action\_result\.data\.\*\.context\.location\.countryCode | string | 
action\_result\.data\.\*\.context\.location\.countryName | string | 
action\_result\.data\.\*\.context\.location\.region | string | 
action\_result\.data\.\*\.context\.location\.city | string | 
action\_result\.data\.\*\.context\.location\.postalCode | string | 
action\_result\.data\.\*\.context\.location\.latitude | numeric | 
action\_result\.data\.\*\.context\.location\.longitude | numeric | 
action\_result\.data\.\*\.context\.location\.dma\_code | numeric | 
action\_result\.data\.\*\.context\.location\.area\_code | numeric | 
action\_result\.data\.\*\.context\.location\.metro\_code | numeric | 
action\_result\.status | string | 
action\_result\.message | string | 
action\_result\.summary | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric |   

## action: 'file reputation'
For a file digest \(md5/sha1/sha256\) returns the risk in downloading the file without the need to scan it

Type: **investigate**  
Read only: **True**

#### Action Parameters
PARAMETER | REQUIRED | DESCRIPTION | TYPE | CONTAINS
--------- | -------- | ----------- | ---- | --------
**resource** |  required  | File Digest | string |  `md5`  `sha1`  `sha256` 

#### Action Output
DATA PATH | TYPE | CONTAINS
--------- | ---- | --------
action\_result\.parameter\.resource | string |  `md5`  `sha1`  `sha256` 
action\_result\.data\.\*\.resource | string |  `md5`  `sha1`  `sha256` 
action\_result\.data\.\*\.risk | numeric | 
action\_result\.data\.\*\.status\.code | numeric | 
action\_result\.data\.\*\.status\.label | string | 
action\_result\.data\.\*\.status\.message | string | 
action\_result\.data\.\*\.reputation\.classification | string | 
action\_result\.data\.\*\.reputation\.severity | string | 
action\_result\.data\.\*\.reputation\.confidence | string | 
action\_result\.data\.\*\.context\.malware\_family | string | 
action\_result\.data\.\*\.context\.protection\_name | string | 
action\_result\.data\.\*\.context\.malware\_types\.\* | string | 
action\_result\.data\.\*\.context\.metadata\.company\_name | string | 
action\_result\.data\.\*\.context\.metadata\.product\_name | string | 
action\_result\.data\.\*\.context\.metadata\.copyright | string | 
action\_result\.data\.\*\.context\.metadata\.original\_name | string | 
action\_result\.status | string | 
action\_result\.message | string | 
action\_result\.summary | string | 
summary\.total\_objects | numeric | 
summary\.total\_objects\_successful | numeric | 