# Sveriges inflation 2020 - 2023 (Nytt: Riksbanken 

Spännande

## Så påverkar inflationen nästa räntebesked
förra månadens inflationssiffror var de sista som presenteras innan Riksbanken gav sitt räntebesked i November 2023. 
<br>
Under 18 månader har det skett nio höjningar av räntan. 


Enligt Alexander Norén på SVT öppnar det upp för att det inte blir någon mer räntehöjning.
<br>
"– Det som också talar för det är att andra tunga riksbanker, som Federal Reserve i USA och europiska centralbanken i Euro-området har sagt att ”nu slutar vi med räntehöjningar”."

Han menar att de andra riksbankernas besked kan göra att trycket minskar på Riksbanken att höja räntan.

## Vad blir konsekvensern om riks banken ökar jämfört med sänker?
Räntesänkningar i sikte?
<br>
Resultatet i September 2023 visade inflationssiffror som gav en saknad pusselbitarna för Riksbanken att använda inför deras räntebesked som gavs i Torsdagen den 20231123. 

I och med att dessa siffror kom in något lägre än väntat spår nu flera ekonomer att räntehöjningarna är över. 

"Den svenska inflationen, som framgår av den bifogade tabellen, var LÄGRE (för en gångs skull) än förväntat i allmänhet. KPIF och KPIFxE var bara 0,1 över Riksbankens prognos. 


En lättnad
<br>
" ... det gör att vi håller fast vid vårt Riksbank-uppmaning om oförändrad reporänta i november", skriver Michael Grahn, chefsekonom på Danske Bank, på X, tidigare Twitter, efter inflationssiffrorna. 

Sannolikheten för att Riksbanken ska höja räntan vid nästa möte har nu sjunkit, konstaterar SEBs seniora ekonom Robert Bergqvist på X: 

"Marknaden prissätter nu ca 30% sannolikhet för att RB höjer räntan nästa vecka, ned från 55% före KPI-siffran. Om Riksbanken ligger still med räntan, som vi fortsätter att tro, måste räntebanan fortsätta att indikera höjning för att inte marknaden ska få glädjefnatt." 



## Hur troligt var en räntesänkning inför Julen 2023?


De positiva inflationssiffror i Maj och september 2023  betyde dock inte säkert att Riksbanken kom att stå över nästa förväntade räntehöjning. Så hur såg sannolikheten för en ytterligare höjning i november?

<i>"Inflationen går åt rätt håll och lite snabbare än förväntat ned(åt). KPIF 4.73 och KPIXE på 7.17. Ändrar inget för Riksbankens kommande möte, det blir en höjning med 25 bps. Men vi går åt rätt håll ...    ... minskar risken något för en november höjning men det blir 25bps då med"</i>, säger Mattias Persson, chefsekonom och global chef för makroanalys på Swedbank på X, tidigare Twitter.

Och så här blev resultatet:


