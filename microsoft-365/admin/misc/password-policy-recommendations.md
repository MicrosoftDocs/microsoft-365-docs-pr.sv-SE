---
title: Policyrekommendationer för lösenord
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9fa2539a-2211-41fd-85a0-bc37b9619ca4
description: Gör organisationen säkrare mot lösenordsattacker och förbjud vanliga lösenord och aktivera riskbaserad multifaktorautentisering.
ms.openlocfilehash: f580ed957b8231bc68c5f21ea9af990808478382
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/18/2021
ms.locfileid: "53006931"
---
# <a name="password-policy-recommendations"></a>Policyrekommendationer för lösenord

Som administratör för en organisation är du ansvarig för att bestämma policyn för användarnas lösenord. Det kan vara komplicerat och förvirrande att ange en lösenordspolicy och den här artikeln innehåller rekommendationer för att skydda organisationen mot lösenordsattacker.
  
Information om hur du anger hur ofta Microsoft 365-lösenord ska upphöra att gälla i organisationen finns i [Ange förfalloprincip för lösenord för Microsoft 365](../manage/set-password-expiration-policy.md).

För mer information om Microsoft 365-lösenord se:

[Återställ lösenord](../add-users/reset-passwords.md) (artikel)

[Ange att en enskild användares lösenord aldrig ska förfalla](../add-users/set-password-to-never-expire.md)(artikel)

[Låt användare återställa sina egna lösenord](../add-users/let-users-reset-passwords.md) (artikel)

[Skicka om en användares lösenord – hjälp för administratörer](../add-users/resend-user-password.md) (artikel)
  
## <a name="understanding-password-recommendations"></a>Förstå rekommendationer om lösenord

Bra metoder för lösenord delas in i några breda kategorier:
  
- **Motarbeta vanliga attacker** Här ingår valet av var användarna kan ange lösenord (kända och betrodda enheter med bra identifiering av skadlig kod, verifierade webbplatser) och valet av vilka lösenord de kan välja (längd och unikhet).

- **Begränsa lyckade attacker** Att begränsa lyckade hackarattacker handlar om att begränsa exponering till en viss tjänst, eller förhindra skadan helt och hållet, om en användares lösenord stjäls. Till exempel att se till att ett avslöjande av din inloggningsinformation för sociala nätverk inte gör ditt bankkonto sårbart, eller att se till att ett konto med svagt skydd inte tar emot återställningslänkar för ett viktigt konto.

- **Förstå människans natur** Många giltiga lösenordsmetoder misslyckas på grund av naturliga mänskliga beteenden. Det är avgörande att förstå människans natur eftersom forskning visar att nästan alla regler som du tillämpar för användarna leder till svagare lösenord. Krav gällande längd, specialtecken och lösenordsändring leder till normalisering av lösenord, vilket gör det enklare för attackerare att gissa eller knäcka lösenord.

## <a name="password-guidelines-for-administrators"></a>Riktlinjer om lösenord för administratörer

Det primära målet med ett säkrare lösenordssystem är lösenordsvariation. Lösenordsprincipen bör innehålla många olika och svårgissade lösenord. Här är några rekommendationer för att skydda organisationen.
  
- Ha ett krav om minimilängd på 8 tecken (längre är inte nödvändigtvis bättre)

