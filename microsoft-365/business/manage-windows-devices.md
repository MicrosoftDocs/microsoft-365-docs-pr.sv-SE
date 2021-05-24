---
title: Aktivera domänaktiverade Windows 10 att hanteras av Microsoft 365 för företag
f1.keywords:
- CSH
ms.author: efrene
author: efrene
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
description: Lär dig hur du Microsoft 365 att skydda lokala Active Directory-anslutna Windows 10 med några få steg.
ms.openlocfilehash: ec80159bdceffd8a13d09a297a2acc1b78c9b1b3
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636095"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a>Aktivera att domänaktiverade Windows 10 hanteras av Microsoft 365 Business Premium

Om din organisation använder Windows Server Active Directory lokalt kan du konfigurera Microsoft 365 Business Premium för att skydda dina Windows 10-enheter, samtidigt som du behåller åtkomsten till lokala resurser som kräver lokal autentisering.
Om du vill konfigurera det här skyddet kan du implementera **Hybrid Azure AD-anslutna enheter.** De här enheterna är anslutna till både din lokala Active Directory och din Azure Active Directory.

## <a name="watch-configure-hybrid-azure-active-directory-join"></a>Titta på: Konfigurera Azure Active Directory hybridkoppling

I den här videon beskrivs stegen för hur du ställer in detta för det vanligaste scenariot, som också beskrivs i anvisningarna nedan.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  
## <a name="before-you-begin"></a>Innan du börjar

- Synkronisera användare till Azure AD med Azure AD Anslut.
- Slutför synkroniseringen av Azure AD Anslut organisationsenhet (OU).
- Kontrollera att alla domänanvändare som du synkroniserar har licenser för att Microsoft 365 Business Premium.

Instruktioner [finns i Synkronisera domänanvändare](manage-domain-users.md) till Microsoft.

## <a name="1-verify-mdm-authority-in-intune"></a>1. Verifiera MDM Authority i Intune

Gå till [Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_Enrollment/EnrollmentMenu/overview) sidan och Microsoft Intune enhetsregistrering . På sidan **Översikt** kontrollerar du att **MDM-behörighet** **är Intune.**

- Om **MDM-behörighet** **är Ingen** klickar du på **MDM-behörigheten** för att ange den till **Intune.**
- Om **MDM-behörighet** är **Microsoft Office 365** går du till Enheter Registrera enheter och använder dialogrutan Lägg till MDM-behörighet till höger för att lägga till  >   **Intune MDM-utfärdare** (dialogrutan Lägg till **MDM-utfärdare** är endast tillgänglig om **MDM-instansen** är inställd på  Microsoft Office 365).

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a>2. Kontrollera att Azure AD är aktiverat för anslutning till datorer

- Gå till administrationscentret och välj Välj Azure Active Directory (välj Visa <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> alla om Azure Active Directory inte visas) i listan **Administrationscenter.**  
- I Azure Active Directory **går du** till fliken **Azure Active Directory** väljer Enheter **och** sedan **Enhetsinställningar**.
- Kontrollera **att Användare kan ansluta enheter till Azure AD** är aktiverat 
    1. Om du vill aktivera alla användare anger du **alla**.
    2. Om du vill aktivera vissa användare anger du **markerad** för att aktivera en viss grupp av användare.
        - Lägg till önskade domänanvändare som synkroniserats i Azure AD till en [säkerhetsgrupp.](../admin/create-groups/create-groups.md)
        - Välj **Välj grupper för** att aktivera MDM-användaromfattningen för säkerhetsgruppen.

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a>3. Kontrollera att Azure AD är aktiverat för MDM

- Gå till administrationscentret och <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> välj Slutpunkt **hanteramenyer**(välj **Visa alla** **om Endpoint Manager** inte visas)
- I **administrationscentret Microsoft Endpoint Manager du** till Enheter **som Windows**  >    >  **Windows Automatisk**  >  **registrering**.
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
> Vi rekommenderar att du installerar den här modulen på den Windows server som kör Azure AD Anslut.

Om du vill skapa den tjänstanslutningspunkt och grupprincip som krävs anropar du cmdleten [Initialize-SecMgmtHybirdDeviceEnrollment.](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) Du behöver dina autentiseringsuppgifter Microsoft 365 Business Premium global administratör när du utför den här uppgiften. När du är redo att skapa resurserna anropar du följande:

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

Med det första kommandot upprättas en anslutning till Microsoft-molnet, och när du uppmanas att göra det anger du dina Microsoft 365 Business Premium som global administratör.

## <a name="5-link-the-group-policy"></a>5. Länka grupprincipen

1. I GPMC (Group Policy Management Console) högerklickar du på den plats där du vill länka principen och väljer Länka en befintlig *GPO...* på snabbmenyn.
2. Välj principen som skapades i steget ovan och klicka sedan på **OK.**

## <a name="get-the-latest-administrative-templates"></a>Hämta de senaste administrativa mallarna

Om du inte ser principen Aktivera automatisk **MDM-registrering** med standardautentiseringsuppgifter för Azure AD kan det beror på att du inte har ADMX installerat för Windows 10, version 1803 eller senare. Lös problemet genom att följa de här anvisningarna (Obs! den senaste MDM.admx är bakåtkompatibel):

1.  Ladda ned: [Administrativa mallar (.admx) för Windows 10 oktober 2020-uppdatering (20H2).](https://www.microsoft.com/download/102157)
2.  Installera paketet på en domänkontrollant.
3.  Navigera, beroende på versionen av Administrativa mallar, till mappen: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 oktober 2020-uppdatering (20H2).**
4.  Byt **namn på** mappen Principdefinitioner i sökvägen ovan till **Principdefinitioner.**
5.  Kopiera mappen **Principdefinitioner** till SYSVOL-resursen, som standard finns i **C:\Windows\SYSVOL\domän\Principer.** 
    -   Om du planerar att använda ett centralt principarkiv för hela domänen lägger du till innehållet i Principdefinitioner där.
6.  Om du har flera domänkontrollanter väntar du tills SYSVOL replikerar för att principerna ska vara tillgängliga. Den här proceduren fungerar även för alla framtida versioner av administrativa mallar.

Nu bör du kunna se principen Aktivera automatisk MDM-registrering med hjälp av **standardautentiseringsuppgifter för Azure AD.**

## <a name="related-content"></a>Relaterat innehåll

[Synkronisera domänanvändare till Microsoft 365](manage-domain-users.md) (artikel)\
[Skapa en grupp i administrationscentret](../admin/create-groups/create-groups.md) (artikel)\
[Självstudiekurs: Konfigurera Azure Active Directory-hybridlösningar för hanterade domäner](/azure/active-directory/devices/hybrid-azuread-join-managed-domains.md) (artikel)