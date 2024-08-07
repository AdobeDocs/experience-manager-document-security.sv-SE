---
title: Introduktion till AEM Document Security Extension for Microsoft&reg; Office
description: Med Document Security Extension for Microsoft&reg; Office kan du använda fördefinierade sekretessinställningar för dina Microsoft&reg; Office-filer.
uuid: a5428c50-fae3-4823-9e6f-0f5306e7248f
content-type: reference
topic-tags: using
discoiquuid: cf93f9f5-1fb6-4909-815e-0ffb8c6ea6d1
exl-id: 3e07c031-3f88-4bde-bdb3-b136ef5f9527
source-git-commit: 3b6a686966fb8d006bed8cc4a4bf5eebe0dfb030
workflow-type: tm+mt
source-wordcount: '1248'
ht-degree: 0%

---

# Introduktion till AEM Document Security Extension for Microsoft® Office{#introduction-to-aem-document-security-extension-for-microsoft-office}

Adobe® Experience Manager Document Security Extension för Microsoft® Office säkerställer att endast de personer du har behörighet att använda Word-, Excel- och PowerPoint-filer som innehåller din immateriella egendom. Genom att använda Document Security Extension för Microsoft® Office kan du använda fördefinierade sekretessinställningar för dina filer.

Document Security Extension for Microsoft® Office förbättrar LiveCycle Rights Management och Document Security för Adobe Experience Manager Forms. Det skyddar Office-filer och ger behöriga användare åtkomst till principskyddade filer enligt gällande sekretessinställningar.

## Hur dokumentsäkerhet skyddar immateriell egendom {#how-document-security-protects-intellectual-property}

Dokumentskydd säkerställer att bara de personer du ger behörighet kan använda filer som innehåller din immateriella egendom. Med dokumentskydd kan du skydda filer med hjälp av sekretessregler. En *princip* är en samling information som innehåller sekretessinställningar och en lista över behöriga användare. De inställningar du anger i en profil avgör hur en mottagare kan använda en fil som du tillämpar profilen på. Du kan till exempel ange om mottagarna ska kunna skriva ut eller kopiera text eller spara ändringar.

Administratörer och användare av dokumentsäkerhet kan skapa profiler. Administratörer skapar organisationsprofiler som är tillgängliga för alla behöriga användare. Administratörer eller koordinatorer för principuppsättningar kan också skapa grupper med profiler som kallas *principuppsättningar* och som är tillgängliga för en delmängd av användare. Användare kan skapa egna profiler, som bara de kan använda. Administratörer, principuppsättningskoordinatorer och användare kan skapa profiler med hjälp av webbsidorna Dokumentsäkerhet.

Även om profiler lagras på dokumentsäkerhet kan du tillämpa dem på filer via Word, Excel eller PowerPoint. När du tillämpar en profil på en fil skyddas informationen som filen innehåller av de sekretessinställningar som anges i profilen. När du distribuerar den profilskyddade filen kan bara behöriga mottagare komma åt innehållet.

Om du använder en skyddsprofil får du full kontroll över filen även sedan du distribuerat den. Du kan granska händelser för att spåra när och hur mottagarna använder filen. Du kan också ändra profilen, hindra användare från att fortsätta få åtkomst till filen och ändra profilen som är kopplad till filen.

## Hur policyer fungerar {#how-policies-work}

Profilerna innehåller information om behöriga användare och sekretessinställningar som ska gälla för immateriell egendom. Dokumentsäkerhet känner igen användare som ingår i en länkad LDAP- eller Active Directory-lista. Användare kan också vara personer som har bjudits in att registrera sig hos Dokumentsäkerhet eller för vilka administratören har skapat ett konto.

Sekretessinställningarna i en profil avgör hur mottagarna kan använda filer som skyddas av profilen. Profiler kan t.ex. anges i profiler om mottagarna kan skriva ut filer, kopiera innehåll till andra filer eller spara ändringar i skyddade filer. Olika sekretessinställningar kan även anges i profiler för olika användare.

När du tillämpar en profil på en fil skyddas informationen som filen innehåller av de sekretessinställningar som anges i profilen. När du distribuerar filen autentiserar Dokumentskydd mottagarna som försöker öppna filen och ger behörighet enligt de behörigheter som anges i profilen.

När en profil har tillämpats på en fil kan sekretessinställningarna för profilen ändras när som helst. Du kan lägga till eller ta bort behöriga användare eller ändra behörigheten för användare när de har tagit emot filen. Den profil som tillämpas på filen kan ändras. Åtkomsten till filen kan återkallas så att alla som har en kopia av filen inte längre kan öppna den.

