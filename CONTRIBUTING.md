# CONTRIBUTING file for the KhronosGroup/glTF-Community project

Contributions to the KhronosGroup/glTF Community repository are welcome.

All contributions must be contained in a GitHub Pull Request (PR). Contributions 
are put into the "extensions/_prefix_" folder. Where _prefix_ is the text
string associated with your organization. The first PR submitted by a GitHub
account needs to execute the [glTF Community License Agreement (CLA)](./CLA.md). 
PRs that change extensions not owned by your organization will be denied. 
You will need to contact the copyright owner for those changes.

A _prefix_ is obtained using the following steps
1. Create a text file with these fields list below. There is an [example](.vendor/PREFIX_TEMPLATE.txt). The file structure is "Name: value", where "Name" is one of "Prefix", "Owner", or "Contact". The colon (:) is required. The value is your information. The file name is _prefix_.txt
    1. your requested prefix (in all CAPITAL letters)
    1. Owner oranization name
    1. Owner contact information (URL is best)
1. Create a pull request with only your _prefix_.txt file in the vendor directory.
1. Sign the CLA
1. If there are no conflicts with other names or Khronos policy, the PR will be approved - generally within one day.

All extension files go into the folder "extensions/_prefix_". The folder or each file should contain a copyright notice and licensing information. Note that the CLA may supersede some of your license terms. It is the vendor's responsibility to ensure consistency of the license in the extension and the CLA.


## Contributor License Agreement

When you propose a pull request on KhronosGroup/glTF you must execute the
Khronos Communbity Contributor License Agreement, to confirm you own
your work and are granting Khronos the necessary permissions to redistribute
it in this repository.
