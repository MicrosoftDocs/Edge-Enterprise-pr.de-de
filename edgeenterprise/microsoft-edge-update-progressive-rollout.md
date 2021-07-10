---
title: Progressive Rollouts für Microsoft Edge Stable-Kanal-Updates
ms.author: aguta
author: dan-wesley
manager: srugh
ms.date: 06/29/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
description: Progressive Rollouts für Microsoft Edge Stable-Kanal-Updates
ms.openlocfilehash: bdcefdc118125d67057fa77513bd732cff6882e3
ms.sourcegitcommit: bce02a5ce2617bb37ee5d743365d50b5fc8e4aa1
ms.translationtype: MT
ms.contentlocale: de-DE
ms.lasthandoff: 07/09/2021
ms.locfileid: "11642291"
---
# <a name="progressive-rollouts-for-microsoft-edge-stable-channel-updates"></a><span data-ttu-id="54615-103">Progressive Rollouts für Microsoft Edge Stable-Kanal-Updates</span><span class="sxs-lookup"><span data-stu-id="54615-103">Progressive rollouts for Microsoft Edge Stable channel updates</span></span>

<span data-ttu-id="54615-104">Beginnend mit Microsoft Edge, Version 83 werden wir schrittweise Rollouts der wichtigsten Updates für den Microsoft Edge Stable-Kanal über einen Zeitraum von wenigen Tagen durchführen.</span><span class="sxs-lookup"><span data-stu-id="54615-104">Starting with Microsoft Edge 83 release, we will perform gradual rollouts of major updates to Microsoft Edge Stable channel over the span of a few days.</span></span> <span data-ttu-id="54615-105">Dieses progressive Rollout ermöglicht es uns, Upgrades zu überwachen und den Browser organisationsweit sicher zu aktualisieren.</span><span class="sxs-lookup"><span data-stu-id="54615-105">This progressive rollout allows us to monitor upgrades and safely update the browser across the organization.</span></span>

> [!NOTE]
> <span data-ttu-id="54615-106">Dieser Artikel bezieht sich auf den Microsoft Edge Stable-Kanal (Version 83 oder höher).</span><span class="sxs-lookup"><span data-stu-id="54615-106">This applies to Microsoft Edge Stable channel version 83 or later.</span></span>

## <a name="why-do-we-need-progressive-rollout"></a><span data-ttu-id="54615-107">Warum sind progressive Rollouts erforderlich?</span><span class="sxs-lookup"><span data-stu-id="54615-107">Why do we need progressive rollout?</span></span>

<span data-ttu-id="54615-108">Durch eine genaue Überwachung des Status unserer Updates und das Rollout derselben über einen Zeitraum von mehreren Tagen können wir die Auswirkungen von Problemen begrenzen, die evtl. im Zusammenhang mit einem neuen Update auftreten.</span><span class="sxs-lookup"><span data-stu-id="54615-108">By monitoring the health of our updates closely and rolling out the updates over the course of several days, we can limit the impact of issues that might occur with the new update.</span></span> <span data-ttu-id="54615-109">Ab Microsoft Edge, Version 83 werden progressive Rollouts für alle Windows 7-, Windows 8- und 8.1- sowie Windows 10-Versionen von Microsoft Edge aktiviert.</span><span class="sxs-lookup"><span data-stu-id="54615-109">With Microsoft Edge release 83, Progressive Rollouts will be enabled for all Windows 7, Windows 8 & 8.1, and Windows 10 versions of Microsoft Edge.</span></span> <span data-ttu-id="54615-110">Sobald verfügbar wird auch Microsoft Edge auf dem Mac unterstützt.</span><span class="sxs-lookup"><span data-stu-id="54615-110">We will support Microsoft Edge on Mac as soon as it is ready.</span></span>

## <a name="how-will-the-updates-work"></a><span data-ttu-id="54615-111">Wie erfolgen die Updates?</span><span class="sxs-lookup"><span data-stu-id="54615-111">How will the updates work?</span></span>

