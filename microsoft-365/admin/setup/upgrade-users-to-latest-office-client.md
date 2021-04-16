---
title: Uppgradera Office 2010 till Microsoft 365 – Microsoft 365-administratör
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
- fwlink 824861; CampaignID
- O365_Comm_SR_UpgradeOffice
- seo-marvel-may2020
- fwlink 824861; CampaignID O365_Comm_SR_UpgradeOffice
- AdminSurgePortfolio
ms.assetid: f6b00895-b5fd-4af6-a656-b7788ea20cbb
description: Läs mer om hur du uppgraderar Microsoft Office till den senaste Office-klienten för användare i organisationen.
ms.openlocfilehash: 3d2d5e54506d06662c6c2feef0d142f1e195163f
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860577"
---
# <a name="upgrade-your-microsoft-365-for-business-users-to-the-latest-office-client"></a>Uppgradera dina Microsoft 365 för företag-användare till den senaste Office-klienten

## <a name="office-2010-reaches-end-of-support"></a>Support för Office 2010 avslutas

Supporten för Office 2010 upphöra den 13 oktober 2020. Microsoft tillhandahåller inte längre följande:

- Teknisk support för problem

- Felkorrigeringar för problem som upptäcks

- Säkerhetskorrigeringar för säkerhetsproblem som upptäcks

