---
title: Microsoft Edge Enterprise-Synchronisierung
ms.author: scottbo
author: dan-wesley
manager: silvanam
ms.date: 12/09/2020
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Microsoft Edge Enterprise-Synchronisierung
ms.openlocfilehash: 791188b5d28c867d6409a4d5373ea6c1ec7e49c7
ms.sourcegitcommit: 482b2e440a62cbf974dc45ac817f9d9d187ba1b9
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 12/10/2020
ms.locfileid: "11205464"
---
# Microsoft Edge Enterprise-Synchronisierung

In diesem Artikel wird erläutert, wie Sie mit Microsoft Edge Favoriten, Kennwörter und andere Browserdaten auf allen angemeldeten Geräten synchronisieren können.

> [!NOTE]
> Dieser Artikel bezieht sich auf Microsoft Edge Version 77 oder höher, sofern nichts anderes angegeben ist.

## Übersicht

Dank der Microsoft Edge-Synchronisierung können Benutzer auf ihre Browserdaten über alle angemeldeten Geräte hinweg zugreifen. Zu den von der Synchronisierung unterstützten Daten gehören:

- Favoriten
- Kennwörter
- Adressen und mehr (Formulareinträge)
- Sammlungen
- Einstellungen
- Erweiterung
- Geöffnete Registerkarten (verfügbar in Microsoft Edge, Version 88)
- Verlauf (verfügbar in Microsoft Edge, Version 88)

Die Synchronisierungsfunktion wird nach Zustimmung des Benutzers aktiviert, und Benutzer können die Synchronisierung für die beiden oben aufgeführten Datentypen aktivieren oder deaktivieren.

> [!NOTE]
> Zusätzliche Geräteverbindungs- und Konfigurationsdaten (wie Gerätename, Marke und Modell) werden hochgeladen, um die Synchronisationsfunktionalität zu unterstützen.

## Voraussetzungen

Die Synchronisierung von Microsoft Edge für Azure Active Directory (Azure AD)-Konten ist für jedes der folgenden Abonnements verfügbar:

- Azure AD Premium (P1 oder P2)
- M365 Business Premium
- Office365E1 und höher
- Azure Information Protection (AIP) (P1 oder P2)
- Alle EDU-Abonnements (Microsoft Apps für Studenten oder Dozenten, Exchange Online für Studenten oder Dozenten, O365 A1 oder höher, M365 A1 oder höher oder Azure Information Protection P1 oder P2 für Studenten oder Dozenten)

## Konfigurieren der Microsoft Edge-Synchronisierung

