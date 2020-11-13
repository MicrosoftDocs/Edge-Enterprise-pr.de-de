---
title: Dokumentation für die Microsoft Edge Update-Richtlinie
ms.author: stmoody
author: dan-wesley
manager: tahills
ms.date: 11/12/2020
audience: ITPro
ms.topic: reference
ms.prod: microsoft-edge
ms.localizationpriority: high
ms.collection: M365-modern-desktop
ms.custom: ''
description: Dokumentation für alle vom Microsoft Edge Updater unterstützten Richtlinien
ms.openlocfilehash: 0cdcda984efff8d10a84431e44c49ffbf28ddf07
ms.sourcegitcommit: c2ac4f889b625210b9365a60a447482fb5b4c9d4
ms.translationtype: HT
ms.contentlocale: de-DE
ms.lasthandoff: 11/12/2020
ms.locfileid: "11167307"
---
# Microsoft Edge – Update-Richtlinien

Die neueste Version von Microsoft Edge enthält die folgenden Richtlinien, mit denen Sie steuern können, wie und wann Microsoft Edge aktualisiert wird.

Weitere Informationen zu anderen in Microsoft Edge verfügbaren Richtlinien finden Sie in der [Microsoft Edge Referenz für Browserrichtlinien](microsoft-edge-policies.md)
> [!NOTE]
> Dieser Artikel bezieht sich auf Microsoft Edge Version 77 oder höher.
## Verfügbare Richtlinien
In dieser Tabelle sind sämtliche, in dieser Version von Microsoft Edge verfügbaren Update-bezogenen Gruppenrichtlinien aufgeführt. Über die Links in der folgenden Tabelle erhalten Sie weitere Einzelheiten zu bestimmten Richtlinien.

