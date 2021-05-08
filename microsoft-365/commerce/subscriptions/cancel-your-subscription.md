---
title: Avbryt din prenumeration
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_subscriptions
- PPM_jmueller
ms.reviewer: jkinma
search.appverid:
- MET150
description: Få reda på hur du avbryter din utvärderingsversion eller betalda prenumeration för Microsoft 365 för företag.
ms.date: 04/08/2021
ms.openlocfilehash: 15ab7ed31af24fa4cb1c83c6babc945871584375
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244666"
---
# <a name="cancel-your-subscription"></a>Avbryt din prenumeration

*Berättigande:* Om du har färre än 25 licenser tilldelade till användare kan du när som helst avbryta din utvärderingsversion eller betalda prenumeration av Microsoft 365 för företag online i administrationscentret för Microsoft 365. Om du har fler än 25 licenser tilldelade till användare, minska det till färre än 25 eller [ring supporten för att avbryta din prenumeration](../../admin/contact-support-for-business-products.md).

*Återbetalning:* All proportionerlig kredit kommer returneras till dig inom nästa faktureringscykel.

> [!NOTE]
> Om du har flera prenumerationer på samma produkt, såsom Microsoft 365 Business Premium, kommer det inte påverka de köpta licenserna eller tjänsterna för andra prenumerationer om du avbryter en av dem.

## <a name="before-you-begin"></a>Innan du börjar

Du måste vara global administratör eller faktureringsadministratörer för att kunna utföra åtgärder som beskrivs i den här artikeln. Mer information finns i [Om administratörsroller](../../admin/add-users/about-admin-roles.md).

## <a name="steps-to-cancel-your-subscription"></a>Steg för att avbryta din prenumeration

Om du har lagt till ett eget domännamn för användning med din prenumeration måste du ta bort domänen innan du avbryter prenumerationen. Mer information finns i [Ta bort en domän](../../admin/get-help-with-domains/remove-a-domain.md).

::: moniker range="o365-worldwide"

1. I administrationscentret går du till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Dina produkter</a>.
2. Hitta den prenumeration du vill avbryta. Välj **Fler åtgärder** (tre punkter) och välj sedan **Avbryt prenumeration**.
3. I fönstret **Avbryt prenumeration** väljer du en anledning till varför du avbryter prenumerationen. Alternativt kan du ge valfri feedback.
4. Välj **Spara**.

Din prenumeration får status **Inaktiverad** och har begränsad funktionalitet tills den tas bort. Mer information om vad du kan förvänta dig när en betald Microsoft 365 för företag-prenumeration avbryts finns i [Vad händer med data och åtkomst när min Microsoft 365 för företag-prenumeration avslutas?](what-if-my-subscription-expires.md)

> [!NOTE]
> Om du tar bort en prenumeration försvinner utgångna och inaktiverade faser så tas data och innehåll i SharePoint Online, inklusive OneDrive, bort omedelbart.

::: moniker-end

::: moniker range="o365-germany"

1. I administrationscentret går du till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=847745" target="_blank">Dina produkter</a>.

::: moniker-end

::: moniker range="o365-21vianet"

1. I administrationscentret går du till sidan **Fakturering** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=850626" target="_blank">Dina produkter</a>.
::: moniker-end

2. Välj fliken **Produkter**.
3. Hitta den prenumeration du vill avbryta. Välj **Fler åtgärder** (tre punkter) och välj sedan **Avbryt prenumeration**.
4. I fönstret **Avbryt prenumeration** väljer du en anledning till varför du avbryter prenumerationen. Alternativt kan du ge valfri feedback.
5. Välj **Spara**.

Din prenumeration får status **Inaktiverad** och har begränsad funktionalitet tills den tas bort. Mer information om vad du kan förvänta dig när en betald Microsoft 365 för företag-prenumeration avbryts finns i [Vad händer med min data och åtkomst när min Microsoft 365 för företag-prenumeration avslutas?](what-if-my-subscription-expires.md).

## <a name="what-happens-when-you-cancel-a-subscription"></a>Vad händer när du avbryter en prenumeration?

Om du avbryter en prenumeration innan perioden gått ut flyttas prenumerationsstatusen direkt till ett inaktiverat läge. För de flesta länder och områden varar det inaktiverade tillståndet i 90 dagar, för de flesta prenumerationer. Administratörer kan fortfarande få åtkomst och säkerhetskopiera data för organisationen under tiden prenumerationen är inaktiverad, men vi rekommenderar att administratör [säkerhetskopierar sina data](back-up-data-before-switching-plans.md) innan de avbryter en prenumeration, särskilt om det är deras enda prenumeration. Administratörer kan också återaktivera prenumerationen under tiden den är inaktiverad.

Efter 90 dagar flyttas prenumerationen till ett borttaget tillstånd. All data som du lämnat kvar kan bli raderad efter de 90 dagarna gått och raderas senast 180 dagar efter prenumerationen avbröts. Du kan inte ta bort en betalningsmetod från en avbruten prenumeration förrän den når det borttagna tillståndet.

### <a name="what-to-expect-for-you-and-your-users-if-you-cancel-a-subscription"></a>Det här kan du och dina användare vänta er om du avbryter en prenumeration
  
- **Administratörsåtkomst** Administratörer kan fortfarande logga in och använda administrationscentret samt köpa andra prenumerationer vid behov. Som global administratör eller faktureringsadministratör har du 90 dagar på dig att [återaktivera prenumerationen](reactivate-your-subscription.md) med alla data intakta.

