A:
Citat ur nästa uppgift på min kurs: "I denna laboration skall du utgå från dokumentplaner och arkivredovisningar (du får försöka få tag i dessa själv, men kör ni fast så hjälper vi till). Dessa skall ni jämföra med hur man i öppna källkodsprojekt styr och hanterar en helt annan typ av information. Där blandas dokument med programkod och rena exekverbara program. Men! Kravet på struktur och ordning och spårbarhet av det man gör är enormt. Jämförandes är fritt helt fritt. Men målet är att ni skall försöka identifiera det unika med både arkivperspektivet och öppen källkodsperspektivet i hur man styr informationshanteringen över tid. "

Em:
I stort sett all open source-utveckling nu för tiden görs genom github.com, som också har utmärkt dokumentation för allt vad open source heter!

Det där är för övrigt en något föråldrad fråga, open source-verktyg används öven inom stängd utveckling och processerna är väldigt snarlika, mest tack vare "git", ett program för distribuerat sammadbete skrivet av Linux' Linus Torvalds

Det brukade vara så att open source använde mest de gamla verktygen CVS och Subversion, medan större företag använde numera nästan utdöda kommersiella verktyg, numera är det mest spelindustrin som använder kommersiella verkyg eftersom git by design processar *text* fruktansvärt effektivt, men skär fullständigt ihop om det ska handera stora binära filer - där är det mest Subversion (open source) och Perforce (kommersiellt) som gäller

A:
min frågas usp är ju att identifiera hur man styr informationshantering över tid i öppen källkodsperspektiv. Hur tror du att jag som inte kan läsa kod lättast kan hitta en sån struktur? Är det github?

Em:
Yup, Linuxkärnan blev ett så stort projekt (tusentals filer, miljontals rader, hundratals utvecklare) att de gamla verktygen de använde helt enkelt inte kunde hantera alltihop, så de körde en hopsnickrad process där man mailade ändringar till en maillista, som sedan för hand kopierades in. Han började se ett mönster i hur såna här meddelanden såg ut och processades, och skrev ett program som gjorde jobbet med att hålla koll på alla dessa ändringar åt honom

Jag förstår inte 100% frågan, men jag gissar att det handlar om hur beslut fattas? I företag är det ju just företagsprocesser som gäller, i open source hamnar det i öppna debatter, främst genom maillistor och "issues" på Github (eller motsvarande sida), jag ska se om jag kan hitta några bra exempel

A:
Nej inte beslut utan det handlar om spårbarhet!

Em:
Aha, som i audit logs? "Person A la till de här tre raderna i filen B vid datum C"?
Jaha, det är commits då, jag ska se om jag kan hitta en läslig logg

I versionskontrollsystem lagras *allting*; det du gör för att ändra en fil är att du skapar en "commit", som innehåller en uppsättning "diffs" (kort för "difference") och en kommentar som förklarar vad du gjorde och varför, som en changelog ("Kleptomaniac Sims will no longer steal subway stations" är en berömd en från The Sims 3…).

Du kan sedan pusha din commit till en server, där det läggs på tidslinjen, och därifrån kan det inte enkelt tas bort - det är en väldig affär att ta bort en commit, eftersom commits verifierar tidigare commits och lyser varningslampor för alla inblandade, så det vill till att du har en väldigt bra anledning (typ att du av misstag fått med ett lösenord i någon fil).Eftersom det som sparas inte är filer utan serier av diffs så kan du också återställa en fil till vilket tidigare stadium som helst genom att stega baklänges genom alla diffs som rör filen och applicera dem baklänges.

(För att ta bort en commit som är en del av en branch redan så måste hela tidslinjen från och med committen före skrivas om)

Systemet kan göra omskrivningen, men det är väldigt mycket bekräftelser på olika stadier och alla som sedan drar ned committen kommer att få varningar om att tidslinjen har ändrats

Och du kan genom att klicka på en commit i listan gå tillbaka till en tidigare version, och läsa förklaringen om vad committen åstadkommit

Du kan såklart skriva "2e3r4etyugijhfxdzs" som kommentar på alla dina commits och göra fullkomligt oläsliga loggar, men inga respektabla open source-projekt låter dig merge-a sådana commits utan att skriva ordentliga kommentarer, just för att man vill kunna läsa vad som händerDu ser i den listan också en Revert, som bara är en tidigare commit fast baklänges, så du "ångrar" den ändringen, men behåller den i historiken