---
title: Konfigurera principen för anslutningsfilter, lista Tillåt, Blockera lista
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 8/27/2019
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
ms.collection:
- M365-security-compliance
description: Om du vill vara säker på att e-post som skickas från personer som du litar på inte är blockerat kan du använda principen för anslutningsfilter för att skapa en lista över tillåt, även känd som en lista över betrodda adresser, av IP-adresser som du litar på. Du kan också skapa en lista över blockerade avsändare.
ms.openlocfilehash: db0d7acc6189f29b247c1dc4004311d2843d139b
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: sv-SE
ms.lasthandoff: 02/15/2020
ms.locfileid: "42809687"
---
# <a name="configure-the-connection-filter-policy"></a>Konfigurera principen för anslutningsfilter

De flesta av oss har vänner och affärspartners som vi litar på. Det kan vara frustrerande att hitta e-post från dem i din skräppostmapp, eller till och med blockeras helt av ett skräppostfilter. Om du vill vara säker på att e-post som skickas från personer som du litar på inte är blockerat kan du använda principen för anslutningsfilter för att skapa en lista över tillåt, även känd som en lista över betrodda adresser, med IP-adresser som du litar på. Du kan också skapa en lista med blockerade avsändare, som är en lista över IP-adresser, vanligtvis från kända spammare, som du aldrig vill ta emot e-postmeddelanden från.

- När du tänker på *[Tillåt listor,](create-safe-sender-lists-in-office-365.md)* tänk på anslutningsfilterprinciper bryr sig om de *betrodda konton som tillåts* av filtret. Detta görs i intresse av att mer exakt filtrera bort mindre betrodda eller ej betrodda användare samtidigt som du behåller det du behöver. En lista över anslutningsfilter Tillåt handlar om att filtrera till de få betrodda iD:n från en mycket större pool med konton och IPs och att underlätta åtkomsten till dina betrodda användare.

- En anslutningsfilterprincip som skapar en blocklista kan betraktas som mindre eller opålitliga konton i filtret i stället.

 Om du vill ha fler skräppostinställningar som gäller för hela organisationen kan du ta en titt på [Hur du förhindrar att bra e-post markeras som skräppost i Office 365](prevent-email-from-being-marked-as-spam.md) eller Så minskar du [skräpposten i Office 365](reduce-spam-email.md). Dessa är användbara om du har kontroll på administratörsnivå och vill förhindra falska positiva eller falska negativ.

> [!TIP]
> Du kanske vill pausa och läsa upp om hur du skapar [listor över tillåt (eller säker avsändare)](create-safe-sender-lists-in-office-365.md) och [Blockera listor](create-block-sender-lists-in-office-365.md).

Följande video visar konfigurationsstegen för anslutningsfilterprincipen:

