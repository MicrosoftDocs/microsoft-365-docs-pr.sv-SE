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
description: Lär dig hur du aktiverar Microsoft 365 för att skydda lokala Active-Directory-anslutna Windows 10-enheter i några få steg.
ms.openlocfilehash: 857651081fb10856d28dd419333ebef655388407
ms.sourcegitcommit: e6e704cbd9a50fc7db1e6a0cf5d3f8c6cbb94363
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/04/2020
ms.locfileid: "44564962"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business-premium"></a>Aktivera domänanslutna Windows 10-enheter som ska hanteras av Microsoft 365 Business Premium

Om din organisation använder Windows Server Active Directory lokalt kan du konfigurera Microsoft 365 Business Premium för att skydda dina Windows 10-enheter, samtidigt som du behåller åtkomsten till lokala resurser som kräver lokal autentisering.
Om du vill konfigurera det här skyddet kan du implementera **Hybrid Azure AD-anslutna enheter**. Dessa enheter är anslutna till både din lokala Active Directory och din Azure Active Directory.

I det här videoklippet beskrivs stegen för hur du konfigurerar det här för det vanligaste scenariot, vilket också beskrivs i de steg som följer.

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3C9hO]
  

## <a name="before-you-get-started-make-sure-you-complete-these-steps"></a>Innan du börjar måste du slutföra följande steg:
- Synkronisera användare till Azure AD med Azure AD Connect.
- Fullständig synkronisering av Azure AD Connect-organisationsenhet (OU).
- Kontrollera att alla domänanvändare som du synkroniserar har licenser till Microsoft 365 Business Premium.

Se [Synkronisera domänanvändare till Microsoft](manage-domain-users.md) för stegen.

## <a name="1-verify-mdm-authority-in-intune"></a>1. Verifiera MDM-myndigheten i Intune

Gå till portal.azure.com och högst upp på sidan sök efter Intune.
På sidan Microsoft Intune väljer du **Enhetsregistrering** och kontrollera att **MDM-behörigheten** är Intune på **sidan** **Microsoft Intune.**

- Om **MDM-behörigheten** är **Ingen**klickar du på **MDM-behörigheten** för att ange den till **Intune**.
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
- Gå till **Automatisk**registrering av Enheter med Windows Windows-registrering i **administrationscentret för Microsoft Slutpunktshanteraren**  >  **Windows**  >  **Windows Enrollment**  >  **Automatic Enrollment**.
- Kontrollera att MDM-användaromfattningen är aktiverad.

    1. Om du vill registrera alla datorer ställer du in på **Alla** för att automatiskt registrera alla användardatorer som är anslutna till Azure AD och nya datorer när användarna lägger till ett arbetskonto i Windows.
    2. Ange till **Vissa** för att registrera datorerna för en viss grupp användare.
        -  Lägg till önskade domänanvändare som synkroniserats i Azure AD i en [säkerhetsgrupp](../admin/create-groups/create-groups.md).
        -  Välj **välj grupper** om du vill aktivera MDM-användaromfattning för den säkerhetsgruppen.

## <a name="4-set-up-service-connection-point-scp"></a>4. Ställ in tjänstanslutningspunkt (SCP)