Mer information [finns i Översikt över slutet på supporten för Office 2010.](/deployoffice/endofsupport/office-2010-end-support-roadmap)

 **Är det här rätt ämne för dig?**
  
 Om du är administratör och ansvarar för Microsoft 365 för företag-prenumerationen i din organisation är du på rätt plats. Administratörer ansvarar vanligtvis för uppgifter som att hantera användare, återställa lösenord, hantera Office-installationer och lägga till eller ta bort licenser.

 Om du inte är administratör och har en [Microsoft 365 Family-produkt](https://support.microsoft.com/office/28cbc8cf-1332-4f04-9123-9b660abb629e#BKMK_OfficePlans) kan du läsa Hur uppgraderar jag [Office](https://support.microsoft.com/office/ee68f6cf-422f-464a-82ec-385f65391350) för information om hur du uppgraderar din äldre, hemanvändningsversion av Office.

## <a name="get-ready-to-upgrade-to-microsoft-365"></a>Gör dig redo att uppgradera till Microsoft 365

Som administratör styr du vilken version av Office personer i organisationen kan installera. Vi rekommenderar att du hjälper användarna i organisationen med äldre versioner av Office, till exempel Office 2010, Office 2013 eller Office 2016, att uppgradera till den senaste versionen för att dra nytta av förbättringar av säkerhet och produktivitet.

## <a name="upgrade-steps"></a>Steg för att uppgradera

Stegen nedan vägleder dig genom processen att uppgradera användarna till den senaste Office-skrivbordsklienten. Vi rekommenderar att du läser igenom de här stegen innan du påbörjar uppgraderingen.
  
## <a name="step-1---check-system-requirements"></a>Steg 1 - Kontrollera systemkrav

[Kontrollera systemkraven för](https://www.microsoft.com/microsoft-365/microsoft-365-and-office-resources) Office för att kontrollera att dina enheter är kompatibla med den senaste versionen av Office. Nyare versioner av Office kan till exempel inte installeras på datorer med Windows XP eller Windows Vista.
  
> [!TIP]
> Om du har användare i organisationen som kör äldre versioner av Windows på sina datorer och bärbara datorer rekommenderar vi att du uppgraderar till Windows 10. Supporten för Windows 7 har nu upphöra. Mer [information finns i Support för Windows 7 upphör i januari 2020.](https://www.microsoft.com/microsoft-365/windows/end-of-windows-7-support?rtc=1)

Läs systemkraven [för Windows 10 för](https://www.microsoft.com/windows/windows-10-specifications) att se om du kan uppgradera deras operativsystem.

### <a name="check-application-compatibility"></a>Utvärdera programkompatibilitet

För att säkerställa en lyckad uppgradering rekommenderar vi att du identifierar dina Office-program - inklusive VBA-skript, makron, tillägg från tredje part och komplexa dokument och kalkylblad - och att du utvärderar deras kompatibilitet med den senaste versionen av Office.
  
Om du använder tillägg från tredje part med din aktuella Office-installation kontaktar du tillverkaren för att försäkra dig om att tilläggen är kompatibla med den senaste versionen av Office.
  
## <a name="step-2---check-your-existing-subscription-plan"></a>Steg 2 - Kontrollera ditt befintliga abonnemang

I vissa Microsoft 365-abonnemang ingår inte fullständiga skrivbordsversioner av Office, och stegen för att uppgradera skiljer sig från abonnemang som innehåller Office.
  
Vet du inte vilket abonnemang du har? Se [Vilken Microsoft 365 för företag-prenumeration har jag?](../admin-overview/what-subscription-do-i-have.md)
  
Om ditt befintliga abonnemang innehåller Office kan du fortsätta till [Steg 3 - Avinstallera Office](#step-3---uninstall-office).
  
Om ditt befintliga abonnemang inte innehåller Office väljer du bland alternativen nedan:
  
### <a name="upgrade-options-for-plans-that-dont-include-office"></a>Uppgraderingsalternativ för abonnemang som inte innehåller Office

 **Alternativ 1: Byta Office-prenumeration**

Byt till en prenumeration som innehåller Office. Se [Byta till ett annat Microsoft 365 för företag-abonnemang](../../commerce/subscriptions/switch-to-a-different-plan.md).

**Alternativ 2: Gör enskilda, enstaka köp av Office eller köp Office via en volymlicens**

 - Gör ett enskilt, enstaka köp av Office. Se [Office Home &amp; Business](https://www.microsoft.com/microsoft-365/buy/compare-all-microsoft-365-products-b) eller [Office Professional](https://www.microsoft.com/microsoft-365/p/office-professional-2019/CFQ7TTC0K7C5/)

     ELLER

 - Köp flera kopior av Office via en volymlicens. Se [Jämför paket som är tillgängliga för volymlicensiering](https://products.office.com/business/microsoft-office-volume-licensing-suites-comparison).

## <a name="step-3---uninstall-office"></a>Steg 3 - Avinstallera Office

Innan du installerar den senaste versionen av Office rekommenderar vi att du avinstallerar alla äldre versioner av Office. Om du ändrar dig när det gäller uppgradering av Office måste du vara tänka på följande fall där du inte kan installera om Office när du har avinstallerat det.
  
Om du använder tillägg från tredje part bör du kontakta tillverkaren för att se om det finns en uppdatering som fungerar med den senaste versionen av Office.

> [!TIP]
> Om du får problem när du avinstallerar Office kan du använda verktyget Microsoft Support- och återställningsassistenten och ta bort Office: Ladda ned och kör Microsoft Support- och [återställningsassistenten.](https://go.microsoft.com/fwlink/?LinkID=2155008)

### <a name="select-the-version-of-office-you-want-to-uninstall"></a>Markera den version av Office du vill avinstallera.

- [Från en dator](https://support.microsoft.com/office/9dd49b83-264a-477a-8fcc-2fdf5dbf61d8)

- [Från en Mac](https://support.microsoft.com/office/eefa1199-5b58-43af-8a3d-b73dc1a8cae3)
  
### <a name="known-issues-trying-to-reinstall-older-versions-of-office-after-an-uninstall"></a>Kända problem vid ominstallation av äldre versioner av Office efter en avinstallation

 **Office via en volymlicens** Om du inte längre har tillgång till installationsfilerna för volymlicensversionen av Office kan du inte göra en ominstallation.

 **Office förinstallerat på din dator** Om du inte längre har en skiva eller produktnyckel (om en sådan bifogades) kan du inte göra en ominstallation.

 **Prenumerationer som inte stöds** Om ditt exemplar av Office erhållits via en in avbrytad prenumeration, till exempel Office 365 Small Business Premium eller Office 365 Mid-size Business, kan du inte installera en äldre version av Office om du inte har produktnyckeln som medkom med prenumerationen.

Om du föredrar att ha den äldre versionen av Office installerad sida vid sida med den senaste versionen finns mer information i [Installera och använda flera versioner av Office på samma dator](https://support.microsoft.com/office/6ebb44ce-18a3-43f9-a187-b78c513788bf). En sida vid sida-installation kan vara rätt val för dig om du till exempel använder tillägg från tredje part i en äldre version av Office och inte kan bekräfta att tilläggen är kompatibla med den senaste versionen.

## <a name="step-4---assign-office-licenses-to-users"></a>Steg 4 - Tilldela licenser till användare

Om du inte redan har gjort det kan du tilldela licenser till alla användare i organisationen som behöver installera Office. Läs mer i Tilldela användare licenser i [Microsoft 365 för företag.](../manage/assign-licenses-to-users.md)
  
## <a name="step-5---install-office"></a>Steg 5 - Installera Office

När du har kontrollerat att de användare som du vill uppgradera har licenser är det sista steget att få dem att installera Office, se Ladda ned och installera eller ominstallera Office på din [PC eller Mac.](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658)
  
> [!TIP]
> Om du inte vill att användarna själva installerar Office kan du läsa mer i artikeln om att [hantera nedladdningsinställningar för programvara i Office 365](/DeployOffice/manage-software-download-settings-office-365). Du kan använda [distributionsverktyget för Office](/DeployOffice/overview-office-deployment-tool) om du vill ladda ned Office-programvaran till ditt lokala nätverk och sedan distribuera Office med hjälp av den programdistributionsmetod som du normalt använder.