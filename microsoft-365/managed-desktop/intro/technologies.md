---
title: Teknologier i Microsoft Hanterat skrivbord
description: I den här artikeln finns en lista över teknologier och program som används på Microsoft Managed Desktop.
keywords: Microsoft Hanterat skrivbord, Microsoft 365, service, dokumentation
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: cb368939e87ddbbfc8f5386c6fc5d6bff110a7ec
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 01/13/2021
ms.locfileid: "49840907"
---
# <a name="microsoft-managed-desktop-technologies"></a>Teknologier i Microsoft Hanterat skrivbord

I den här artikeln finns en lista över teknologier och program som används på Microsoft Managed Desktop.

<!-- Microsoft 365 E5; Device as a Service -->
<!-- in O365 table, standard suite, removed this sentence "Please see the Installation of Project/Visio 64bit Click to Run Addendum for important deployment instructions. -->

Microsoft 365 Enterprise-licensiering krävs för alla hanterade Microsoft-användare. För mer information om licens krav för tjänsten, se [förutsättningar för Microsoft Managed Desktop](../get-ready/prerequisites.md).

I den här artikeln sammanfattas de komponenter som ingår i de företags licenser som krävs, med en beskrivning av hur tjänsten använder varje komponent med Microsoft-hanterade Skriv bords enheter. Specifika roller och ansvars områden för varje område är detaljerade i Microsoft Managed Desktop Documentation. 

## <a name="office-365-e3-or-e5"></a>Office 365 E3 eller E5
 |
 --- | ---
Microsoft 365-appar för Enterprise (64-bitar) | Dessa Office-program levereras med enheten: Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype för företag, OneNote.<br><br>De 64-bitars fullständiga versionerna av Microsoft Project och Microsoft Visio ingår inte. Men eftersom installationen av dessa program beror på Microsoft 365-programmen för installation av Enterprise har Microsoft Managed Desktop skapat Microsoft Intune-distributioner och säkerhets grupper som du kan använda för att distribuera dessa program till licensierade användare. Mer information finns i [Installera Microsoft Project eller Microsoft Visio på Microsoft Managed Station ära enheter](../get-started/project-visio.md).
OneDrive |Med enkel inloggning i Azure Active Directory aktive ras användarna först när de loggar in på OneDrive.<br><br>Kända Mappomdirigering för "Skriv bord", "dokument" och "bilder"-mappar är inkluderade. aktiverat och konfigurerat av Microsoft Managed Desktop.
Store-appar |    Microsoft Sway och Power BI levereras inte med enheten. Dessa appar kan laddas ned från Microsoft Store.
Win32-program |    Team levereras inte med enheten, utan är paketerat och tillhandahålls av Microsoft för Microsoft-hanterade Station ära enheter. Azure information Protection-klienten levereras inte med enheten, men det går att paketera den för distribution.
Webb program |  Yammer, Office i en webbläsare, Delve, Flow, StaffHub, PowerApps och Planner levereras inte med enheten. Användare kan komma åt webb versionen av dessa program med en webbläsare.


## <a name="windows-10-enterprise-e5-or-e3-with-microsoft-defender-for-endpoint"></a>Windows 10 Enterprise, E5 eller E3 med Microsoft Defender för slut punkt

 |
 --- | ---
Application Virtualization (App-V) |    Kunderna kan distribuera App-V-paket med hjälp av Intune Win32 app Management-klienten.
Microsoft Defender för Endpoint |    Microsoft Managed Desktop använder den här produkten för att övervaka enhets säkerhet. 

## <a name="enterprise-mobility--security-e5"></a>Företags mobilitet + säkerhet, E5

 |
 --- | ---
Företags mobilitet + säkerhet E3<br>Azure Active Directory Premium P2 |    Du kan använda alla funktioner i Enterprise Mobility + Security E3 och Azure Active Directory Premium P2 för att hantera MDM-enheter.
Microsoft Cloud App Security |  Du kan använda den här valfria funktionen med Microsoft hanterat skriv bord.
Azure information Protection P2  | Du kan använda den här valfria funktionen med Microsoft hanterat skriv bord.
