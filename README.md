# Telefrag

Telefrag is a cross-platform library, service, and suite of utilities that allow you to rapidly develop Telegram integrations (bots, payments, authentication) in either .NET or JavaScript with a toolkit full of ready-made reusable components.  Telefrag abstracts away all of Telegram's API details, persistent state and storage, webhooks, certificates, web server configuration, authentication/authorization, and more.  Make your bots highly-available by creating a multi-node cluster.

``` csharp
    public class RandomBot : FragBot
    {
        private Random RNG = new Random();

        [BotCommand(Description = "Gets a random number between 0 and 1.")]
        public async Task Random(Context c)
        {
            await c.Reply($"Random number: {RNG.Next()}");
        }

        [BotCommand(Description = "Gets a random number between min and max.")]
        [RequiredParam(0, "min")]
        [RequiredParam(1, "max")]
        public async Task Random(Context c, Argument min, Argument max)
        {
            await c.Reply($"Random number: {RNG.Next(min, max)}");
        }
    }
```
This example creates a bot that will accept either `/random` or `/random <min> <max>`, and will reply to the user's message directly with the result.   

The bot automatically will respond to `/start` and `/help` with appropriate replies without any required configuration.

## Notable Features 

* Rich class library including counters, timers, commands, callbacks, tracers, loggers, and so much more.
* Database access abstracted away.  Pluggable database provider framework allows custom data stores.
* Span bots across multiple nodes in a cluster/farm -- automatic state/config sync between cluster nodes with active/passive (default) and active/active (requires a load balancer or GSLB) modes
* Web UI included
* Native Telegram authentication, as well as Windows authentication for API and UI access
* Automatic webhook and polling system configures tests, configures, and manages webhooks for you with automatic certificate management
* Multiple-instance aware
* Fully asynchronous, cross-platform, and built on .NET Core 3.1

## Hosting

| Hosting Mode | Platforms | Description |
|--|--|--|
|**Command Line** | Windows, Linux, MacOS | Telefrag run self-hosted from a self-contained executable;  this allows you to spawn the process in the background on Linux and MacOS for use as a system service. <br /><br />Log events are written to stdout, and console commands can be entered from stdin.
|**Windows Service** | Windows | Telefrag runs self-hosted in a Windows Service. <br /><br />Useful for running on Windows as a standalone service (e.g. not as part of a website you're integrating with Telegram and/or bots with a UI)
|**IIS** | Windows | Add Telefrag to your own ASP.NET web application.  Telefrag seamlessly integrates into your application's request pipeline and allows you to directly integrate your web app with Telegram without any intermediary API.