<span data-ttu-id="54615-112">Jeder Installation von Microsoft Edge wird ein Upgradewert zugewiesen.</span><span class="sxs-lookup"><span data-stu-id="54615-112">Each installation of Microsoft Edge is assigned an upgrade value.</span></span> <span data-ttu-id="54615-113">Nachdem mit dem inkrementellen Rollout begonnen wurde, wird das Update angezeigt, wenn der Wert auf Ihrem Gerät innerhalb des Wertebereiches für das Upgrade liegt.</span><span class="sxs-lookup"><span data-stu-id="54615-113">When we start rolling out incrementally, you'll see the update when the value on your device falls within the upgrade value range.</span></span> <span data-ttu-id="54615-114">Im Laufe des Rollouts (also innerhalb weniger Tage) erhalten alle Benutzer das Update.</span><span class="sxs-lookup"><span data-stu-id="54615-114">As the rollout progresses (within a few days), all users will eventually get the update.</span></span> <span data-ttu-id="54615-115">Das Rollout von Browser-Updates mit kritischen Sicherheitsfixes erfolgt schneller als das von Updates, die keine kritischen Sicherheitsfixes umfassen.</span><span class="sxs-lookup"><span data-stu-id="54615-115">Browser updates with critical security fixes will have a faster rollout cadence than updates that don't have critical security fixes.</span></span> <span data-ttu-id="54615-116">Dies geschieht, um sofortigen Schutz vor Sicherheitsrisiken zu gewährleisten.</span><span class="sxs-lookup"><span data-stu-id="54615-116">This is done to ensure prompt protection from vulnerabilities.</span></span>

## <a name="how-does-this-affect-enterprises"></a><span data-ttu-id="54615-117">Wie wirkt sich dies auf Unternehmen aus?</span><span class="sxs-lookup"><span data-stu-id="54615-117">How does this affect enterprises?</span></span>

<span data-ttu-id="54615-118">Microsoft Edge-Produkte werden über verschiedene Mechanismen wie Microsoft Intune, Windows Server Update Service (WSUS) und Configuration Manager an Unternehmen verteilt.</span><span class="sxs-lookup"><span data-stu-id="54615-118">Microsoft Edge artifacts are distributed to enterprises using multiple mechanisms such as Microsoft Intune, Windows Server Update Service (WSUS), and Configuration Manager.</span></span> <span data-ttu-id="54615-119">Diese Bereitstellungstools verhalten sich im Hinblick auf das progressive Rollout unterschiedlich:</span><span class="sxs-lookup"><span data-stu-id="54615-119">These deployment tools behave differently with respect to Progressive Rollout:</span></span>

- <span data-ttu-id="54615-120">Unternehmen, die die Verteilung über Microsoft Intune verwalten, sind für automatische Updates registriert.</span><span class="sxs-lookup"><span data-stu-id="54615-120">Enterprises that manage distribution via Microsoft Intune are registered for auto-updates.</span></span> <span data-ttu-id="54615-121">Das progressive Rollout wird verwendet, und innerhalb weniger Tage erfolgt für alle Benutzer eine Aktualisierung.</span><span class="sxs-lookup"><span data-stu-id="54615-121">Progressive Rollout is used, and all the users will see an update in a few days.</span></span>
- <span data-ttu-id="54615-122">Unternehmen, die die Verteilung über WSUS (Windows Server Update Services) oder den Configuration Manager verwalten, sind nicht für automatische Updates registriert.</span><span class="sxs-lookup"><span data-stu-id="54615-122">Enterprises that manage distribution through WSUS (Windows Server Update Services) or Configuration Manager are not registered for auto-updates.</span></span> <span data-ttu-id="54615-123">Administratoren verwalten und übernehmen die verfügbaren Updates von Anfang an.</span><span class="sxs-lookup"><span data-stu-id="54615-123">Administrators manage and apply the updates that will be available from the start.</span></span> <span data-ttu-id="54615-124">Das progressive Rollout wirkt sich nicht auf diesen Vorgang aus.</span><span class="sxs-lookup"><span data-stu-id="54615-124">Progressive Rollout does not affect this process.</span></span>

<span data-ttu-id="54615-125">Wenn Sie irgendwelche Anliegen oder Fragen haben, teilen Sie Ihr wertvolles Feedback mit uns über die Feedback-Schaltfläche (UserVoice) innerhalb der Anwendung, oder unten in den Kommentaren.</span><span class="sxs-lookup"><span data-stu-id="54615-125">Please share your valuable feedback through user voice, the in-application feedback button, or below in the comments if you have any concerns or questions.</span></span>

## <a name="see-also"></a><span data-ttu-id="54615-126">Weitere Informationen</span><span class="sxs-lookup"><span data-stu-id="54615-126">See also</span></span>

- [<span data-ttu-id="54615-127">Microsoft Edge Enterprise-Angebotsseite</span><span class="sxs-lookup"><span data-stu-id="54615-127">Microsoft Edge Enterprise landing page</span></span>](https://aka.ms/EdgeEnterprise)
