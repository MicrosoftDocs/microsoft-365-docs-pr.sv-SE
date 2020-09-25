---
title: Samar beta med gäster på en webbplats
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-3tiersprotection
- m365solution-securecollab
ms.custom:
- seo-marvel-apr2020
localization_priority: Normal
f1.keywords: NOCSH
description: Lär dig mer om de Microsoft 365-inställningar som behövs för att konfigurera en SharePoint-webbplats för samarbete med gäster.
ms.openlocfilehash: cb3cfc52191be4bacfb9d84672131149082ee80e
ms.sourcegitcommit: 1423e08a02d30f0a2b993fb99325c3f499c31787
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277574"
---
# <a name="collaborate-with-guests-in-a-site"></a>Samar beta med gäster på en webbplats

Om du behöver samar beta med gäster mellan dokument, data och listor kan du använda en SharePoint-webbplats. Moderna SharePoint-webbplatser är anslutna till Microsoft 365-grupper och kan hantera webbplats medlemskap och tillhandahålla ytterligare samarbets verktyg, till exempel en delad post låda och kalender.

I den här artikeln går vi igenom de Microsoft 365-inställningar som behövs för att konfigurera en SharePoint-webbplats för samarbete med gäster.

## <a name="video-demonstration"></a>Videodemonstration

I den här videon visas de konfigurations steg som beskrivs i det här dokumentet.</br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE44Llg?autoplay=false]

## <a name="azure-external-collaboration-settings"></a>Inställningar för extern samarbete i Azure

