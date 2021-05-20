---
title: Samarbeta med gäster i ett dokument
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
recommendations: false
description: I den här artikeln får du lära dig hur du samarbetar med gäster i ett dokument i SharePoint och OneDrive.
ms.openlocfilehash: 338c7f32944bccb766ed923c12a9fceee4d81db8
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/19/2021
ms.locfileid: "52537841"
---
# <a name="collaborate-with-guests-on-a-document"></a>Samarbeta med gäster i ett dokument

Om du behöver samarbeta med personer utanför organisationen i dokument i SharePoint eller OneDrive kan du skicka dem en delningslänk till dokumentet. I den här artikeln går vi igenom de konfigurationssteg Microsoft 365 behöver för att konfigurera delningslänkar för SharePoint och OneDrive för organisationens behov.

## <a name="video-demonstration"></a>Videodemonstration

I den här videon visas konfigurationsstegen som beskrivs i det här dokumentet.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE450Vt?autoplay=false]

## <a name="azure-external-collaboration-settings"></a>Inställningar för externt Samarbete i Azure

Delning i Microsoft 365 styrs på sin högsta nivå av inställningarna för [B2B-externt samarbete i Azure Active Directory](/azure/active-directory/external-identities/delegate-invitations). Om gästdelning är inaktiverat eller begränsat i Azure AD åsidosätter den här inställningen alla delningsinställningar som du konfigurerar i Microsoft 365.

Kontrollera inställningarna för B2B externt samarbete för att säkerställa att delning med gäster inte blockeras.

