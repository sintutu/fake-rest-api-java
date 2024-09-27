# Add Test Project

## Add Project with Maven

The intent of this section is to create the test project. I had intended to do so using `mvn` and having some command analogous to `dotnet new nunit` to use within `mvn`. It was a bit of a waste of time. See [here](./maven/add-test-project-with-maven.md) for my musings on this.

This resulted in running 

```bash
 mvn archetype:generate --define groupId=com.sintutu.fakeapitests --define artifactId=fakeapitests --define archetypeVersion=1.5 --define interactiveMode=false
 ```

 and then deleting the directory fakeapitests/src/main and all its children.

 
## Add Selenium

The first bit of work was adding the selenium dependency. That is documented in [Add Selenium Dependency](./selenium/add-selenium-dependency-to-test-project.md)

Next is to test that I can invoke selenium. For this I follow [Write your first Selenium script](https://www.selenium.dev/documentation/webdriver/getting_started/first_script/) and document in [Add first selenium test](./selenium/add-first-selenium-test.md)




