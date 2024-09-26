# Awesome .NET Testing
Inspired by [awesome-dotnet-core](https://github.com/thangchung/awesome-dotnet-core), [awesome-dotnet](https://github.com/quozd/awesome-dotnet). Contributions are always welcome! 

### Not included
* Language agnostic external tools written in .NET: load generators, reports etc.
* Long-dead projects, .NET Framework-only projects.
* Purely commercial products without a free version (a free trial doesn't count).

### Legend
**[~]** – May not be actively maintained at the moment, but still has community value and runs on modern .NET.

**[$]** – Has a paid "pro" version, restrictive license, or closed source code.

### Contents
- [Test frameworks overview](#test-frameworks-overview)
- [Architecture](#architecture)
- [Assertions](#assertions)
- [Behavior Driven Development (BDD)](#behavior-driven-development-bdd)
- [Code coverage](#code-coverage)
  - [Coverage collection](#coverage-collection)
  - [Coverage visualization](#coverage-visualization)
- [Fake data generators](#fake-data-generators)
- [Mocks](#mocks)
  - [General purpose](#general-purpose)
  - [Specific](#specific)
- [Mutations](#mutations)
- [Random \& fuzzy testing](#random--fuzzy-testing)
- [Security](#security)
- [Snapshots](#snapshots)
- [Web UI test automation](#web-ui-test-automation)
- [Uncategorized](#uncategorized)
- [Appendix I. xUnit extensions](#appendix-i-xunit-extensions)


### Test frameworks overview
* The Big Three: [MSTest](https://github.com/microsoft/testfx), [NUnit](https://github.com/nunit/nunit), [xUnit](https://github.com/xunit/xunit).

* [Fixie](https://github.com/fixie/fixie) – A test framework similar to NUnit and xUnit, but with an emphasis on low-ceremony defaults and flexible customization.

### Architecture
* [ArchUnitNET](https://github.com/TNG/ArchUnitNET) – A library for checking the dependencies between classes, members, interfaces, and more.
* [NetArchTest](https://github.com/BenMorris/NetArchTest) – A library for creating tests that enforce conventions for class design, naming and dependency in .NET code bases.

### Assertions
* [ExpressionToCode](https://github.com/EamonNerbonne/ExpressionToCode) – A library that generates valid, readable C# from an expression tree, inspired by PowerAssert.NET. 
* [Fluent Assertions](https://github.com/fluentassertions/fluentassertions) – A set of extension methods that allow you to more naturally specify the expected outcome of a TDD or BDD-style unit tests.
* [NFluent](https://github.com/tpierrain/NFluent) – An assertion library which aims to fluent your .NET TDD experience.
* [PowerAssert.NET](https://github.com/PowerAssert/PowerAssert.Net) – A .NET port of Groovy's PowerAssert. It prints an easy-to-understand decomposition of your assertion's expression tree (with values) whenever an assertion fails.
* [Shouldly](https://github.com/shouldly/shouldly) – An assertion framework which focuses on giving great error messages when the assertion fails while being simple and terse.

### Behavior Driven Development (BDD)
* [BDTest](https://github.com/thomhurst/BDTest) – A testing and reporting framework focusing on "Behaviour Driven Testing" ideology. It can be used with other frameworks (such as MSTest, xUnit or NUnit) or standalone. Think of BDTest as a pure code-based alternative to SpecFlow.
* [LightBDD](https://github.com/LightBDD/LightBDD) – A framework for writing tests that are easy to read, easy to track during execution and summarize in user friendly report.
* [Machine.Specifications (MSpec)](https://github.com/machine/machine.specifications) – A "context/specification" test framework. **[~]**
* [SpecFlow](https://github.com/SpecFlowOSS/SpecFlow) – Cucumber for .NET. It provides test automation based on the Gherkin specification language and integrates to Visual Studio. **[~]**

### Code coverage
#### Coverage collection
* [.NET built-in coverage data collector](https://learn.microsoft.com/en-us/dotnet/core/tools/dotnet-test#:~:text=in%20your%20project.-,%2D%2Dcollect%20%3CDATA_COLLECTOR_NAME%3E,-Enables%20data%20collector) – Can be called by `dotnet test --collect "Code Coverage"` command. To avoid confusion with `dotnet-coverage` please visit [this thread](https://devblogs.microsoft.com/dotnet/whats-new-in-our-code-coverage-tooling/?commentid=20263#comment-20263).
* [AltCover](https://github.com/SteveGilham/altcover) – Instrumenting coverage tool for .NET and Mono.
* [coverlet](https://github.com/tonerdo/coverlet) – A cross platform code coverage framework for .NET, with support for line, branch and method coverage.
* [dotnet-coverage](https://learn.microsoft.com/en-us/dotnet/core/additional-tools/dotnet-coverage) – A utility for collection coverage data of a running process, merging of coverage reports, binary `.coverage` file convertation. 
* [JetBrains.dotCover.CommandLineTools](https://www.jetbrains.com/help/dotcover/Running_Coverage_Analysis_from_the_Command_LIne.html) – A console tool that allows you to run coverage analysis of unit tests or applications using the command-line prompt. 
* [Microsoft.CodeCoverage.Console](https://learn.microsoft.com/en-us/visualstudio/test/microsoft-code-coverage-console-tool?view=vs-2022) – A closed-source coverage collector, available only with Visual Studio Enterprise. **[$]** 
* [MiniCover](https://github.com/lucaslorentz/minicover) – A minimalist code coverage tool for .NET.

#### Coverage visualization
* Visual Studio: 
  * [FineCodeCoverage](https://github.com/FortuneN/FineCodeCoverage) – Free Visual Studio extension for test code coverage visualization.
  * CodeRush.
  * ReSharper + dotCover.
  * Built-in support in Enterprise version.
* Rider: built-in support.
* VSCode: [Coverage Gutters](https://marketplace.visualstudio.com/items?itemName=ryanluker.vscode-coverage-gutters) extension.

### Fake data generators
* [AutoFixture](https://github.com/AutoFixture/AutoFixture) – minimize the 'Arrange' phase of your unit tests by automating non-relevant setup. Auto-injecting mocks, auto-generation of test cases etc.
* [Bogus](https://github.com/bchavez/Bogus) – A simple fake data generator. It is fundamentally a C# port of faker.js and inspired by FluentValidation's syntax sugar.
* [GenFu](https://github.com/MisterJames/GenFu) – Smartly building up objects to use for test and prototype data. It will walk your object graph and fill in the properties on your type with realistic looking data. **[~]** 

### Mocks
#### General purpose
* [FakeItEasy](https://github.com/FakeItEasy/FakeItEasy) – A .NET dynamic fake library for creating all types of fake objects, mocks, stubs etc.
* [JustMock](https://www.telerik.com/products/mocking.aspx) – A flexible and complete mocking tool for crafting unit tests. **[$]** 
* [Moq](https://github.com/Moq/moq4) – Most popular, mock both interfaces and classes, strong-typed, has IntelliSense integration, no Record/Replay idioms.
* [NSubstitute](https://github.com/nsubstitute/nsubstitute) – A friendly substitute for .NET mocking libraries.

#### Specific
* [mockhttp](https://github.com/richardszalay/mockhttp) – Testing layer for Microsoft's HttpClient library.
* [Moq.Contrib.HttpClient](https://github.com/maxkagamine/Moq.Contrib.HttpClient) – A set of extension methods for mocking HttpClient and IHttpClientFactory with Moq.
* [netDumbster](https://github.com/cmendible/netDumbster) – A fake SMTP server.
* [Stubbery](https://markvincze.github.io/Stubbery/) – A library for creating and running Web API stubs in .NET.

### Mutations
* [Stryker.NET](https://github.com/stryker-mutator/stryker-net) – Mutation testing tool. It allows you to test your tests by temporarily inserting bugs in your source code. [HowTo](https://engincanv.github.io/c%23/.net/stryker/2024/02/10/mutation-testing-in-c-sharp-with-stryker.html).

### Random & fuzzy testing
* [CsCheck](https://github.com/AnthonyLloyd/CsCheck) – C# random testing library inspired by QuickCheck.
* [FsCheck](https://github.com/fscheck/FsCheck) – F# random testing library inspired by QuickCheck.
* [SharpFuzz](https://github.com/Metalnem/sharpfuzz) – AFL-based fuzz testing for .NET. [The basics of fuzzy testing](https://xebia.com/blog/fuzzing-in-c/).

### Security
* [HCL AppScan CodeSweep](https://marketplace.visualstudio.com/items?itemName=HCLTechnologies.hclappscancodesweep) – SAST extension for Visual Studio Code.
* [PVS-Studio](https://pvs-studio.com/) – SAST. [Free for OSS](https://pvs-studio.com/en/order/open-source-license/). **[$]**
* [snyk.io](https://snyk.io/product/snyk-code/) – SAST. Free for [individual developers and small teams](https://snyk.io/plans/). **[$]**
* [SonarQube](https://www.sonarsource.com/products/sonarqube/) – SAST. Community Edition is [free & open source](https://www.sonarsource.com/open-source-editions/sonarqube-community-edition/). **[$]**

### Snapshots
* [Snapshooter](https://github.com/SwissLife-OSS/snapshooter) – A snapshot tool based on the idea of [Jest Snapshot Testing](https://jestjs.io/docs/en/snapshot-testing/).
* [Verify](https://github.com/VerifyTests/Verify) – A snapshot tool to simplify the assertion of complex data models and documents.

### Web UI test automation
* [Atata](https://github.com/atata-framework/atata) – A full-featured framework based on Selenium WebDriver.
* [PuppeteerSharp](https://github.com/hardkoded/puppeteer-sharp) – A multi-purpose browser automation library.
* [Telerik Test Studio](https://docs.telerik.com/teststudio/welcome) – Functional UI, load/performance and API testing for web and WPF desktop applications. It is not based on Selenium or other Open Source frameworks but on the Telerik Testing Framework (proprietary). **[$]**

### Uncategorized
* [NCrunch](https://www.ncrunch.net/) – Automatic concurrent (live) testing for Visual Studio and JetBrains Rider. **[$]**
* [Expecto](https://github.com/haf/expecto) – A Smooth Testing framework for F# with tests as values. Unit testing, property based testing, performance testing and stress testing.
* [FlaUI](https://github.com/FlaUI/FlaUI) – Automated UI testing of Windows applications (Win32, WinForms, WPF, Store Apps etc.).
* [Fuchu](https://github.com/mausch/Fuchu) – A unit-testing library for F# with tests-as-values which makes DSLs extremely easy to create. **[~]**
* [Meziantou.Extensions.Logging.InMemory](https://github.com/meziantou/Meziantou.Framework) - Log verification for Microsoft.Extensions.Logging.ILogger.
* [MyTested.AspNetCore.Mvc](https://github.com/ivaylokenov/MyTested.AspNetCore.Mvc) – A strongly-typed unit testing library providing an easy fluent interface to test the ASP.NET Core, perfectly suitable for both MVC and API scenarios.
* [ReportPortal](https://github.com/reportportal/reportportal) – AI-powered test automation dashboard: real-time analytics, test results visualization, machine learning. **[$]** 
* [Serilog.Sinks.InMemory](https://github.com/serilog-contrib/SerilogSinksInMemory) - Log verification for [Serilog](https://serilog.net/).
* [Testcontainers](https://github.com/testcontainers/testcontainers-dotnet) – A library to support tests with throwaway instances of Docker containers. It is built on top of the .NET Docker remote API and provides a lightweight implementation to support your test environment.

### Appendix I. xUnit extensions
* [ReSharper Live Templates for xUnit.net](https://github.com/JetBrains/resharper-xunit-templates) - Add various Live Templates for xUnit.net to ReSharper.
* [Xunit.Categories](https://github.com/brendanconnolly/Xunit.Categories) - Friendlier attributes to help categorize your tests.
* [Xunit.Combinatorial](https://github.com/AArnott/Xunit.Combinatorial) - Parameterize your Xunit test methods: auto-generate parameters, generate all parameter combinations, or randomly generate values.
* [Xunit.DependencyInjection](https://github.com/pengweiqhca/Xunit.DependencyInjection) - Use Microsoft.Extensions.DependencyInjection to resolve xUnit test cases.
* [Xunit.SkippableFact](https://github.com/AArnott/Xunit.SkippableFact) - Report a "skipped" result in run time.
