# ZipSlipNodeJS
Proof of Concept of Zip Slip Vulnerability
### Vulnerability Description
adm-zip npm library before 0.4.9 is vulnerable to directory traversal, allowing attackers to write to arbitrary files via a ../ (dot dot slash) in a Zip archive entry that is mishandled during extraction which will allow the attacker to overwrite important system files outside the desired extraction directory which may lead to RCE. This vulnerability is also known as 'Zip-Slip'.

*CVE :* CVE-2018-1002204

### Vulnerable Module Information 
* Name : adm-zip 
* Vulnerable versions : < 0.4.9
* Version tested during Proof of Concept : 0.4.7
* URL : https://www.npmjs.com/package/adm-zip/v/0.4.7

### Exploitation Methodology 
* An Attacker craft archive that holds directory traversal filenames (e.g. ../../../../../../../../../tmp/evil.sh) and during extraction process if the vulnerability exists a the file will be created/overwritten outside the desired directo.

### Reproduction Steps 
1) After Installing NodeJS and NPM followed by adm-zip 0.4.7.
2) ![alt text](https://raw.githubusercontent.com/GPUkiller/ZipSlipNodeJS/master/1.png)
