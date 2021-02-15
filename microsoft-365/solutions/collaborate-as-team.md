---
title: Samarbeta med gäster i ett team
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
description: Läs mer om de konfigurationssteg för Microsoft 365 som krävs för att skapa ett team för uppgift, konversation och dokumentation med gäster i Teams.
ms.openlocfilehash: 66c5692dd8cd233d8b3639f8ce0755ce51b60c0a
ms.sourcegitcommit: a62ac3c01ba700a51b78a647e2301f27ac437c5a
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/12/2021
ms.locfileid: "50233080"
---
# <a name="collaborate-with-guests-in-a-team"></a>Samarbeta med gäster i ett team

Om du behöver samarbeta med gäster i dokument, uppgifter och konversationer rekommenderar vi att du använder Microsoft Teams. Teams innehåller alla samarbetsfunktioner som är tillgängliga i Office och SharePoint med fortlöpande chatt och en anpassningsbar och utökningsbar uppsättning samarbetsverktyg i en enhetlig användarupplevelse.

I den här artikeln går vi igenom de konfigurationssteg för Microsoft 365 som krävs för att skapa ett team för samarbete med gäster. När du har konfigurerat gäståtkomst kan du bjuda in gäster till team genom att följa stegen i Lägga till [gäster i ett team i Teams.](https://support.microsoft.com/office/fccb4fa6-f864-4508-bdde-256e7384a14f)

## <a name="video-demonstration"></a>Videodemonstration

Den här videon visar konfigurationsstegen som beskrivs i det här dokumentet.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44NTr?autoplay=false]

## <a name="azure-external-collaboration-settings"></a>Inställningar för externt samarbete i Azure

Delning i Microsoft 365 styrs på högsta nivå av [inställningarna för B2B externt samarbete i Azure Active Directory.](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations) Om gästdelning är inaktiverat eller begränsat i Azure AD åsidosätter den här inställningen alla delningsinställningar som du konfigurerar i Microsoft 365.

Kontrollera inställningarna för B2B externt samarbete för att säkerställa att delning med gäster inte blockeras.

