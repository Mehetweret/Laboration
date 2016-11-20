Em:
Du skulle kunna skriva någon uppsats eller liknande i version control, det är vad jag gör. Varje gång jag gör någon större ändring så gör jag en commit och pushar, på så sätt kan jag aldrig tappa bort filen eller av misstag radera någonting.

Du har redan ett Github-konto, så det absolut lättaste är att ladda ned Github for Windows eller Github for Mac (beroende på plattform), det ger dig ett grafiskt gränssnitt för det hela, termen för en versionskontrollerad mapp är "repository" (den termen används väldigt mycket)

Om du skriver i Word eller Pages så kommer du förresten få något svårläsliga commits, jag skriver det mesta i Markdown, jag försöker hitta en bra, grafisk Markdown-editor…

Yup, du skapar ett Repository som existerar både på din dator och på servern, du lägger till någonting, skapar en Commit som beskriver ändringen, sedan Pushar du till servern (behöver inte göras efter varje commit)

De grafiska klienterna kallar Pusha "Sync" eftersom de även gör en Pull när du trycker på den knappen för att kolla om någon annan gjort en ändringPoängen med att använda ett textbaserat format som Markdown är att du får mycket läsligare diffs, Pages och Word använder invecklade XML-format som inte är gjorda för att läsas utanför dem(Och jag tycker det går snabbare att skriva "**" än att trycka Äpple+B)

Försök bara skriva vanligt och använd Format-menyn som om det vore en vanlig text editor, då ser du vad som händer

Bra, spara nu textfilen i den mappen
du gör det i Finderrepositories är bara mapparall extra funktionalitet hanteras av programmet och en dold mapp med metadata (".git")
högerklicka och välj "open in Finder"

om du går till vänstra fliken längst upp så borde den nu synas som en "Uncommitted Change", där du kan kryssa i filen och skriva en Summary nedanför

"Commit to master" betyder att skriva en commit med den här ändringen till branchen "master" - branches är ett sätt att göra flera, parallella tidslinjer, exempelvis för att experimentera med nya funktioner utan att bråka med vad som fungerar

Yup, och om du klickar på en annan commit så kan du se vad som ändrades där

Det är främst listan som är användbar, bollarna visualiserar snarare grenar