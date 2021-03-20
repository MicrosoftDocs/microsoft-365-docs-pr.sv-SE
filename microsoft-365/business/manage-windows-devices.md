---
title: Aktivera att domän anslutna Windows 10-enheter hanteras av Microsoft 365 för företag
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
description: Läs om hur du aktiverar Microsoft 365 för att skydda lokala Active-Directory-anslutna Windows 10-enheter med några få steg.
ms.openlocfilehash: 82d4ac3f1d6aba9489f9ea153de3a3d2083b47ec
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 03/19/2021
ms.locfileid: "50913203"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a>Aktivera att domän anslutna Windows 10-enheter hanteras av Microsoft 365 Business Premium

Om din organisation använder Windows Server Active Directory lokalt kan du konfigurera Microsoft 365 Business Premium för att skydda dina Windows 10-enheter, samtidigt som du behåller åtkomsten till lokala resurser som kräver lokal autentisering.
Om du vill konfigurera det här skyddet kan du implementera **Hybrid Azure AD-anslutna enheter.** Dessa enheter är anslutna till både din lokala Active Directory och Azure Active Directory.

I den här videon beskrivs stegen för hur du ställer in detta för det vanligaste scenariot, som också beskrivs i anvisningarna nedan.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a>Innan du börjar bör du kontrollera att du har slutfört följande steg:
- Synkronisera användare till Azure AD med Azure AD Connect.
- Slutför synkroniseringen av organisationsenheten i Azure AD Connect (OU).
- Kontrollera att alla domänanvändare som du synkroniserar har licenser för Microsoft 365 Business Premium.

Instruktioner [finns i Synkronisera domänanvändare](manage-domain-users.md) till Microsoft.

## <a name="1-verify-mdm-authority-in-intune"></a>1. Verifiera MDM Authority i Intune

Gå till [Slutpunktshanteraren](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) och på sidan Microsoft Intune  väljer du Enhetsregistrering. På sidan Översikt kontrollerar du sedan att **MDM-behörighet** **är Intune.**

- Om **MDM-behörighet** **är Ingen** klickar du på **MDM-behörigheten** för att ange den till **Intune.**
- Om **MDM-behörighet** är **Microsoft Office 365** går du till Enheter Registrera enheter och använder dialogrutan Lägg till MDM-behörighet till höger för att lägga till   >   **Intune MDM-utfärdare** (dialogrutan Lägg till MDM-instans är bara tillgänglig om  **MDM-instansen** är inställd på Microsoft Office 365). 

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a>2. Kontrollera att Azure AD är aktiverat för anslutning till datorer

- Gå till administrationscentret och välj Azure Active Directory (välj Visa alla om Azure Active Directory inte <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> visas) i **listan Administrationscenter.**  
- I **administrationscentret för Azure Active Directory** går du till Azure Active **Directory** och väljer **Enheter** och sedan **Enhetsinställningar.**
- Kontrollera **att Användare kan ansluta enheter till Azure AD** är aktiverat 
    1. Om du vill aktivera alla användare anger du **alla**.
    2. Om du vill aktivera vissa användare anger du **markerad** för att aktivera en viss grupp av användare.
        - Lägg till önskade domänanvändare som synkroniserats i Azure AD till en [säkerhetsgrupp.](../admin/create-groups/create-groups.md)
        - Välj **Välj grupper för** att aktivera MDM-användaromfattningen för säkerhetsgruppen.

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a>3. Kontrollera att Azure AD är aktiverat för MDM

- Gå till administrationscentret och <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> välj Slutpunktshanteramen t (välj **Visa alla** om **Slutpunktshanteraren** inte visas) 
- Gå till **Enheter Windows Windows-registrering** automatisk **registrering** i  >  **administrationscentret** för Microsoft  >    >  **Endpoint Manager.**
- Kontrollera att MDM-användaromfattningen är aktiverad.

    1. Om du vill registrera  alla datorer anger du Alla för automatisk registrering av alla användardatorer som är medlemmar i Azure AD och nya datorer när användarna lägger till ett arbetskonto i Windows.
    2. Ange några **för** att registrera datorer i en viss grupp av användare.
        -  Lägg till önskade domänanvändare som synkroniserats i Azure AD till en [säkerhetsgrupp.](../admin/create-groups/create-groups.md)
        -  Välj **Välj grupper för** att aktivera MDM-användaromfattningen för säkerhetsgruppen.

## <a name="4-create-the-required-resources"></a>4. Skapa de resurser som krävs 

Det har blivit enklare att utföra de uppgifter som krävs för att konfigurera [hybrid-AD-koppling](/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) med hjälp av cmdleten [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) som hittades i PowerShell-modulen [SecMgmt.](https://www.powershellgallery.com/packages/SecMgmt) När du anropar den här cmdleten skapas och konfigureras den nödvändiga tjänstanslutningspunkten och grupprincipen.

Du kan installera den här modulen genom att skapa följande från en instans av PowerShell:

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

Med det första kommandot upprättas en anslutning till Microsoft-molnet, och när du uppmanas att göra det anger du dina autentiseringsuppgifter som global administratör för Microsoft 365 Business Premium.

## <a name="5-link-the-group-policy"></a>5. Länka grupprincipen

1. I GPMC (Group Policy Management Console) högerklickar du på den plats där du vill länka principen och väljer Länka en befintlig *GPO...* på snabbmenyn.
2. Välj principen som skapades i steget ovan och klicka sedan på **OK.**

## <a name="get-the-latest-administrative-templates"></a>Hämta de senaste administrativa mallarna

Om du inte ser principen Aktivera automatisk **MDM-registrering** med standardautentiseringsuppgifter för Azure AD kan det beror på att du inte har ADMX installerat för Windows 10, version 1803 eller senare. Lös problemet genom att följa de här anvisningarna (Obs! den senaste MDM.admx är bakåtkompatibel):

1.  Ladda ned: [Administrativa mallar (.admx) för Windows 10 oktober 2020-uppdatering (20H2).](https://www.microsoft.com/download/102157)
2.  Installera paketet på en domänkontrollant.
3.  Navigera, beroende på versionen av Administrativa mallar, till mappen: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 oktober 2020 Update (20H2).**
4.  Byt **namn på** mappen Principdefinitioner i sökvägen ovan till **Principdefinitioner.**
5.  Kopiera mappen **Principdefinitioner** till SYSVOL-resursen, som standard finns i **C:\Windows\SYSVOL\domän\Principer.** 
    -   Om du planerar att använda ett centralt principarkiv för hela domänen lägger du till innehållet i Principdefinitioner där.
6.  Om du har flera domänkontrollanter väntar du tills SYSVOL replikerar för att principerna ska vara tillgängliga. Den här proceduren fungerar även för alla framtida versioner av administrativa mallar.

Nu bör du kunna se principen Aktivera automatisk MDM-registrering med hjälp av **standardautentiseringsuppgifter för Azure AD.**