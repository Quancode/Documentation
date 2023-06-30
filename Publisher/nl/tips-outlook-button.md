# Tips om buttons in Outlook correct weer te geven met de drag-and-drop-editor

Microsoft Outlook ondersteunt niet alle HTML-stijlen. Dit zorgt ervoor dat de verzonden e-mail vanuit de drag-and-drop-editor in Outlook er anders uit kan zien. Met name de knoppen kunnen qua styling afwijken.  

We hebben daarom een aantal tips op een rij gezet, die ervoor zorgen dat je buttons correct worden weergegeven in Outlook.

## Tip 1
Schakel de knop 'Ondersteuning voor Outlook' in de editor aan. De knop zorgt voor de meest nauwkeurige weergave van je knoppen in Outlook.

Hoe schakel ik de knop 'Ondersteuning voor Outlook' in?
- Ga naar de E-mail-editor.
- Ga naar de desbetreffende drag-and-drop template.
- Kies voor de optie 'Uiterlijk' in de template.
- Kies voor de optie 'Knoppen'.
- Zet de knop 'Ondersteuning voor Outlook' aan.

![Afbeelding](https://github.com/Quancode/Documentation/blob/master/Publisher/images/gitbuttonnieuw2.png)


## TIP 2
Houd de grootte van de knop binnen de standaardafmetingen. Het wordt aanbevolen om de knopgrootte beperkt te houden tot 600px bij 200px of minder, aangezien grotere knoppen weergaveproblemen kunnen veroorzaken. Mocht bijvoorbeeld de tekst toch buiten de button vallen, gebruik dan de padding functies om de tekst weer centraal in de button te krijgen:

- Voeg extra interne padding toe, zodat er meer ruimte ontstaat voor de tekst in de button.

![Afbeelding](https://github.com/Quancode/Documentation/blob/master/Publisher/images/Screenshot%202023-03-29%20at%2016.57.28.png)

- Maak in de broncode template de tekst kleiner binnen de IF-MSO-tags, zodat deze op Outlook kleiner wordt weergeven.

Om styling specifiek voor Outlook mee te geven, kun je gebruik maken van MSO-tags (Microsoft Office). Deze code wordt genegeerd door andere e-mailclients. Een IF MSO-code ziet er als volgt uit:

```
 <!--[if mso]><a href="https://copernica.com" target="_blank" hidden>
	<v:roundrect xmlns:v="urn:schemas-microsoft-com:vml" xmlns:w="urn:schemas-microsoft-com:office:word" esdevVmlButton href="https://copernica.com" 
                style="height:41px; v-text-anchor:middle; width:163px" arcsize="50%" stroke="f"  fillcolor="#eb6c10">
		            <w:anchorlock></w:anchorlock>
		            <center style='color:#ffffff; font-family:Exo, Helvetica, Arial, sans-serif; font-size:15px; font-weight:400; line-height:15px;  mso-text-raise:1px'>Knop</center>
	</v:roundrect></a>
<![endif]-->
```

In de afbeelding zie je waar je de tekst kan verkleinen.

![Afbeelding](https://github.com/Quancode/Documentation/blob/master/Publisher/images/Screenshot%202023-03-29%20at%2017.00.40.png)


## Tip 3
Vermijd het gebruik van Flash-elementen. Deze elementen worden mogelijk niet ondersteund door Outlook. Een goed voorbeeld hiervan is het hover-effect. 

## Tip 4 
Gebruik een webveilig lettertype of maak gebruik van een fallback lettertype wanneer de eigen lettertype niet functioneert.
Houd het lettertype eenvoudig en gemakkelijk leesbaar en gebruik webveilige lettertypen zoals Arial, Verdana of Times New Roman. Dit vergroot de kans dat de e-mail correct wordt weergegeven in Outlook.

Wanneer de eigen lettertype niet functioneert, past de Fallback Service het lettertype aan naar een door jou ingestelde 'backup' lettertype. Voorbeelden van fallback lettertypen families zijn: Serif en Sans-serif.

Door onderstaand IF MSO-code in het hoofdgedeelte van de code te plaatsen, zou de fallback lettertype in elke versie van Outlook zichtbaar moeten zijn. Voeg je eigen lettertype-family fallback letterype toe.

```
<!--[if mso]>
 
<style>
    span, td, table, div {
      font-family: Arial, serif !important;
    }
</style>
 
<![endif]-->
```

Let op: in een aantal versies van Outlook wordt het lettertype standaard ingesteld op Times New Roman, zelfs als de fallback van de lettertypefamilie in de code is gedefinieerd.


## Tip 5
Test je e-mail in verschillende e-mailclients. Zorg bij het ontwerpen van de e-mail dat deze op verschillende platforms getest wordt, om er zeker van te zijn dat uw knop correct wordt weergegeven op alle apparaten en e-mailclients.

Staat de juiste oplossing er niet bij? Neem dan gerust contact op met onze support-afdeling (https://ms.copernica.com/#/support)