![Skärmbild av sidan med inställningar för organisationsrelationer i Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

Så här ställer du in inställningar för externt samarbete

1. Logga in på Azure Active Directory på [https://aad.portal.azure.com](https://aad.portal.azure.com) .
2. Klicka på Azure Active Directory i det **vänstra navigeringsfönstret.**
3. Klicka **på Externa identiteter.**
4. Klicka på **Inställningar för externt** samarbete i det vänstra navigeringsfönstret på kom **igång-skärmen.**
5. Se till **att administratörer och användare med gästrollen som** inbjudna kan bjuda in och att medlemmar kan bjuda **in** är båda inställda på **Ja.**
6. Om du har gjort ändringar klickar du på **Spara**.

Observera inställningarna i avsnittet **Begränsningar för** samarbete. Kontrollera att domänerna för de gäster som du vill samarbeta med inte är blockerade.

Om du arbetar med gäster från flera organisationer kanske du vill begränsa deras möjlighet att komma åt katalogdata. Det gör att de inte kan se vilka andra som är gäster i katalogen. Det gör du genom att **välja** Gästanvändare har begränsad åtkomst till egenskaper och medlemskap i katalogobjektsinställningar under begränsningar för gästanvändaråtkomst, och åtkomsten till gästanvändare begränsas till egenskaper och medlemskap i egna **katalogobjekt.** 

## <a name="teams-guest-access-settings"></a>Inställningar för gäståtkomst i Teams

Teams har en master på/av-knapp för gäståtkomst och en mängd olika inställningar som är tillgängliga för att styra vad gäster kan göra i ett team. Huvudväxeln, **Tillåt gäståtkomst i Teams måste** vara **på** för att gäståtkomst ska fungera i Teams.

Kontrollera att gäståtkomst är aktiverat i Teams och gör eventuella justeringar i gästinställningarna utifrån dina affärsbehov. Tänk på att de här inställningarna påverkar alla team.

![Skärmbild av växling för gäståtkomst i Teams](../media/teams-guest-access-toggle-on.png)

Att ange inställningar för gäståtkomst i Teams

1. Logga in på Administrationscenter för Microsoft 365 på [https://admin.microsoft.com](https://admin.microsoft.com).
2. Klicka på Visa alla i **navigeringsrutan till vänster.**
3. Under **Administrationscenter** klickar du på **Teams**.
4. I det vänstra navigeringsfönstret i administrationscentret för Teams expanderar du **organisationsomfattande inställningar och** klickar på **Gäståtkomst.**
5. Kontrollera att **Tillåt gäståtkomst i Teams** är inställt på **På**.
6. Gör önskade ändringar i de ytterligare gästinställningarna och klicka sedan på **Spara**.

När gäståtkomst i Teams har aktiverats kan du, om du vill, styra gäståtkomsten till enskilda team och deras associerade SharePoint-webbplatser med hjälp av känslighetsetiketter. Mer information finns i [Använd känslighetsetiketter för att skydda innehåll i Microsoft Teams, Microsoft 365-grupper och SharePoint-webbplatser](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).

> [!NOTE]
> Det kan ta upp till 24 timmar innan Teams gästinställningar aktiveras när du aktiverar det.

## <a name="microsoft-365-groups-guest-settings"></a>Gästinställningar i Microsoft 365-grupper

Teams använder Microsoft 365-grupper för teammedlemskap. Gästinställningarna i Microsoft 365 Groups måste vara aktiverat för att gäståtkomst i Teams ska fungera.

![Skärmbild av gästinställningarna för Microsoft 365-grupper i administrationscenter för Microsoft 365](../media/office-365-groups-guest-settings.png)

Så här anger du gästinställningar för Microsoft 365-grupper

1. I det vänstra navigeringsfönstret i administrationscentret för Microsoft 365 expanderar du **Inställningar.**
2. Klicka **på Organisationsinställningar.**
3. Klicka på **Microsoft 365-grupper i listan.**
4. Kontrollera att kryssrutorna Låt gruppägare lägga till personer utanför  organisationen i **Microsoft 365-grupper** som gäster och låt gästgruppmedlemmar få åtkomst till gruppinnehållskryssrutor är markerade.
5. Klicka på Spara ändringar om du **har gjort ändringar.**


## <a name="sharepoint-organization-level-sharing-settings"></a>Delningsinställningar på SharePoint-organisationsnivå

Teams-innehåll, till exempel filer, mappar och listor, lagras i SharePoint. För att gäster ska ha åtkomst till dessa objekt i Teams måste delningsinställningarna på SharePoint-organisationsnivå tillåta delning med gäster.

Inställningarna på organisationsnivå avgör vilka inställningar som är tillgängliga för enskilda webbplatser, inklusive webbplatser som är kopplade till grupper. Webbplatsinställningarna får inte vara mer tillåtande än inställningarna på organisationsnivå.

Välj Alla om du vill tillåta fil- och mappdelning med oauticerade **personer.** Om du vill säkerställa att alla gäster måste autentisera väljer du **Nya och befintliga gäster.** Välj den mest tillåtande inställningen som kommer att behövas av någon webbplats i organisationen.

![Skärmbild av delningsinställningar för SharePoint på organisationsnivå](../media/sharepoint-organization-external-sharing-controls.png)


Så här anger du delningsinställningar på organisationsnivå i SharePoint

1. Klicka på **SharePoint** i det vänstra navigeringsfönstret i administrationscentret **för** Microsoft 365.
2. Expandera Principer i det vänstra navigeringsfönstret i administrationscentret för SharePoint och **klicka** sedan på **Delning.**
3. Kontrollera att extern delning för SharePoint är inställt på **Alla** eller **Nya och befintliga gäster.**
4. Om du har gjort ändringar klickar du på **Spara**.


## <a name="sharepoint-organization-level-default-link-settings"></a>Standardinställningar för SharePoint-länkar på organisationsnivå

Standardinställningarna för fil- och mapplänk bestämmer vilket länkalternativ som ska visas för användare som standard när de delar en fil eller mapp. Användare kan ändra länktypen till något av de andra alternativen innan de delar, om du vill.

Tänk på att den här inställningen påverkar alla team och SharePoint-webbplatser i organisationen.

Välj någon av följande länktyper som väljs som standard när användare delar filer och mappar:

- **Alla som har** länken – Välj det här alternativet om du förväntar dig att göra mycket oauticerad delning av filer och mappar. Om du vill tillåta *alla länkar* men är orolig för oautisk delning av misstag kan du betrakta ett av de andra alternativen som standardalternativ. Den här länktypen är bara tillgänglig om du har aktiverat **delning för alla.**
- **Endast personer i organisationen –** Välj det här alternativet om du förväntar dig att de flesta fil- och mappdelningar ska vara med personer i organisationen.
- **Specifika personer** – Tänk på det här alternativet om du förväntar dig att göra mycket fil- och mappdelning med gäster. Den här typen av länk fungerar med gäster och kräver att de autentiseras.
 
![Skärmbild av delningsinställningar för filer och mappar för SharePoint på organisationsnivå](../media/sharepoint-organization-files-folders-sharing-settings.png)


Så här ställer du in standardinställningar för SharePoint-länkar på organisationsnivå

1. Gå till sidan Delning i administrationscentret för SharePoint.
2. Välj **den standarddelningslänk** som du vill använda under Fil- och mapplänkar.
3. Om du har gjort ändringar klickar du på **Spara**.

## <a name="create-a-team"></a>Skapa ett team

Nästa steg är att skapa det team som du planerar att använda för att samarbeta med gäster.

Skapa ett team
1. I Teams klickar du **på** Gå med i **eller skapa ett team längst** ned i den vänstra rutan på fliken Team.
2. Klicka **på Skapa ett team.**
3. Klicka **på Skapa ett team från grunden.**
4. Välj **Privat** eller **Offentlig.**
5. Skriv ett namn och en beskrivning för gruppen och klicka sedan på **Skapa.**
6. Klicka **på Hoppa över.**

Vi bjuder in användare senare. Sedan är det viktigt att kontrollera delningsinställningarna på webbplatsnivå för den SharePoint-webbplats som är kopplad till gruppen.

## <a name="sharepoint-site-level-sharing-settings"></a>Delningsinställningar på webbplatsnivå i SharePoint

Kontrollera inställningarna för delning på webbplatsnivå för att kontrollera att de tillåter den typ av åtkomst som du vill använda för det här teamet. Om du till exempel anger inställningar på organisationsnivå till **Alla,** men du vill att alla gäster ska autentiseras för teamet, kontrollerar du att delningsinställningarna på webbplatsnivå är inställda på Nya och **befintliga gäster.**

![Skärmbild av inställningar för extern delning för SharePoint](../media/sharepoint-site-external-sharing-settings.png)

Så här anger du delningsinställningar på webbplatsnivå
1. I det vänstra navigeringsfönstret i administrationscentret för SharePoint expanderar du **Webbplatser** och klickar **på Aktiva webbplatser.**
2. Välj webbplatsen för det team som du just har skapat.
3. Klicka på ... och väljer **Delning.**
4. Kontrollera att delning är inställt **på Alla** eller Nya och **befintliga gäster.**
5. Om du har gjort ändringar klickar du på **Spara**.

## <a name="invite-users"></a>Bjud in användare

Inställningarna för gästdelning är nu konfigurerade så att du kan börja lägga till interna användare och gäster i teamet. 

Så här bjuder du in interna användare till ett team
1. Klicka på Fler alternativ ( **) i** gruppen och klicka sedan på Lägg **\*\*\*** till **medlem.**
2. Skriv namnet på den person som du vill bjuda in.
3. Klicka **på Lägg** till och sedan på **Stäng.**

Bjuda in gäster till ett team
1. Klicka på Fler alternativ ( **) i** gruppen och klicka sedan på Lägg **\*\*\*** till **medlem.**
2. Skriv e-postadressen till gästen som du vill bjuda in.
3. Klicka **på Redigera gästinformation.**
4. Skriv gästens fullständiga namn och klicka på bockmarkeringen.
5. Klicka **på Lägg** till och sedan på **Stäng.**

## <a name="see-also"></a>Se även

[Metodtips för att dela filer och mappar med oautentiserade användare](best-practices-anonymous-sharing.md)

[Begränsa oavsiktlig exponering för filer när de delas med gäster](share-limit-accidental-exposure.md)

[Skapa en säker miljö för gästdelning](create-secure-guest-sharing-environment.md)

[Skapa ett B2B-extranät med hanterade gäster](b2b-extranet.md)

[SharePoint- och OneDrive-integrering med Azure AD B2B](https://docs.microsoft.com/sharepoint/sharepoint-azureb2b-integration-preview)

[Delningsalternativ är nedtonade när du delar från SharePoint eller OneDrive](https://docs.microsoft.com/sharepoint/troubleshoot/administration/sharing-options-grayed-out-when-sharing-from-sharepoint-online-or-onedrive)
