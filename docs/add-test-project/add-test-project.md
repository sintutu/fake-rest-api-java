# Add Test Project

The intent of this section is to create the test project. I had intended to do so using `mvn` and having some command analogous to `dotnet new nunit` to use within `mvn`. It was a bit of a waste of time. See [here](add-test-project-with-maven.md) for my musings on this.

This resulted in running 

```bash
 mvn archetype:generate --define groupId=com.sintutu.fakeapitests --define artifactId=fakeapitests --define archetypeVersion=1.5 --define interactiveMode=false
 ```

 and then deleting the directory fakeapitests/src/main and all its children.

 


