---
title: Microsoft Edge-Proxyeinstellungen
ms.author: brianalt
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: 'Verwenden von Befehlszeilenoptionen zum Konfigurieren von Proxyeinstellungen '
ms.openlocfilehash: 99a5f0776ea42f1e26050e0d30adb48a63907b8c
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2021
ms.locfileid: "11642161"
---
# <a name="how-to-use-microsoft-edge-command-line-options-to-configure-proxy-settings"></a><span data-ttu-id="cd1c4-103">So verwenden Sie Microsoft Edge-Befehlszeilenoptionen zum Konfigurieren von Proxyeinstellungen</span><span class="sxs-lookup"><span data-stu-id="cd1c4-103">How to use Microsoft Edge command-line options to configure proxy settings</span></span>

<span data-ttu-id="cd1c4-104">In diesem Artikel wird beschrieben, wie Sie mithilfe von Befehlszeilenoptionen die Standardnetzwerkeinstellungen des Systems überschreiben können.</span><span class="sxs-lookup"><span data-stu-id="cd1c4-104">This article describes how you can use command-line options to override the default system network settings.</span></span>

>[!NOTE]
><span data-ttu-id="cd1c4-105">Dieser Artikel bezieht sich auf Microsoft Edge Version 77 oder höher.</span><span class="sxs-lookup"><span data-stu-id="cd1c4-105">This article applies to Microsoft Edge version 77 or later.</span></span>

## <a name="system-network-settings"></a><span data-ttu-id="cd1c4-106">Netzwerkeinstellungen des Systems</span><span class="sxs-lookup"><span data-stu-id="cd1c4-106">System network settings</span></span>

<span data-ttu-id="cd1c4-107">Der Microsoft Edge-Netzwerkstapel verwendet standardmäßig die Netzwerkeinstellungen des Systems.</span><span class="sxs-lookup"><span data-stu-id="cd1c4-107">The Microsoft Edge network stack uses the system network settings by default.</span></span> <span data-ttu-id="cd1c4-108">Zu diesen Einstellungen gehören *Proxyeinstellungen* sowie *Zertifikat- und private Schlüsselspeicher*.</span><span class="sxs-lookup"><span data-stu-id="cd1c4-108">These settings include *proxy settings*, and *certificate and private key stores*.</span></span>

<span data-ttu-id="cd1c4-109">Es gibt Szenarien, in denen Benutzer eine Alternative zur Verwendung der Standardproxyeinstellungen des Systems anfordern.</span><span class="sxs-lookup"><span data-stu-id="cd1c4-109">There are scenarios where users request an alternative to using the system's default proxy settings.</span></span> <span data-ttu-id="cd1c4-110">Zur Unterstützung dieser Szenarien unterstützt Microsoft Edge Befehlszeilenoptionen, mit denen Sie benutzerdefinierte Proxyeinstellungen konfigurieren können.</span><span class="sxs-lookup"><span data-stu-id="cd1c4-110">To support these scenarios, Microsoft Edge supports command-line options that you can use to configure custom proxy settings.</span></span>

<span data-ttu-id="cd1c4-111">Diese Befehlszeilenoptionen entsprechen den folgenden Richtlinien in der **Proxyserver**-Gruppe:</span><span class="sxs-lookup"><span data-stu-id="cd1c4-111">These command-line options correspond to the following policies in the **Proxy server** group:</span></span>

