---
title: Begränsa delning i Microsoft 365
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
- m365initiative-externalcollab
search.appverid:
- SPO160
- MET150
f1.keywords: NOCSH
ms.custom: ''
localization_priority: Priority
description: Lär dig mer om olika alternativ för att begränsa eller inaktivera delning i Microsoft 365.
ms.openlocfilehash: 504d2b5dd72aead266697d273395e371ad6f5846
ms.sourcegitcommit: 8a726ed7ec19a8728c079780fa4d343a5f759fbb
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 11/13/2020
ms.locfileid: "49030047"
---
# <a name="limit-sharing-in-microsoft-365"></a>Begränsa delning i Microsoft 365

Även om du inte kan inaktivera intern delning helt, eller ta bort knappen Dela från webbplatser, finns det flera olika sätt som du kan använda för att begränsa delning i Microsoft 365 för att uppfylla organisationens behov.

Olika metoder för att dela filer visas i tabellen nedan. Klicka på länken i kolumnen **Delningsmetod** om du vill ha mer information.

|Delningsmetod|Beskrivning|Begränsningsalternativ|
|:-------------|:----------|:-------------|
|[Microsoft 365-grupp eller team](#microsoft-365-group-or-team)|Personer som beviljats åtkomst till ett team i Microsoft Teams eller en grupp i Microsoft 365 har redigeringsbehörighet för filer på den associerade SharePoint-webbplatsen.|Om gruppen eller teamet är privat skickas delningsinbjudningar för att gå med i gruppen till ägaren för godkännande. Administratörer kan inaktivera gäståtkomst eller använda känslighetsetikett för att förhindra åtkomst av personer utanför organisationen.|
|[SharePoint-webbplats](#sharepoint-site)|Personer kan beviljas åtkomst som ägare, medlem eller besökare till en SharePoint-webbplats, och får samma åtkomstnivå till filer på webbplatsen.|Webbplatsbehörigheter kan begränsas så att bara webbplatsägare kan dela webbplatsen. Administratörer kan ange att en webbplats ska vara skrivskyddad eller blockera åtkomst helt.|
|[Dela med vissa personer](#sharing-with-specific-people)|Webbplatsmedlemmar och personer med redigeringsbehörighet kan ge direkt behörighet till filer och mappar eller dela dem med hjälp av länkarna *Vissa personer*.|Webbplatsbehörigheter kan begränsas så att bara webbplatsägare kan dela filer och mappar. I det här fallet skickas direkt åtkomst och länkdelning för *Vissa personer* från webbplatsmedlemmar till webbplatsägaren för godkännande.|
|[Gästdelning i SharePoint](#sharepoint-guest-sharing)|SharePoint-webbplatsägare och -medlemmar kan dela filer och mappar med personer utanför organisationen.|Gästdelning kan inaktiveras för hela organisationen eller för enskilda webbplatser.|
|[Delningslänkarna *Personer i din organisation*](#people-in-your-organization-sharing-links)|SharePoint-webbplatsägare och -medlemmar kan dela filer genom att använda länkarna *Personer i din organisation* som fungerar för alla inom organisationen.|Länkarna *Personer i din organisation* kan inaktiveras på webbplatsnivå.|
|[Skapa webbplatser, grupper och teams](#create-sites-groups-and-teams)|Som standard kan användare skapa nya webbplatser, grupper och teams som de kan dela innehåll ifrån.|Administratörer kan begränsa vem som kan skapa webbplatser, grupper och teams.|
|[E-post](#email)|Personer som har åtkomst till en fil kan skicka den till andra via e-post.|Administratörer kan kryptera filer med hjälp av känslighetsetiketter för att förhindra att de delas med obehöriga personer.|
|[Nedladdning eller filkopia](#download-or-file-copy)|Personer som har åtkomst till en fil kan ladda ned eller kopiera och dela den med andra som inte omfattas av Microsoft 365.|Administratörer kan kryptera filer med hjälp av känslighetsetiketter för att förhindra att de delas med obehöriga personer.|

Du kan också begränsa under vilka förhållanden folk kommer åt delat innehåll. Mer information finns i [villkorlig åtkomst](#conditional-access) senare i den här artikeln.

Du kan använda de administratörskontroller som beskrivs i den här artikeln för att begränsa delning i organisationen, men vi rekommenderar att du använder de funktioner för säkerhet och efterlevnad som finns i Microsoft 365 för att skapa en säker delningsmiljö. Mer information finns i [Filsamarbete i SharePoint med Microsoft 365](https://docs.microsoft.com/sharepoint/deploy-file-collaboration) och [Konfigurera en team med säkerhetsisolering](secure-teams-security-isolation.md).

Om du vill förstå hur delning används i organisationen [kör du en rapport om fil- och mappdelning](https://docs.microsoft.com/sharepoint/sharing-reports).

## <a name="microsoft-365-group-or-team"></a>Microsoft 365-grupp eller team

Om du vill begränsa delning i en Microsoft 365-grupp eller ett Microsoft Teams-team är det viktigt att du gör gruppen eller teamet privat. Personer i din organisation kan gå med i en offentlig grupp eller ett team när som helst. Om inte gruppen eller teamet är privat finns det inget sätt att begränsa delningen av gruppen eller dess filer i organisationen.

### <a name="guest-sharing"></a>Gästdelning

Om du vill förhindra gäståtkomst i Teams kan du inaktivera gästdelning i administrationscentret för Teams.

Inaktivera gästdelning för Teams
1. I administrationscentret för Teams expanderar du **Organisationsomfattande inställningar** och klickar sedan på **Gäståtkomst**.
2. Inaktivera **Tillåt gäståtkomst i Teams**.
3. Klicka på **Spara**.

Om du vill förhindra gäståtkomst i Microsoft 365-grupper kan du inaktivera inställningarna för gäståtkomst för grupper i administrationscentret för Microsoft 365.

Inaktivera gästdelning i Microsoft 365-grupper
1. I administrationscentret för Microsoft 365 klickar du på **Inställningar** och klickar sedan på **Organisationsinställningar**.
2. På fliken **Tjänster** klickar du på **Microsoft 365-grupper**.
3. Avmarkera kryssrutorna **Låt gruppmedlemmar utanför organisationen få åtkomst till gruppinnehåll** och **Låt gruppägare lägga till personer utanför organisationen i grupper**.
4. Klicka på **Spara ändringar**.

    ![Skärmbild av delningsinställningarna för Microsoft 365-grupper i administrationscentret för Microsoft 365](../media/office-365-groups-guest-settings-off.png)

> [!NOTE]
> Om du vill förhindra gästdelning för en viss grupp eller team kan du göra det med [Microsoft PowerShell](per-group-guest-access.md) eller [känslighetsetiketter](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).

Du kan begränsa gästdelning till användare från vissa domäner genom att tillåta eller blockera domäner i Azure Active Directory. Detta påverkar även gästdelning i SharePoint om du har aktiverat [SharePoint- och OneDrive-integrering med Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview).

Tillåta delningsinbjudningar endast från angivna domäner
1. Gå till sidan Översikt i Azure Active Directory och klicka på **Organisationsrelationer**.
2. Klicka på **Inställningar**.
3. Under **Samarbetsbegränsningar** väljer du **Neka inbjudningar till de angivna domänerna** eller **Tillåt bara inbjudningar till de angivna domänerna**. Skriv sedan de domäner du vill använda.
4. Klicka på **Spara**.

    ![Skärmbild av inställningar för samarbetsbegränsningar i Azure Active Directory](../media/azure-ad-allow-only-specified-domains.png)

## <a name="sharepoint-site"></a>SharePoint-webbplats

Du kan begränsa SharePoint-webbplatsdelning till enbart webbplatsägare. Det förhindrar att webbplatsmedlemmar delar webbplatsen. Kom ihåg att om webbplatsen är ansluten till en Microsoft 365-grupp kan gruppmedlemmar bjuda in andra till gruppen och dessa användare får åtkomst till webbplatsen.

Begränsa webbplatsdelning till ägare
1. Klicka på kugghjulsikonen på webbplatsen och klicka sedan på **Webbplatsbehörigheter**.
2. Under **Delningsinställningar** klickar du på **Ändra delningsinställningar**.
3. Välj **Webbplatsägare och medlemmar, och personer med redigeringsbehörighet kan dela filer och mappar, men endast webbplatsägare kan dela webbplatsen**.
4. Klicka på **Spara**.

    ![Skärmbild av inställningar för delningsbehörigheter på en SharePoint-webbplats](../media/sharepoint-site-sharing-permissions-level-two.png)

Du kan förhindra användare som inte är medlemmar i webbplatsen från att begära åtkomst genom att inaktivera åtkomstbegäranden.

Inaktivera åtkomstbegäranden
1. Klicka på kugghjulsikonen på webbplatsen och klicka sedan på **Webbplatsbehörigheter**.
2. Under **Delningsinställningar** klickar du på **Ändra delningsinställningar**.
3. Inaktivera **Tillåt åtkomstbegäranden** och klicka sedan på **Spara**.

Du kan begränsa delning av webbplatser till vissa domäner genom att tillåta eller blockera domäner för den webbplatsen.

Begränsa webbplatsdelning per domän
1. I administrationscentret för SharePoint, under **Webbplatser** , klickar du på **Aktiva webbplatser**.
2. Klicka på den webbplats du vill konfigurera.
3. Klicka på **Redigera** under **Extern delning** på fliken **Principer**.
4. Under **Avancerade inställningar för extern delning** väljer du **Begränsa delning per domän**.
5. Lägg till de domäner du vill tillåta eller blockera och klicka sedan på **Spara**.
6. Klicka på **Spara**.

    ![Skärmbild av inställning för tillåtna domäner på webbplatsnivå](../media/limit-site-sharing-by-domain.png)

### <a name="block-access-to-a-site"></a>Blockera åtkomst till en webbplats

Du kan blockera åtkomst till en webbplats eller skrivskydda en webbplats genom att ändra webbplatsens låstillstånd. Mer information finns i [Låsa och låsa upp webbplatser](https://docs.microsoft.com/sharepoint/manage-lock-status).

### <a name="permissions-inheritance"></a>Behörighetsarv

Även om det inte rekommenderas, kan du använda [SharePoint behörighetsarv](https://docs.microsoft.com/sharepoint/what-is-permissions-inheritance) för att anpassa åtkomstnivåer för webbplatser och underwebbplatser.

## <a name="sharing-with-specific-people"></a>Dela med vissa personer

Om du vill begränsa delningen av en webbplats eller dess innehåll, kan du konfigurera webbplatsen så att bara webbplatsägare kan dela filer, mappar och webbplatsen. När det här är konfigurerat skickas webbplatsmedlemmars försök att dela filer eller mappar med hjälp av länkarna *Vissa personer* till webbplatsägaren för godkännande.

Begränsa delning av webbplatser, filer och mappar till ägare
1. Klicka på kugghjulsikonen på webbplatsen och klicka sedan på **Webbplatsbehörigheter**.
2. Under **Delningsinställningar** klickar du på **Ändra delningsinställningar**.
3. Välj **Endast webbplatsägare kan dela filer, mappar och webbplatsen**.
4. Klicka på **Spara**.

    ![Skärmbild av inställningar för delningsbehörigheter på en SharePoint-webbplats inställd på endast ägare.](../media/sharepoint-site-only-site-owners-can-share.png)

## <a name="sharepoint-guest-sharing"></a>Gästdelning i SharePoint

Om du vill förhindra att SharePoint- eller OneDrive-filer och -mappar delas med personer utanför organisationen, kan du inaktivera gästdelning för hela organisationen eller för en enskild webbplats.

Inaktivera gästdelning i SharePoint för organisationen
1. I administrationscentret för SharePoint, under **Principer** , klickar du på **Delning**.
2. Under **Extern delning** drar du reglaget för SharePoint nedåt till **Endast personer i din organisation**.
3. Klicka på **Spara**.

    ![Skärmbild av delningsinställningar för SharePoint på organisationsnivå inställd på Alla](../media/sharepoint-tenant-sharing-off.png)


Inaktivera gästdelning för en webbplats
1. I administrationscentret för SharePoint, under **Webbplatser** , klickar du på **Aktiva webbplatser**.
2. Klicka på den webbplats du vill konfigurera.
3. Klicka på **Redigera** under **Extern delning** på fliken **Principer**.
4. Under **Extern delning** väljer du **Endast personer i din organisation** och klickar sedan på **Spara**.

    ![Skärmbild på SharePoint webbplatsnivå delningsinställningar inställd på Bara personer i egen organisationen](../media/sharepoint-site-external-sharing-settings-off.png)

Om du vill tillåta delning med personer utanför organisationen, men du vill vara säker på att alla autentiseras, kan du inaktivera länkarna *Alla* (anonym delning) för hela organisationen eller för en enskild webbplats.

Inaktivera länkarna *Alla* på organisationsnivå
1. I administrationscentret för SharePoint, under **Principer** , klickar du på **Delning**.
2. Under **Extern delning** drar du reglaget för SharePoint nedåt till **Nya och befintliga gäster**.
3. Klicka på **Spara**.

    ![Skärmbild på delningsinställningar för SharePoint på organisationsnivå inställd på Nya och nuvarande gäster](../media/sharepoint-guest-sharing-new-existing-guests.png)

Inaktivera *Alla* -länkar för en webbplats
1. I administrationscentret för SharePoint, under **Webbplatser** , klickar du på **Aktiva webbplatser**.
2. Klicka på den webbplats du vill konfigurera.
3. Klicka på **Redigera** under **Extern delning** på fliken **Principer**.
4. Under **Extern delning** väljer du **Nya och befintliga gäster** och klickar sedan på **Spara**.

    ![Skärmbild av delningsinställningar för SharePoint på webbplatsnivå inställd på Nya och nuvarande inställningar](../media/sharepoint-site-external-sharing-settings-new-existing-guests.png)

## <a name="people-in-your-organization-sharing-links"></a>Delningslänkarna *Personer i din organisation*

Som standard kan medlemmar på en webbplats dela filer och mappar med andra personer i din organisation genom att använda länken *Personer i din organisation*. Du kan inaktivera länkarna *Personer i din organisation* genom att använda PowerShell:

`Set-SPOSite -Identity <site> -DisableCompanyWideSharingLinks`

Till exempel:

`Set-SPOSite -Identity https://contoso.sharepoint.com -DisableCompanyWideSharingLinks`

## <a name="create-sites-groups-and-teams"></a>Skapa webbplatser, grupper och teams

Som standard kan användare skapa nya webbplatser, grupper och teams som de kan använda för att dela innehåll (beroende på dina delningsinställningar). Du kan begränsa vem som kan skapa webbplatser, grupper och teams. Se följande exempel:

- [Hantera webbplatsskapande i SharePoint](https://docs.microsoft.com/sharepoint/manage-site-creation)
- [Hantera vilka som kan skapa Microsoft 365 Grupper](https://docs.microsoft.com/microsoft-365/solutions/manage-creation-of-groups)

Observera att begränsande av grupper hindrar teamskapande.

## <a name="email"></a>E-post

Du kan förhindra oönskad delning av e-postmeddelanden genom att använda kryptering. Detta förhindrar att e-postmeddelanden vidarebefordras eller på annat sätt delas med obehöriga användare. Du kan aktivera e-postkryptering genom att använda känslighetsetiketter. Mer information finns i [Begränsa åtkomst till innehåll med hjälp av kryptering i känslighetsetiketter](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels).

## <a name="download-or-file-copy"></a>Nedladdning eller filkopia

Användare som har åtkomst till filer och mappar i Microsoft 365 kan ladda ned filer och kopiera dem till externa medier. Om du vill minska risken för oönskad fildelning kan du kryptera innehållet med hjälp av känslighetsetiketter.

## <a name="conditional-access"></a>Villkorlig åtkomst

Villkorlig åtkomst i Azure Active Directory tillhandahåller alternativ för att begränsa eller förhindra delning med personer baserat på nätverksplats, enhets status, inloggnings risker och andra faktorer. Se [Vad är Villkorlig Åtkomst?](https://docs.microsoft.com/azure/active-directory/conditional-access/overview)

SharePoint tillhandahåller direkt integration med villkorlig åtkomst för Microsoft Azure Active Directory för både ohanterade enheter och nätverksplats. Se följande exempel för detaljer:

- [Hantera åtkomst från ohanterade enheter](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)
- [Hantera åtkomst till SharePoint och OneDrive data baserat på nätverksplats](https://docs.microsoft.com/sharepoint/control-access-based-on-network-location)

## <a name="see-also"></a>Se även

[Inställningar för gästdelning i Microsoft 365](microsoft-365-guest-settings.md)
