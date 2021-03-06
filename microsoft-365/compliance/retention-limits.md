---
title: Begränsningar när det gäller principer för kvarhållning och kvarhållningsetiketter
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
hideEdit: true
description: Förstå det högsta antalet principer och objekt per princip när det gäller principer för kvarhållning och kvarhållningsetiketter
ms.openlocfilehash: 92647911cfc3435c2d88ce5caa0624a34467a60f
ms.sourcegitcommit: 3e197d1ff7d8100faeaf1f5a33f1ad4ed2f72e99
ms.translationtype: HT
ms.contentlocale: sv-SE
ms.lasthandoff: 06/11/2021
ms.locfileid: "52908107"
---
# <a name="limits-for-retention-policies-and-retention-label-policies"></a>Begränsningar när det gäller principer för kvarhållning och kvarhållningsetiketter

>*[Licensieringsvägledning för Microsoft 365 för säkerhet och efterlevnad](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*

När du använder [ principer för kvarhållning och kvarhållningsetiketter ](retention.md#retention-policies-and-retention-labels) för att automatiskt kvarhålla eller ta bort data åt organisationen så finns det några maxantal som du bör känna till.

## <a name="maximum-number-of-policies-per-tenant"></a>Högsta antal principer per klientorganisation

En enskild klientorganisation kan ha högst 10 000 principer (alla konfigurationer). Maxantalet inkluderar olika kvarhållningsprinciper och andra efterlevnadsprinciper, till exempel DLP-principer, informationsbarriärer, eDiscovery-undantag och känslighetsetiketter.

Inom denna gräns på 10.000 principer finns det också några begränsningar för det högsta antalet kvarhållningsprinciper per arbetsbelastning:

- Exchange (valfri konfiguration): 1 800
- SharePoint eller OneDrive: (alla webbplatser inkluderas automatiskt): 13
- SharePoint eller OneDrive (specifika platser inkluderas eller exkluderas): 2 600

Även om kvarhållningprinciper för Teams och Yammer använder e-postlådor för att lagra data för kvarhållningssyften, exkluderar de högsta antalet principer för Exchange Online lagringsprinciper för Teams och Yammer.

## <a name="maximum-number-of-items-per-policy"></a>Högsta antal objekt per princip

Om du använder den valfria konfigurationen för att begränsa dina kvarhållningsinställningar till specifika användare, specifika Microsoft 365-grupper eller specifika webbplatser, finns det några begränsningar per princip som du bör känna till: 

Högsta antal objekt per kvarhållningsprincip:

- Exchange-postlådor: 1 000
- Microsoft 365-grupper: 1 000
- Teams-kanalmeddelanden: 1 000
- Teams-chattar: 1 000
- Community-meddelanden i Yammer: 1 000
- Användarmeddelanden i Yammer: 1 000
- SharePoint webbplatser: 100
- OneDrive konton: 100

Skype för företag måste vara begränsat till specifika användare och det maximala antalet som stöds per princip är 1 000.

Eftersom dessa begränsningar gäller per princip kan du skapa ytterligare principer som har samma kvarhållningsinställningar om du behöver använda specifika inkluderingar eller exkluderingar som leder till att du överskrider dessa antal. I nästa avsnitt finns några [exempel på scenarion och lösningar](#examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers) som använder flera kvarhållningsprinciper av den här anledningen.

Men flera principer medför högre administrationskostnader, så bekräfta alltid om du verkligen behöver inkluderingar och exkluderingar. Kom ihåg att standardkonfigurationen som gäller för hela platsen inte har några begränsningar och att det här konfigurationsvalet kan vara en bättre lösning än att skapa och underhålla flera principer.

> [!TIP]
> Om du behöver skapa och underhålla flera principer för det här scenariot kan du överväga att använda [PowerShell](retention.md#powershell-cmdlets-for-retention-policies-and-retention-labels) för att få en effektivare konfiguration.

### <a name="examples-of-using-multiple-policies-to-avoid-exceeding-maximum-numbers"></a>Exempel på att använda flera principer för att undvika att överskrida maxantalen

Följande exempel innehåller några designlösningar för när du inte bara kan ange en kvarhållningsprincips plats och måste ta hänsyn till maxantalet objekt som angavs i det föregående avsnittet.

Exempel för Exchange:

- **Krav**: I en organisation med över 40 000 användarpostlådor måste de flesta användare kvarhålla sin e-post i 7 år, men en delmängd av de identifierade användarna (425) måste kvarhålla sin e-post i endast 5 år.

- **Lösning**: Skapa en kvarhållningsprincip för e-post i Exchange med en kvarhållningsperiod på sju år och exkludera delmängden bland användarna. Skapa sedan en andra kvarhållningsprincip för e-post i Exchange med en kvarhållningsperiod på fem år och inkludera delmängden bland användarna. 
    
    I båda fallen är antalet som inkluderas och exkluderas under det maximala antalet angivna postlådor för en enskild princip och vissa användare måste uttryckligen undantas från den första principen eftersom den har en [längre kvarhållningsperiod](retention.md#the-principles-of-retention-or-what-takes-precedence) än den andra principen. Om det krävs en längre kvarhållningsprincip för delmängden användare behöver du inte utesluta dem från den första principen.
     
    Om någon ny blir medlem i organisationen inkluderas postlådan automatiskt i den första principen på sju år och antalet som stöds påverkas inte alls med den här lösningen. Nya användare som kräver kvarhållningsperioden på fem år ökar dock siffrorna för att inkludera och exkludera, och den här gränsen nås vid 1 000.

Exempel från SharePoint:

- **Krav**: en organisation har flera tusen SharePoint-webbplatser men bara 2 000 webbplatser kräver en kvarhållningsperiod på 10 år och 8 000 webbplatser kräver en kvarhållningsperiod på 4 år.

- **Lösning**: Skapa 20 kvarhållningsprinciper för SharePoint med en kvarhållningsperiod på 10 år som omfattar 100 specifika webbplatser och skapa 80 kvarhållningsprinciper för SharePoint med en kvarhållningsperiod på 4 år som omfattar 100 specifika webbplatser.
    
    Eftersom du inte behöver kvarhålla alla SharePoint-webbplatser måste du skapa kvarhållningsprinciper som specificerar de specifika webbplatserna. Eftersom en kvarhållningsprincip inte stöder fler än 100 angivna webbplatser måste du skapa flera principer för de två kvarhållningsperioderna. De här kvarhållningsprinciperna har ett maxantal webbplatser som ingår. Nästa nya webbplats som måste kvarhållas kräver en ny kvarhållningsprincip, oavsett hur lång kvarhållningsperioden är.

## <a name="maximum-number-of-items-for-disposition"></a>Högsta antal objekt för disposition

När det [dispositionen av innehåll](disposition.md) finns det några begränsningar du bör känna till:

- 1 000 000 objekt som väntar på disposition per steg för varje bevarandeetikett

- Dispositionsbevis i upp till sju år efter att objektet kasserades med en begränsning på 1 000 000 objekt per bevarandeetikett under perioden. 
    
Om du behöver ett bevis på disposition som är högre än den här gränsen på 1 000 000 för objekt som markeras som arkivhandlingar kontaktar du [Microsoft Support](../business-video/get-help-support.md).
