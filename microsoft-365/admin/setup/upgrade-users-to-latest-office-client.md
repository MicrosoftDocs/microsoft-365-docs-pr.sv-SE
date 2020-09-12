---
title: Uppgradera dina Microsoft 365 för företag-användare till den senaste Office-klienten
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekuako
manager: scotv
audience: Admin
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.custom:
- fwlink 824861; CampaignID O365_Comm_SR_UpgradeOffice
- AdminSurgePortfolio
ms.assetid: f6b00895-b5fd-4af6-a656-b7788ea20cbb
description: Lär dig hur du uppgraderar användarna till den senaste Office-klienten.
ms.openlocfilehash: 7cddf1554a5892ddac510fc77238529194c1a2a0
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/12/2020
ms.locfileid: "47545734"
---
# <a name="upgrade-your-microsoft-365-for-business-users-to-the-latest-office-client"></a>Uppgradera dina Microsoft 365 för företag-användare till den senaste Office-klienten

## <a name="office-2010-reaches-end-of-support"></a>Office 2010 har slut på support

Office 2010 kommer att nå Supportens slut den 13 oktober 2020. När Office 2010 når Supportens slut kommer Microsoft inte längre att tillhandahålla följande:

- Teknisk support för problem

- Program korrigeringar för problem som upptäcks

- Säkerhets korrigeringar för säkerhets problem som upptäcks

