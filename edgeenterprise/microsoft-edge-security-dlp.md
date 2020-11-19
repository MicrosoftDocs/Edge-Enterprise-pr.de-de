---
title: Verhinderung von Datenverlust in Microsoft Edge
ms.author: archandr
author: dan-wesley
manager: seanlynd
ms.date: 11/18/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Verhinderung von Datenverlust (DLP) in Microsoft Edge
ms.openlocfilehash: 72f670caf34a09cdfc7f47575f688c2a39d3c221
ms.sourcegitcommit: 5a5be508c3c9c57187aca821b4a16f639abdd7e2
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/18/2020
ms.locfileid: "11176942"
---
# Verhinderung von Datenverlust (DLP) in Microsoft Edge

Die Verhinderung von Datenverlust (Data Loss Prevention, DLP) ist ein System von Technologien, die vertrauliche Unternehmensdaten erkennen und vor unbefugtem Zugriff schützen. Die Unternehmen müssen vertrauliche Informationen schützen und deren nicht autorisierte Offenlegung verhindern, um den Unternehmensstandards und Branchenvorschriften zu entsprechen. Zu den vertraulichen Informationen gehören unter anderem Finanzdaten oder personenbezogene Informationen (PII) wie Kreditkartennummern, Sozialversicherungsnummern oder Krankenakten.

Die Fernarbeit hat den Schwerpunkt auf die Verwendung von DLP verstärkt. Angesichts der zunehmenden Nutzung von persönlichen und geschäftlichen Aktivitäten auf Geräten sehen Unternehmen ein erhöhtes Risiko einer nicht autorisierten Freigabe von Unternehmensdaten außerhalb des Arbeitsplatzes.

Diese Kombination von Benutzeraktivitäten hat sich auch auf Geräte ausgebreitet, bei denen Daten zwischen privaten und unternehmensinternen Geräten über eine Vielzahl von öffentlichen und privaten Netzwerken verschoben werden. Das Ergebnis ist ein erheblich erhöhtes Risiko, vertrauliche Daten bereitzustellen.

Microsoft Edge unterstützt nativ zwei unterschiedliche DLP-Lösungen, Microsoft Endpoint DLP und Windows Information Protection (WIP).

## Microsoft Endpoint-Verhinderung von Datenverlust (Endpunkt-DLP)

Microsoft Endpoint DLP ist die nächste Generation der Verhinderung von Datenverlust unter Verwendung moderner Konzepte wie des datenzentrischen Schutzes. Sie ist in Windows 10 und Microsoft Edge integriert, sodass keine zusätzlichen Agents oder Plugins auf dem Gerät benötigt werden.

> [!NOTE]
> Dieser Artikel bezieht sich auf Microsoft Edge Version 85 oder neuer.

Weitere Informationen zu Endpunkt-DLP finden Sie unter:

- [Informationen zur Verhinderung von Microsoft 365-Endpunkt Datenverlust](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about?view=o365-worldwide)
- [Erste Schritte mit der Verhinderung von Endpunkt Datenverlust](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-getting-started?view=o365-worldwide)

Microsoft Edge erzwingt administratorenkonfigurierte Richtlinien für vertrauliche Dateien und zeichnet Überwachungsereignisse für nicht kompatible Aktivitäten auf.

Einige der Benutzeraktivitäten, die Sie auf Geräten unter Windows 10 überwachen und verwalten können, umfassen die folgenden Aktivitäten:

- Dateiupload: Schützen Sie den vertraulichen Dateiupload vor nicht autorisierten Cloud-Speicherorten. Die nächsten drei Screenshots zeigen eine Reihenfolge, in der ein Benutzer versucht, eine vertrauliche Datendatei in den lokalen Speicher zu setzen.
- Schutz der Zwischenablage: Verhindern, dass vertrauliche Daten aus der Datei kopiert werden.
- Druckschutz: Schützen vertraulicher Dateien, die gedruckt werden sollen.
- Auf USB/ Im Netzwerk speichern: Schützen vertraulicher Dateien vor dem Speichern in einem USB-Speicher oder nicht autorisierten Netzwerkspeicherorten.

Ausführlichere Informationen zu den Benutzeraktivitäten, die Sie überwachen und verwalten können, finden Sie unter [Endpunktaktivitäten, die Sie überwachen und entsprechende Maßnahmen ergreifen können](https://docs.microsoft.com/microsoft-365/compliance/endpoint-dlp-learn-about?view=o365-worldwide#endpoint-activities-you-can-monitor-and-take-action-on).

## Windows Information Protection

Lesen Sie [Support für Windows Information Protection](https://docs.microsoft.com/deployedge/microsoft-edge-security-windows-information-protection), in dem beschrieben wird, wie Microsoft Edge Windows Information Protection (WIP) unterstützt. In den folgenden Abschnitten finden Sie Informationen zu den Systemanforderungen, den Vorteilen und den unterstützten Funktionen:

- [Systemanforderungen](https://docs.microsoft.com/deployedge/:microsoft-edge-security-windows-information-protection#system-requirements)
- [Vorteile von Windows Information Protection](https://docs.microsoft.com/deployedge/microsoft-edge-security-windows-information-protection#windows-information-protection-benefits)
- [In Microsoft Edge unterstützte WIP-Features](https://docs.microsoft.com/DeployEdge/microsoft-edge-security-windows-information-protection#wip-features-supported-in-microsoft-edge)

## Weitere Informationen

- [Microsoft Edge Enterprise-Angebotsseite](https://aka.ms/EdgeEnterprise)
- [Video: Verhinderung von Datenverlust in Microsoft Edge](https://www.youtube.com/watch?v=dLD04U9eTqg)
- [Übersicht über die Verhinderung von Datenverlust](https://docs.microsoft.com/microsoft-365/compliance/data-loss-prevention-policies?view=o365-worldwide)
- [Schützen von Unternehmensdaten mithilfe von Windows Information Protection](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip)
