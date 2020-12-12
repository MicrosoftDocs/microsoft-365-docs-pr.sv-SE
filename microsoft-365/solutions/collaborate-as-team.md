---
title: Samar beta med gäster i ett team
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
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: Lär dig mer om de Microsoft 365-konfigurations steg som behövs för att skapa ett team för aktivitet, konversation och dokument samarbete med gäster i Teams.
ms.openlocfilehash: cc962e22bde70220e07f805b0a7a83c111886369
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 12/11/2020
ms.locfileid: "49659612"
---
# <a name="collaborate-with-guests-in-a-team"></a>Samar beta med gäster i ett team

Om du behöver samar beta med gäster mellan dokument, uppgifter och konversationer rekommenderar vi att du använder Microsoft Teams. Teams innehåller alla samarbets funktioner som är tillgängliga i Office och SharePoint med beständig chatt och en anpassningsbar och en utökning av samarbets verktyg i enhetlig användar upplevelse.

I den här artikeln går vi igenom de Microsoft 365-inställningar som behövs för att skapa ett team för samarbete med gäster.

## <a name="video-demonstration"></a>Videodemonstration

I den här videon visas de konfigurations steg som beskrivs i det här dokumentet.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-external-collaboration-settings"></a>Inställningar för extern samarbete i Azure

Delning i Microsoft 365 regleras på högsta nivå av [B2B-inställningen för externt samarbete i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations). Om gäst delning är inaktiverat eller begränsat i Azure AD åsidosätter den här inställningen eventuella delnings inställningar som du konfigurerar i Microsoft 365.

Kontrol lera inställningarna för externt samarbete för B2B för att säkerställa att delning med gäster inte blockeras.

