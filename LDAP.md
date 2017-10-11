## LDAP

> Resources related to `LDAP` protocol learning.

#### Overview 

`LDAP` (Lightweight Directory Access Protocol) - lightweight, standard-base, open protocol that describes communication behaviour with directory services over internet.

Ldap is service independent and support various types of directory services including but not limited to very popular `Microsoft ActiveDirectory`.

`directory service` - directory is very similar to database but instead it store attribute based entry related information in tree based structure.


An `LDAP` directory has a tree structure. All entries (called objects) of the directory have a defined position within this hierarchy. This hierarchy is called the directory information tree (DIT). 

The complete path to the desired entry, which unambiguously identifies it, is called distinguished name or DN. 

A single node along the path to this entry is called relative distinguished name or RDN. Objects can generally be assigned to certain possible types.


General structure overview:

<img src="https://www.pks.mpg.de/~mueller/docs/suse10.1/suselinux-manual_en/manual/images/ldap_tree.png" height="300px" width="500px">


Commonly Used Object Classes and Attributes



| Object Class       | Meaning                                                          | Example Entry | Compulsory Attributes |
| ------------------ | :--------------------------------------------------------------: | ------------: | --------------------- |
| dcObject           | domainComponent (name components of the domain)                  | suse          | dc                    |
| organizationalUnit | organizationalUnit (organizational unit)                         | doc           | ou                    |
| inetOrgPerson      | inetOrgPerson (person-related data for the intranet or Internet) | Geeko Linux   | sn and cn             |



#### Resources

 - Learning LDAP https://www.ldap.com/getting-started-with-ldap
 - Python3 LDAPv2/3 client http://ldap3.readthedocs.io/tutorial_intro.html#what-ldap-is-not

