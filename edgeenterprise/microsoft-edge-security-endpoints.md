---
title: Zulassungsliste für Microsoft Edge-Endpunkte
ms.author: kvice
author: dan-wesley
manager: srugh
ms.date: 11/25/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Zulassungsliste für Microsoft Edge-Endpunkte
ms.openlocfilehash: 3d46e2e8c85eadc39cf9788df44b45592ea4fb1b
ms.sourcegitcommit: ed6a5afabf909df87bec48671c4c47bcdfaeb7bc
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/02/2020
ms.locfileid: "11194689"
---
# <span data-ttu-id="35567-103">Zulassungsliste für Microsoft Edge-Endpunkte</span><span class="sxs-lookup"><span data-stu-id="35567-103">Allow list for Microsoft Edge endpoints</span></span>

<span data-ttu-id="35567-104">Microsoft Edge erfordert zur Unterstützung der zugehörigen Features eine Internetverbindung.</span><span class="sxs-lookup"><span data-stu-id="35567-104">Microsoft Edge requires connectivity to the Internet to support its features.</span></span> <span data-ttu-id="35567-105">In diesem Artikel werden die Domänen-URLs aufgeführt, die Sie der Zulassungsliste hinzufügen müssen, um die Kommunikation über Firewalls und andere Sicherheitsmechanismen sicherzustellen.</span><span class="sxs-lookup"><span data-stu-id="35567-105">This article identifies the domain URLs that you need to add to the Allow list to ensure communications through firewalls and other security mechanisms.</span></span>

> [!NOTE]
> <span data-ttu-id="35567-106">Dieser Artikel bezieht sich auf Microsoft Edge Version 77 oder neuer.</span><span class="sxs-lookup"><span data-stu-id="35567-106">This applies  to Microsoft Edge version 77 or later.</span></span>

## <span data-ttu-id="35567-107">Domänen-URLs für Zulassungsliste</span><span class="sxs-lookup"><span data-stu-id="35567-107">Domain URLs to allow</span></span>

<span data-ttu-id="35567-108">Lassen Sie die folgenden Domänen-URLs für Microsoft Edge zu.</span><span class="sxs-lookup"><span data-stu-id="35567-108">Allow the following domain URLs for Microsoft Edge.</span></span>

### <span data-ttu-id="35567-109">Updatedienst</span><span class="sxs-lookup"><span data-stu-id="35567-109">Update Service</span></span>

<span data-ttu-id="35567-110">Der Dienst, der Microsoft Edge verwendet, um nach neuen Updates zu suchen.</span><span class="sxs-lookup"><span data-stu-id="35567-110">The service that Microsoft Edge uses to check for new updates.</span></span>

- `https://msedge.api.cdp.microsoft.com`

### <span data-ttu-id="35567-111">Experimentier- und Konfigurationsservice</span><span class="sxs-lookup"><span data-stu-id="35567-111">Experimentation and Configuration service</span></span>

- `https://config.edge.skype.com`

### <span data-ttu-id="35567-112">Speicherorte für den Download von Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="35567-112">Download locations for Microsoft Edge</span></span>

<span data-ttu-id="35567-113">Speicherorte, von denen Microsoft Edge während einer Erstinstallation oder bei einem Update heruntergeladen werden kann.</span><span class="sxs-lookup"><span data-stu-id="35567-113">Locations Microsoft Edge can be downloaded from during an initial install or when an update is available.</span></span> <span data-ttu-id="35567-114">Der Downloadort wird vom Update Dienst festgelegt.</span><span class="sxs-lookup"><span data-stu-id="35567-114">The download location is determined by the Update Service.</span></span>

#### <span data-ttu-id="35567-115">HTTP</span><span class="sxs-lookup"><span data-stu-id="35567-115">HTTP</span></span>

- `http://msedge.f.tlu.dl.delivery.mp.microsoft.com`
- `http://msedge.f.dl.delivery.mp.microsoft.com`
- `http://msedge.b.tlu.dl.delivery.mp.microsoft.com`
- `http://msedge.b.dl.delivery.mp.microsoft.com`

