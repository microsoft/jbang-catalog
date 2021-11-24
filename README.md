# JBang Catalog

[JBang](https://jbang.dev) is an open source project that allows developers to script programs in Java, and optionally rely on dependencies hosted on Maven Central. Learn more about JBang from this [InfoQ article](https://www.infoq.com/news/2020/10/scripting-java-jbang/).

This repository hosts the catalog of Microsoft projects with support for JBang.

Before continuing, [install JBang](https://www.jbang.dev/download/).

To list the latest available artifacts in the Microsoft JBang's catalog, run the following:

```bash
$ jbang catalog list microsoft
```

Currently there are three projects:

- Minecraft Java Server
- Azure Application Insights Agent
- Playwright

## Minecraft Java Server

To start a Minecraft Java Server using JBang, follow these steps:

1. [Install JBang](https://www.jbang.dev/download/).
2. Create a folder `minecraft-server` and get into it on your terminal.
3. Read and accept the [Minecraft EULA](https://account.mojang.com/documents/minecraft_eula). To accept the EULA, create a local file named `eula.txt` with content `eula=true` inside.
4. Run the server:

```bash
~/minecraft-server $ echo "eula=true" > eula.txt
~/minecraft-server $ jbang minecraft-server@microsoft
```

Once you start the server, a `server.properties` file will be created for further customizations. [Learn more](https://help.minecraft.net/hc/en-us/articles/360058525452-How-to-Setup-a-Minecraft-Java-Edition-Server).

## Playwright

TODO

## Azure Application Insights

TODO

## Contributing

This project welcomes contributions and suggestions.  Most contributions require you to agree to a
Contributor License Agreement (CLA) declaring that you have the right to, and actually do, grant us
the rights to use your contribution. For details, visit https://cla.opensource.microsoft.com.

When you submit a pull request, a CLA bot will automatically determine whether you need to provide
a CLA and decorate the PR appropriately (e.g., status check, comment). Simply follow the instructions
provided by the bot. You will only need to do this once across all repos using our CLA.

This project has adopted the [Microsoft Open Source Code of Conduct](https://opensource.microsoft.com/codeofconduct/).
For more information see the [Code of Conduct FAQ](https://opensource.microsoft.com/codeofconduct/faq/) or
contact [opencode@microsoft.com](mailto:opencode@microsoft.com) with any additional questions or comments.

## Trademarks

This project may contain trademarks or logos for projects, products, or services. Authorized use of Microsoft 
trademarks or logos is subject to and must follow 
[Microsoft's Trademark & Brand Guidelines](https://www.microsoft.com/en-us/legal/intellectualproperty/trademarks/usage/general).
Use of Microsoft trademarks or logos in modified versions of this project must not cause confusion or imply Microsoft sponsorship.
Any use of third-party trademarks or logos are subject to those third-party's policies.