Dessa steg förenklas från [konfigurera hybrid azure AD-anslutning](https://docs.microsoft.com/azure/active-directory/devices/hybrid-azuread-join-managed-domains#configure-hybrid-azure-ad-join). För att slutföra de steg du behöver för att använda Azure AD Connect och dina globala administratörs- och Active Directory-administratörslösenord från Microsoft 365 Business Premium.

1.  Starta Azure AD Connect och välj sedan **Konfigurera**.
2.  På sidan **Ytterligare uppgifter** väljer du **Konfigurera enhetsalternativ**och väljer sedan **Nästa**.
3.  På sidan **Översikt** väljer du **Nästa**.
4.  På sidan **Anslut till Azure AD** anger du autentiseringsuppgifterna för en global administratör för Microsoft 365 Business Premium.
5.  På sidan **Enhetsalternativ** väljer du **Konfigurera Hybrid Azure AD-koppling**och väljer sedan **Nästa**.
6.  På **SCP-sidan,** för varje skog där du vill att Azure AD Connect ska konfigurera SCP, slutför du följande steg och välj sedan **Nästa:**
    - Markera rutan bredvid skogsnamnet. Skogen ska vara ditt AD-domännamn.
    - Öppna listrutan under kolumnen **Autentiseringstjänst** och välj matchande domännamn (det bör bara finnas ett enda alternativ).
    - Välj **Lägg till** om du vill ange autentiseringsuppgifterna för domänadministratören.  
7.  Välj Endast Windows 10 eller senare domänanslutna enheter på sidan **Enhetsoperativsystem.**
8.  På sidan **Klar att konfigurera** väljer du **Konfigurera**.
9.  På sidan **Konfigurationens klara** väljer du **Avsluta**.


## <a name="5-create-a-gpo-for-intune-enrollment--admx-method"></a>5. Skapa ett GPO för Intune-registrering – ADMX-metoden

Använda. ADMX-mallfil.

1.  Logga in på AD-server, sök och öppna **Server Manager**  >  **Tools**  >  **Grupprinciphantering**för Serverhanterarens verktyg .
2.  Välj ditt domännamn under **Domäner** och högerklicka på **Grupprincipobjekt** för att välja **Nytt**.
3.  Ge det nya nationella användarobjektet ett namn, till exempel "*Cloud_Enrollment*" och välj sedan **OK**.
4.  Högerklicka på den nya grupprincipobjektet under **Grupprincipobjekt** och välj **Redigera**.
5.  Gå till Administrativa mallar för **datorkonfigurationsprinciper**i Redigeraren för **grupprinciphantering.**  >  **Policies**  >  **Administrative Templates**  >  **Windows Components**  >  **MDM**
6. Högerklicka på **Aktivera automatisk MDM-registrering med standardautentiseringsuppgifter för Azure AD** och välj sedan **Aktiverad**  >  **OK**. Stäng redigeringsfönstret.

> [!IMPORTANT]
> Om du inte ser principen **Aktivera automatisk MDM-registrering med standardautentiseringsuppgifter för Azure AD**läser du Hämta de [senaste administrativa mallarna](#get-the-latest-administrative-templates).

## <a name="6-deploy-the-group-policy"></a>6. Distribuera grupprincipen

1.  Markera grupprincipobjektet från steg 3 ovan under **Domäner** > grupprincipobjekt i Serverhanteraren, till exempel "Cloud_Enrollment".
2.  Välj fliken **Omfattning** för dittrincipobjekt.
3.  Högerklicka på länken till domänen under **Länkar**på fliken Scope.
4.  Välj **Tvingad** om du vill distribuera den nationella säkerhetsobjektet och sedan **PÅ OK** på bekräftelseskärmen.

## <a name="get-the-latest-administrative-templates"></a>Hämta de senaste administrativa mallarna

Om du inte ser principen **Aktivera automatisk MDM-registrering med standardautentiseringsuppgifter för Azure AD**kan det bero på att du inte har ADMX installerat för Windows 10, version 1803, version 1809 eller version 1903. För att åtgärda problemet följer du dessa steg (Obs: den senaste MDM.admx är bakåtkompatibel):

1.  Ladda ned: [Administrativa mallar (.admx) för Windows 10 Maj 2019 Update (1903)](https://www.microsoft.com/download/details.aspx?id=58495&WT.mc_id=rss_alldownloads_all).
2.  Installera paketet på PDC (Primary Domain Controller).
3.  Navigera beroende på version till mappen: **C:\Program Files (x86)\Microsoft Group Policy\Windows 10 Maj 2019 Update (1903) v3**.
4.  Byt namn på mappen **Principdefinitioner** i sökvägen ovan till **PolicyDefinitions**.
5.  Kopiera **mappen Principdefinitioner** till **mappen C:\Windows\SYSVOL\domain\Policies**. 
    -   Om du planerar att använda ett centralt principarkiv för hela domänen lägger du till innehållet i PolicyDefinitions där.
6.  Starta om den primära domänkontrollanten för att principen ska vara tillgänglig. Denna procedur kommer att fungera för alla framtida versioner också.

Nu bör du kunna se principen **Aktivera automatisk MDM-registrering med standard Azure AD-autentiseringsuppgifter** tillgängliga.