- [<span data-ttu-id="cd1c4-112">ProxyBypassList</span><span class="sxs-lookup"><span data-stu-id="cd1c4-112">ProxyBypassList</span></span>](./microsoft-edge-policies.md#proxybypasslist)
- [<span data-ttu-id="cd1c4-113">ProxyMode</span><span class="sxs-lookup"><span data-stu-id="cd1c4-113">ProxyMode</span></span>](./microsoft-edge-policies.md#proxymode)
- [<span data-ttu-id="cd1c4-114">ProxyPacUrl</span><span class="sxs-lookup"><span data-stu-id="cd1c4-114">ProxyPacUrl</span></span>](./microsoft-edge-policies.md#proxypacurl)
- [<span data-ttu-id="cd1c4-115">ProxyServer</span><span class="sxs-lookup"><span data-stu-id="cd1c4-115">ProxyServer</span></span>](./microsoft-edge-policies.md#proxyserver)
- [<span data-ttu-id="cd1c4-116">ProxySettings</span><span class="sxs-lookup"><span data-stu-id="cd1c4-116">ProxySettings</span></span>](./microsoft-edge-policies.md#proxysettings)

## <a name="command-line-options-for-proxy-settings"></a><span data-ttu-id="cd1c4-117">Befehlszeilenoptionen für Proxyeinstellungen</span><span class="sxs-lookup"><span data-stu-id="cd1c4-117">Command-line options for proxy settings</span></span>

<span data-ttu-id="cd1c4-118">Microsoft Edge unterstützt die folgenden proxybezogenen Befehlszeilenoptionen.</span><span class="sxs-lookup"><span data-stu-id="cd1c4-118">Microsoft Edge supports the following proxy-related command-line options.</span></span>

 **`--no-proxy-server`**
 
<span data-ttu-id="cd1c4-119">Weist Microsoft Edge an, keinen Proxy zu verwenden, auch wenn das System anderweitig für die Verwendung eines Proxys konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="cd1c4-119">Tells Microsoft Edge not to use a Proxy, even if the system is otherwise configured to use one.</span></span> <span data-ttu-id="cd1c4-120">Es werden alle anderen bereitgestellten Proxyeinstellungen außer Kraft gesetzt.</span><span class="sxs-lookup"><span data-stu-id="cd1c4-120">It overrides any other proxy settings that are provided.</span></span>

**`--proxy-auto-detect`**

<span data-ttu-id="cd1c4-121">Weist Microsoft Edge an, Ihre Proxykonfiguration zu testen und automatisch zu erkennen.</span><span class="sxs-lookup"><span data-stu-id="cd1c4-121">Tells Microsoft Edge to try and automatically detect your proxy configuration.</span></span> <span data-ttu-id="cd1c4-122">Dieses Argument wird ignoriert, wenn `--proxy-server` konfiguriert ist.</span><span class="sxs-lookup"><span data-stu-id="cd1c4-122">This argument is ignored if `--proxy-server` is configured.</span></span>

**`--proxy-server=<scheme>=<uri>[:<port>][;...] | <uri>[:<port>] | "direct://"`**

<span data-ttu-id="cd1c4-123">Weist Microsoft Edge an, eine benutzerdefinierte Proxykonfiguration zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="cd1c4-123">Tells Microsoft Edge to use a custom proxy configuration.</span></span> <span data-ttu-id="cd1c4-124">Sie können eine benutzerdefinierte Proxykonfiguration auf drei Arten angeben.</span><span class="sxs-lookup"><span data-stu-id="cd1c4-124">You can specify a custom proxy configuration in three ways.</span></span>

1. <span data-ttu-id="cd1c4-125">Stellen Sie eine durch Semikola getrennte Zuordnung des Listenschemas zu URL/Port-Paaren bereit.</span><span class="sxs-lookup"><span data-stu-id="cd1c4-125">Provide a semicolon-separated mapping of list scheme to url/port pairs.</span></span> <span data-ttu-id="cd1c4-126">Beispielsweise weist `--proxy-server="http=proxy1:8080;ftp=ftpproxy"` Microsoft Edge an, den HTTP-Proxy „proxy1: 8080” für http-URLs und den HTTP-Proxy „ftpproxy: 80” für ftp-URLs zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="cd1c4-126">For example, `--proxy-server="http=proxy1:8080;ftp=ftpproxy"` tells Microsoft Edge to use HTTP proxy "proxy1:8080" for http URLs and HTTP proxy "ftpproxy:80" for ftp URLs.</span></span>
2. <span data-ttu-id="cd1c4-127">Indem ein einzelner URI mit optionalem Port für alle URLs bereitgestellt wird.</span><span class="sxs-lookup"><span data-stu-id="cd1c4-127">By providing a single uri with optional port to use for all URLs.</span></span> <span data-ttu-id="cd1c4-128">Beispielsweise verwendet `--proxy-server="proxy2:8080"` den Proxy unter „proxy2: 8080” für den gesamten Datenverkehr.</span><span class="sxs-lookup"><span data-stu-id="cd1c4-128">For example, `--proxy-server="proxy2:8080"` will use the proxy at "proxy2:8080" for all traffic.</span></span>
3. <span data-ttu-id="cd1c4-129">Mit dem speziellen Wert „direct://”.</span><span class="sxs-lookup"><span data-stu-id="cd1c4-129">By using the special "direct://" value.</span></span> <span data-ttu-id="cd1c4-130">Beispielsweise stellt `--proxy-server="direct://"` sicher, dass keine der Verbindungen einen Proxy verwendet.</span><span class="sxs-lookup"><span data-stu-id="cd1c4-130">For example, `--proxy-server="direct://"` will make all connections not use a proxy.</span></span> 

>[!NOTE]
><span data-ttu-id="cd1c4-131">Sie können Microsoft Edge so konfigurieren, dass versucht wird, einen Proxy zu verwenden, und dass ein Fallback ausgeführt wird, wenn der Proxy nicht verfügbar ist.</span><span class="sxs-lookup"><span data-stu-id="cd1c4-131">You can configure Microsoft Edge to try using a proxy and fallback to going direct if the proxy isn't available.</span></span> <span data-ttu-id="cd1c4-132">Beispiel: `--proxy-server="http://proxy2:8080,direct://`.</span><span class="sxs-lookup"><span data-stu-id="cd1c4-132">For example, `--proxy-server="http://proxy2:8080,direct://`.</span></span>

**`--proxy-bypass-list=(<trailing_domain>|<ip-address>)[:<port>][;...]`**

<span data-ttu-id="cd1c4-133">Weist Microsoft Edge an, alle angegebenen Proxys für die angegebene durch Semikola getrennte Liste der Hosts zu umgehen.</span><span class="sxs-lookup"><span data-stu-id="cd1c4-133">Tells Microsoft Edge to bypass any specified proxy for the specified semicolon-separated list of hosts.</span></span> <span data-ttu-id="cd1c4-134">Dieses Kennzeichen muss mit `--proxy-server` verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cd1c4-134">This flag must be used with `--proxy-server`.</span></span>

>[!NOTE]
><span data-ttu-id="cd1c4-135">Für den Abgleich von nachgestellten Domänen sind keine „.”-Trennzeichen erforderlich. Die Trennzeichen „\*microsoft.com” stimmen mit „imicrosoft.com” überein.</span><span class="sxs-lookup"><span data-stu-id="cd1c4-135">Trailing-domain matching doesn't require "." separators, "\*microsoft.com" will match "imicrosoft.com".</span></span> <span data-ttu-id="cd1c4-136">Beispielsweise verwendet `--proxy-server="proxy2:8080" --proxy-bypass-list="*.microsoft.com;*example.com;127.0.0.1:8080"` den Proxyserver „proxy2” auf Port 8080 für alle Hosts, mit Ausnahme der Anforderungen für \*.microsoft.com, example.com und 127.0.0.1 auf Port 8080.</span><span class="sxs-lookup"><span data-stu-id="cd1c4-136">For example, `--proxy-server="proxy2:8080" --proxy-bypass-list="*.microsoft.com;*example.com;127.0.0.1:8080"` will use the proxy server "proxy2" on port 8080 for all hosts except requests for \*.microsoft.com, example.com, and 127.0.0.1 on port 8080.</span></span> <span data-ttu-id="cd1c4-137">Im vorherigen Beispiel werden imicrosoft.com-Anforderungen weiterhin mit Proxys übertragen.</span><span class="sxs-lookup"><span data-stu-id="cd1c4-137">In the previous example, imicrosoft.com requests will still be proxied.</span></span> <span data-ttu-id="cd1c4-138">Allerdings werden iexample.com-Anforderungen den Proxy umgehen, da \*example.com anstelle von \*.example.com angegeben wurde.</span><span class="sxs-lookup"><span data-stu-id="cd1c4-138">However, iexample.com requests will bypass the proxy because \*example.com was specified instead of \*.example.com.</span></span>

**`--proxy-pac-url=<pac-file-url>`**

<span data-ttu-id="cd1c4-139">Weist Microsoft Edge an, die PAC-datei unter der angegebenen URL zu verwenden.</span><span class="sxs-lookup"><span data-stu-id="cd1c4-139">Tells Microsoft Edge to use the PAC file at the specified URL.</span></span> <span data-ttu-id="cd1c4-140">Beispielsweise weist `--proxy-pac-url="https://wpad/proxy.pac"` Microsoft Edge an, Proxyinformationen für URL-Anforderungen mithilfe der **proxy.pac**-Datei aufzulösen.</span><span class="sxs-lookup"><span data-stu-id="cd1c4-140">For example, `--proxy-pac-url="https://wpad/proxy.pac"` tells Microsoft Edge to resolve proxy information for URL requests using the **proxy.pac** file.</span></span>

## <a name="content-license"></a><span data-ttu-id="cd1c4-141">Lizenz für Inhalte</span><span class="sxs-lookup"><span data-stu-id="cd1c4-141">Content license</span></span>

> [!NOTE]
> <span data-ttu-id="cd1c4-142">Teile dieser Seite sind Änderungen, die auf von Chromium.org erstellten und freigegebenen Werken basieren und gemäß den in der [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/) beschriebenen Begriffen verwendet werden.</span><span class="sxs-lookup"><span data-stu-id="cd1c4-142">Portions of this page are modifications based on work created and shared by Chromium.org and used according to terms described in the [Creative Commons Attribution 4.0 International License](http://creativecommons.org/licenses/by/4.0/).</span></span> <span data-ttu-id="cd1c4-143">Die Originalseite von Chromium finden Sie [hier](https://www.chromium.org/developers/design-documents/network-settings#TOC-Command-line-options-for-proxy-sett).</span><span class="sxs-lookup"><span data-stu-id="cd1c4-143">The original page can be found [here](https://www.chromium.org/developers/design-documents/network-settings#TOC-Command-line-options-for-proxy-sett).</span></span>
  
<a rel="license" href="http://creativecommons.org/licenses/by/4.0/"><img alt="Creative Commons License" style="border-width:0" src="https://i.creativecommons.org/l/by/4.0/88x31.png" /></a><br /><span data-ttu-id="cd1c4-144">Diese Arbeit unterliegt einer <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.</span><span class="sxs-lookup"><span data-stu-id="cd1c4-144">This work is licensed under a <a rel="license" href="http://creativecommons.org/licenses/by/4.0/">Creative Commons Attribution 4.0 International License</a>.</span></span>

## <a name="see-also"></a><span data-ttu-id="cd1c4-145">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="cd1c4-145">See also</span></span>

- <span data-ttu-id="cd1c4-146">Informationen zu erweiterten Konfigurationseinstellungen und zusätzlichen Optionen finden Sie in der [Proxy-Dokumentation](https://chromium.googlesource.com/chromium/src/+/HEAD/net/docs/proxy.md) des Chromium Open Source-Projekts.</span><span class="sxs-lookup"><span data-stu-id="cd1c4-146">To see advanced configuration settings and additional options, consult the [proxy documentation](https://chromium.googlesource.com/chromium/src/+/HEAD/net/docs/proxy.md) in the Chromium Open Source project.</span></span>
- [<span data-ttu-id="cd1c4-147">Microsoft Edge Enterprise-Angebotsseite</span><span class="sxs-lookup"><span data-stu-id="cd1c4-147">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)