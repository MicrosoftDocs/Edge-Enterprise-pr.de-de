---
title: Unterstützung und Konfiguration der Identität in Microsoft Edge
ms.author: avvaid
author: dan-wesley
manager: srugh
ms.date: 02/05/2021
audience: ITPro
ms.topic: conceptual
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
description: Unterstützung und Konfiguration der Identität in Microsoft Edge
ms.openlocfilehash: 05dc0fabe212f31fe9207c72d097913d5765915f
ms.sourcegitcommit: c290b0b0fa6b7d7f94dcdfdda91302da733326ec
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 02/06/2021
ms.locfileid: "11314608"
---
# Unterstützung und Konfiguration der Identität in Microsoft Edge

In diesem Artikel wird beschrieben, wie Microsoft Edge die Identität verwendet, um Features wie Synchronisierung und Einmaliges Anmelden (Single Sign-On, SSO) zu unterstützen. Microsoft Edge unterstützt die Anmeldung mit Active Directory Domain Services- (AD DS), Azure Active Directory- (Azure AD) und Microsoft-Konten (MSA). Derzeit unterstützt Microsoft Edge nur Azure Active Directory-Konten (Azure AD), die zur globalen Cloud oder der unabhängigen GCC (Government Community Cloud) gehören. Wir arbeiten daran, Unterstützung für weitere unabhängige Clouds hinzuzufügen.

> [!NOTE]
> Dieser Artikel bezieht sich auf Microsoft Edge Version 77 oder neuer.

## Browser-Anmelde- und Authentifizierungsfeatures

Microsoft Edge unterstützt die Anmeldung bei einem Browserprofil mit einem Azure AD-, MSA- oder Domänenkonto. Der für die Anmeldung verwendete Kontotyp bestimmt, welche authentifizierten Features für den Benutzer in Microsoft Edge verfügbar sind. In der folgenden Tabelle wird die Funktionsunterstützung für die einzelnen Kontotypen zusammengefasst.

| Feature   | Azure AD Premium | Azure AD Free | Lokale AD DS | MSA     |
|----|------------------|---------------|----------------|---------|
| Synchronisieren | Ja | Nein. | Nein | Ja |
| SSO mit Primärem Aktualisierungstoken | Ja | Ja | Nein | Ja |
| Nahtlose SSO | Ja | Ja | Ja | n. a. |
| Integrierte Windows-Authentifizierung | Ja | Ja | Ja | n. a. |
| Enterprise-Seite „Neue Registerkarte” | Erfordert O365 |   Erfordert O365 | Nein | n. a. |
| Microsoft Search | Erfordert O365 | Erfordert O365 | Nein | n. a. |

## Wie Benutzer sich bei Microsoft Edge anmelden können

### Automatische Anmeldung

Microsoft Edge verwendet für die automatische Anmeldung beim Browser das BS-Standardkonto. Je nachdem, wie ein Gerät konfiguriert ist, können die Benutzer mit einer der folgenden Vorgehensweisen automatisch bei Microsoft Edge angemeldet werden.

