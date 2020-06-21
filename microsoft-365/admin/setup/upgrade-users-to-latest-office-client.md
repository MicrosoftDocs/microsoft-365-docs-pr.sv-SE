---
title: Uppgradera dina Microsoft 365 för företagsanvändare till den senaste Office-klienten
f1.keywords:
- NOCSH
ms.author: kwekuako
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
description: Läs om hur du uppgraderar användarna till den senaste Office-klienten.
ms.openlocfilehash: fb2513b2112dd8427222d43d14184895df3b594b
ms.sourcegitcommit: 659adf65d88ee44f643c471e6202396f1ffb6576
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/17/2020
ms.locfileid: "44778883"
---
# <a name="upgrade-your-microsoft-365-for-business-users-to-the-latest-office-client"></a>Uppgradera dina Microsoft 365 för företagsanvändare till den senaste Office-klienten

## <a name="office-2010-reaches-end-of-support"></a>Office 2010 når supportens

Office 2010 kommer att nå sitt stöd den 13 oktober 2020. När Office 2010 når supportens tillhandahåller Microsoft inte längre följande:

- Teknisk support för frågor

- Buggfixar för problem som upptäcks

- Säkerhetskorrigeringar för säkerhetsproblem som upptäcks

Mer information finns i [supportöversikten för Office 2010](https://docs.microsoft.com/deployoffice/office-2010-end-support-roadmap) för mer information.

 **Är detta rätt ämne för dig?**
  
 Om du är administratör som ansvarar för Microsoft 365 för företag-prenumerationen i din organisation är du på rätt plats. Administratörer är vanligtvis ansvariga för uppgifter som att hantera användare, återställa lösenord, hantera Office-installationer och lägga till eller ta bort licenser.

 Om du inte är administratör och har en [Microsoft 365-produkt](https://support.microsoft.com/office/28cbc8cf-1332-4f04-9123-9b660abb629e#BKMK_OfficePlans) läser [du Hur uppgraderar jag Office](https://support.microsoft.com/office/ee68f6cf-422f-464a-82ec-385f65391350) för information om hur du uppgraderar din äldre hemmaanvändningsversion av Office.

## <a name="get-ready-to-upgrade"></a>Gör dig redo att uppgradera

Som administratör styr du vilken version av Office-personer i organisationen som kan installera. Vi rekommenderar starkt att du hjälper användare i organisationen som kör äldre versioner av Office, till exempel Office 2010, Office 2013 eller Office 2016 att uppgradera till den senaste versionen för att dra nytta av dess säkerhets- och produktivitetsförbättringar.

## <a name="upgrade-steps"></a>Steg för att uppgradera

The steps below will guide you through the process of upgrading your users to the latest Office desktop client. We recommend you read through these steps before beginning the upgrade process.
  
## <a name="step-1---check-system-requirements"></a>Steg 1 - Kontrollera systemkrav

[Kontrollera systemkraven](https://products.office.com/office-system-requirements) för Office för att se till att dina enheter är kompatibla med den senaste versionen av Office. Nyare versioner av Office kan till exempel inte installeras på datorer med Windows XP eller Windows Vista.
  
> [!TIP]
> Om du har användare i organisationen som kör äldre versioner av Windows på sina datorer eller bärbara datorer rekommenderar vi att du uppgraderar till Windows 10. Windows 7 har nått slutet av supporten. Läs [Support för Windows 7 slutar i januari 2020](https://www.microsoft.com/microsoft-365/windows/end-of-windows-7-support?rtc=1) för mer information.

Kolla in [systemkraven för Windows 10](https://www.microsoft.com/windows/windows-10-specifications) för att se om du kan uppgradera deras operativsystem.

### <a name="check-application-compatibility"></a>Utvärdera programkompatibilitet

För att säkerställa en lyckad uppgradering rekommenderar vi att du identifierar dina Office-program - inklusive VBA-skript, makron, tillägg från tredje part och komplexa dokument och kalkylblad - och att du utvärderar deras kompatibilitet med den senaste versionen av Office.
  
Om du använder tillägg från tredje part med din aktuella Office-installation kontaktar du tillverkaren för att försäkra dig om att tilläggen är kompatibla med den senaste versionen av Office.
  
## <a name="step-2---check-your-existing-subscription-plan"></a>Steg 2 - Kontrollera ditt befintliga abonnemang

Vissa Microsoft 365-abonnemang innehåller inte de fullständiga skrivbordsversionerna av Office och stegen för att uppgradera är olika om ditt abonnemang inte innehåller Office.
  
Är du osäker på vilken prenumerationsplan du har? Se [Vilken prenumeration på Microsoft 365 för företag har jag?](../admin-overview/what-subscription-do-i-have.md)
  
Om ditt befintliga abonnemang innehåller Office kan du fortsätta till [Steg 3 - Avinstallera Office](#step-3---uninstall-office).
  
Om ditt befintliga abonnemang inte innehåller Office väljer du bland alternativen nedan:
  
### <a name="upgrade-options-for-plans-that-dont-include-office"></a>Uppgraderingsalternativ för abonnemang som inte innehåller Office

 **Alternativ 1: Växla Office-prenumerationer**

Byt till en prenumeration som innehåller Office. Se [Växla till ett annat Microsoft 365 för affärsplan](../../commerce/subscriptions/switch-to-a-different-plan.md).

**Alternativ 2: Köp enskilda engångsköp av Office eller köp Office via en volymlicens**

 - Köp ett enskilt engångsköp av Office. Se [Office Home &amp; Business](https://products.office.com/home-and-business) eller [Office Professional](https://products.office.com/professional)

     ELLER

 - Köp flera kopior av Office via en volymlicens. Se [Jämför paket som är tillgängliga för volymlicensiering](https://products.office.com/business/microsoft-office-volume-licensing-suites-comparison).

## <a name="step-3---uninstall-office"></a>Steg 3 - Avinstallera Office

Innan du installerar den senaste versionen av Office rekommenderar vi att du avinstallerar alla äldre versioner av Office. Om du ändrar dig om att uppgradera Office bör du dock tänka på följande fall där du inte kan installera om Office efter att du har avinstallerat det.
  
Om du använder tillägg från tredje part bör du kontakta tillverkaren för att se om det finns en uppdatering som fungerar med den senaste versionen av Office.

### <a name="select-the-version-of-office-you-want-to-uninstall"></a>Markera den version av Office du vill avinstallera.

- [Från en dator](https://support.microsoft.com/office/9dd49b83-264a-477a-8fcc-2fdf5dbf61d8)

- [Från en Mac](https://support.microsoft.com/office/eefa1199-5b58-43af-8a3d-b73dc1a8cae3)
  
### <a name="known-issues-trying-to-reinstall-older-versions-of-office-after-an-uninstall"></a>Kända problem vid ominstallation av äldre versioner av Office efter en avinstallation

 **Office via en volymlicens** Om du inte längre har tillgång till installationsfilerna för volymlicensversionen av Office kan du inte göra en ominstallation.

 **Office förinstallerat på din dator** Om du inte längre har en skiva eller produktnyckel (om en sådan bifogades) kan du inte göra en ominstallation.

 **Prenumerationer som inte stöds** Om ditt exemplar av Office erhölls via prenumerationer som har upphört, till exempel Office 365 Small Business Premium eller Office 365 Mid-size Business, kan du inte installera en äldre version av Office om du inte har produktnyckeln som medföljde prenumerationen.

If you'd prefer to install your older version of Office side-by-side with the latest version, you can see a list of versions where this is supported in, [Install and use different versions of Office on the same PC](https://support.microsoft.com/office/6ebb44ce-18a3-43f9-a187-b78c513788bf). A side-by-side installation might be the right choice for you, if for example, you've installed third-party add-ins you're using with your older version of Office and you're not yet sure they're compatible with the latest version.

## <a name="step-4---assign-office-licenses-to-users"></a>Steg 4 - Tilldela licenser till användare

Om du inte redan har gjort det läser du Tilldela licenser till alla användare i organisationen som behöver installera Office, se [Tilldela licenser till användare i Microsoft 365 för företag](../manage/assign-licenses-to-users.md).
  
## <a name="step-5---install-office"></a>Steg 5 - Installera Office

När du har verifierat att de användare som du vill uppgradera alla har licenser är det sista steget att låta dem installera Office, se [Hämta och installera eller installera om Office på din PC eller Mac](https://support.microsoft.com/office/4414eaaf-0478-48be-9c42-23adc4716658).
  
> [!TIP]
> If you don't want your users installing Office themselves, see [Manage software download settings in Office 365](https://docs.microsoft.com/DeployOffice/manage-software-download-settings-office-365). You can use the [Office Deployment Tool](https://docs.microsoft.com/DeployOffice/overview-office-deployment-tool) to download the Office software to your local network and then deploy Office by using the software deployment method you typically use.