Om principen tillåter åtkomst offline kan mottagarna även använda principskyddade filer offline (utan en aktiv Internet- eller nätverksanslutning) under den tidsperiod som anges i principen.

## Så här fungerar profilskyddade filer {#how-policy-protected-files-work}

För att en användare ska kunna öppna och använda principskyddade Word-, Excel- och PowerPoint-filer måste profilen inkludera användaren som mottagare. Eller så måste den tillåta anonym åtkomst. Användaren måste ha Document Security Extension for Microsoft® Office installerat. Om du vill ge en profilskyddad fil till någon som inte har Document Security Extension för Microsoft® Office kan du ge dem en kopia av programmet. Eller så kan du tala om för dem hur de laddar ned den från din webbplats. Om du inte har installationsprogrammet kan du hämta det från [hämtningssidan](https://experienceleague.adobe.com/en/docs/experience-manager-document-security/using/download-installer).

När en användare försöker öppna en profilskyddad fil ansluter Document Security Extension för Microsoft® Office till Document Security för att autentisera användaren. Om Dokumentsäkerhet är konfigurerat för att granska filanvändningen ser användaren ett meddelande om att filanvändningen håller på att granskas. Dokumentskydd avgör vilka filbehörigheter som användaren och användaren kan använda filen enligt principinställningarna under följande förhållanden:

* För den giltighetsperiod som anges i policyn.
* Tills en administratör eller den person som tillämpade profilen antingen återkallar åtkomsten till filen eller ändrar profilen.

  Om den person som tillämpade profilen ändrar profilen eller nekar åtkomst till filen, ändras eller tas användarens behörigheter bort för filen även om användaren redan har filen. Om själva filen har återkallats kan användaren få en uppdaterad kopia via en URL.

  Om principen tillåter offlineåtkomst kan användare öppna principskyddade filer utan Internet- eller nätverksanslutning under den angivna offlinelåneperioden. När offlineleasingperioden är slut måste användaren vara online och synkronisera med Document Security, som påbörjar en ny låneperiod.

  Om principen tillåter offlineåtkomst kan användare öppna principskyddade filer utan Internet- eller nätverksanslutning under den angivna offlinelåneperioden. Händelser, till exempel försök att öppna den nya filen, granskas också och registreras på samma sätt som för den ursprungliga filen.

## Skydda filerna med dokumentskydd {#using-document-security-to-protect-your-files}

Du kan använda profiler för att skydda dina filer i olika situationer.

Till exempel tar en tillverkare emot anbud från leverantörer som tillhandahåller delar till en ny produkt. Tillverkaren skall förse anbudsgivarna med äganderättsskyddad information för att kunna färdigställa inlämnade anbud. Tillverkaren använder Dokumentskydd för att skydda filerna med en profil som gör att budgivarna kan öppna filerna och visa informationen. Anbudsgivarna hindras dock från att ändra, skriva ut eller kopiera filerna, och alla som inte har behörighet hindras från att öppna filerna.

Efter att ha godkänt ett anbud uppdaterar tillverkaren policyn för att ge den godkända budgivaren behörighet att skriva ut, kopiera och spara ändringar lokalt. Tillverkaren tar också bort de anbudsgivare som inte lyckades och återkallar deras tillstånd att öppna filerna.

När man arbetar med den vinnande budgivaren ändrar tillverkarens tekniker några av designspecifikationerna i filerna. För att publicera de nya specifikationerna återkallar tillverkaren åtkomsten till vissa av filerna och publicerar nya versioner. När ingenjörer försöker öppna filen ser de ett meddelande om att åtkomsten till filen har återkallats. Meddelandet innehåller en URL där de kan hämta en ny version av filen.

## Ytterligare information {#additional-information}

Resurserna i den här tabellen kan hjälpa dig att lära dig mer om AEM dokumentsäkerhet:

<table >
 <tbody>
  <tr>
   <th><p>Mer information om</p> </th>
   <th><p>Se</p> </th>
  </tr>
  <tr>
   <td><p>Hjälp för AEM</p> </td>
   <td><p><a href="https://experienceleague.adobe.com/en/docs/experience-manager-65/content/forms/administrator-help/get-started/configure-general-aem-forms-settings">Administratörshjälp</a> eller klicka på länken Hjälp i det övre högra hörnet på sidan på administrationssidorna för dokumentsäkerhet.</p> </td>
  </tr>
  <tr>
   <td><p>Uppdateringar, teknisk information och ytterligare information om den här produktversionen</p> </td>
   <td><p><a href="https://experienceleague.adobe.com/?support-solution=General&amp;support-tab=home#support">Experience Cloud tekniska support</a></p> </td>
  </tr>
 </tbody>
</table>