#### <span data-ttu-id="35567-116">HTTPS</span><span class="sxs-lookup"><span data-stu-id="35567-116">HTTPS</span></span>

- `https://msedge.sf.tlu.dl.delivery.mp.microsoft.com`
- `https://msedge.sf.dl.delivery.mp.microsoft.com`
- `https://msedge.sb.tlu.dl.delivery.mp.microsoft.com`
- `https://msedge.sb.dl.delivery.mp.microsoft.com`

  > [!TIP]
  > <span data-ttu-id="35567-117">Zur Vereinfachung der Zulassungsliste für Downloadorte kann eine Wildcard verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="35567-117">To simplify the allow list for download locations a wild card can be used:</span></span> `*.dl.delivery.mp.microsoft.com`

### <span data-ttu-id="35567-118">Speicherorte für den Download von Erweiterungen für Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="35567-118">Download locations for Microsoft Edge Extensions</span></span>

<span data-ttu-id="35567-119">Speicherorte, von denen Microsoft Edge-Erweiterungen während einer Erstinstallation oder bei einem Update heruntergeladen werden können.</span><span class="sxs-lookup"><span data-stu-id="35567-119">Locations Microsoft Edge Extensions can be downloaded from during an initial install or when an update is available.</span></span> <span data-ttu-id="35567-120">Der Downloadort wird vom Update Dienst festgelegt.</span><span class="sxs-lookup"><span data-stu-id="35567-120">The download location is determined by the Update Service.</span></span>

#### <span data-ttu-id="35567-121">HTTP</span><span class="sxs-lookup"><span data-stu-id="35567-121">HTTP</span></span>

- `http://msedgeextensions.f.tlu.dl.delivery.mp.microsoft.com`
- `http://msedgeextensions.f.dl.delivery.mp.microsoft.com`
- `http://msedgeextensions.b.tlu.dl.delivery.mp.microsoft.com`
- `http://msedgeextensions.b.dl.delivery.mp.microsoft.com`

#### <span data-ttu-id="35567-122">HTTPS</span><span class="sxs-lookup"><span data-stu-id="35567-122">HTTPS</span></span>

- `https://msedgeextensions.sf.tlu.dl.delivery.mp.microsoft.com`
- `https://msedgeextensions.sf.dl.delivery.mp.microsoft.com`
- `https://msedgeextensions.sb.tlu.dl.delivery.mp.microsoft.com`
- `https://msedgeextensions.sb.dl.delivery.mp.microsoft.com`

  > [!TIP]
  > <span data-ttu-id="35567-123">Zur Vereinfachung der Zulassungsliste für Downloadorte kann eine Wildcard verwendet werden:</span><span class="sxs-lookup"><span data-stu-id="35567-123">To simplify the allow list for download locations a wild card can be used:</span></span> `*.dl.delivery.mp.microsoft.com`

### <span data-ttu-id="35567-124">Optional für die Download-Übermittlungsoptimierung</span><span class="sxs-lookup"><span data-stu-id="35567-124">Optionally for Download Delivery Optimization</span></span>