Delning i Microsoft 365 regleras på högsta nivå av [organisations Relations inställningarna i Azure Active Directory](https://docs.microsoft.com/azure/active-directory/external-identities/delegate-invitations). Om gäst delning är inaktiverat eller begränsat i Azure AD åsidosätter detta eventuella delnings inställningar som du konfigurerar i Microsoft 365.

Kontrol lera inställningarna för extern samarbete för att se till att delning med gäster inte blockeras.

![Skärm bild av sidan med inställningar för extern samarbets katalog i Azure Active Directory](../media/azure-ad-organizational-relationships-settings.png)

Så här anger du inställningar för extern samarbete:


1. Logga in på Microsoft Azure på [https://portal.azure.com](https://portal.azure.com) .
2. I det vänstra navigerings fältet klickar du på **Azure Active Directory**.
3. Välj **externa identiteter** och klicka på **Inställningar för externt samarbete**.
4. I fönstret **Inställningar för gäst inbjudningar** kontrollerar du att **Administratörer och användare i rollen som inbjudan gäst kan bjuda** in och **medlemmar kan bjuda** in till **Ja**.
5. Om du har gjort ändringar klickar du på **Spara**.

Observera inställningarna i avsnittet **samarbets begränsningar** . Kontrol lera att domänerna för de gäster som du vill samar beta med inte är blockerade.

Om du arbetar med gäster från flera organisationer kan det vara bra att begränsa deras möjligheter att komma åt katalog data. Detta hindrar dem från att se vem som är gäst i katalogen. För att göra det, under **gäst användares restriktioner**, väljer du **gäst användare har begränsad åtkomst till egenskaper och medlemskap i inställningar för katalog objekt** eller **gäst användares åtkomst är begränsad till egenskaper och medlemskap i deras egna katalog objekt**.

## <a name="microsoft-365-groups-guest-settings"></a>Inställningar för Microsoft 365-grupper

Moderna SharePoint-webbplatser använder Microsoft 365 Groups för att styra åtkomst till webbplatsen. Inställningarna för gruppen Microsoft 365-grupper måste aktive ras för att gäst åtkomsten på SharePoint-webbplatser ska fungera.

![Skärmbild av gästinställningarna för Microsoft 365-grupper i administrationscenter för Microsoft 365](../media/office-365-groups-guest-settings.png)

Ange inställningar för Microsoft 365-grupper

1. I det vänstra navigerings fältet i administrations centret för Microsoft 365 expanderar du **Inställningar**.
2. Klicka på **tjänster & tillägg**.
3. I listan klickar du på **Microsoft 365 Groups**.
4. Kontrol lera att **grupp medlemmarna utanför din organisation får grupp innehållet** och **låta grupp ägarna lägga till personer utanför organisationen för grupper** markerar båda kryss rutorna.
5. Om du har gjort ändringarna klickar du på **Spara ändringar**.


## <a name="sharepoint-organization-level-sharing-settings"></a>Delnings inställningar för SharePoint-organisationnivå

För att gäster ska ha åtkomst till SharePoint-webbplatser måste delnings inställningarna för SharePoint-organisations nivå tillåta delning med gäster.

Inställningarna på organisations nivå bestämmer vilka inställningar som är tillgängliga för enskilda webbplatser. Webbplats inställningarna kan inte vara mer tillåtna än inställningarna på organisations nivå.

Om du vill tillåta overifierad fil-och mappdelning väljer du **vem som helst**. Om du vill vara säker på att alla personer utanför din organisation måste autentisera, väljer du **nytt och befintligt gäster**. Välj den mest tillåtna inställningen som behövs för en webbplats i organisationen.

![Skärmbild av delningsinställningar för SharePoint på organisationsnivå](../media/sharepoint-organization-external-sharing-controls.png)


Så här anger du delnings inställningar för SharePoint-organisationnivå

1. Klicka på **SharePoint**i det vänstra navigerings fältet **i administrations**centret för Microsoft 365.
2. I navigeringsfönstret till vänster i administrationscentret för SharePoint klickar du på **Delning**.
3. Kontrol lera att extern delning för SharePoint är inställt på **vem som helst** eller **nya och befintliga gäster**.
4. Om du har gjort ändringar klickar du på **Spara**.

## <a name="create-a-site"></a>Skapa en webbplats

Nästa steg är att skapa den webbplats du planerar att använda för att samar beta med gäster.

Skapa en webbplats
1. I administrationscentret för SharePoint, under **Webbplatser**, klickar du på **Aktiva webbplatser**.
2. Klicka på **Skapa**.
3. Klicka på **grupp webbplats**.
4. Ange ett namn på webbplatsen och ange gruppens ägare (webbplats ägare).
5. Under **Avancerade inställningar**väljer du om du vill att det ska vara en offentlig eller privat webbplats.
6. Klicka på **Nästa**.
7. Klicka på **Slutför**.

Vi bjuder in användare senare. Sedan är det viktigt att kontrol lera delnings inställningarna för webbplatsen på webbplats nivå.

## <a name="sharepoint-site-level-sharing-settings"></a>Delnings inställningar för SharePoint-webbplats nivå

Kontrol lera inställningarna för delning av webbplats nivå för att se till att de tillåter åtkomst typen som du vill använda för webbplatsen. Om du till exempel ställer in inställningar på organisations nivå till **vem som helst**, men vill att alla gäster ska autentiseras för webbplatsen, kontrollerar du att inställningarna för delning av webbplats nivå är inställda på **nya och befintliga gäster**.

Observera att webbplatsen inte kan delas med overifierade personer (**alla** inställningar), men enskilda filer och mappar kan.

![Skärmbild av inställningar för extern delning för SharePoint](../media/sharepoint-site-external-sharing-settings.png)

Ange delnings inställningar på webbplats nivå
1. I navigeringsfönstret till vänster i administrationscentret för SharePoint expanderar du **Webbplatser** och klickar på **Aktiva webbplatser**.
2. Välj den webbplats du just har skapat.
3. Klicka på **Delning** i menyfliksområdet.
4. Kontrol lera att delning är inställt på **vem som helst** eller **nya och befintliga gäster**.
5. Om du har gjort ändringar klickar du på **Spara**.

## <a name="invite-users"></a>Bjuda in användare

Inställningar för gäst delning är nu konfigurerade så att du kan börja lägga till interna användare och gäster på din webbplats. Webbplats åtkomsten styrs via den associerade Microsoft 365-gruppen, så vi lägger till användare där.

Bjuda in interna användare till en grupp
1. Navigera till den webbplats där du vill lägga till användare.
2. Klicka på **medlemmar** i det övre högra hörnet.
3. Klicka på **Lägg till medlemmar**.
4. Skriv namnen eller e-postadresserna för de användare som du vill bjuda in till webbplatsen och klicka sedan på **Spara**.

Gäst användare kan inte läggas till från webbplatsen. Du måste lägga till dem med hjälp av Outlook på webben.

Så här bjuder du in gäster till en grupp
1. I Outlook på webben klickar du under **grupper**på den grupp där du vill lägga till medlemmar.
2. Öppna grupp kontakt kortet och klicka på **Lägg till medlemmar**under **fler alternativ** (...).
3. Skriv e-postadresserna för de gäster som du vill bjuda in och klicka sedan på **Lägg till**.
4. Klicka på **Stäng**.

## <a name="see-also"></a>Se även

[Metodtips för att dela filer och mappar med oautentiserade användare](best-practices-anonymous-sharing.md)

[Begränsa oavsiktlig exponering för filer när de delas med gäster](share-limit-accidental-exposure.md)

[Skapa en säker miljö för gästdelning](create-secure-guest-sharing-environment.md)

[Skapa ett B2B-extranät med hanterade gäster](b2b-extranet.md)
