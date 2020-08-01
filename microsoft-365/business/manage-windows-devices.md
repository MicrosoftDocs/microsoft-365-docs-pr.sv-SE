---
title: Aktivera domänanslutna Windows 10-enheter som ska hanteras av Microsoft 365 för företag
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
description: Lär dig hur du aktiverar Microsoft 365 för att skydda lokala Active-Directory-anslutna Windows 10-enheter med bara några få steg.
ms.openlocfilehash: 2eaf5aa76cae1680b93af008af615ae872e4fb20
ms.sourcegitcommit: fab425ea4580d1924fb421e6db233d135f5b7d19
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 07/31/2020
ms.locfileid: "46533794"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a>Aktivera domänanslutna Windows 10-enheter som ska hanteras av Microsoft 365 Business Premium

Om din organisation använder Windows Server Active Directory lokalt kan du konfigurera Microsoft 365 Business Premium för att skydda dina Windows 10-enheter, samtidigt som du behåller åtkomsten till lokala resurser som kräver lokal autentisering.
Om du vill konfigurera det här skyddet kan du implementera **Hybrid Azure AD-anslutna enheter**. Dessa enheter är anslutna till både din lokala Active Directory och din Azure Active Directory.

I det här videoklippet beskrivs stegen för hur du ställer in det här för det vanligaste scenariot, vilket också beskrivs i de steg som följer.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a>Innan du börjar måste du följa de här stegen:
- Synkronisera användare till Azure AD med Azure AD Connect.
- Fullständig Synkronisering av Azure AD Connect-organisationsenhet (OU).
- Kontrollera att alla domänanvändare som du synkroniserar har licenser till Microsoft 365 Business Premium.

Se [Synkronisera domänanvändare till Microsoft](manage-domain-users.md) för stegen.

## <a name="1-verify-mdm-authority-in-intune"></a>1. Verifiera MDM-myndighet i Intune

Gå till portal.azure.com och högst upp på sidan sök efter Intune.
På sidan Microsoft Intune väljer du **Enhetsregistrering** och kontrollera att **MDM-behörigheten** är Intune på **sidan** **Microsoft Intune**.

- Om **MDM-behörigheten** är **Ingen**klickar du på **MDM-behörigheten** för att ställa in den på **Intune**.
- Om **MDM-behörigheten** är **Microsoft Office 365**går du till **Devices**  >  **Enheters registrera enheter** och använder dialogrutan Lägg till **MDM-behörighet** till höger för att lägga till **Intune MDM-behörighet** (dialogrutan **Lägg till MDM-auktoritet** är endast tillgänglig om **MDM-behörigheten** är inställd på Microsoft Office 365).

## <a name="2-verify-azure-ad-is-enabled-for-joining-computers"></a>2. Verifiera att Azure AD är aktiverat för att ansluta till datorer

- Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> och välj Azure Active **Directory** (välj Visa alla om Azure Active Directory inte visas) i listan **Administrationscenter.** 
- I **administrationscentret**för Azure Active Directory går du till **Azure Active Directory,** väljer **Enheter** och sedan **Enhetsinställningar**.
- Verifiera**att användare kan ansluta till enheter till Azure AD** är aktiverat 
    1. Om du vill aktivera alla användare anger du **alla**.
    2. Om du vill aktivera specifika användare anger du **till Markerad** för att aktivera en viss grupp användare.
        - Lägg till önskade domänanvändare som synkroniserats i Azure AD i en [säkerhetsgrupp](../admin/create-groups/create-groups.md).
        - Välj **välj grupper** om du vill aktivera MDM-användaromfattning för den säkerhetsgruppen.

## <a name="3-verify-azure-ad-is-enabled-for-mdm"></a>3. Verifiera att Azure AD är aktiverat för MDM