- **Användaråtkomst** Användarna kan inte använda tjänster som OneDrive för företag eller få åtkomst till kunddata som e-post eller dokument på gruppwebbplatser. Office-program, som Word och Excel, flyttas så småningom till ett skrivskyddat läge med nedsatt funktionalitet och [meddelanden om ej licensierad produkt](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx) visas.

Mer information finns i [Vad händer med mina data och åtkomst när min prenumerationen går ut?](what-if-my-subscription-expires.md)

> [!IMPORTANT]
> Om du vill att dina prenumerationsdata ska raderas innan den typiska inaktiveringsperioden är slut kan du [stänga kontot](../close-your-account.md).

## <a name="other-steps-you-might-have-to-take"></a>Andra åtgärder du kan behöva vidta

### <a name="change-custom-domain-settings"></a>Ändra inställningar för egen domän

Om du använder en egen domän med din prenumeration finns det några extra steg du behöver gå igenom innan du kan avbryta din prenumeration. Om du inte har en egen domän kan du gå vidare till [Spara dina data](#save-your-data).

#### <a name="change-your-domain-nameserver-records-if-needed"></a>Ändra domänens namnserverposter (om det behövs)

Om du har konfigurerat en anpassad domän har du lagt till DNS-poster så att domänen fungerar med Microsoft 365-tjänster. Innan du tar bort domänen behöver du uppdatera DNS-posterna, exempelvis domänens MX-post hos DNS-värden.

Ändra till exempel MX-posten hos din DNS-värd. E-post som skickas till din domän inte längre kommer till din Microsoft-adress utan går till din nya e-postleverantör i stället. (En MX-post bestämmer vart e-post för domänen skickas.)

- Om dina namnserverposter (NS) [pekar på Office 365-namnservrar](../../admin/setup/add-domain.md) kommer ändringar i MX-posten inte att börja gälla förrän du ändrar dina NS-poster så att de pekar på din nya DNS-värd (se Steg 2).

- Innan du uppdaterar MX-posten bör du meddela användarna vilket datum du kommer att byta deras e-post. Meddela också vilken ny e-postleverantör du tänker använda. Om användarna vill flytta sin befintliga Microsoft-e-post till den nya leverantören måste de gå igenom några extra steg.

- Följ resterande steg i den här artikeln den dag du ändrar MX-posten.

#### <a name="update-your-domain-mx-and-other-dns-records-if-youre-using-a-custom-domain"></a>Uppdatera domänens MX-post och andra DNS-poster (om du använder en egen domän)

Om du bytte dina namnserverposter (NS) till Microsoft 365 när du konfigurerade din domän måste du konfigurera eller uppdatera MX-posten och andra DNS-poster hos den DNS-värd du tänker använda, och sedan ändra NS-posten till den DNS-värden.

Om du inte bytte NS-poster när du konfigurerade din domän kommer din e-post direkt att börja skickas till den nya adressen när du ändrar MX-posten.

För att ändra dina NS-poster, se [Ta bort en domän](../../admin/get-help-with-domains/remove-a-domain.md).

### <a name="save-your-data"></a>Spara dina data

När uppsägningen blivit aktiv förlorar användarna sin tillgång till sina data. Se därför till att de sparar sina OneDrive för företag- eller SharePoint Online-filer till en annan plats. Kvarlämnade kunddata tas bort efter 30 dagar, senast 180 dagar efter prenumerationen avbrutits.

- Om du vill flytta e-post, kontakter, uppgifter och kalenderinformation till ett annat konto hittar du information i artikeln om att [exportera eller säkerhetskopiera e-post, kontakter och kalender till en Outlook-datafil (.pst)](https://support.microsoft.com/office/14252b52-3075-4e9b-be4e-ff9ef1068f91.aspx).

- Om du vill spara ett dokumentbibliotek eller listinnehåll (till exempel kontakter) från en SharePoint Online-miljö (OneDrive för företag eller gruppwebbplatser) på filresurser eller på en lokal dator kan du läsa mer i artikeln om [manuell migrering av SharePoint Online-innehåll](https://docs.microsoft.com/sharepoint/troubleshoot/migration-tool/content-manual-migration).

### <a name="uninstall-office-optional"></a>Avinstallera Office (valfritt)

Om du har avbrutit prenumerationen och [inte flyttat användare till en annan prenumeration](move-users-different-subscription.md) som omfattar Microsoft 365 körs Microsoft 365 i läget Nedsatt funktionalitet. Det innebär att användare bara kan läsa och skriva ut dokument, och att [meddelanden om ej licensierad produkt](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx) visas Microsoft 365-program. Se till att användarna [avinstallerar Office](https://support.microsoft.com/office/9dd49b83-264a-477a-8fcc-2fdf5dbf61d8.aspx) från sina datorer för att undvika förvirring.

## <a name="next-steps"></a>Nästa steg

Om du vill stänga ditt konto hos Microsoft helt och hållet, se [Avsluta ditt konto](../close-your-account.md).

## <a name="related-content"></a>Relaterat innehåll

[Förnya prenumerationen](renew-your-subscription.md) (artikel)\
[Återaktivera prenumerationen](reactivate-your-subscription.md)
[Flytta användare till en annan prenumeration](move-users-different-subscription.md) (artikel)
