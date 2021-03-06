---
title: Vad händer med mina data och min åtkomst när prenumerationen går ut?
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
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
search.appverid: MET150
description: Läs om vad som händer med dina data när prenumerationen för Microsoft 365 för företag förfaller, inaktiveras eller om du avbryter den.
ms.date: 04/08/2021
ms.openlocfilehash: d0821214f9a8c242306685db2ee7faf3779cecff
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333032"
---
# <a name="what-happens-to-my-data-and-access-when-my-microsoft-365-for-business-subscription-ends"></a>Vad händer med mina data och åtkomst när prenumerationen för Microsoft 365 för företag går ut?

Om prenumerationen går ut – antingen eftersom den förfaller eller för att du vill avbryta – kommer din åtkomst till Microsoft 365-tjänster, program och kunddata gå igenom flera tillstånd innan prenumerationen är helt inaktiverad eller *borttagen*. Om du har förståelse för förloppet kommer du vara beredd på att återaktivera din prenumeration i tid, eller – om du lämnar Microsoft 365 – säkerhetskopiera dina data innan de tas bort permanent.

Läs igenom den viktiga informationen innan du kontaktar [Supporten för Microsoft 365](../../business-video/get-help-support.md).
  
## <a name="what-happens-to-data-when-a-subscription-expires"></a>Vad händer med data när en prenumeration förfaller?

- Om prenumerationen förfaller går den igenom följande steg: Förfallen/Inaktiverad/Borttagen. Prenumerationen går direkt till tillståndet Förfallen efter att den har nått sitt slutdatum.
- Om du inaktiverar återkommande fakturering för din årsprenumeration går den igenom samma steg som en förfallen prenumeration. Första steget börjar på årsdagen för årsprenumerationen, inte på det datum då du sade upp återkommande fakturering för prenumerationen.
- Om du avbryter din månadsprenumeration inaktiveras den omedelbart (vid uppsägningsdatum). Det innebär att användarna förlorar åtkomst till Microsoft 365-tillgångarna omedelbart och att endast administratörer har åtkomst till data under de kommande 90 dagarna.

Följande tabell visar vad du kan förvänta dig när en betald prenumeration för Microsoft 365 för företag upphör.

| Aktiv | Förfallen <br/>(30 dagar\*) | Inaktiverad <br/>(90 dagar\*) | Borttagen |
|------------------------------------------------------------------------|------------------------------------------------------------------------------|------------------------------------------------------------------------------|-------------------------------------------------------------------------------------------|
| *Data är tillgängliga för alla*                                               | *Data är tillgängliga för alla*                                                     | *Data är endast tillgängliga för administratörer*                                             | **Data borttagen<br/>Azure Active Directory tas bort om det inte används av andra tjänster** |
| Användare har normal åtkomst till Microsoft 365, filer och program   | Användare har normal åtkomst till Microsoft 365, filer och program              | Användare har inte åtkomst till Microsoft 365, filer eller program                        | Användare har inte åtkomst till Microsoft 365, filer eller program                                     |
| Administratörer har normal åtkomst till Microsoft 365, data och Office-program | Administratörer har åtkomst till administrationscentret                                           | Administratörer har åtkomst till administrationscentret men kan inte tilldela licenser till användare       | Administratörer har åtkomst till administrationscentret för att kunna köpa och hantera andra prenumerationer             |
|                                                                        | Globala administratörer eller faktureringsadministratörer kan återaktivera prenumerationen i administrationscentret | Globala administratörer eller faktureringsadministratörer kan återaktivera prenumerationen i administrationscentret |                                                                                           |

*För de flesta erbjudanden, i de flesta länder och regioner.
  
