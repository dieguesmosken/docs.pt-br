---
ms.openlocfilehash: 164d7a8277cf985735b959c73eb87391944e795b
ms.sourcegitcommit: cdb295dd1db589ce5169ac9ff096f01fd0c2da9d
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 06/09/2020
ms.locfileid: "84602897"
---

### <a name="install-the-sdk"></a><span data-ttu-id="e6eb9-101">Instalar o SDK</span><span class="sxs-lookup"><span data-stu-id="e6eb9-101">Install the SDK</span></span>

<span data-ttu-id="e6eb9-102">SDK do .NET Core permite que você desenvolva aplicativos com o .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e6eb9-102">.NET Core SDK allows you to develop apps with .NET Core.</span></span> <span data-ttu-id="e6eb9-103">Se você instalar SDK do .NET Core, não será necessário instalar o tempo de execução correspondente.</span><span class="sxs-lookup"><span data-stu-id="e6eb9-103">If you install .NET Core SDK, you don't need to install the corresponding runtime.</span></span> <span data-ttu-id="e6eb9-104">Para instalar o SDK do .NET Core, execute os seguintes comandos:</span><span class="sxs-lookup"><span data-stu-id="e6eb9-104">To install .NET Core SDK, run the following commands:</span></span>

```bash
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y dotnet-sdk-2.1
```

> [!IMPORTANT]
> <span data-ttu-id="e6eb9-105">Se você receber uma mensagem de erro semelhante a **não é possível localizar o pacote dotnet-SDK-2,1**, consulte a seção [solução de problemas da apt](#apt-troubleshooting) .</span><span class="sxs-lookup"><span data-stu-id="e6eb9-105">If you receive an error message similar to **Unable to locate package dotnet-sdk-2.1**, see the [APT troubleshooting](#apt-troubleshooting) section.</span></span>

### <a name="install-the-runtime"></a><span data-ttu-id="e6eb9-106">Instalar o runtime</span><span class="sxs-lookup"><span data-stu-id="e6eb9-106">Install the runtime</span></span>

<span data-ttu-id="e6eb9-107">O tempo de execução do .NET Core permite executar aplicativos que foram feitos com o .NET Core que não incluiu o tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="e6eb9-107">The .NET Core Runtime allows you to run apps that were made with .NET Core that didn't include the runtime.</span></span> <span data-ttu-id="e6eb9-108">Os comandos a seguir instalam o tempo de execução de ASP.NET Core, que é o tempo de execução mais compatível para o .NET Core.</span><span class="sxs-lookup"><span data-stu-id="e6eb9-108">The commands below install the ASP.NET Core Runtime, which is the most compatible runtime for .NET Core.</span></span> <span data-ttu-id="e6eb9-109">Em seu terminal, execute os comandos a seguir.</span><span class="sxs-lookup"><span data-stu-id="e6eb9-109">In your terminal, run the following commands.</span></span>

```bash
sudo apt-get update; \
  sudo apt-get install -y apt-transport-https && \
  sudo apt-get update && \
  sudo apt-get install -y aspnetcore-runtime-2.1
```

> [!IMPORTANT]
> <span data-ttu-id="e6eb9-110">Se você receber uma mensagem de erro semelhante a **não é possível localizar o pacote aspnetcore-Runtime-2,1**, consulte a seção [solução de problemas da apt](#apt-troubleshooting) .</span><span class="sxs-lookup"><span data-stu-id="e6eb9-110">If you receive an error message similar to **Unable to locate package aspnetcore-runtime-2.1**, see the [APT troubleshooting](#apt-troubleshooting) section.</span></span>

<span data-ttu-id="e6eb9-111">Como alternativa ao tempo de execução de ASP.NET Core, você pode instalar o tempo de execução do .NET Core que não inclui suporte a ASP.NET Core: substitua `aspnetcore-runtime-2.1` no comando acima por `dotnet-runtime-2.1` .</span><span class="sxs-lookup"><span data-stu-id="e6eb9-111">As an alternative to the ASP.NET Core Runtime, you can install the .NET Core Runtime that doesn't include ASP.NET Core support: replace `aspnetcore-runtime-2.1` in the command above with `dotnet-runtime-2.1`.</span></span>

```bash
sudo apt-get install -y dotnet-runtime-2.1
```