- Ha inte krav på teckensammansättning. Exempel: \*&amp;(^%$

- Kräv inte regelbundna lösenordsåterställningar för användarkonton

- Förbjud vanliga lösenord, för att undvika de mest sårbara lösenorden i systemet

- Utbilda användarna så att de inte återanvänder sina organisationslösenord utanför arbetet

- Tillämpa registrering för [multifaktorautentisering](../security-and-compliance/set-up-multi-factor-authentication.md)

- Aktivera riskbaserade multifaktorautentiseringskontroller

### <a name="password-guidance-for-your-users"></a>Hjälp om lösenord för användare

Här är lite hjälp om lösenord för användarna i organisationen. Se till att informera användarna om de här rekommendationerna och tillämpa rekommenderade lösenordsprinciper på organisationsnivå.
  
- Använd inte ett lösenord som är samma som eller liknar ett du använder på andra webbplatser

- Använd inte ett enskilt ord, till exempel **lösenord**, eller en vanlig fras, till exempel **jagälskardig**

- Gör lösenord svåra att gissa sig till, även för personer som vet mycket om dig, till exempel namn och födelsedagar för dina vänner och din familj, din favoritartist och fraser som du använder ofta

## <a name="some-common-approaches-and-their-negative-impacts"></a>Några vanliga metoder och deras negativa följder

Det här är några av de vanligaste metoderna för lösenordshantering, men forskning varnar oss för deras negativa följder.
  
### <a name="password-expiration-requirements-for-users"></a>Krav på giltighetstid för lösenord för användare

Lösenordets utgångskrav gör mer skada än nytta, eftersom dessa krav får användarna att välja förutsägbara lösenord, sammansatta av ord och nummer som är nära relaterade till varandra. I dessa fall kan nästa lösenord förutsägas baserat på föregående lösenord. Lösenordens utgångskrav erbjuder inga fördelar för inneslutning eftersom cyberbrottslingar nästan alltid använder referenser så fort de äventyrar dem. Kolla in [tid att ompröva obligatoriska lösenordsändringar ](https://go.microsoft.com/fwlink/p/?linkid=861018)för mer information.
  
### <a name="requiring-long-passwords"></a>Krav på långa lösenord

Krav på lösenordslängd (fler än cirka 10 tecken) kan leda till förutsägbara och oönskade användarbeteenden. Användare som måste ha ett lösenord med minst 16 tecken kan till exempel välja upprepade mönster som **fyrafyrafyrafyra** eller **lösenordlösenord** som uppfyller kravet på teckenlängd men inte är svåra att gissa sig till. Längdkrav ökar dessutom risken för att användare använder sig av andra osäkra metoder, till exempel att skriva ned sina lösenord, använda dem igen eller lagra dem okrypterade i sina dokument. För att uppmuntra användare att komma på ett unikt lösenord rekommenderar vi att ha ett rimligt krav om minimilängd på 8 tecken.
  
### <a name="requiring-the-use-of-multiple-character-sets"></a>Krav på användning av flera teckenuppsättningar

Krav på lösenordskomplexitet minskar nyckelutrymmet och leder till förutsägbart användarbeteende, vilket gör mer skada än nytta. I de flesta system tillämpas någon nivå av krav på lösenordskomplexitet. Till exempel måste lösenord innehålla tecken från samtliga av följande tre kategorier:
  
- versaler

- gemener

- icke-alfanumeriska tecken

De flesta använder liknande mönster, till exempel en versal i den första positionen, en symbol i den sista och en siffra i de sista två. Cyberbrottslingar vet om det, så de kör sina ordlisteattacker med de vanligaste ersättningarna, ”$” för ”s”, ”@” för ”a”, ”1” för ”l”. Att tvinga användare att välja en kombination av versaler, gemener, siffror och specialtecken har en negativ effekt. Vissa komplexitetskrav hindrar till och med användare från att använda säkra lösenord som de kommer ihåg, och tvingar dem att komma på mindre säkra lösenord som är svårare att komma ihåg.
  
## <a name="successful-patterns"></a>Lyckade mönster

Här finns däremot några rekommendationer om hur du uppmuntrar lösenordsvariation.
  
### <a name="ban-common-passwords"></a>Förbjud vanliga lösenord

Det viktigaste lösenordskravet du bör tillämpa när användarna skapar lösenord är att förbjuda användning av vanliga lösenord för att minska organisationens känslighet för råstyrkeattacker. Vanliga användarlösenord är bland annat **abcdefg**, **lösenord** och **sommar**.
  
### <a name="educate-users-to-not-re-use-organization-passwords-anywhere-else"></a>Utbilda användare så att de inte återanvänder organisationslösenord någon annanstans

Ett av de viktigaste budskapen att få fram till organisationens användare är att de inte ska återanvända sitt organisationslösenord någon annanstans. Användning av organisationslösenord på externa webbplatser ökar kraftigt risken för att cyberbrottslingar får tag på lösenorden.
  
### <a name="enforce-multi-factor-authentication-registration"></a>Tillämpa registrering för multifaktorautentisering

Se till att användarna uppdaterar kontakt- och säkerhetsinformation, till exempel en alternativ e-postadress, telefonnummer eller en enhet som är registrerad för push-meddelanden, så att de kan svara på säkerhetskontroller och meddelas om säkerhetshändelser. Uppdaterad kontakt- och säkerhetsinformation hjälper användarna att bekräfta sin identitet om de någonsin glömmer sitt lösenord eller om någon annan försöker ta över deras konto. Det ger också en alternativ meddelandekanal vid säkerhetshändelser, till exempel inloggningsförsök eller ändrade lösenord. 
  
Mer information finns i [Konfigurera multifaktorautentisering](../security-and-compliance/set-up-multi-factor-authentication.md).
  
### <a name="enable-risk-based-multi-factor-authentication"></a>Aktivera riskbaserad multifaktorautentisering

Med riskbaserad multifaktorautentisering går det att kontrollera att användaren är den riktiga kontoägaren när misstänkt aktivitet identifieras av systemet. 
  
## <a name="next-steps"></a>Nästa steg

Vill du veta mer om hur du hanterar lösenord? Här är några rekommenderade artiklar att läsa:

- [Vägledning för Microsoft-lösenord](https://www.microsoft.com/research/wp-content/uploads/2016/06/Microsoft_Password_Guidance-1.pdf)

- [Fyller starka webblösenord någon funktion?](https://go.microsoft.com/fwlink/p/?linkid=861008)

- [Lösenordsportföljer och användare med begränsad insats](https://go.microsoft.com/fwlink/p/?linkid=861014)

- [Förhindra svaga lösenord genom att läsa användarnas tankar](https://go.microsoft.com/fwlink/p/?linkid=861015)

- [Välja säkra lösenord](https://go.microsoft.com/fwlink/p/?linkid=861016)

- [Dags att ompröva obligatoriska lösenordsändringar](https://go.microsoft.com/fwlink/p/?linkid=861018)

- [2015 års sämsta lösenord](https://go.microsoft.com/fwlink/p/?linkid=861020)

## <a name="related-content"></a>Relaterat innehåll

[Återställa lösenord](../add-users/reset-passwords.md) (artikel)\
[Ställa in en enskild användares lösenord för att aldrig ska förfalla](../add-users/set-password-to-never-expire.md)(artikel)\
[Låt användare återställa sina egna lösenord](../add-users/let-users-reset-passwords.md) (artikel)\
[Skicka om en användares lösenord – hjälp för administratörer](../add-users/resend-user-password.md) (artikel)