|||
|-|-|
|[Anwendungen](#applications)|[Voreinstellungen](#preferences)|
|[Proxyserver](#proxy-server)|[Microsoft Edge WebView](#microsoft-edge-webview)|

### [Anwendungen](#applications-policies)
|Richtlinienname|Beschriftung|
|-|-|
|[InstallDefault](#installdefault)|Standardinstallation zulassen|
|[UpdateDefault](#updatedefault)|Die Updaterichtlinie überschreibt die Standardrichtlinie|
|[Installieren](#install)|Installation zulassen (pro Kanal)|
|[Aktualisieren](#update)|Außerkraftsetzung von Updaterichtlinien (pro Kanal)|
|[Allowsxs](#allowsxs)|Microsoft Edge Seite-an-Seite-Browserumgebung zulassen|
|[CreateDesktopShortcutDefault](#createdesktopshortcutdefault)|Standardeinstellung für das Verhindern der Erstellung von Desktopverknüpfungen bei der Installation|
|[CreateDesktopShortcut](#createdesktopshortcut)|Verhindern der Erstellung von Desktopverknüpfungen bei der Installation (pro Kanal)|
|[RollbackToTargetVersion](#rollbacktotargetversion)|Zurücksetzung auf Zielversion (pro Kanal)|
|[TargetVersionPrefix](#targetversionprefix)|Außerkraftsetzung der Zielversion (pro Kanal)|

### [Voreinstellungen](#preferences-policies)
|Richtlinienname|Beschriftung|
|-|-|
|[AutoUpdateCheckPeriodMinutes](#autoupdatecheckperiodminutes)|Überschreibung des Überprüfungszeitraums für automatische Updates|
|[UpdatesSuppressed](#updatessuppressed)|Zeitraum in jedem Tag zum Unterdrücken der automatischen Überprüfung auf Updates|

### [Proxyserver](#proxy-server-policies)
|Richtlinienname|Untertitel für Hörgeschädigte|
|-|-|
|[ProxyMode](#proxymode)|Möglichkeit zur Angabe der Proxyservereinstellungen wählen|
|[ProxyPacUrl](#proxypacurl)|URL zu einer PAC-Proxydatei|
|[ProxyServer](#proxyserver)|Adresse oder URL des Proxyservers|

### [Microsoft Edge WebView](#microsoft-edge-webview-policies)
|Richtlinienname|Beschriftung|
|-|-|
|[Installieren](#install-webview)|Installation zulassen|
|[Update/Aktualisieren](#update-webview)|Außerkraftsetzung von Updaterichtlinien|

## Anwendungsrichtlinien

[Zurück zum Anfang](#microsoft-edge---update-policies)
### InstallDefault
#### Standardinstallation zulassen
>Microsoft Edge Update 1.2.145.5 und höher

#### Beschreibung
Sie können das Standardverhalten aller Kanäle festlegen, damit Microsoft Edge für in die Domäne eingebundene Geräte. zugelassen oder blockiert wird.

Sie können diese Richtlinie für einzelne Kanäle außer Kraft setzen, indem Sie die Richtlinie '[Installation zulassen](#install)' für bestimmte Kanäle aktivieren.

Wenn Sie diese Richtlinie deaktivieren, wird die Installation von Microsoft Edge blockiert. Dies wirkt sich nur auf die Installation der Microsoft Edge-Software aus, wenn die Richtlinie "[Installation zulassen](#install)" auf "nicht konfiguriert festgelegt ist.

Diese Richtlinie verhindert nicht, dass Microsoft Edge Update ausgeführt wird, oder dass Benutzer die Microsoft Edge-Software auf andere Weise installieren.

Diese Richtlinie ist nur für Windows-Instanzen verfügbar, die in eine Microsoft® Active Directory®-Domäne eingebunden werden.
#### Windows-Informationen und -Einstellungen
##### Informationen zur Gruppenrichtlinie (ADMX)
- Eindeutiger Name der GP: InstallDefault
- GP-Name: Standardinstallation zulassen
- GP-Pfad: Administrative Vorlagen/Microsoft Edge Update/Anwendungen
- Name der GP-ADMX-Datei: msedgeupdate.admx
##### Windows-Registrierungseinstellungen
- Pfad: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- Name des Wertes: InstallDefault
- Werttyp: REG_DWORD
##### Beispielwert:
```
0x00000001
```
[Zurück zum Anfang](#microsoft-edge---update-policies)


### UpdateDefault
#### Die Updaterichtlinie überschreibt die Standardrichtlinie
>Microsoft Edge Update 1.2.145.5 und höher

#### Beschreibung
Hier können Sie das Standardverhalten für alle Kanäle angeben, wie Microsoft Edge Update verfügbare Updates für Microsoft Edge verarbeitet. Kann für einzelne Kanäle durch Angabe der Richtlinie '[Außerkraftsetzung von Updaterichtlinien](#update)' für diese bestimmten Kanäle außer Kraft gesetzt werden.

  Wenn Sie diese Richtlinie aktivieren, verarbeitet Microsoft Edge Update Microsoft Edge-Updates entsprechend der Konfiguration der folgenden Optionen:
   - Updates immer zulassen: Updates werden immer dann angewendet, wenn sie gefunden werden, entweder durch die regelmäßige Updateprüfung oder durch eine manuelle Updateprüfung.
   - Nur automatische unbeaufsichtigte Updates: Updates werden nur angewendet, wenn sie von der regelmäßigen Updateprüfung gefunden werden.
   - Nur manuelle Updates: Updates werden nur angewendet, wenn der Benutzer eine manuelle Updateprüfung ausführt.
   - Updates deaktiviert: Updates werden nie angewendet.

  Wenn Sie „manuelle Updates” auswählen, stellen Sie sicher, dass Sie regelmäßig nach Updates suchen, indem Sie den manuellen Updatemechanismus der App verwenden, sofern verfügbar. Wenn Sie Updates deaktivieren, suchen Sie regelmäßig nach Updates und verteilen Sie diese an die Benutzer.

  Wenn Sie diese Richtlinie nicht aktivieren und konfigurieren, behandelt Microsoft Edge Update die verfügbaren Updates gemäß der Richtlinie '[Außerkraftsetzung von Updaterichtlinien](#update)'.

  Diese Richtlinie ist nur für Windows-Instanzen verfügbar, die in eine Microsoft® Active Directory®-Domäne eingebunden werden.
#### Windows-Informationen und -Einstellungen
##### Informationen zur Gruppenrichtlinie (ADMX)
- Eindeutiger Name der GP: UpdateDefault
- GP-Name: Die Updaterichtlinie überschreibt die Standardrichtlinie
- GP-Pfad: Administrative Vorlagen/Microsoft Edge Update/Anwendungen
- Name der GP-ADMX-Datei: msedgeupdate.admx
##### Windows-Registrierungseinstellungen
- Pfad: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- Name des Wertes: UpdateDefault
- Werttyp: REG_DWORD
##### Beispielwert:
```
0x00000003
```
[Zurück zum Anfang](#microsoft-edge---update-policies)


### Installieren
#### Installation zulassen
>Microsoft Edge Update 1.2.145.5 und höher

#### Beschreibung
Gibt an, ob ein Microsoft Edge-Kanal auf in die Domäne eingebundene Geräte installiert werden kann.

  Wenn Sie diese Richtlinie für einen Kanal aktivieren, wird die Installation von Microsoft Edge nicht blockiert.

  Wenn Sie diese Richtlinie für einen Kanal deaktivieren, wird die Installation von Microsoft Edge blockiert.

  Wenn Sie diese Richtlinie nicht für einen Kanal konfigurieren, bestimmt die Richtlinienkonfiguration '[Standardinstallation zulassen](#installdefault)', ob Benutzer diesen Kanal von Microsoft Edge installieren können.

  Diese Richtlinie ist nur für Windows-Instanzen verfügbar, die in eine Microsoft® Active Directory®-Domäne eingebunden werden.
#### Windows-Informationen und -Einstellungen
##### Informationen zur Gruppenrichtlinie (ADMX)
- Eindeutiger Name der GP: Install
- GP-Name: Installation zulassen
- GP-Pfad: 
  - Administrative Vorlagen/Microsoft Edge Update/Anwendungen/Microsoft Edge
  - Administrative Vorlagen/Microsoft Edge Update/Anwendungen/Microsoft Edge Beta
  - Administrative Vorlagen/Microsoft Edge Update/Anwendungen/Microsoft Edge Canary
  - Administrative Vorlagen/Microsoft Edge Update/Anwendungen/Microsoft Edge Dev
- Name der GP-ADMX-Datei: msedgeupdate.admx
##### Windows-Registrierungseinstellungen
- Pfad: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- Name des Wertes: 
  - (Stable): Install{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}
  - (Beta): Install{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}
  - (Canary): Install{65C35B14-6C1D-4122-AC46-7148CC9D6497}
  - (Dev): Install{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}
- Werttyp: REG_DWORD
##### Beispielwert:
```
0x00000001
```
[Zurück zum Anfang](#microsoft-edge---update-policies)


### Update
#### Außerkraftsetzung von Updaterichtlinien
>Microsoft Edge Update 1.2.145.5 und höher

#### Beschreibung
Gibt an, wie Microsoft Edge Update verfügbare Updates von Microsoft Edge behandelt.

Wenn Sie diese Richtlinie aktivieren, verarbeitet Microsoft Edge Update Microsoft Edge-Updates entsprechend der Konfiguration der folgenden Optionen:
  - Updates immer zulassen: Updates werden immer dann angewendet, wenn sie gefunden werden, entweder durch die regelmäßige Updateprüfung oder durch eine manuelle Updateprüfung.
  - Nur automatische unbeaufsichtigte Updates: Updates werden nur angewendet, wenn sie von der regelmäßigen Updateprüfung gefunden werden.
  - Nur manuelle Updates: Updates werden nur angewendet, wenn der Benutzer eine manuelle Updateprüfung ausführt. (Nicht alle Apps bieten eine Schnittstelle für diese Option.)
  - Updates deaktiviert: Updates werden nie angewendet.

Wenn Sie „manuelle Updates” auswählen, stellen Sie sicher, dass Sie regelmäßig nach Updates suchen, indem Sie den manuellen Updatemechanismus der App verwenden, sofern verfügbar. Wenn Sie Updates deaktivieren, suchen Sie regelmäßig nach Updates und verteilen Sie diese an die Benutzer.

Wenn Sie diese Richtlinie nicht aktivieren und konfigurieren, behandelt Microsoft Edge Update die verfügbaren Updates gemäß der Richtlinie '[Die Updaterichtlinie überschreibt die Standardrichtlinie](#updatedefault)'.

Weitere Informationen finden Sie unter [https://go.microsoft.com/fwlink/?linkid=2136406](https://go.microsoft.com/fwlink/?linkid=2136406).

Diese Richtlinie ist nur für Windows-Instanzen verfügbar, die in eine Microsoft® Active Directory®-Domäne eingebunden werden.
#### Windows-Informationen und -Einstellungen
##### Informationen zur Gruppenrichtlinie (ADMX)
- Eindeutiger Name der GP: Update
- GP-Name: Außerkraftsetzung von Updaterichtlinien
- GP-Pfad: 
  - Administrative Vorlagen/Microsoft Edge Update/Anwendungen/Microsoft Edge
  - Administrative Vorlagen/Microsoft Edge Update/Anwendungen/Microsoft Edge Beta
  - Administrative Vorlagen/Microsoft Edge Update/Anwendungen/Microsoft Edge Canary
  - Administrative Vorlagen/Microsoft Edge Update/Anwendungen/Microsoft Edge Dev
- Name der GP-ADMX-Datei: msedgeupdate.admx
##### Windows-Registrierungseinstellungen
- Pfad: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- Name des Wertes: 
  - (Stable): Update{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}
  - (Beta): Update{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}
  - (Canary): Update{65C35B14-6C1D-4122-AC46-7148CC9D6497}
  - (Dev): Update{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}
- Werttyp: REG_DWORD
##### Beispielwert:
```
0x00000001
```
[Zurück zum Anfang](#microsoft-edge---update-policies)


### Allowsxs
#### Microsoft Edge Seite-an-Seite-Browserumgebung zulassen
>Microsoft Edge Update 1.2.145.5 und höher

#### Beschreibung
Mit dieser Richtlinie können Benutzer Microsoft Edge (Edge-HTML) und Microsoft Edge (Chromium-basiert) nebeneinander ausführen.

Wenn diese Richtlinie auf „Nicht konfiguriert” festgelegt ist, ersetzt Microsoft Edge (Chromium-basiert) Microsoft Edge (Edge-HTML) nach dem stabilen Kanal von Microsoft Edge (Chromium-basierten), und die Sicherheitsupdates vom November2019 werden installiert.  Hierbei handelt es sich um das gleiche Verhalten wie bei der Einstellung „Deaktiviert“.

Die Einstellung „Deaktiviert” blockiert eine Seite-an-Seite-Umgebung, und Microsoft Edge (Chromium-basiert) ersetzt Microsoft Edge (Edge-HTML) nach dem stabilen Kanal von Microsoft Edge (Chromium-basierten). Außerdem werden die Sicherheitsupdates vom November2019 installiert.  Hierbei handelt es sich um das gleiche Verhalten wie bei der Einstellung „Nicht konfiguriert“.

Wenn diese Richtlinie aktiviert ist, können Microsoft Edge (Chromium-basiert) und Microsoft Edge (Edge-HTML) nach der Installation von Microsoft Edge (Chromium-basiert) nebeneinander ausgeführt werden.

Damit diese Gruppenrichtlinie wirksam wird, muss sie vor der automatischen Installation von Microsoft Edge (Chromium-basiert) von Windows Update konfiguriert werden. Hinweis: Ein Benutzer kann das automatische Update von Microsoft Edge (Chromium-basiert) mit dem Microsoft Edge (Chromium-basiert) Blocker Toolkit blockieren.
#### Windows-Informationen und -Einstellungen
##### Informationen zur Gruppenrichtlinie (ADMX)
- Eindeutiger Name der GP: Allowsxs
- GP-Name: Microsoft Edge Seite-an-Seite-Browserumgebung zulassen
- GP-Pfad: Administrative Vorlagen/Microsoft Edge Update/Anwendungen
- Name der GP-ADMX-Datei: msedgeupdate.admx
##### Windows-Registrierungseinstellungen
- Pfad: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- Name des Wertes: Allowsxs
- Werttyp: REG_DWORD
##### Beispielwert:
```
0x00000001
```
[Zurück zum Anfang](#microsoft-edge---update-policies)


### CreateDesktopShortcutDefault
#### Standardeinstellung für das Verhindern der Erstellung von Desktopverknüpfungen bei der Installation
>Microsoft Edge Update 1.3.128.0 und höher

#### Beschreibung
Ermöglicht es Ihnen, das Standardverhalten aller Kanäle für die Erstellung einer Desktopverknüpfung festzulegen, wenn Microsoft Edge installiert wird.

  Wenn Sie diese Richtlinie aktivieren, wird beim Installieren von Microsoft Edge eine Desktopverknüpfung erstellt.
Wenn Sie diese Richtlinie deaktivieren, wird beim Installieren von Microsoft Edge keine Desktopverknüpfung erstellt.
Wenn Sie diese Richtlinie nicht konfigurieren, wird während der Installation eine Desktopverknüpfung zu Microsoft Edge erstellt.
Wenn Microsoft Edge bereits installiert ist, hat diese Richtlinie keine Auswirkung.
#### Windows-Informationen und -Einstellungen
##### Informationen zur Gruppenrichtlinie (ADMX)
- Eindeutiger Name der GP: CreateDesktopShortcutDefault
- GP-Name: Standardeinstellung "Erstellung von Desktopverknüpfungen bei der Installation verhindern"
- GP-Pfad: Administrative Vorlagen/Microsoft Edge Update/Anwendungen
- Name der GP-ADMX-Datei: msedgeupdate.admx
##### Windows-Registrierungseinstellungen
- Pfad: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- Wertname: CreateDesktopShortcutDefault
- Werttyp: REG_DWORD
##### Beispielwert:
```
0x00000001
```
[Zurück zum Anfang](#microsoft-edge---update-policies)


### CreateDesktopShortcut
#### GP-Name: Erstellen von Desktopverknüpfungen bei Standardinstallation
>Microsoft Edge Update 1.3.128.0 und höher

#### Beschreibung
Wenn Sie diese Richtlinie aktivieren, wird beim Installieren von Microsoft Edge eine Desktopverknüpfung erstellt.
Wenn Sie diese Richtlinie deaktivieren, wird beim Installieren von Microsoft Edge keine Desktopverknüpfung erstellt.
Wenn Sie diese Richtlinie nicht konfigurieren, wird während der Installation eine Desktopverknüpfung zu Microsoft Edge erstellt.
Wenn Microsoft Edge bereits installiert ist, hat diese Richtlinie keine Auswirkung.

  Wenn Sie diese Richtlinie für einen Kanal nicht konfigurieren, bestimmt die Richtlinienkonfiguration "[Standardeinstellung für das Verhindern der Erstellung von Desktopverknüpfungen bei der Installation](#createdesktopshortcutdefault)", ob bei Installation von Microsoft Edge eine Verknüpfung erstellt wird oder nicht.
#### Windows-Informationen und -Einstellungen
##### Informationen zur Gruppenrichtlinie (ADMX)
- Eindeutiger Name der GP: CreateDesktopShortcut
- GP-Name: Erstellen von Desktopverknüpfungen bei Installation verhindern
- GP-Pfad: 
  - Administrative Vorlagen/Microsoft Edge Update/Anwendungen/Microsoft Edge
  - Administrative Vorlagen/Microsoft Edge Update/Anwendungen/Microsoft Edge Beta
  - Administrative Vorlagen/Microsoft Edge Update/Anwendungen/Microsoft Edge Canary
  - Administrative Vorlagen/Microsoft Edge Update/Anwendungen/Microsoft Edge Dev
- Name der GP-ADMX-Datei: msedgeupdate.admx
##### Windows-Registrierungseinstellungen
- Pfad: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- Name des Wertes: 
  - (Stable): CreateDesktopShortcut{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}
  - (Beta): CreateDesktopShortcut{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}
  - (Canary): CreateDesktopShortcut{65C35B14-6C1D-4122-AC46-7148CC9D6497}
  - (Dev): CreateDesktopShortcut{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}
- Werttyp: REG_DWORD
##### Beispielwert:
```
0x00000001
```
[Zurück zum Anfang](#microsoft-edge---update-policies)


### RollbackToTargetVersion
#### Zurücksetzung auf Zielversion
>Microsoft Edge Update 1.3.133.3 und höher

#### Beschreibung
Gibt an, dass Microsoft Edge Update Installationen von Microsoft Edge auf die in "[Zielversionaußerkraftsetzung](#targetversionprefix)" angegebene Version zurücksetzen soll.

Diese Richtlinie hat keine Wirkung, es sei denn, "[Zielversionaußerkraftsetzung](#targetversionprefix)" ist festgelegt und "[Update-Richtlinie außer Kraft setzen](#update)" auf einen der Zustände "ein" festgelegt ist (Updates immer zulassen, Nur automatische unbeaufsichtigte Updates, Nur manuelle Updates).

Wenn Sie diese Richtlinie deaktivieren oder nicht konfigurieren, bleiben Installationen mit einer höheren Version als die von "[Zielversionaußerkraftsetzung](#targetversionprefix)" unverändert.

Wenn Sie diese Richtlinie aktivieren, werden Installationen mit einer aktuellen Version, die höher ist als durch "[Zielversionaußerkraftsetzung](#targetversionprefix)" angegeben, auf die Zielversion herabgestuft.

Wir empfehlen Benutzern, die neueste Version des Microsoft Edge-Browsers zu installieren, um den Schutz durch die neuesten Sicherheitsupdates zu gewährleisten. Ein Rollback zu einer früheren Version birgt Risiken, die mit bekannten Sicherheitsproblemen zu tun haben. Diese Richtlinie ist als vorübergehender Fix zur Behebung von Problemen in einem Microsoft Edge-Browser-Update vorgesehen.

Bevor Sie die Browserversion vorübergehend zurücksetzen, empfehlen wir, die Synchronisierung ([https://go.microsoft.com/fwlink/?linkid=2133032](https://go.microsoft.com/fwlink/?linkid=2133032)) für alle Benutzer in Ihrer Organisation zu aktivieren. Wenn Sie die Synchronisierung nicht aktivieren, besteht das Risiko eines endgültigen Verlusts von Browserdaten. Verwenden Sie diese Richtlinie auf eigenes Risiko.

Hinweis: alle Versionen, die für einen Rollback verfügbar sind, können Sie hier [https://aka.ms/EdgeEnterprise](https://aka.ms/EdgeEnterprise) anzeigen.

Diese Richtlinie bezieht sich auf Microsoft Edge Version 86 oder neuer.

Weitere Informationen finden Sie unter [https://go.microsoft.com/fwlink/?linkid=2133918](https://go.microsoft.com/fwlink/?linkid=2133918).

Diese Richtlinie ist nur für Windows-Instanzen verfügbar, die in eine Microsoft® Active Directory®-Domäne eingebunden werden.
#### Windows-Informationen und -Einstellungen
##### Informationen zur Gruppenrichtlinie (ADMX)
- Eindeutiger Name der GP: RollbackToTargetVersion
- Name der GP: Zurücksetzung auf Zielversion
- GP-Pfad: 
  - Administrative Vorlagen/Microsoft Edge Update/Anwendungen/Microsoft Edge
  - Administrative Vorlagen/Microsoft Edge Update/Anwendungen/Microsoft Edge Beta
  - Administrative Vorlagen/Microsoft Edge Update/Anwendungen/Microsoft Edge Canary
  - Administrative Vorlagen/Microsoft Edge Update/Anwendungen/Microsoft Edge Dev
- Name der GP-ADMX-Datei: msedgeupdate.admx
##### Windows-Registrierungseinstellungen
- Pfad: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- Name des Wertes: 
  - (Stable): RollbackToTargetVersion{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}
  - (Beta): RollbackToTargetVersion{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}
  - (Canary): RollbackToTargetVersion{65C35B14-6C1D-4122-AC46-7148CC9D6497}
  - (Dev): RollbackToTargetVersion{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}
- Werttyp: REG_DWORD
##### Beispielwert:
```
0x00000001
```
[Zurück zum Anfang](#microsoft-edge---update-policies)


### TargetVersionPrefix
#### Zielversion außer Kraft setzen
>Microsoft Edge Update 1.3.119.43 und höher

#### Beschreibung
Wenn diese Richtlinie und die automatische Aktualisierung aktiviert sind, wird Microsoft Edge auf die durch diesen Richtlinienwert angegebene Version aktualisiert.

Der Richtlinienwert muss eine bestimmte Microsoft Edge-Version sein, z. B. 83.0.499.12.

Wenn ein Gerät über eine neuere Version von Microsoft Edge als der angegebene Wert verfügt, bleibt Microsoft Edge bei der neueren Version und wird nicht auf die angegebene Version herabgestuft.

Wenn die angegebene Version nicht vorhanden oder nicht ordnungsgemäß formatiert ist, bleibt Microsoft Edge bei der aktuellen Version und wird nicht automatisch auf zukünftige Versionen aktualisiert.

Weitere Informationen finden Sie unter [https://go.microsoft.com/fwlink/?linkid=2136707](https://go.microsoft.com/fwlink/?linkid=2136707).

Diese Richtlinie ist nur für Windows-Instanzen verfügbar, die in eine Microsoft® Active Directory®-Domäne eingebunden werden.
#### Windows-Informationen und -Einstellungen
##### Informationen zur Gruppenrichtlinie (ADMX)
- Eindeutiger Name der GP: TargetVersionPrefix
- GP-Name: Zielversion außer Kraft setzen
- GP-Pfad: 
  - Administrative Vorlagen/Microsoft Edge Update/Anwendungen/Microsoft Edge
  - Administrative Vorlagen/Microsoft Edge Update/Anwendungen/Microsoft Edge Beta
  - Administrative Vorlagen/Microsoft Edge Update/Anwendungen/Microsoft Edge Canary
  - Administrative Vorlagen/Microsoft Edge Update/Anwendungen/Microsoft Edge Dev
- Name der GP-ADMX-Datei: msedgeupdate.admx
##### Windows-Registrierungseinstellungen
- Pfad: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- Name des Wertes: 
  - (Stable): TargetVersionPrefix{56EB18F8-B008-4CBD-B6D2-8C97FE7E9062}
  - (Beta): TargetVersionPrefix{2CD8A007-E189-409D-A2C8-9AF4EF3C72AA}
  - (Canary): TargetVersionPrefix{65C35B14-6C1D-4122-AC46-7148CC9D6497}
  - (Dev): TargetVersionPrefix{0D50BFEC-CD6A-4F9A-964C-C7416E3ACB10}
- Werttyp: REG_SZ
##### Beispielwert:
```
83.0.499.12
```
[Zurück zum Anfang](#microsoft-edge---update-policies)


## Einstellungsrichtlinien

[Zurück zum Anfang](#microsoft-edge---update-policies)
### AutoUpdateCheckPeriodMinutes
#### Überschreibung des Überprüfungszeitraums für automatische Updates
>Microsoft Edge Update 1.2.145.5 und höher

#### Beschreibung
Wenn diese Richtlinie aktiviert ist, können Sie einen Wert für die Mindestanzahl von Minuten zwischen automatischen Updateprüfungen festlegen. Andernfalls sucht die automatische Updateprüfung standardmäßig alle 10 Stunden nach Updates.

  Wenn Sie alle automatischen Updateprüfungen deaktivieren möchten, setzen Sie den Wert auf 0 (nicht empfohlen).
#### Windows-Informationen und -Einstellungen
##### Informationen zur Gruppenrichtlinie (ADMX)
- Eindeutiger Name der GP: AutoUpdateCheckPeriodMinutes
- GP-Name: Überschreibung des Überprüfungszeitraums für automatische Updates
- GP-Pfad: Administrative Vorlagen/Microsoft Edge Update/Einstellungen
- Name der GP-ADMX-Datei: msedgeupdate.admx
##### Windows-Registrierungseinstellungen
- Pfad: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- Name des Wertes: AutoUpdateCheckPeriodMinutes
- Werttyp: REG_DWORD
##### Beispielwert:
```
0x00000578
```
[Zurück zum Anfang](#microsoft-edge---update-policies)


### UpdatesSuppressed
#### Zeitraum in jedem Tag zum Unterdrücken der automatischen Überprüfung auf Updates
>Microsoft Edge Update 1.3.33.5 und höher

#### Beschreibung
Wenn Sie diese Richtlinie aktivieren, werden die Updateprüfungen jeden Tag ab Stunde:Minute für einen Zeitraum der Dauer (in Minuten) unterdrückt. Die Dauer ist von der Sommerzeit nicht betroffen. Wenn die Startzeit z.B. 22:00 lautet und die Dauer 480Minuten beträgt, werden Updates genau 8 Stunden lang unterdrückt, unabhängig davon, ob die Sommerzeit in diesem Zeitraum beginnt oder endet.

  Wenn Sie diese Richtlinie deaktivieren oder nicht konfigurieren, werden die Updateprüfungen während eines bestimmten Zeitraums nicht unterdrückt.
#### Windows-Informationen und -Einstellungen
##### Informationen zur Gruppenrichtlinie (ADMX)
- Eindeutiger Name der GP: UpdatesSuppressed
- GP-Name: Zeitraum in jedem Tag zum Unterdrücken der automatischen Überprüfung auf Updates
  - Optionen {Stunde, Minute, Dauer}
- GP-Pfad: Administrative Vorlagen/Microsoft Edge Update/Einstellungen
- Name der GP-ADMX-Datei: msedgeupdate.admx
##### Windows-Registrierungseinstellungen
- Pfad: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- Name des Wertes: 
  - UpdatesSuppressedDurationMin
  - UpdatesSuppressedStartHour
  - UpdatesSuppressedStartMin
- Werttyp: REG_DWORD
##### Beispielwert:
```
duration   : 0x0000003c
start hour : 0x00000001
start min  : 0x00000002
```
[Zurück zum Anfang](#microsoft-edge---update-policies)


## Proxyserver-Richtlinien

[Zurück zum Anfang](#microsoft-edge---update-policies)
### ProxyMode
#### Möglichkeit zur Angabe der Proxyservereinstellungen wählen
>Microsoft Edge Update 1.3.21.81 und höher

#### Beschreibung
Mit dieser Option können Sie die Proxyserver-Einstellungen angeben, die von Microsoft Edge Update verwendet werden.

  Wenn Sie diese Richtlinie aktivieren, können Sie zwischen den folgenden Proxyserveroptionen wählen:
   - Wenn Sie niemals einen Proxyserver verwenden und immer eine direkte Verbindung herstellen, werden alle anderen Optionen ignoriert.
   - Wenn Sie die System-Proxyeinstellungen verwenden oder den Proxyserver automatisch erkennen möchten, werden alle anderen Optionen ignoriert.
   - Wenn Sie den Proxymodus für feste Server auswählen, können Sie unter '[Adresse oder URL des Proxyservers](#proxyserver)' weitere Optionen angeben.
   - Wenn Sie ein PAC-Proxyskript verwenden, müssen Sie die URL für das Skript unter '[URL zu einer PAC-Proxydatei](#proxypacurl)' angeben.

  Wenn Sie diese Richtlinie aktivieren, können Benutzer in Ihrer Organisation die Proxyeinstellungen in Microsoft Edge Update nicht ändern.

  Wenn Sie diese Richtlinie deaktivieren oder nicht konfigurieren, werden keine Proxyservereinstellungen konfiguriert. Benutzer in Ihrer Organisation können jedoch ihre eigenen Proxyeinstellungen für Microsoft Edge Update auswählen.
#### Windows-Informationen und -Einstellungen
##### Informationen zur Gruppenrichtlinie (ADMX)
- Eindeutiger Name der GP: ProxyMode
- GP-Name: Möglichkeit zur Angabe der Proxyservereinstellungen wählen
- GP-Pfad: Administrative Vorlagen/Microsoft Edge Update/Proxyserver
- Name der GP-ADMX-Datei: msedgeupdate.admx
##### Windows-Registrierungseinstellungen
- Pfad: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- Name des Wertes: ProxyMode
- Werttyp: REG_SZ
##### Beispielwert:
```
fixed_servers
```
[Zurück zum Anfang](#microsoft-edge---update-policies)


### ProxyPacUrl
#### URL zu einer PAC-Proxydatei
>Microsoft Edge Update 1.3.21.81 und höher

#### Beschreibung
Ermöglicht die Angabe einer URL für eine PAC-Datei (Proxy Auto-Config).

  Wenn Sie diese Richtlinie aktivieren, können Sie eine URL für eine PAC-Datei angeben, um zu automatisieren, wie Microsoft Edge Update den geeigneten Proxyserver zum Abrufen einer bestimmten Website auswählt.

  Diese Richtlinie wird nur angewendet, wenn Sie in der Richtlinie '[Möglichkeit zur Angabe der Proxyservereinstellungen wählen](#proxymode)' manuelle Proxyeinstellungen festgelegt haben.

  Konfigurieren Sie diese Richtlinie nicht, wenn Sie eine andere Proxy-Einstellung als manuell in der Richtlinie '[Möglichkeit zur Angabe der Proxyservereinstellungen wählen](#proxymode)' ausgewählt haben.
#### Windows-Informationen und -Einstellungen
##### Informationen zur Gruppenrichtlinie (ADMX)
- Eindeutiger Name der GP: ProxyPacUrl
- GP-Name: URL zu einer PAC-Proxydatei
- GP-Pfad: Administrative Vorlagen/Microsoft Edge Update/Proxyserver
- Name der GP-ADMX-Datei: msedgeupdate.admx
##### Windows-Registrierungseinstellungen
- Pfad: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- Name des Wertes: ProxyPacUrl
- Werttyp: REG_SZ
##### Beispielwert:
```
https://www.microsoft.com
```
[Zurück zum Anfang](#microsoft-edge---update-policies)


### ProxyServer
#### Adresse oder URL des Proxyservers
>Microsoft Edge Update 1.3.21.81 und höher

#### Beschreibung
Hier können Sie die URL des Proxy-Servers angeben, den Microsoft Edge Update verwenden soll.

  Wenn Sie diese Richtlinie aktivieren, können Sie die Proxyserver-URL festlegen, die von Microsoft Edge Update in Ihrer Organisation verwendet wird.

  Diese Richtlinie wird nur angewendet, wenn Sie in der Richtlinie '[Möglichkeit zur Angabe der Proxyservereinstellungen wählen](#proxymode)' manuelle Proxyeinstellungen ausgewählt haben.

  Konfigurieren Sie diese Richtlinie nicht, wenn Sie eine andere Proxy-Einstellung als manuell in der Richtlinie '[Möglichkeit zur Angabe der Proxyservereinstellungen wählen](#proxymode)' ausgewählt haben.
#### Windows-Informationen und -Einstellungen
##### Informationen zur Gruppenrichtlinie (ADMX)
- Eindeutiger Name der GP: ProxyServer
- GP-Name: Adresse oder URL des Proxyservers
- GP-Pfad: Administrative Vorlagen/Microsoft Edge Update/Proxyserver
- Name der GP-ADMX-Datei: msedgeupdate.admx
##### Windows-Registrierungseinstellungen
- Pfad: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- Name des Wertes: ProxyServer
- Werttyp: REG_SZ
##### Beispielwert:
```
https://www.microsoft.com
```
[Zurück zum Anfang](#microsoft-edge---update-policies)


## Microsoft Edge WebView-Richtlinien

[Zurück zum Anfang](#microsoft-edge---update-policies)
### Installieren (WebView)
#### Installation zulassen
>Microsoft Edge Update 1.3.127.1 und höher

#### Beschreibung
Hiermit können Sie festlegen, ob Microsoft Edge WebView mithilfe von Microsoft Edge Update installiert werden kann.

  - Wenn Sie diese Richtlinie aktivieren, können Benutzer Microsoft Edge über Microsoft Edge Update installieren.
  - Wenn Sie diese Richtlinie deaktivieren, können Benutzer Microsoft Edge nicht über Microsoft Edge Update installieren.
  - Wenn Sie diese Richtlinie nicht konfigurieren, bestimmt die Richtlinienkonfiguration "[Standardinstallation zulassen](#installdefault)", ob Benutzer Microsoft Edge WebView über Microsoft Edge Update installieren können.
#### Windows-Informationen und -Einstellungen
##### Informationen zur Gruppenrichtlinie (ADMX)
- Eindeutiger Name der GP: Install
- GP-Name: Installation zulassen
- GP-Pfad: Administrative Vorlagen/Microsoft Edge Update/Microsoft Edge WebView
- Name der GP-ADMX-Datei: msedgeupdate.admx
##### Windows-Registrierungseinstellungen
- Pfad: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- Name des Wertes: 
  - Install{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}
- Werttyp: REG_DWORD
##### Beispielwert:
```
0x00000001
```
[Zurück zum Anfang](#microsoft-edge---update-policies)


### Update (WebView)
#### Außerkraftsetzung von Updaterichtlinien
>Microsoft Edge Update 1.3.127.1 und höher

#### Beschreibung
Sie können angeben, ob automatische Updates für Microsoft Edge WebView aktiviert sind oder nicht. Microsoft Edge WebView ist eine Komponente, die von Anwendungen zum Anzeigen von Webinhalten verwendet wird.
"Automatische Updates" ist standardmäßig aktiviert. Durch das Deaktivieren von automatischen Updates für Microsoft Edge WebView können Kompatibilitätsprobleme mit Anwendungen verursacht werden, die von dieser Komponente abhängig sind.

  Wenn Sie diese Richtlinie aktivieren, verarbeitet Microsoft Edge Update die Microsoft Edge WebView-Updates entsprechend der Konfiguration der folgenden Optionen:
  - Updates immer zulassen: Updates werden automatisch heruntergeladen und angewendet
  - Updates deaktiviert: Updates werden nie heruntergeladen und angewendet

  Wenn Sie diese Richtlinie nicht aktivieren, werden Updates automatisch heruntergeladen und angewendet.
#### Windows-Informationen und -Einstellungen
##### Informationen zur Gruppenrichtlinie (ADMX)
- Eindeutiger Name der GP: Update
- GP-Name: Außerkraftsetzung von Updaterichtlinien
- GP-Pfad: Administrative Vorlagen/Microsoft Edge Update/Microsoft Edge WebView
- Name der GP-ADMX-Datei: msedgeupdate.admx
##### Windows-Registrierungseinstellungen
- Pfad: HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\EdgeUpdate
- Name des Wertes: 
  - Update{F3017226-FE2A-4295-8BDF-00C3A9A7E4C5}
- Werttyp: REG_DWORD
##### Beispielwert:
```
0x00000001
```
[Zurück zum Anfang](#microsoft-edge---update-policies)


## Weitere Informationen
  - [Konfigurieren von Microsoft Edge](configure-microsoft-edge.md)
  - [Microsoft Edge Enterprise-Angebotsseite](https://aka.ms/EdgeEnterprise)