- **Das Gerät ist Hybrid/AAD-J:** verfügbar unter Win10, niedrigeren Windows-Versionen und entsprechenden Serverversionen.
Der Benutzer wird automatisch mit seinem Azure AD-Konto angemeldet.
- **Das Gerät ist einer Domäne beigetreten:** verfügbar unter Win10, niedrigeren Windows-Versionen und entsprechenden Serverversionen.
Standardmäßig wird der Benutzer nicht automatisch angemeldet. Wenn Benutzer automatisch mit Domänenkonten angemeldet werden sollen, verwenden Sie die [ConfigureOnPremisesAccountAutoSignIn](https://docs.microsoft.com/deployedge/microsoft-edge-policies#configureonpremisesaccountautosignin)-Richtlinie. Wenn Benutzer automatisch mit ihren Azure AD-Konten angemeldet werden sollen, sollten Sie für Ihre Geräte eine Hybridverbindung in Erwägung ziehen.
- **BS-Standardkonto ist MSA:** Win10 RS3 (Version 1709/Build 10.0.16299) und höher. Dieses Szenario ist auf Unternehmensgeräten unwahrscheinlich. Wenn aber das BS-Standardkonto MSA ist, meldet sich Microsoft Edge automatisch mit dem MSA-Konto an.

### Manuelle Anmeldung

Wenn der Benutzer nicht automatisch bei Microsoft Edge angemeldet wird, kann er sich bei der ersten Ausführung, in den Browsereinstellungen oder im Identitäts-Flyout manuell bei Microsoft Edge anmelden.

### Verwalten der Browser-Anmeldung

Zur Verwaltung der Browser-Anmeldung können Sie die folgenden Richtlinien verwenden:

- Stellen Sie sicher, dass die Benutzer immer über ein Arbeitsprofil in Microsoft Edge verfügen. [Siehe NonRemovableProfileEnabled](https://docs.microsoft.com/deployedge/microsoft-edge-policies#nonremovableprofileenabled)
- Beschränken Sie die Anmeldung auf eine Gruppe vertrauenswürdiger Konten. [Siehe RestrictSigninToPattern](https://docs.microsoft.com/deployedge/microsoft-edge-policies#restrictsignintopattern)
- Deaktivieren oder Erzwingen der Browser-Anmeldung. [Siehe BrowserSignin](https://docs.microsoft.com/deployedge/microsoft-edge-policies#browsersignin)

## Browser für einmaliges Anmelden (SSO) im Web

Auf einigen Plattformen können Sie Microsoft Edge so konfigurieren, dass die Benutzer automatisch bei Websites angemeldet werden. Mit dieser Option müssen sie die Anmeldeinformationen für den Zugriff auf ihre Arbeits-Websites nicht jedes Mal erneut eingeben, was zur Steigerung der Produktivität beiträgt.

### SSO mit Primärem Aktualisierungstoken (PRT)

Microsoft Edge bietet native Unterstützung für PRT-basiertes SSO, es wird auch keine Erweiterung benötigt. Unter Windows 10 RS3 und höher erhalten Benutzer, die in ihrem Browserprofil angemeldet sind, SSO mit dem PRT-Mechanismus für Websites, die PRT-basiertes SSO unterstützen.

Bei einem primären Aktualisierungstoken (PRT) handelt es sich um einen Azure AD-Schlüssel, der für die Authentifizierung auf Windows 10-, iOS- und Android-Geräten verwendet wird. Es ermöglicht das Einmalige Anmelden (Single Sign-On, SSO) bei den Anwendungen, die auf diesen Geräten verwendet werden. Weitere Informationen finden Sie unter [Was ist ein Primäres Aktualisierungstoken?](https://docs.microsoft.com/azure/active-directory/devices/concept-primary-refresh-token).

### Nahtlose SSO

Ähnlich wie für PRT SSO bietet Microsoft Edge native Unterstützung für nahtlose SSO, ohne dass eine Erweiterung erforderlich ist. Unter Windows 10 RS3 und höher erhalten Benutzer, die in ihrem Browserprofil angemeldet sind, SSO mit dem PRT-Mechanismus für Websites, die PRT-basiertes SSO unterstützen.

Bei der nahtlosen einmaligen Anmeldung werden Benutzer automatisch angemeldet, wenn sie Unternehmensgeräte verwenden, die mit einem Unternehmensnetzwerk verbunden sind. Wenn diese Option aktiviert ist, müssen die Benutzer ihre Kennwörter nicht eingeben, um sich bei Azure AD anzumelden. Normalerweise müssen sie nicht einmal ihre Benutzernamen eingeben. Weitere Informationen finden Sie unter [Active Directory – nahtlose Einmalige Anmeldung](https://docs.microsoft.com/azure/active-directory/hybrid/how-to-connect-sso).

### Integrierte Windows-Authentifizierung (WIA)

Microsoft Edge unterstützt auch die integrierte Windows-Authentifizierung für Authentifizierungsanforderungen im internen Netzwerk einer Organisation für alle Anwendungen, die einen Browser für die Authentifizierung verwenden. Dies wird in allen Versionen von Windows 10 und niedrigeren Windows-Versionen unterstützt. Standardmäßig verwendet Microsoft Edge die Intranetzone als Zulassungsliste für die WIA. Alternativ können Sie die Liste der Server, die für die integrierte Authentifizierung aktiviert sind, mithilfe der [AuthServerAllowlist](https://docs.microsoft.com/deployedge/microsoft-edge-policies#authserverallowlist)-Richtlinie anpassen. Unter MacOS ist diese Richtlinie erforderlich, um die integrierte Authentifizierung zu ermöglichen.

Damit WIA-basiertes SSO in Microsoft Edge (Version 77 und höher) unterstützt wird, müssen Sie möglicherweise auch einige serverseitige Konfigurationen vornehmen. Sie müssen wahrscheinlich die AD FS-Eigenschaft (Active Directory Federation Services) **WiaSupportedUserAgents** konfigurieren, damit Unterstützung für die neue Benutzer-Agent-Zeichenfolge für Microsoft Edge hinzugefügt wird. Informationen hierzu finden Sie unter [Anzeigen von WIASupportedUserAgent-Einstellungen](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/configure-ad-fs-browser-wia#view-wiasupporteduseragent-settings) und [Ändern der WIASupportedUserAgent-Einstellungen](https://docs.microsoft.com/windows-server/identity/ad-fs/operations/configure-ad-fs-browser-wia#change-wiasupporteduseragent-settings). Nachstehend finden Sie ein Beispiel für die Microsoft Edge-Zeichenfolge des Benutzer-Agenten unter Windows 10. Näheres erfahren Sie unter [Microsoft Edge Benutzer-Agent](https://docs.microsoft.com/microsoft-edge/web-platform/user-agent-string). 

Das folgende Beispiel einer UA-Zeichenfolge bezieht sich auf den zum Zeitpunkt der Veröffentlichung dieses Artikels neuesten Entwicklerkanal-Build:<br> `"Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/80.0.3951.0 Safari/537.36 Edg/80.0.334.2"`

Für Dienste, die das Delegieren von „Anmeldeinformationen aushandeln“ erfordern, unterstützt Microsoft Edge die beschränkte Delegierung mithilfe der [AuthNegotiateDelegateAllowlist](https://docs.microsoft.com/deployedge/microsoft-edge-policies#authnegotiatedelegateallowlist)-Richtlinie.

## Zusätzliche Authentifizierungskonzepte

### Proaktive Authentifizierung

Proaktive Authentifizierung ist eine Optimierung gegenüber einer Browser-zu-Website-SSO, bei der die Authentifizierung für bestimmte Erstanbieterwebsites per Frontlader geladen wird. Dadurch wird die Leistung der Adressleiste verbessert, wenn der Benutzer Bing als Suchmaschine verwendet. Auf diese Weise erhalten Benutzer personalisierte MSB-Suchergebnisse (Microsoft Search for Business). Außerdem ermöglicht es das Zulassen der Authentifizierung bei wichtigen Diensten wie etwa "Neue Tabseite" in Office. Sie können dies mithilfe der [ProactiveAuthEnabled]( https://docs.microsoft.com/deployedge/microsoft-edge-policies#proactiveauthenabled)-Richtlinie steuern.

### Windows Hello CredUI für die NTLM-Authentifizierung

Wenn eine Website versucht, Benutzer mit den NTLM- oder Negotiate-Mechanismen anzumelden und SSO nicht verfügbar ist, bieten wir den Benutzern eine Möglichkeit, ihre BS-Anmeldeinformationen für die Website freizugeben, um die Authentifizierungsaufforderung mithilfe von Windows Hello CredUI zu erfüllen. Dieser Anmeldevorgang wird nur für Benutzer unter Windows 10 angezeigt, denen während einer NTLM- oder Negotiate-Aufforderung keine SSO-Option angeboten wird.

### Automatische Anmeldung mit gespeicherten Kennwörtern

Wenn ein Benutzer Kennwörter in Microsoft Edge speichert, kann er eine Funktion aktivieren, die ihn automatisch bei Websites anmeldet, auf denen sie Anmeldeinformationen gespeichert haben. Benutzer können diese Funktion unter *edge://settings/passwords* ein- bzw. ausschalten. Wenn Sie diese Funktion konfigurieren möchten, können Sie hierfür die [Kennwort-Manager](https://docs.microsoft.com/deployedge/microsoft-edge-policies#password-manager-and-protection)-Richtlinien verwenden.

## Weitere Informationen

- [Microsoft Edge Enterprise-Angebotsseite](https://aka.ms/EdgeEnterprise)
- [Video: Microsoft Edge und Identität](microsoft-edge-video-identity.md)
- [Identitäts- und Zugriffsmanagement](https://www.microsoft.com/security/technology/identity-access-management)
- [Identitätsplattform](https://developer.microsoft.com/identity)
- [Vier Schritte zu einer starken Identitätsgrundlage mit Azure Active Directory](https://docs.microsoft.com/azure/active-directory/hybrid/four-steps)