> [!NOTE]
>
> **Vad är kunddata?** Kunddata, som definierat i [Villkor för Microsofts onlinetjänst](https://go.microsoft.com/fwlink/p/?LinkId=613649), hänvisar till alla data, inklusive alla text-, ljud- och bildfiler som tillhandahålls till Microsoft av eller för kundens räkning genom kundens användning av Microsoft 365-tjänster. Mer information om hur du skyddar kunddata finns i [Kom igång med Microsoft Service Trust Portal](../../compliance/get-started-with-service-trust-portal.md).

## <a name="what-happens-if-i-cancel-a-subscription"></a>Vad händer om jag avbryter en prenumeration?

Om du avbryter din prenumeration innan periodens slutdatum hoppar prenumerationen över tillståndet Förfallen och går direkt till tillståndet Inaktiverad, som är 90 dagar för de flesta prenumerationer, i de flesta länder och regioner. Vi rekommenderar att du [Säkerhetskopierar dina data](back-up-data-before-switching-plans.md) innan du avbryter, men som administratör kan du fortfarande komma åt och säkerhetskopiera dina data för din organisation under tiden prenumerationen är i tillståndet Inaktiverad. Kvarlämnade kunddata kan tas bort efter 90 dagar och kommer vara borttaget senast 180 dagar efter prenumerationen avbröts.
  
Det här kan du förvänta dig för dig själv och dina användare om du avbryter en prenumeration.
  
- **Administratörsåtkomst** Administratörer kan fortfarande logga in och använda administrationscentret samt köpa andra prenumerationer efter behov. Som global administratör eller faktureringsadministratör har du 90 dagar på dig att [återaktivera prenumerationen](reactivate-your-subscription.md) med alla data intakta.

- **Användaråtkomst** Användarna kan inte använda tjänster som OneDrive för företag eller få åtkomst till kunddata, till exempel e-post eller dokument på gruppwebbplatser. Office-program, som Word och Excel, flyttas så småningom till ett skrivskyddat läge med nedsatt funktionalitet och [meddelanden om ej licensierad produkt](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx) visas.

Information om hur du avbryter prenumerationen finns i [Avbryt prenumeration](cancel-your-subscription.md).
  
> [!IMPORTANT]
> Om du vill att dina prenumerationsdata ska raderas innan det typiska tillståndet Inaktiverad är slut kan du [stänga ditt konto](../close-your-account.md).
  
> [!NOTE]
>
> Om du tar bort en prenumeration försvinner utgångna och inaktiverade faser så tas data och innehåll i SharePoint Online, inklusive OneDrive, bort omedelbart.

## <a name="what-are-my-options-if-my-subscription-is-about-to-expire"></a>Vilka alternativ har jag när min prenumeration är på väg att förfalla?

När en prenumeration är aktiv har du och slutanvändarna normal åtkomst till dina data, tjänster som e-post, OneDrive för företag och Office-program. Som administratör får du ett antal aviseringar via e-post och i administrationscentret när prenumerationen närmar sig förfallodatumet.
  
Innan prenumerationen förfaller kan du göra följande:
  
- **Aktivera återkommande fakturering för prenumerationen.**
  - Om **Återkommande fakturering** redan har aktiverats behöver du inte vidta någon åtgärd. Din prenumeration faktureras automatiskt och du debiteras ytterligare för ett år eller en månad, beroende på din nuvarande betalningssfrekvens. Om du av någon anledning har inaktiverat **Återkommande fakturering** kan du alltid [Återaktivera återkommande fakturering](renew-your-subscription.md).
  - Om du har köpt Microsoft 365-appar för företag med ett förbetalt kort kan du [aktivera återkommande fakturering](renew-your-subscription.md) för prenumerationen.
  - Kontakta din partner för att köpa en ny produktnyckel om du är kund hos Open Volume Licensing med en förbetald prenumeration på ett år. Du får instruktioner via e-post för att aktivera nyckeln i [Volume Licensing Service Center](https://go.microsoft.com/fwlink/p/?LinkID=282016). Information om hur du hittar en ny partner, eller en tidigare partner finns i [Hitta din partner eller återförsäljare](../../admin/manage/find-your-partner-or-reseller.md).
  - Om du har Microsoft 365-program för företag hittar du mer information i [Hantera återkommande fakturering för din prenumeration](renew-your-subscription.md).
- **Låt prenumerationen förfalla.**
  - Om du betalar med kreditkort eller faktura och inte vill fortsätta prenumerationen kan du [Inaktivera återkommande fakturering](renew-your-subscription.md). Prenumerationen går ut på förfallodatumet och du kan ignorera alla relaterade e-postaviseringar.
  - Om du är kund hos Open Volume Licensing och arbetar med en partner kan du låta prenumerationen förfalla genom att inte vidta någon åtgärd.
  - Om du är Microsoft 365 Business Standard-kund och du har förbetalt din prenumeration, och aktiverat den med en produktnyckel, kan du låta prenumerationen gå ut genom att inte vidta någon åtgärd.
- **Avbryta innan prenumerationen förfaller.** Mer information finns i [Avbryta prenumerationen](cancel-your-subscription.md).

## <a name="what-happens-after-my-subscription-expires"></a>Vad händer efter att min prenumeration förfallit?

Om du låter prenumerationen förfalla går den igenom flera olika tillstånd innan den tas bort permanent. Det ger dig som administratör tid att återaktivera den om du vill fortsätta tjänsten, eller för att säkerhetskopiera dina data om du bestämmer dig för att du inte längre vill ha prenumerationen.
  
Det här kan du förvänta dig när prenumerationen är i de olika tillstånden.
  
### <a name="state-expired"></a>Tillstånd: Förfallen

**Vad du kan förvänta dig:** Tillståndet Förfallen varar i 30 dagar för de flesta prenumerationer, inklusive prenumerationer som köpts via [Microsoft Open](https://go.microsoft.com/fwlink/p/?LinkID=613298), i de flesta länder och regioner. För Volymlicensprodukter, med undantag för Microsoft Open, varar tillståndet Förfallen i 90 dagar.

I det här läget har användare normal åtkomst till Microsoft 365-portalen, Office-program och tjänster som e-post och SharePoint Online.
  
Som administratör har du fortfarande åtkomst till administrationscentret. Oroa dig inte, globala administratörer eller faktureringsadministratörer kan [återaktivera prenumerationen](reactivate-your-subscription.md) och fortsätta använda Microsoft 365. [Säkerhetskopiera dina data](back-up-data-before-switching-plans.md) om du inte återaktiverar prenumerationen.
  
### <a name="state-disabled"></a>Tillstånd: Inaktiverad

**Vad du kan förvänta dig:** Om du inte återaktiverar prenumerationen under tillståndet Förfallen flyttas den till tillståndet Inaktiverad som varar i 90 dagar för de flesta prenumerationer, i de flesta länder och regioner. För Volymlicensprodukter varar tillståndet Inaktiverad i 30 dagar.

I det här tillståndet minskar åtkomsten avsevärt. Användarna kan inte logga in eller få åtkomst till tjänster som e-post eller SharePoint Online. Office-program flyttas så småningom till ett skrivskyddat läge med nedsatt funktionalitet och [meddelanden om ej licensierad produkt](https://support.microsoft.com/office/0d23d3c0-c19c-4b2f-9845-5344fedc4380.aspx) visas. Du kan fortfarande logga in och komma åt till administrationscentret men kan inte tilldela licenser till användare. Dina kunddata, inklusive alla användardata, e-postmeddelanden och filer på gruppwebbplatser är endast tillgängliga för dig och andra administratörer.

Som global administratör eller faktureringsadministratör kan du [återaktivera prenumerationen](reactivate-your-subscription.md) och fortsätta använda Microsoft 365 med alla kunddata intakta. [Säkerhetskopiera dina data](back-up-data-before-switching-plans.md) om du väljer att inte återaktivera.

### <a name="state-deleted"></a>Tillstånd: Borttagen
  
**Vad du kan förvänta dig:** Prenumerationen tas bort om du inte återaktiverar prenumerationen när den är förfallen eller inaktiverad.
  
Administratörer och användare har inte längre åtkomst till de tjänster och Office-program som ingår i prenumerationen. Alla kunddata, allt från användardata till dokument och e-post, tas bort permanent och kan inte återskapas.
  
Just nu kan du inte återaktivera prenumerationen. Som global administratör eller faktureringsadministratör har du dock fortfarande åtkomst till administrationscenter för att hantera andra prenumerationer eller för att köpa nya prenumerationer och möta verksamhetsbehoven.
  
> [!NOTE]
>
> - Det går inte återställa de data som var kopplade till en borttagen prenumeration genom att lägga till en ny prenumeration av samma typ som den borttagna prenumerationen.
> - Om en CSP-licens inaktiveras gäller inte tillståndet Förfallen på 30 dagar och tjänsterna inaktiveras omedelbart. Data tas bort efter 90 dagar om klientorganisationen inte återaktiveras genom att en ny licens läggs till.

### <a name="what-happens-when-my-trial-ends"></a>Vad händer när utvärderingsperioden går ut?

När utvärderingsversionen löper ut kan du inte fortsätta använda Microsoft 365 kostnadsfritt. Du har några olika möjligheter:

- **Köp Microsoft 365.** När din utvärderingsversion går ut flyttas den till tillståndet Förfallen som ger dig ytterligare 30 dagar (för de flesta utvärderingsversioner, i de flesta länder och regioner) för att köpa Microsoft 365. Information om hur du konverterar utvärderingsversionen till en betald prenumeration finns i [Köpa en prenumeration från din kostnadsfria utvärderingsversion](../try-or-buy-microsoft-365.md#buy-a-subscription-from-your-free-trial).
- **Förläng utvärderingsversionen.** Behöver du mer tid för att utvärdera Microsoft 365? I vissa fall kan du [förlänga utvärderingsversionen](../extend-your-trial.md).
- **Avbryt utvärderingsversionen eller låt den förfalla.** Om du bestämmer dig för att inte köpa Microsoft 365 kan du låta utvärderingsversionen förfalla eller [avbryta den](cancel-your-subscription.md). Säkerhetskopiera alla data som du vill behålla. Strax efter tillståndet Förfallen på 30 dagar raderas kontoinformationen och data för utvärderingsversionen raderas permanent.

> [!NOTE]
>
> Informationen på den här sidan omfattas av [Ändringsnotiser och ansvarsfriskrivning för principer för Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=613651). Gå tillbaka till den här webbplatsen med jämna mellanrum för att granska eventuella ändringar.

## <a name="related-content"></a>Relaterat innehåll

[Avbryt prenumerationen](./cancel-your-subscription.md) (artikel)\
[Förnya Microsoft 365 för företag](./renew-your-subscription.md) (artikel)\
[Återaktivera prenumerationen](./reactivate-your-subscription.md) (artikel)