<span data-ttu-id="35567-125">Weitere Informationen zur Übermittlungsoptimierung finden Sie unter [Übermittlungsoptimierung für Windows 10-Updates](https://aka.ms/waas-do).</span><span class="sxs-lookup"><span data-stu-id="35567-125">For information about delivery optimization, see [Delivery Optimization for Windows 10 updates](https://aka.ms/waas-do).</span></span>

- <span data-ttu-id="35567-126">Kommunikation Client-zu-Dienst: `*.do.dsp.mp.microsoft.com` : (HTTP Port 80, HTTPS Port 443)</span><span class="sxs-lookup"><span data-stu-id="35567-126">Client to Service communication: `*.do.dsp.mp.microsoft.com` (HTTP Port 80, HTTPS Port 443)</span></span>
- <span data-ttu-id="35567-127">Kommunikation Client-zu-Client: TCP-Port 7680 muss für eingehenden Datenverkehr geöffnet sein</span><span class="sxs-lookup"><span data-stu-id="35567-127">Client to Client communication: TCP port 7680 should be open for inbound traffic</span></span>

### <span data-ttu-id="35567-128">Sync</span><span class="sxs-lookup"><span data-stu-id="35567-128">Sync</span></span>

<span data-ttu-id="35567-129">Diese Endpunkte verwalten das Lesen und Schreiben von synchronisierten Daten, die Rechteverwaltung für sichere Daten und die Benachrichtigung des Browsers, wenn neue Synchronisierungsdaten verfügbar sind.</span><span class="sxs-lookup"><span data-stu-id="35567-129">These endpoints manage the reading and writing of synced data, rights management for secure data, and notifying the browser when new sync data is available.</span></span>

- <span data-ttu-id="35567-130">Edge-Synchronisierungsdienst-Endpunkte:</span><span class="sxs-lookup"><span data-stu-id="35567-130">Edge sync service endpoints:</span></span>

  - `https://edge-enterprise.activity.windows.com`
  - `https://edge.activity.windows.com`

- <span data-ttu-id="35567-131">Azure Information Protection-Endpunkte:</span><span class="sxs-lookup"><span data-stu-id="35567-131">Azure Information Protection endpoints:</span></span>

  - `https://api.aadrm.com` <span data-ttu-id="35567-132">(für die meisten Mandanten)</span><span class="sxs-lookup"><span data-stu-id="35567-132">(for most tenants)</span></span>
  - `https://api.aadrm.de` <span data-ttu-id="35567-133">(für Mandanten in Deutschland)</span><span class="sxs-lookup"><span data-stu-id="35567-133">(for tenants in Germany)</span></span>
  - `https://api.aadrm.cn` <span data-ttu-id="35567-134">(für Mandanten in China)</span><span class="sxs-lookup"><span data-stu-id="35567-134">(for tenants in China)</span></span>

- [<span data-ttu-id="35567-135">Windows-Benachrichtigungsdienst-Endpunkte</span><span class="sxs-lookup"><span data-stu-id="35567-135">Windows Notification Service endpoints</span></span>](https://docs.microsoft.com/windows/uwp/design/shell/tiles-and-notifications/firewall-allowlist-config)

## <span data-ttu-id="35567-136">Andere Dienste zur Browserunterstützung</span><span class="sxs-lookup"><span data-stu-id="35567-136">Other browser support services</span></span>

<span data-ttu-id="35567-137">Stellen Sie Metadaten für Browser Features bereit, z.B. Tracking-Schutz, Zertifikatsperrlisten und Updates für Browserkomponenten.</span><span class="sxs-lookup"><span data-stu-id="35567-137">Provide metadata for browser features such as tracking protection, certificate revocation lists, and other browser component updates.</span></span> <span data-ttu-id="35567-138">Stellen Sie herunterladbare Rechtschreibwörterbücher und Listen zur Blockierung von Werbung bereit.</span><span class="sxs-lookup"><span data-stu-id="35567-138">Provide downloadable spellcheck dictionaries and ad-blocking block lists.</span></span> <span data-ttu-id="35567-139">Stellen Sie Dienste bereit, um Browserfeatures wie Sammlungen, AutoFill und Erweiterungsspeicher zu unterstützen.</span><span class="sxs-lookup"><span data-stu-id="35567-139">Provide services to support browser features such as collections, autofill, and extension store.</span></span>

- `http://edge.microsoft.com/`
- `https://edge.microsoft.com/`

## <span data-ttu-id="35567-140">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="35567-140">See also</span></span>

- [<span data-ttu-id="35567-141">Microsoft Edge Enterprise-Angebotsseite</span><span class="sxs-lookup"><span data-stu-id="35567-141">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
- [<span data-ttu-id="35567-142">Angebotsseite der Microsoft Edge-Dokumentation</span><span class="sxs-lookup"><span data-stu-id="35567-142">Microsoft Edge documentation landing page</span></span>](https://docs.microsoft.com/DeployEdge/)
- [<span data-ttu-id="35567-143">Verwalten von Verbindungsendpunkten für Windows 10 Enterprise, Version 1903</span><span class="sxs-lookup"><span data-stu-id="35567-143">Manage connection endpoints for Windows 10 Enterprise, version 1903</span></span>](https://docs.microsoft.com/windows/privacy/manage-windows-1903-endpoints)