Se [Office 2010-översikten](https://docs.microsoft.com/deployoffice/office-2010-end-support-roadmap) för att få mer information.

 **Är det här rätt avsnitt för dig?**
  
 Om du är administratör för Microsoft 365 för företag-prenumerationen i din organisation är du på rätt plats. Administratörer ansvarar normalt för uppgifter som att hantera användare, återställa lösen ord, hantera Office-installationer och lägga till eller ta bort licenser.

 Om du inte är administratör och har en [Microsoft 365-familj](https://support.microsoft.com/office/28cbc8cf-1332-4f04-9123-9b660abb629e#BKMK_OfficePlans) kan du läsa [Hur uppgraderar jag Office](https://support.microsoft.com/office/ee68f6cf-422f-464a-82ec-385f65391350) för information om hur du uppgraderar din äldre, Home-version av Office.

## <a name="get-ready-to-upgrade"></a>Förbered dig för att uppgradera

Som administratör kan du kontrol lera vilken version av Office-kontakter som finns i organisationen. Vi rekommenderar starkt att du hjälper användare i din organisation att köra äldre versioner av Office, till exempel Office 2010, Office 2013 eller Office 2016-uppgradering till den senaste versionen för att utnyttja säkerheten och produktiviteten.

## <a name="upgrade-steps"></a>Steg för att uppgradera

Stegen nedan vägleder dig genom processen att uppgradera användarna till den senaste Office-skrivbordsklienten. Vi rekommenderar att du läser igenom de här stegen innan du påbörjar uppgraderingen.
  
## <a name="step-1---check-system-requirements"></a>Steg 1 - Kontrollera systemkrav

[Kontrol lera system kraven](https://products.office.com/office-system-requirements) för Office för att se till att dina enheter är kompatibla med den senaste versionen av Office. Nyare versioner av Office kan till exempel inte installeras på datorer med Windows XP eller Windows Vista.
  
> [!TIP]
> Om du har användare i din organisation som kör en äldre version av Windows på sina datorer eller bärbara datorer rekommenderar vi att du uppgraderar till Windows 10. Windows 7 har nått Supportens slut. Läs [Support för Windows 7 upphör i januari 2020](https://www.microsoft.com/microsoft-365/windows/end-of-windows-7-support?rtc=1) för mer information.

Kontrol lera [system kraven för Windows 10](https://www.microsoft.com/windows/windows-10-specifications) för att se om du kan uppgradera sina operativ system.

### <a name="check-application-compatibility"></a>Utvärdera programkompatibilitet

För att säkerställa en lyckad uppgradering rekommenderar vi att du identifierar dina Office-program - inklusive VBA-skript, makron, tillägg från tredje part och komplexa dokument och kalkylblad - och att du utvärderar deras kompatibilitet med den senaste versionen av Office.
  
Om du använder tillägg från tredje part med din aktuella Office-installation kontaktar du tillverkaren för att försäkra dig om att tilläggen är kompatibla med den senaste versionen av Office.
  
## <a name="step-2---check-your-existing-subscription-plan"></a>Steg 2 - Kontrollera ditt befintliga abonnemang

Vissa Microsoft 365-abonnemang inkluderar inte fullständigt Skriv bords versioner av Office och uppgraderings stegen är annorlunda om ditt abonnemang inte innehåller Office.
  
Vet du inte vilket abonnemang du har? Se [vilken Microsoft 365 för företag-prenumeration har jag?](../admin-overview/what-subscription-do-i-have.md)
  
Om ditt befintliga abonnemang innehåller Office kan du fortsätta till [Steg 3 - Avinstallera Office](#step-3---uninstall-office).
  
Om ditt befintliga abonnemang inte innehåller Office väljer du bland alternativen nedan:
  
### <a name="upgrade-options-for-plans-that-dont-include-office"></a>Uppgraderingsalternativ för abonnemang som inte innehåller Office

 **Alternativ 1: byta Office-prenumeration**

Byt till en prenumeration som innehåller Office. Se [byta till ett annat Microsoft 365 för företag-abonnemang](../../commerce/subscriptions/switch-to-a-different-plan.md).

**Alternativ 2: Köp enskilda, engångs köp av Office eller Köp Office via en volym licens**

 - Köp ett individuellt inköp av Office. Se [Office Home &amp; Business](https://products.office.com/home-and-business) eller [Office Professional](https://products.office.com/professional)

     ELLER

 - Köp flera kopior av Office via en volym licens. Se [Jämför paket som är tillgängliga för volymlicensiering](https://products.office.com/business/microsoft-office-volume-licensing-suites-comparison).

## <a name="step-3---uninstall-office"></a>Steg 3 - Avinstallera Office

Vi rekommenderar att du avinstallerar alla äldre versioner av Office innan du installerar den senaste versionen av Office. Om du ändrar dig om att uppgradera Office kan du emellertid tänka på följande om du inte kan installera om Office när du har avinstallerat det.
  
Om du använder tillägg från tredje part bör du kontakta tillverkaren för att se om det finns en uppdatering som fungerar med den senaste versionen av Office.

### <a name="select-the-version-of-office-you-want-to-uninstall"></a>Markera den version av Office du vill avinstallera.

- [Från en dator](https://support.microsoft.com/office/9dd49b83-264a-477a-8fcc-2fdf5dbf61d8)

- [Från en Mac](https://support.microsoft.com/office/eefa1199-5b58-43af-8a3d-b73dc1a8cae3)
  
### <a name="known-issues-trying-to-reinstall-older-versions-of-office-after-an-uninstall"></a>Kända problem vid ominstallation av äldre versioner av Office efter en avinstallation

 **Office via en volymlicens** Om du inte längre har tillgång till installationsfilerna för volymlicensversionen av Office kan du inte göra en ominstallation.

 **Office förinstallerat på din dator** Om du inte längre har en skiva eller produktnyckel (om en sådan bifogades) kan du inte göra en ominstallation.

 **Abonnemang som inte stöds** Om ditt exemplar av Office erhölls via borttagna prenumerationer, till exempel Office 365 Small Business Premium eller Office 365 Mid-Size Business, kommer du inte att kunna installera en äldre version av Office om du inte har den produkt som medföljde ditt abonnemang.

Om du föredrar att ha den äldre versionen av Office installerad sida vid sida med den senaste versionen finns mer information i [Installera och använda flera versioner av Office på samma dator](https://support.microsoft.com/office/6ebb44ce-18a3-43f9-a187-b78c513788bf). En sida vid sida-installation kan vara rätt val för dig om du till exempel använder tillägg från tredje part i en äldre version av Office och inte kan bekräfta att tilläggen är kompatibla med den senaste versionen.

## <a name="step-4---assign-office-licenses-to-users"></a>Steg 4 - Tilldela licenser till användare

Om du inte redan har gjort det kan du tilldela licenser till användare i organisationen som behöver installera Office, se [tilldela licenser till användare i Microsoft 365 för företag](../manage/assign-licenses-to-users.md).
  
## <a name="step-5---install-office"></a>Steg 5 - Installera Office

När du har verifierat de användare du vill uppgradera alla har licenser, det sista steget är att låta dem installera Office, läser du [Ladda ned och installera eller ominstallera Office på PC eller Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658).
  
> [!TIP]
> Om du inte vill att användarna själva installerar Office kan du läsa mer i artikeln om att [hantera nedladdningsinställningar för programvara i Office 365](https://docs.microsoft.com/DeployOffice/manage-software-download-settings-office-365). Du kan använda [distributionsverktyget för Office](https://docs.microsoft.com/DeployOffice/overview-office-deployment-tool) om du vill ladda ned Office-programvaran till ditt lokala nätverk och sedan distribuera Office med hjälp av den programdistributionsmetod som du normalt använder.
