# Telefrag

Telefrag is a .NET Core library for interacting with Telegram using its various APIs and rapid development of highly composable components.  The primary goal of Telefrag was to decouple Telegram's nuances from C# developers and create a C#-friendly way of tying existing apps into Telegram.  The secondary goal was to make it easy for normal users to run their own custom bots with pluggable personalities or "layers" which can be offered as part of an ecosystem.

See the [Telefrag wiki](https://github.com/nillkitty/Telefrag/wiki) for more information and documentation as development continues.

The scope of the Telefrag project has been refactored into these components/phases:

| Phase | Status | Package | Description |
|--|--|--|--|
| 1 | In Development | `Telefrag.Common`  | Common utilities and constructs;  required by all other packages.  |
| 1 | In Development | `Telefrag.Bots` | Bot API functionality;  exposes **Bot** which allows sending and receiving Updates and Events at a low level.  When using or deriving from Bot, all update handling,  string parsing,  state tracking, etc. must be done by the consumer.
| 2 | In Development | `Telefrag.Bots.Toolkit` | The **Toolkit** is a [layer](Layers) that adds higher level abstractions such as Command, Callback, Menu, Code, etc.
| 2 | In Development | `Telefrag.Data.SqlServer` | Allows use of a SQL Server as an ObjectStore
| 2 | In Development | `Telefrag.Security` | Provides the default authorization model/security framework
| 3 | Not Started | `Telefrag.Bots.Utility` | **UtilityBot** is a bot useful for diagnostics or learning the Telefrag framework.  It allows debug and diagsnotics access to Telefrag via Telegram.
| 4 | Not Started | `Telefrag.Clients` | Client API functionality;  exposes **Client** which allows connecting to Telegram as a full self-contained MTProto client.
| 5 | Not Started | `Telefrag.Hosting` | Provides the framework needed for hosting Telefrag as a dedicated service (including ASP.NET pipeline) with administrative control and management
| 6 | Not Started | `Telefrag.Hosts.ConsoleHost` | Console host (Kestrel/HTTP.sys)
| 6 | Not Started | `Telefrag.Hosts.ServiceHost` | Windows Service host (Kestrel/HTTP.sys)
| 6 | Not Started | `Telefrag.Hosts.IISHost` | IIS host
| 7 | Not Started | `Telefrag.UI.Web` | ASP.NET-powered web administration console
| 8 | Not Started | `Telefrag.UI.Studio` | WPF-powered thick administration console