```python
# Riksbanken: Styrräntan

import matplotlib.pyplot as plt 
from matplotlib.figure import Figure 
import numpy as np 

fig = plt.figure(figsize =(7, 6)) 
ax = fig.add_axes([0.1, 0.1, 0.8, 0.8]) 

#Period
x = np.array(['2013-11-25', '2014-01-02', '2014-06-02', '2015-01-02', '2016-06-01', '2016-12-30', '2017-06-01', '2017-12-29', '2018-01-02', '2018-06-01', '2019-01-02', '2019-06-03', '2020-01-02', '2020-06-01', '2021-01-04', '2021-06-01', '2022-01-03', '2022-06-01', '2023-01-02', '2023-06-01', '2023-11-23', '2023-11-24'])

#Värde
y = np.array(['1','0.75', '0.75', '0.0', '0.5', '0.5','0.5', '0.5', '0.5', '0.5', '0.5', '0.25', '0.25', '0.0', '0.0', '0.0', '0.0', '0.25', '2.5', '3.5', '4', '4'])
              
ax.plot(x, y) 

fig.suptitle("Sveriges Riksbank Styrräntan 2013 - 2023\n\n", fontweight ="bold") 
plt.title("Analys: Patrik Ackell 2023", loc = 'right')

#plt.xlabel("Månad och år", fontweight ="bold", rotation=90)    #, ha="right")

# plt.xticks(x[::5]
# ax.xticks(x[::5]
#plt.xlabel("Månad och år", fontweight ="bold", rotation="vertical")
plt.xlabel("\nMånad och år", fontweight ="bold")
#plt.xticks(x[::1],  rotation='vertical')
plt.xticks(rotation='vertical')

plt.ylabel("Procent styrränta")

fig.set_figwidth(15) 

# Saving the figure as JPG.
#plt.savefig("Sveriges-Riksbank-Styrräntan-2013-2023.jpg")
 
# Saving the figure as JPG - saving figure by changing parameter values.
#plt.savefig("Sveriges-Riksbank-Styrräntan-2013-2023-tight", facecolor='white', bbox_inches="tight", pad_inches=0.3, transparent=True)

plt.show()
```


    
![png](output_8_0.png)
    


### Definition:

#### Metoder för att mäta inflation
Inflationen mäts vanligtvis genom att med hjälp av ett prisindex då man räknar ut hur prisnivån har ändrats under en 12-månadersperiod. Det vanligaste och mest kända prisindexet i Sverige är konsumentprisindex (KPI). Indexet visar hur mycket det kostar att leva i Sverige och hur denna kostnad utvecklas över tid. 
<br>
Målet för Riksbankens penningpolitik är att inflationen ska vara 2 procent per år, mätt som den årliga procentuella förändringen i KPIF (konsumentprisindex med fast ränta). KPIF beräknas med samma data och på samma sätt som KPI, men utan att effekten av ändrade boräntor räknas med. 

#### KPIF
(konsumentprisindex med fast ränta). KPIF beräknas med samma data och på samma sätt som KPI, men utan att effekten av ändrade boräntor räknas med. 


Källa: https://www.riksbank.se/sv/penningpolitik/inflationsmalet/hur-mats-inflation/

#### KPIXE
Källa och mer info om KPIXE finns i PDF-format att ladda ner:    https://www.google.com/url?sa=t&rct=j&q=&esrc=s&source=web&cd=&cad=rja&uact=8&ved=2ahUKEwjx-YXQ0raCAxWQa_EDHW3sC3MQFnoECBkQAQ&url=https%3A%2F%2Fwww.konj.se%2Fdownload%2F18.130dc716150d75fadf771c3%2F1446730399510%2FSkillnaden-mellan-KPI-och-KPIX.pdf&usg=AOvVaw0nlkDJFLrVhni6y1ajKxk8&opi=89978449

#### Skillnaden mellan KPI och KPIX
Den långsiktiga skillnaden mellan inflationstakten mätt som KPI respektive KPIX och antas i allmänhet vara försumbar. 
<br>
Denna fördjupning visar att det finns skäl för att skillnaden på längre sikt är omkring 0,3 procentenheter. 
<br>
Om det råder osäkerhet om vilket inflationsmått som Riksbanken styr mot 2 procent, kan det påverka hushållens och företagens inflationsförväntningar.


Sedan 1993 har målet för penningpolitiken i Sverige varit att upprätthålla ett fast penningvärde. Riksbanken har preciserat målet som att den årliga ökningen av konsumentprisindex (KPI) ska vara 2 procent. 
<br>
I praktiken vägleds emellertid penningpolitiken av utvecklingen av det underliggande inflationsmåttet KPIX (tidigare UND1X), som Riksbanken därmed givit ”en speciell status”. 


Skillnaden mellan KPI och KPIX är att det senare måttet exkluderar räntekostnader för egnahem och den direkta effekten av förändrade indirekta skatter och subventioner.



v0.1