> [!VIDEO https://www.microsoft.com/videoplayer/embed/b2f5bea3-e1a7-44b3-b7e2-07fac0d0ca40?autoplay=false]

## <a name="what-do-you-need-to-know-before-you-begin"></a>Vad behöver jag veta innan jag börjar?

- Beräknad tid: 15 minuter

- Du måste ha tilldelats behörigheter för att kunna utföra de här procedurerna. Mer information om vilka behörigheter du behöver finns i posten "Anti-spam" i [avsnittet Funktionsbehörigheter i Exchange Online.](https://docs.microsoft.com/exchange/permissions-exo/feature-permissions)

- Om du vill hämta IP-adressen till avsändaren vars meddelanden du vill tillåta eller blockera kan du kontrollera meddelandets Internet-rubrik. Leta efter CIP-huvudet enligt beskrivningen i [anti-spam-meddelanderubriker](anti-spam-message-headers.md). Information om hur du visar ett meddelandehuvud i olika e-postklienter finns i [Visa internetmeddelanderubriker i Outlook](https://support.office.com/article/cd039382-dc6e-4264-ac74-c048563d212c).

- E-postmeddelanden som skickas från en IP-adress i IP-blockeringslistan avvisas, inte markerade som skräppost och ingen ytterligare filtrering sker.

- Följande anslutningsfilterprocedur kan också utföras via remote PowerShell. Använd [cmdleten Get-HostedConnectionFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/get-hostedconnectionfilterpolicy) för att granska inställningarna och [Princip-HostedConnectionFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/antispam-antimalware/set-hostedconnectionfilterpolicy) för att redigera principinställningarna för anslutningsfilter. Mer information om hur du använder Windows PowerShell för att ansluta till Exchange Online Protection finns i [Ansluta till Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-eop/connect-to-exchange-online-protection-powershell). Mer information om hur du använder Windows PowerShell för att ansluta till Exchange Online finns i [Ansluta till Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell).

## <a name="use-the-eac-to-edit-the-default-connection-filter-policy"></a>Använd EAC för att redigera standardprincipen för anslutningsfilter

Du skapar en IP-lista eller IP-blockeringslista genom att redigera anslutningsfilterprincipen i Administrationscentret för Exchange (EAC). Principinställningarna för anslutningsfilter tillämpas endast på inkommande meddelanden.

1. Navigera till filter för \> **skyddsanslutning**i Administrationscentret för Exchange (EAC) och dubbelklickar sedan på standardprincipen. **Protection**

2. Klicka på menyalternativet **Anslutningsfiltrering** och skapa sedan de listor du vill använda: en IP-lista, en IP-blocklista eller båda.

   Om du vill ![skapa](../../media/ITPro-EAC-AddIcon.gif)dessa listor klickar du på Lägg till ikon . I den efterföljande dialogrutan anger du IP-adressen eller adressintervallet och klickar sedan på **ok**. Upprepa den här processen om du vill lägga till ytterligare adresser. (Du kan också redigera eller ta bort IP-adresser efter att de har lagts till.)

   Ange IPV4 IP-adresser i formatet nnn.nnn.nnnn där nnn är ett tal från 0 till 255. Du kan också ange CIDR-intervall (Classless Inter-Domain Routing) i formatet nnn.nnn.nnn.nnn/rr där rr är ett tal från 24 till 32. Om du vill ange intervall utanför intervallet 24 till 32 finns i nästa avsnitt, Ytterligare överväganden när du [konfigurerar IP Tillåt-listor](#additional-considerations-when-configuring-ip-allow-lists).

   > [!NOTE]
   > Om du lägger till en IP-adress i båda listorna tillåts e-post som skickas från den IP-adressen. <br/><br/> Du kan ange högst 1273 poster, där en post är antingen en enda IP-adress eller ett CIDR-intervall med IP-adresser från /24 till /32. <br/><br/> Om du skickar TLS-krypterade meddelanden stöds inte IPv6-adresser och adressintervall.

3. Du kan också markera kryssrutan **Aktivera säker lista** för att förhindra att e-post saknas från vissa välkända avsändare. Hur? Microsoft prenumererar på tredjepartskällor till betrodda avsändare. Om du använder den här säkra listan innebär det att dessa betrodda avsändare inte av misstag markeras som skräppost. Vi rekommenderar att du väljer det här alternativet eftersom det bör minska antalet falska positiva (bra e-post som klassificeras som skräppost) som du får.

4. Klicka på **Spara**. En sammanfattning av standardprincipinställningarna visas i det högra fönstret.

## <a name="additional-considerations-when-configuring-ip-allow-lists"></a>Ytterligare överväganden när du konfigurerar IP Allow-listor

Följande är ytterligare överväganden som du kanske vill överväga eller som du bör vara medveten om när du konfigurerar en IP Allow-lista.

### <a name="specifying-a-cidr-range-that-falls-outside-of-the-recommended-range"></a>Ange ett CIDR-intervall som faller utanför det rekommenderade intervallet

Om du vill ange ett CIDR IP-adressintervall från /1 till /23 måste du skapa en regel för e-postflöde som fungerar på IP-adressintervallet som anger att skräppostförtroendenivån (SCL) ska **kringgå skräppostfiltrering** (vilket innebär att alla meddelanden som tas emot inom det här IP-adressintervallet är inställda på "inte skräppost") och ingen ytterligare filtrering utförs av tjänsten). Men om någon av dessa IP-adresser visas på någon av Microsofts egna blocklistor eller på någon av våra blockeringslistor från tredje part blockeras dessa meddelanden fortfarande. Vi rekommenderar därför starkt att du använder IP-adressintervallet /24 till /32.

Om du vill skapa den här regeln för e-postflöde utför du följande steg.

1. Navigera till regler för **e-postflöde** \> **i**EAC.

2. Klicka ![på](../../media/ITPro-EAC-AddIcon.gif) Lägg till ikon och välj sedan **Skapa en ny regel**.

3. Ge regeln ett namn och klicka sedan på **Fler alternativ**.

4. Under **Använd den här regeln om**väljer du **Avsändare** och väljer sedan **IP-adress i något av dessa intervall eller exakt matchar**.

5. I **ange IP-adresser**i ange IP-adressintervallet](../../media/ITPro-EAC-AddIcon.gif)klickar du på Lägg **till** ![ikonen och klickar sedan på **ok**.

6. Under **Gör följande** ruta ställer du in åtgärden genom att välja Ändra **meddelandeegenskaperna** och ställ sedan **in förtroendenivån för skräppost (SCL).** I rutan **Ange SCL** väljer du **Bypass-skräppostfiltrering**och klickar på **ok**.

7. Om du vill kan du göra val för att granska regeln, testa regeln, aktivera regeln under en viss tidsperiod och andra val. Vi rekommenderar att du testar regeln under en period innan du tillämpar den. [Procedurer för regler för e-postflöde i Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures) innehåller mer information om dessa val.

8. Klicka på **Spara** för att spara regeln. Regeln visas i listan över regler.

När du har skapat och tillämpat regeln förbigår tjänsten skräppostfiltrering för det IP-adressintervall som du har angett.

### <a name="scoping-an-ip-allow-list-exception-for-a-specific-domain"></a>Omfå en IP Tillåt list undantag för en viss domän

I allmänhet rekommenderar vi att du lägger till IP-adresserna (eller IP-adressintervallen) för alla dina domäner som du anser vara säkra i ip-tillåtlistan. Men om du inte vill att ip-tillåtlisteposten ska gälla för alla dina domäner kan du skapa en regel för e-postflöde (kallas även en transportregel) som förutom specifika domäner.

Anta till exempel att du har tre domäner: ContosoA.com, ContosoB.com och ContosoC.com, och du vill lägga till IP-adressen (för enkelhetens skull, låt oss använda 1.2.3.4) och hoppa över filtrering endast för domänContosoB.com. Du skulle skapa en IP Allow-lista för 1.2.3.4, som anger spam konfidensnivå (SCL) till -1 (vilket innebär att den klassificeras som icke-spam) för alla domäner. Du kan sedan skapa en regel för e-postflöde som anger SCL för alla domäner utom ContosoB.com till 0. Detta resulterar i att meddelandet genomsöks på nytt för alla domäner som är associerade med IP-adressen med undantag för ContosoB.com som är domänen som anges som undantag i regeln. ContosoB.com har fortfarande en SCL på -1 vilket innebär hoppa över filtrering, medan ContosoA.com och ContosoC.com har SCLs på 0, vilket innebär att de kommer att skannas om av innehållsfiltret.

Gör så här:

1. Navigera till regler för **e-postflöde** \> **i**EAC.

2. Klicka ![på](../../media/ITPro-EAC-AddIcon.gif) Lägg till ikon och välj sedan **Skapa en ny regel**.

3. Ge regeln ett namn och klicka sedan på **Fler alternativ**.

4. Under **Använd den här regeln om**väljer du **Avsändare** och väljer sedan **IP-adress i något av dessa intervall eller exakt matchar**.

5. Ange IP-adress- eller IP-adressintervallet som du angav i listan Tillåt IP](../../media/ITPro-EAC-AddIcon.gif)i rutan Ange **IP-adresser,** klicka på Lägg **till** ![ikon och klicka sedan på **OK**.

6. Under **Gör följande**anger du åtgärden genom att välja Ändra **meddelandeegenskaperna** och ställ sedan **in förtroendenivån för skräppost (SCL).** Markera **0**i rutan **Ange SCL** och klicka på **OK**.

7. Klicka på **Lägg till undantag**och välj **Avsändare** och välj **domän**under **Utom om**det finns .

8. Ange den domän som du vill kringgå skräppostfiltrering för i rutan **Ange domän,** till exempel **contosob.com**. Klicka på](../../media/ITPro-EAC-AddIcon.gif) Lägg **till** ![lägg till ikon om du vill flytta den till listan med fraser. Upprepa det här steget om du vill lägga till ytterligare domäner som undantag och klicka på **ok** när du är klar.

9. Om du vill kan du göra val för att granska regeln, testa regeln, aktivera regeln under en viss tidsperiod och andra val. Vi rekommenderar att du testar regeln under en period innan du tillämpar den. [Procedurer för regler för e-postflöde i Exchange Server](https://docs.microsoft.com/Exchange/policy-and-compliance/mail-flow-rules/mail-flow-rule-procedures) innehåller mer information om dessa val.

10. Klicka på **Spara** för att spara regeln. Regeln visas i listan över regler.

När du har skapat och tillämpat regeln kringgås skräppostfiltrering för IP-adressen eller IP-adressintervallet som du har angett endast för domänundantaget som du angav.

### <a name="scenarios-where-allowed-ip-addresses-are-still-filtered"></a>Scenarier där tillåtna IP-adresser fortfarande filtreras

Meddelanden från tillåtna IP-adresser som du har konfigurerat i anslutningsfilterprinciper omfattas fortfarande av skräppostfiltrering i följande scenarier:

- Käll-IP-adressen i anslutningsfilterprincipen är också konfigurerad i en lokal, IP-baserad inkommande koppling i *alla* klientdatorer (låt oss anropa den här klient-A- **och** klient-A- och Exchange Online Protection-servern som först stöter på meddelandet i Office 365 råkar båda vara i samma Active Directory-skog i Microsoft-datacenter. I det här fallet läggs **IPV:CAL** till i meddelandets [anti-spam-meddelanderubriker](anti-spam-message-headers.md) (som anger meddelandet kringgick skräppostfiltrering), men meddelandet är fortfarande föremål för skräppostfiltrering.

- Din klientorganisation (där du har konfigurerat anslutningsfilterprincipen) och Exchange Online Protection-servern som först stöter på meddelandet i Office 365 råkar båda vara i olika Active Directory-skogar i Microsoft-datacenter. I det här fallet läggs **IPV:CAL** inte till i meddelanderubrikerna, så meddelandet är fortfarande föremål för skräppostfiltrering.

Om du stöter på något av dessa scenarier kan du skapa en regel för e-postflöde i EAC med (minst) följande inställningar för att säkerställa meddelanden från IP-adressen eller adresserna kring kringgå skräppostfiltrering:

- Regelvillkor: **Använd den här regeln om** \> **avsändar-IP-adressen** \> **finns i något av dessa intervall eller exakt matchar** \> (din IP-adress eller dina IP-adresser).

- Regelåtgärd: **Ändra meddelandeegenskaperna** \> **Ange förtroendenivån för skräppost (SCL)** \> **Bypass spam filtrering**.

Detta är i princip samma regelskapande procedur från föregående [Scoping en IP Allow list undantag för en viss domän](#scoping-an-ip-allow-list-exception-for-a-specific-domain) avsnitt.

## <a name="new-to-office-365"></a>Är du ny på Office 365?

||
|:-----|
|![Den korta ikonen för](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) LinkedIn Learning **New till Office 365?** Upptäck kostnadsfria videokurser för **Office 365-administratörer och IT-proffs**som kommer till dig genom LinkedIn Learning.|

## <a name="for-more-information"></a>Mer information

[Betrodd avsändare och blockerade avsändarlistor i Exchange Online](safe-sender-and-blocked-sender-lists-faq.md)

[Konfigurera principer för skräppostfilter](configure-your-spam-filter-policies.md)

[Konfigurera den utgående skräppostprincipen](configure-the-outbound-spam-policy.md)

[Så här förhindrar du att bra e-post markeras som skräppost i Office 365](prevent-email-from-being-marked-as-spam.md)

[Så här minskar du skräppost en post i Office 365](reduce-spam-email.md)
