---
title: Aktivera domän anslutna Windows 10-enheter för att hanteras av Microsoft 365 för företag
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: Läs om hur du aktiverar Microsoft 365 för att skydda lokala Active Directory-anslutna Windows 10-enheter med några få steg.
ms.openlocfilehash: 0b597110447272be128bfe1866234ac25a8e67e6
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407087"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a>Aktivera domän anslutna Windows 10-enheter för att hanteras av Microsoft 365 Business Premium

Om din organisation använder Windows Server Active Directory lokalt kan du konfigurera Microsoft 365 Business Premium för att skydda dina Windows 10-enheter, samtidigt som du behåller åtkomsten till lokala resurser som kräver lokal autentisering.
Om du vill konfigurera det här skyddet kan du implementera **Hybrid Azure AD-anslutna enheter.** Dessa enheter är anslutna till både din lokala Active Directory och Azure Active Directory.

I det här videoklippet beskrivs hur du ställer in det här för det vanligaste scenariot, vilket också beskrivs i anvisningarna nedan.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a>Innan du börjar kontrollerar du att du har slutfört de här stegen:
- Synkronisera användare till Azure AD med Azure AD Connect.
- Slutför synkroniseringen av Organisationsenhet (OU) i Azure AD Connect.
- Kontrollera att alla domänanvändare som du synkroniserar har licenser till Microsoft 365 Business Premium.

Anvisningar [finns i Synkronisera domänanvändare till Microsoft.](manage-domain-users.md)

## <a name="1-verify-mdm-authority-in-intune"></a>1. Verifiera MDM Authority i Intune

Gå till [Slutpunktshanteraren,](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) välj Enhetsregistrering på sidan Microsoft  Intune och kontrollera sedan på sidan Översikt att **MDM-behörighet** är **Intune.**

- Om **MDM-behörighet** **är Ingen** klickar du på **MDM-instansen** för att ställa in den på **Intune.**
- Om **MDM** authority is **Microsoft Office 365**, go to **Devices**  >  **Enroll devices** and use the **Add MDM authority dialog** on the right to add **Intune MDM** authority **(the Add MDM Authority** dialog is only available if the **MDM Authority** is set to Microsoft Office 365).

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a>2. Kontrollera att Azure AD är aktiverat för anslutning till datorer

- Gå till administrationscentret och välj Azure Active Directory (välj Visa alla om Azure Active Directory inte visas) i listan <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a>  **administrationscenter.** 
- Gå till Azure Active Directory i **administrationscentret** för **Azure Active Directory,** välj **Enheter** och sedan **Enhetsinställningar.**
- Kontrollera **att användare kan ansluta enheter till Azure AD är** aktiverat 
    1. Ange till Alla om du vill aktivera **alla användare.**
    2. Om du vill aktivera vissa användare anger du **Markerad** för att aktivera en viss grupp av användare.
        - Lägg till önskade domänanvändare som synkroniserats i Azure AD i en [säkerhetsgrupp.](../admin/create-groups/create-groups.md)
        - Välj **Välj grupper för** att aktivera MDM-användaromfattningen för säkerhetsgruppen.

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a>3. Kontrollera att Azure AD är aktiverat för MDM

- Gå till administrationscentret och <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> välj Slutpunktshanterare (välj Visa alla **om** **Slutpunktshanteraren** inte visas) 
- Gå till **Automatisk registrering för Windows-registrering** för enheter   >  **i administrationscentret** för Microsoft  >    >  **Endpoint Manager.**
- Kontrollera att MDM-användaromfattningen är aktiverad.

    1. Om du vill registrera  alla datorer anger du alla att automatiskt registrera alla användardatorer som är medlemmar i Azure AD och nya datorer när användarna lägger till ett arbetskonto i Windows.
    2. Ange några **som** registrerar datorerna i en viss grupp av användare.
        -  Lägg till önskade domänanvändare som synkroniserats i Azure AD i en [säkerhetsgrupp.](../admin/create-groups/create-groups.md)
        -  Välj **Välj grupper för** att aktivera MDM-användaromfattningen för säkerhetsgruppen.

## <a name="4-create-the-required-resources"></a>4. Skapa de resurser som krävs 

Det har blivit enklare att utföra de uppgifter som krävs för att konfigurera [hybrid-AD-koppling](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) med hjälp av cmdleten [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) som hittades i PowerShell-modulen [SecMgmt.](https://www.powershellgallery.com/packages/SecMgmt) När du anropar den här cmdleten skapas och konfigureras den nödvändiga tjänstanslutningspunkten och grupprincipen.

Du kan installera den här modulen genom att använda följande i en instans av PowerShell:

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> Vi rekommenderar att du installerar den här modulen på Den Windows Server som kör Azure AD Connect.

Om du vill skapa den tjänstanslutningspunkt och grupprincip som krävs anropar du cmdleten [Initialize-SecMgmtHybirdDeviceEnrollment.](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) Du behöver dina autentiseringsuppgifter som global administratör för Microsoft 365 Business Premium när du utför den här uppgiften. När du är redo att skapa resurserna anropar du följande:

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

Det första kommandot upprättar en anslutning till Microsoft-molnet och när du uppmanas att göra det anger du dina autentiseringsuppgifter som global Administratör för Microsoft 365 Business Premium.

## <a name="5-link-the-group-policy"></a>5. Länka grupprincip

1. I grupprincip Management Console (GPMC) högerklickar du på den plats där du vill länka principen och väljer Länka en befintlig *GPO ...* på snabbmenyn.
2. Välj principen som skapades i steget ovan och klicka sedan på **OK.**

## <a name="get-the-latest-administrative-templates"></a>Hämta de senaste administrativa mallarna

Om du inte ser principen Aktivera automatisk **MDM-registrering** med standardautentiseringsuppgifter för Azure AD kan det beror på att du inte har ADMX installerat för Windows 10, version 1803 eller senare. Lös problemet genom att följa de här stegen (Obs! den senaste MDM.admx är bakåtkompatibel):

1.  Ladda ned: [Administrativa mallar (.admx) för Windows 10 oktober 2020-uppdatering (20H2).](https://www.microsoft.com/download/102157)
2.  Installera paketet på en domänkontrollant.
3.  Navigera, beroende på vilken version av administrativa mallar som finns i mappen: **C:\Program (x86)\Microsoft grupprincip\Windows 10 oktober 2020 Uppdatering (20H2).**
4.  Byt **namn på mappen** Principdefinitioner i sökvägen ovan till **Principdefinitioner.**
5.  Kopiera mappen **Principdefinitioner** till SYSVOL-resursen som standard i **C:\Windows\SYSVOL\domän\Principer.** 
    -   Om du planerar att använda ett centralt principarkiv för hela domänen lägger du till innehållet i Principdefinitioner där.
6.  Om du har flera domänkontrollanter väntar du tills SYSVOL replikerar för att principerna ska vara tillgängliga. Den här proceduren fungerar även för alla framtida versioner av administrativa mallar.

Nu bör du kunna se principen Aktivera automatisk **MDM-registrering med standardautentiseringsuppgifter för Azure AD** tillgängliga.