![Skärmbild av sidan med inställningar för organisationsrelationer i Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

Så här anger du inställningar för extern samarbete

1. Logga in på Azure Active Directory på [https://aad.portal.azure.com](https://aad.portal.azure.com) .
2. I det vänstra navigerings fönstret klickar du på **Azure Active Directory**.
3. Klicka på **externa identiteter**.
4. Klicka på **Inställningar för extern samarbete** i det vänstra navigerings fönstret på skärmen **Kom igång** .
5. Kontrol lera att **Administratörer och användare i rollen för att bjuda in gäst kan bjuda** in och **medlemmar kan bjuda** in till **Ja**.
6. Om du har gjort ändringar klickar du på **Spara**.

Observera inställningarna i avsnittet **samarbets begränsningar** . Kontrol lera att domänerna för de gäster som du vill samar beta med inte är blockerade.

Om du arbetar med gäster från flera organisationer kan det vara bra att begränsa deras möjligheter att komma åt katalog data. Detta hindrar dem från att se vem som är gäst i katalogen. För att göra det, under **gäst användares restriktioner**, väljer du **gäst användare har begränsad åtkomst till egenskaper och medlemskap i inställningar för katalog objekt** eller **gäst användares åtkomst är begränsad till egenskaper och medlemskap i deras egna katalog objekt**.

## <a name="teams-guest-access-settings"></a>Inställningar för gäst åtkomst för Teams

Teams har en Master på/av-knapp för gäst åtkomst och en mängd olika inställningar som är tillgängliga för att kontrol lera vad gäster kan göra i ett team. Huvud växeln, **Tillåt gäst åtkomst i teamen** måste vara **aktive** ras för att gäst åtkomst ska fungera i Teams.

Kontrol lera att gäst åtkomst är aktive rad i Teams och gör eventuella justeringar av gäst inställningarna utifrån dina företags behov. Tänk på att dessa inställningar påverkar alla team.

![Skärmbild av växling för gäståtkomst i Teams](../media/teams-guest-access-toggle-on.png)

Att ange inställningar för gäståtkomst i Teams

1. Logga in på Administrationscenter för Microsoft 365 på [https://admin.microsoft.com](https://admin.microsoft.com).
2. I det vänstra navigerings fönstret klickar du på **Visa alla**.
3. Under **Administrationscenter** klickar du på **Teams**.
4. I administrations centret för Teams, i det vänstra navigerings fönstret, expanderar du **Inställningar för hela organisationen** och klickar på **gäst åtkomst**.
5. Kontrollera att **Tillåt gäståtkomst i Teams** är inställt på **På**.
6. Gör önskade ändringar i de ytterligare gästinställningarna och klicka sedan på **Spara**.

När gästen är aktive rad kan du välja att kontrol lera gäst åtkomsten till enskilda team och deras tillhör ande SharePoint-webbplatser med känslighets etiketter. Mer information finns i [använda känslighets etiketter för att skydda innehåll i Microsoft Teams, microsoft 365 Groups och SharePoint-webbplatser](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).

> [!NOTE]
> Det kan ta upp till 24 timmar innan gäst inställningarna blir aktiva när du har aktiverat det.

## <a name="microsoft-365-groups-guest-settings"></a>Inställningar för Microsoft 365-grupper

Teams använder Microsoft 365 Groups för grupp medlemskap. Inställningarna för gruppen Microsoft 365-grupper måste aktive ras för att gäst åtkomst ska fungera.

![Skärmbild av gästinställningarna för Microsoft 365-grupper i administrationscenter för Microsoft 365](../media/office-365-groups-guest-settings.png)

Ange inställningar för Microsoft 365-grupper

1. Expandera **Inställningar** i det vänstra navigerings fönstret i administrations centret för Microsoft 365.
2. Klicka på **org Settings**.
3. I listan klickar du på **Microsoft 365 Groups**.
4. Kontrol lera att **gruppen låt grupp ägarna lägger till personer utanför organisationen till Microsoft 365-grupper som gäster** och **Låt grupp medlemmarna i gruppen för gäst grupps medlemmar** vara markerade.
5. Om du har gjort ändringarna klickar du på **Spara ändringar**.


## <a name="sharepoint-organization-level-sharing-settings"></a>Delnings inställningar för SharePoint-organisationnivå

Team innehåll som filer, mappar och listor lagras i SharePoint. För att gäster ska få till gång till dessa objekt i Teams måste delnings inställningarna för SharePoint på organisations nivå tillåta delning med gäster.

Inställningarna på organisations nivå bestämmer vilka inställningar som är tillgängliga för enskilda webbplatser, till exempel webbplatser som är kopplade till Teams. Webbplats inställningarna kan inte vara mer tillåtna än inställningarna på organisations nivå.

Om du vill tillåta fil-och mappdelning med oautentiserade personer väljer du **vem som helst**. Om du vill vara säker på att alla gäster måste autentisera, väljer du **nytt och befintligt gäster**. Välj den mest tillåtna inställningen som behövs för en webbplats i organisationen.

![Skärmbild av delningsinställningar för SharePoint på organisationsnivå](../media/sharepoint-organization-external-sharing-controls.png)


Så här anger du delnings inställningar för SharePoint på organisations nivå

1. Klicka på **SharePoint** i det vänstra navigerings fältet **i administrations** centret för Microsoft 365.
2. Expandera **principer** i det vänstra navigerings fönstret i administrations centret för SharePoint och klicka sedan på **delning**.
3. Kontrol lera att extern delning för SharePoint är inställt på **vem som helst** eller **nya och befintliga gäster**.
4. Om du har gjort ändringar klickar du på **Spara**.


## <a name="sharepoint-organization-level-default-link-settings"></a>Inställningar för SharePoint-standardinställningar på organisations nivå

Standardinställningen för fil-och mappikonen styr det länk alternativ som visas för användarna som standard när de delar en fil eller mapp. Användare kan ändra länktyp till något av de andra alternativen innan de delas, om så önskas.

Tänk på att den här inställningen påverkar alla team och SharePoint-webbplatser i organisationen.

Välj någon av följande länk typer som visas som standard när användare delar filer och mappar:

- **Vem som helst med länken** – Välj det här alternativet om du förväntar dig att göra en massa delning av filer och mappar. Om du vill tillåta *alla* länkar, men är bekymrad över oavsiktlig autentisering, bör du överväga något av de andra alternativen som standard. Den här länk typen är bara tillgänglig om du har aktiverat **någon** delning.
- **Endast personer i organisationen** – Välj det här alternativet om du tror att de flesta fil-och mappdelning är med i din organisation.
- **Vissa personer** -Överväg det här alternativet om du förväntar dig att göra många fil-och mappdelning med gästerna. Den här typen av länk fungerar med gäster och kräver att de autentiseras.
 
![Skärmbild av delningsinställningar för filer och mappar för SharePoint på organisationsnivå](../media/sharepoint-organization-files-folders-sharing-settings.png)


Så här anger du inställningar för standard länken för SharePoint på organisations nivå

1. Gå till sidan delning i administrations centret för SharePoint.
2. Under **fil-och mappaktiviteter** väljer du den standard delnings länk som du vill använda.
3. Om du har gjort ändringar klickar du på **Spara**.

## <a name="create-a-team"></a>Skapa ett team

Nästa steg är att skapa teamet som du planerar att använda för att samar beta med gäster.

Skapa ett team
1. I Teams klickar du på **Anslut eller skapa ett team** längst ned i den vänstra rutan på fliken **team** .
2. Klicka på **skapa ett team**.
3. Klicka på **skapa ett team från början**.
4. Välj **privat** eller **offentlig**.
5. Ange ett namn och en beskrivning för gruppen och klicka sedan på **skapa**.
6. Klicka på **hoppa över**.

Vi bjuder in användare senare. Sedan är det viktigt att kontrol lera delnings inställningarna på webbplats nivå för SharePoint-webbplatsen som är kopplad till gruppen.

## <a name="sharepoint-site-level-sharing-settings"></a>Delnings inställningar på SharePoint-webbplats nivå

Kontrol lera inställningarna för delning av webbplats nivå för att se till att de tillåter åtkomst typen för det här teamet. Om du till exempel ställer in inställningar på organisations nivå till **vem som helst**, men vill att alla gäster ska autentiseras för det här teamet, kontrollerar du att inställningarna för delning av webbplats nivå är inställda på **nya och befintliga gäster**.

![Skärmbild av inställningar för extern delning för SharePoint](../media/sharepoint-site-external-sharing-settings.png)

Ange delnings inställningar på webbplats nivå
1. I administrations centret för SharePoint, i det vänstra navigerings fönstret, expanderar du **webbplatser** och klickar på **aktiva webbplatser**.
2. Välj webbplatsen för det team som du just har skapat.
3. Klicka på... och välj **dela**.
4. Kontrol lera att delning är inställt på **vem som helst** eller **nya och befintliga gäster**.
5. Om du har gjort ändringar klickar du på **Spara**.

## <a name="invite-users"></a>Bjuda in användare

Inställningar för gäst delning är nu konfigurerade så att du kan börja lägga till interna användare och gäster i gruppen. 

Bjuda in interna användare till ett team
1. I gruppen klickar du på **fler alternativ** ( **\*\*\*** ) och sedan på **Lägg till medlem**.
2. Skriv namnet på den person som du vill bjuda in.
3. Klicka på **Lägg till** och sedan på **Stäng**.

Så här bjuder du in gäster till ett team
1. I gruppen klickar du på **fler alternativ** ( **\*\*\*** ) och sedan på **Lägg till medlem**.
2. Skriv e-postadressen för den gäst som du vill bjuda in.
3. Klicka på **Redigera gäst information**.
4. Skriv in gästens namn och klicka på bock markeringen.
5. Klicka på **Lägg till** och sedan på **Stäng**.

## <a name="see-also"></a>Se även

[Metodtips för att dela filer och mappar med oautentiserade användare](best-practices-anonymous-sharing.md)

[Begränsa oavsiktlig exponering för filer när de delas med gäster](share-limit-accidental-exposure.md)

[Skapa en säker miljö för gästdelning](create-secure-guest-sharing-environment.md)

[Skapa ett B2B-extranät med hanterade gäster](b2b-extranet.md)

[SharePoint och OneDrive-integrering med Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)