- Gå till administrationscentret på <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">https://admin.microsoft.com</a> och välj **Slutpunktshanterare**t (välj **Visa alla** om **Slutpunktshanteraren** inte visas)
- Gå till Automatisk registrering av **Enheter**med Windows Windows-registrering i **administrationscentret för Microsoft Slutpunktshanteraren**  >  **Windows**  >  **Windows Enrollment**  >  **Automatic Enrollment**.
- Kontrollera att MDM-användaromfattningen är aktiverad.

    1. Om du vill registrera alla datorer ställer du in på **Alla** för att automatiskt registrera alla användardatorer som är anslutna till Azure AD och nya datorer när användarna lägger till ett arbetskonto i Windows.
    2. Ange att **vissa** ska registrera datorerna för en viss grupp användare.
        -  Lägg till önskade domänanvändare som synkroniserats i Azure AD i en [säkerhetsgrupp](../admin/create-groups/create-groups.md).
        -  Välj **välj grupper** om du vill aktivera MDM-användaromfattning för den säkerhetsgruppen.

## <a name="4-create-the-required-resources"></a>4. Skapa de resurser som krävs 

Att utföra de uppgifter som krävs för att [konfigurera hybrid Azure AD-koppling](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join) har förenklats med hjälp av cmdleten [Initialize-SecMgmtHybirdDeviceEnrollment](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) som finns i [SecMgmt](https://www.powershellgallery.com/packages/SecMgmt) PowerShell-modulen. När du anropar den här cmdleten skapas och konfigureras den tjänstanslutningspunkt och grupprincip som krävs.

Du kan installera den här modulen genom att anropa följande från en instans av PowerShell:

```powershell
Install-Module SecMgmt
```

> [!IMPORTANT]
> Vi rekommenderar att du installerar den här modulen på Windows Server som kör Azure AD Connect.

Om du vill skapa den nödvändiga tjänstanslutningspunkten och grupprincipen anropar du cmdleten [Initialize-SecMgmtHybirdDeviceEnrollment.](https://github.com/microsoft/secmgmt-open-powershell/blob/master/docs/help/Initialize-SecMgmtHybirdDeviceEnrollment.md) Du behöver dina globala administratörsuppgifter för Microsoft 365 Business Premium när du utför den här uppgiften. När du är redo att skapa resurserna aktiverar du följande:

```powershell
PS C:\> Connect-SecMgmtAccount
PS C:\> Initialize-SecMgmtHybirdDeviceEnrollment -GroupPolicyDisplayName 'Device Management'
```

Det första kommandot upprättar en anslutning till Microsoft-molnet och när du uppmanas att ange dina globala administratörsautentiseringsuppgifter för Microsoft 365 Business Premium.

## <a name="5-link-the-group-policy"></a>5. Länka koncernpolicyn

1. Högerklicka på den plats där du vill länka principen i Konsolen Grupprinciphantering (GPMC) och välj *Länka ett befintligt grupprincipobjekt...* på snabbmenyn.
2. Markera den princip som skapats i ovanstående steg och klicka sedan på **OK**.

## <a name="get-the-latest-administrative-templates"></a>Hämta de senaste administrativa mallarna

Om du inte ser principen **Aktivera automatisk MDM-registrering med standardautentiseringsuppgifter för Azure AD**kan det bero på att du inte har ADMX installerat för Windows 10, version 1803, version 1809 eller version 1903. För att åtgärda problemet följer du dessa steg (Obs: den senaste MDM.admx är bakåtkompatibel):

1.  Ladda ned: [Administrativa mallar (.admx) för Windows 10 Maj 2019 Update (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).
2.  Installera paketet på PDC (Primary Domain Controller).
3.  Navigera, beroende på version till mappen: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 Maj 2019 Update (1903) v3**.
4.  Byt namn på mappen **Principdefinitioner** i sökvägen ovan till **PolicyDefinitions**.
5.  Kopiera **mappen Principdefinitioner** till **mappen C:\Windows\SYSVOL\domain\Policies**. 
    -   Om du planerar att använda ett centralt principarkiv för hela domänen lägger du till innehållet i PolicyDefinitions där.
6.  Starta om den primära domänkontrollanten för att principen ska vara tillgänglig. Denna procedur kommer att fungera för alla framtida versioner också.

Nu bör du kunna se principen **Aktivera automatisk MDM-registrering med standard Azure AD-autentiseringsuppgifter** tillgängliga.