Konfigurationsoptionen für die Microsoft Edge-Synchronisierung stehen über den Azure Information Protection (AIP)-Dienst zur Verfügung. Wenn AIP für einen Mandanten aktiviert ist, können alle Benutzer Microsoft Edge-Daten unabhängig von der Lizenzierung synchronisieren. Anweisungen zum Aktivieren von AIP finden Sie [hier](https://docs.microsoft.com/azure/information-protection/activate-office365).

Um die Synchronisierung auf eine bestimmte Benutzergruppe zu beschränken, können Sie die [AIP-Richtlinie zur Onboarding-Steuerung](https://docs.microsoft.com/powershell/module/aipservice/set-aipserviceonboardingcontrolpolicy?view=azureipps&preserve-view=true) für diese Benutzer aktivieren. Wenn die Synchronisierung immer noch nicht verfügbar ist, nachdem Sie sich vergewissert haben, dass das Onboarding für alle erforderlichen Benutzer erfolgt ist, stellen Sie mithilfe des PowerShell-Cmdlets [Get-AIPServiceIPCv3](https://docs.microsoft.com/powershell/module/aipservice/get-aipserviceipcv3?view=azureipps&preserve-view=true)  sicher, dass IPCv3Service aktiviert ist.

> [!CAUTION]
> Die Aktivierung von Azure Information Protection erlaubt auch anderen Anwendungen, wie z.B. Microsoft Word oder Microsoft Outlook, Inhalte mit AIP zu schützen. Darüber hinaus wird jede Onboarding-Kontrollrichtlinie, die zur Einschränkung der Edge-Synchronisierung verwendet wird, auch andere Anwendungen daran hindern, Inhalte mithilfe von AIP zu schützen.

## Microsoft Edge und Enterprise State Roaming

Der neue Microsoft Edge ist eine plattformübergreifende Anwendung mit erweiterten Möglichkeiten zur Synchronisierung von Benutzerdaten auf allen Geräten und nicht mehr Teil von Azure AD Enterprise State Roaming. Das neue Microsoft Edge erfüllt jedoch die ESR-Datenschutzoptionen wie z.B. die Möglichkeit, einen eigenen Schlüssel zu verwenden. Weitere Informationen finden sie unter [Microsoft Edge und Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md).

## Synchronisierungs-Gruppenrichtlinien

Die folgenden Gruppenrichtlinien wirken sich auf die Microsoft Edge-Synchronisierung aus:

- [SyncDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#syncdisabled): Deaktiviert die Synchronisierung vollständig.
- [SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled): Deaktiviert das Speichern des Browserverlaufs und die Synchronisierung. Die Synchronisierung geöffneter Registerkarten wird durch diese Richtlinie ebenfalls deaktiviert.
- [AllowDeletingBrowserHistory](https://docs.microsoft.com/deployedge/microsoft-edge-policies#allowdeletingbrowserhistory): Wenn diese Richtlinie deaktiviert ist, wird auch die Verlaufsdatensynchronisierung deaktiviert.
- [SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled): Konfigurieren Sie die Liste der Typen, die von der Synchronisierung ausgeschlossen werden.
- [RoamingProfileSupportEnabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#roamingprofilesupportenabled): Zulassen, dass Active Directory (AD)-Profile lokalen Speicher verwenden. Weitere Informationen finden Sie unter [Lokale Synchronisierung für Active Directory (AD)-Benutzende](https://docs.microsoft.com/DeployEdge/microsoft-edge-on-premises-sync).
- [ForceSync]( https://docs.microsoft.com/deployedge/microsoft-edge-policies#forcesync): Aktivieren Sie die Synchronisierung standardmäßig, und fordern Sie keine Benutzerzustimmung zur Synchronisierung an.  

## Häufig gestellte Fragen

### SICHERHEIT und von SERVER-/DATENKONFORMITÄT

#### Werden die synchronisierten Daten verschlüsselt?

Die Daten werden beim Transport mithilfe von TLS 1.2 oder höher verschlüsselt. Alle Datentypen werden im Ruhezustand im Microsoft-Dienst zusätzlich mit AES128 verschlüsselt. Alle Datentypen mit Ausnahme derjenigen, die für die Synchronisierung von geöffneten Registerkarten und Verlaufsdaten verwendet werden, werden mit über [Azure Information Protection](https://docs.microsoft.com/azure/information-protection/)verwalteten Schlüsseln zusätzlich verschlüsselt, bevor sie das Gerät des Benutzers verlassen.

#### Warum werden die Daten von geöffneten Registerkarten und Verlaufsdaten nicht zusätzlich clientseitig verschlüsselt?  

Um die Ressourcennutzung auf Endbenutzergeräten zu verringern, werden Verlaufsdaten serverseitig basierend auf den Roamingdaten geöffneter Registerkarten generiert. Dieser Vorgang wäre bei clientseitiger Verschlüsselung dieser Daten nicht möglich. Wenden Sie die Richtlinien [SavingBrowserHistoryDisabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#savingbrowserhistorydisabled) oder [SyncTypesListDisabled](https://docs.microsoft.com/DeployEdge/microsoft-edge-policies#synctypeslistdisabled) an, um die Synchronisierung von geöffneten Registerkarten und Verlaufsdaten zu deaktivieren.

#### Können Mandantenadministratoren ihren eigenen Schlüssel mitbringen?

Ja, über  [Azure Information Protection](https://azure.microsoft.com/services/information-protection/).

#### Wo werden Microsoft Edge-Synchronisierungsdaten für gespeichert?

Synchronisierte Daten für Azure AD-Konten werden auf sicheren Servern entsprechend der Mandanten-ID gespeichert. Beispielsweise werden die Daten eines in den USA registrierten Mandanten auf Servern gespeichert, die sich in dieser geografischen Region befinden, und verwenden die gleiche Speicherlösung wie Office-Anwendungen.

#### Verlassen die Daten jemals die Cloud von Microsoft, abgesehen von der Synchronisierung mit Microsoft Edge?

Nein.

#### Unter welche Nutzungsbedingungen fällt die Unternehmenssynchronisierung?

Die Nutzungsbedingungen für die Microsoft Edge-Synchronisierung gehören zur Microsoft-Softwarelizenz, die in Microsoft Edge unter  *edge://terms* einsehbar ist. Ihr Abonnement und die Nutzungsbedingungen von Azure AD fallen letztlich unter die [Onlinedienst-Vertragsbedingungen](https://www.microsoft.com/licensing/product-licensing/products) von Microsoft Corporation.

#### Unterstützt Microsoft Edge Government Community Cloud (GCC) High-Compliance?

Derzeit nicht. Für Kunden in der GCC High-Cloud ist die Microsoft Edge-Synchronisierung deaktiviert.

### ANWENDEN DER SYNCHRONISIERUNG

#### Warum wird die Microsoft Edge-Synchronisierung nicht in allen M365-Abonnements unterstützt?

Die Unternehmenssynchronisierung ist von Azure Information Protection abhängig, das nicht in allen M365-Abonnements verfügbar ist.

#### Basiert die Microsoft Edge-Synchronisierung auf Enterprise State Roaming (ESR)?

Nein. ESR kann verwendet werden, um die Synchronisierung zu aktivieren, aber Microsoft Edge-Synchronisierung ist nicht Teil von ESR. Weitere Informationen finden sie unter [Microsoft Edge-Synchronisierung](microsoft-edge-enterprise-sync.md) sowie [Microsoft Edge und Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md).

#### Wird Microsoft Edge jemals die Synchronisierung zwischen Microsoft Edge und IE unterstützen?

Es gibt keine Pläne, diese Synchronisierung zu unterstützen. Wenn Sie in Ihrer Umgebung noch IE zur Unterstützung von Legacyanwendungen benötigen, sollten Sie unseren [neuen IE-Modus](https://docs.microsoft.com/deployedge/edge-ie-mode) in Betracht ziehen.

#### Wird Microsoft Edge mit der Vorgängerversion von Microsoft Edge synchronisiert?

Nein. Wir sind der Meinung, dass die Verbindung dieser beiden Ökosysteme zu Kompromissen bezüglich der Zuverlässigkeit der Synchronisation in Microsoft Edge führen würde. Wir stellen sicher, dass vorhandene Daten zu Microsoft Edge migriert werden. Benutzer können zudem Daten aus dem Browser Ihrer Wahl importieren. Dies bedeutet auch, dass der neue Microsoft Edge-Browser keine Möglichkeit für eine Synchronisierung mit dem IE bietet.

### VERWALTEN DER SYNCHRONISIERUNG

#### Kann ich verhindern, dass meine Benutzer mit einem persönlichen Mandanten synchronisiert werden?

Nicht direkt. Sie können jedoch mithilfe der Richtlinie [RestrictSigninToPattern](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern) festlegen, welche Profile sich bei Microsoft Edge anmelden können.

## Weitere Informationen

- [Angebotsseite für Microsoft Edge für Unternehmen](https://aka.ms/EdgeEnterprise)
- [Microsoft Edge und Enterprise State Roaming](microsoft-edge-enterprise-state-roaming.md)
