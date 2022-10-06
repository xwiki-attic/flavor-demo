Moved to xwiki-attic on 6th of October 2022, see https://forum.xwiki.org/t/remove-the-demo-flavor/10198

# Demo Flavor

Flavor demonstrating the capabilities of XWiki, featuring several recommended Extensions installed by default.

* Project Lead: [Vincent Massol](http://www.xwiki.org/xwiki/bin/view/XWiki/VincentMassol)
* [Documentation & Download](http://extensions.xwiki.org/xwiki/bin/view/Extension/Demo%20Flavor/)
* [Issue Tracker](https://jira.xwiki.org/browse/DEMOFLAVOR)
* Communication: [Mailing List](http://dev.xwiki.org/xwiki/bin/view/Community/MailingLists), [IRC](http://dev.xwiki.org/xwiki/bin/view/Community/IRC)
* [Development Practices](http://dev.xwiki.org)
* Minimal XWiki version supported: XWiki 9.5.1
* License: LGPL 2.1
* Translations: N/A
* Sonar Dashboard: N/A
* Continuous Integration Status: [![Build Status](http://ci.xwiki.org/job/XWiki%20Contrib/job/flavor-demo/job/master/badge/icon)](http://ci.xwiki.org/job/XWiki%20Contrib/job/flavor-demo/job/master/)

## Development Testing

If you're making changes to the sources and want to rebuild and test inside an XWiki runtime, perform the following:
* Build the flavor: `mvn clean install`
* Edit the `META-INF/extension.xed` file inside the XWiki WAR you're testing with and add the Demo flavor to the list
  of known flavors. Note that this is a hack since normally the canonical way would be to deploy the flavor in a 
  searchable XWiki Extensions Repository but that's a lot more complex and time-consuming.
  * Modify the `<xwiki.extension.knownFlavors>` tag to add the flavor id and version. For example:
  ```
  <xwiki.extension.knownFlavors>
    org.xwiki.platform:xwiki-platform-distribution-flavor-mainwiki/11.10,
    org.xwiki.platform:xwiki-platform-distribution-flavor-wiki/11.10,
    org.xwiki.contrib:flavor-demo/1.1-SNAPSHOT</xwiki.extension.knownFlavors>
  ```
* Add your local Maven repository as an Extension repository in the XWiki instance.
* Start or restart XWiki.