![Skärmbild av sidan med inställningar för organisationsrelationer i Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

Inställningar för externt samarbete

1. Logga in till Azure Active Directory på [https://aad.portal.azure.com](https://aad.portal.azure.com).
2. I det vänstra navigeringsfönstret klickar du på **Azure Active Directory**.
3. Klicka på **Externa identiteter**.
4. På skärmen **Kom igång** i det vänstra navigeringsfönstret klickar du på **inställningar för externt samarbete**.
5. Se till **administratörer och användare i gästens inbjudna roll kan bjuda in** och **Medlemmar kan bjuda in** är båda inställda på **Ja**.
6. Om du har gjort ändringar klickar du på **Spara**.

Observera inställningarna i avsnittet **Begränsningar för samarbete**. Kontrollera att domänerna för de gäster som du vill samarbeta med inte är blockerade.

Om du arbetar med gäster från flera organisationer kanske du vill begränsa deras åtkomst till katalogdata. Det gör att de inte kan se vem mer som är gäst i katalogen. **Under begränsningar för gästanvändaråtkomst** kan du göra det genom att välja **Gästanvändare har begränsad åtkomst till egenskaper och medlemskap i inställningar för katalogobjekt** eller **Gästanvändaråtkomst begränsas till egenskaper och medlemskap i sina egna katalogobjekt**.

## <a name="sharepoint-organization-level-sharing-settings"></a>SharePoint delningsinställningar på organisationsnivå

För att personer utanför organisationen ska ha tillgång till ett dokument i SharePoint eller OneDrive måste delningsinställningarna på SharePoint- och OneDrive-organisationsnivå tillåta delning med personer utanför organisationen.

Inställningarna på organisationsnivå för SharePoint inställningar som ska vara tillgängliga för enskilda SharePoint webbplatser. Webbplatsinställningar får inte vara mer tillåtande än inställningarna på organisationsnivå. Inställningen på organisationsnivå för OneDrive avgör vilken delningsnivå som ska vara tillgänglig i användarnas OneDrive bibliotek.

Om SharePoint och OneDrive väljer du Alla om du vill tillåta icke-autisk fil- och **mappdelning.** Om du vill säkerställa att personer utanför organisationen måste autentisera väljer du **Nya och befintliga gäster.** *Länkar* för alla är det enklaste sättet att dela: personer utanför organisationen kan öppna länken utan autentisering och kan överföra den till andra.

Välj SharePoint mest tillåtande inställning som behövs av alla webbplatser i organisationen.

![Skärmbild av delningsinställningar för SharePoint på organisationsnivå](../media/sharepoint-organization-external-sharing-controls.png)


För att ange delningsinställningar för SharePoint på organisationsnivå

1. I det vänstra navigeringsfönstret i administrationscentret för Microsoft 365 går du till **Administrationscenter** och klickar på **SharePoint**.
2. I det SharePoint navigeringsfönstret i vänstra navigeringsfönstret, under Principer, **klickar du** på **Delning.**
3. Kontrollera att extern delning för SharePoint eller OneDrive är inställt på **Alla** eller **Nya och befintliga gäster.** (Observera att OneDrive kan vara mer tillåtande än SharePoint inställning.)
4. Om du har gjort ändringar klickar du på **Spara**.

## <a name="sharepoint-organization-level-default-link-settings"></a>Standardinställningar för länkar på organisationsnivå i SharePoint

Standardinställningarna för filer och mappar avgör vilket länkalternativ som visas för användarna när de delar en fil eller mapp. Användare kan ändra länktypen till något av de andra alternativen innan de delar om de vill.

Tänk på att den här SharePoint påverkar webbplatser i organisationen samt OneDrive.

Välj en länk från någon av följande typer som sedan väljs som standard när användare delar filer och mappar:

- **Alla som har länken** – Välj det här alternativet om du förväntar dig att göra många oautherade fil- och mappdelningar. Om du vill tillåta att *Alla* -länkar men är bekymrad över oavsiktlig overifierad delning kan du överväga något av de andra alternativen som standard. Den här länktypen är bara tillgänglig om du har aktiverat **Alla** delning.
- **Endast personer i organisationen** – Välj det här alternativet om du förväntar dig att de flesta fil- och mappdelningar ska vara med personer inom organisationen.
- **Vissa personer** – Överväg det här alternativet om du förväntar dig att göra mycket fil- och mappdelning med gäster. Den här länktypen fungerar med gäster och kräver att de verifieras.
 
![Skärmbild av delningsinställningar för filer och mappar för SharePoint på organisationsnivå](../media/sharepoint-organization-files-folders-sharing-settings.png)


Så här anger SharePoint och OneDrive inställningar för länkar på organisationsnivå

1. Gå till sidan Delning i administrationscentret för SharePoint.
2. Välj den standard delningslänk du vill använda under **Fil- och mapplänkar**.
3. Om du har gjort ändringar klickar du på **Spara**.

Om du vill ange behörighet för delningslänken går du till Välj den **behörighet som är markerad som standard för delningslänkar.**

1. Välj **Visa** om du inte vill att obehöriga användare ska kunna göra ändringar i filer och mappar.
2. Välj **Redigera** om du vill tillåta att obehöriga användare gör ändringar i filer och mappar.

Observera att ovanstående två förinsändningsalternativ inte bara kan tillämpas för gäster/externa användare utan även för interna användare. Vilket behörighetsalternativ du väljer avgörs av eget gottfinnande.

Ange behörigheter för länkar som tillåter delning med alla

1. Under de **här länkarna kan ge följande behörigheter:** underfönstret 
    1. I **listrutan** Filer 
        - Välj **Visa och** redigera om du vill tillåta oauthenticerade användare att göra ändringar i filerna.
        - Välj **Visa** om du inte vill att oauthenticerade användare ska göra ändringar i filerna.
    2. I **listrutan** Mappar
        - Välj **Visa, redigera och ladda** upp om du vill tillåta att icke-obehöriga användare gör ändringar i mapparna.
        - Välj **Visa** om du inte vill att obehöriga användare ska göra ändringar i mapparna.

## <a name="sharepoint-site-level-sharing-settings"></a>Delningsinställningar på webbplatsnivå i SharePoint

Om du delar filer och mappar som finns på en SharePoint-webbplats måste du kontrollera inställningarna för delning på webbplatsnivå för den webbplatsen.

![Skärmbild av inställningar för extern delning för SharePoint](../media/sharepoint-site-external-sharing-settings.png)

Så här anger du delningsinställningar på webbplatsnivå

1. I navigeringsfönstret till vänster i administrationscentret för SharePoint expanderar du **Webbplatser** och klickar på **Aktiva webbplatser**.
2. Välj den webbplats där du vill dela filer och mappar med gäster.
3. Bläddra åt höger på raden (där den valda webbplatsen finns) och klicka någonstans i kolumnen **Extern** delning.
4. På den sida som visas klickar du på **fliken** Principer.
5. Under fönstret **Extern delning** klickar du på **Redigera.**
6. Kontrollera att delning är inställt på **Alla** eller **Nya och befintligt gäster**.
7. Om du har gjort ändringar klickar du på **Spara**.

## <a name="invite-users"></a>Bjuda in användare

Inställningarna för gästdelning är nu konfigurerade. så att användare nu kan dela filer och mappar med personer utanför organisationen. Mer [information OneDrive dela filer och](https://support.office.com/article/9fcc2f7d-de0c-4cec-93b0-a82024800c07) SharePoint mappar finns i Dela filer [och](https://support.office.com/article/1fe37332-0f9a-4719-970e-d2578da4941c) mappar.

## <a name="see-also"></a>Se även

[Metodtips för att dela filer och mappar med overifierade användare](best-practices-anonymous-sharing.md)

[Begränsa oavsiktlig exponering för filer när de delas med gäster](share-limit-accidental-exposure.md)

[SharePoint- och OneDrive-integrering med Azure AD B2B](/sharepoint/sharepoint-azureb2b-integration-preview)