## 11. OOP
Pro logiku a práci s daty v OOP (objektově orientovaném programování) používáme objekty. 
* Výhody: usnadňují práci ve více lidech, kód je znovupoužitelný
* Objekty si pamatují svůj stav / vlastnost (objekt auto má stav barva – červená) a poskytuje na venek nějaké operace / metody (auto může zatroubit)

Příklady:
* Objekt auto má vlastnosti barva, značka, motor (který může být také objekt) a metody zatroubení, nastartování, otevření okna
* Objekt tlačítko má vlastnosti text, který zobrazuje, barvu pozadí, pozice atd. Má metody stisknutí, dojité stisknutí (které se zavolají, když na ně uživatel klikne)

Dědičnost, zapouzdření, polymorfismus
* **Dědičnost**: Třídy mohou dědit z jiných tříd. Například máme třídu rostlina, která má vlastnosti stáří a výška. Potom máme třídu strom, která dědí ze třídy rostlina, má tedy taky vlastnosti stáří a výška, plus nějaké svoje další (třeba jestli je to listnatý strom)
* **Zapouzdření**: Zaručuje, že objekt nebude přímo upravován. Každý objekt poskytuje rozhraní, přes který se k němu přistupuje (například něž aby kód přímo měnil počet peněž na bankovním účtu, kód řekne objektu, že chce přičíst částku a objekt si to pořeší sám)
* **Polymorfismus:** pokud očekáváme nějaké chování od třídy, mělo by být stejné jako u tříd, které z ní dědí. Příklad strom, rostlina – můžeme zjistit vlastnost věk u rostliny, měli by jsme ho tedy moct zjistit i u stromu

Z **tříd** vytváříme jednotlivé objekty (instance třídy), s kterými pak pracujem. Je to vlastně předpis, jak by měl objekt vypadat. Například třídu strom, z ní vytvoříme nový objekt (instanci) smrk. 
## 12. Programování – proměné, …
Do **proměnných** uchováváme data, datový typ je druh dat, které budou v proměnné. Například do proměné typu int můžeme uchovávat jenom celá čísla. Proměná musí mít unikátní jméno. Převod mezi datovými typy se nazývá parsování.
* **int** – jenom celá čísla
* **double** – i desetiná čísla
* **string** – text, píše se v úvozovkách

`int nazevPromene = 5;`

**Funkce, metody a procedury** jsou pojmenované části kódu, které můžeme zavolat. 
* **Funkce:** může brát vstupní data (parametry), vždy nějaké data vrátí
* **Procedůra:** nevrací žádná data, jenom provede příkazy
* **Metoda:** je v objektu (auto má metody zatrub)
```c#
int zdvojnasob(int cislo)
{
    return cislo * 2;
}
int deset = zdvojnasob(5) //zavolani funkce s parametrem 5 a dání hodnoty co vrátí do proměné
```
Tato funkce bere **argument** cislo typu int. Argumenty jsou data, která posáláme funkci při jejím zavolání. Existují dva druhy:
* **Hodnotou** - pošleme do funkce přímo hodnotu (např. 5). Pokud ji ve funkci změníme, nezmění se mimo
* **Referencí** - pošleme odkaz na proměnou, pokud ji ve funkci změníme, změní se i mimo. V C# například objekty
## 13: Větvení, cykly
**Cyklus** je část kódu, která se na základě nějaké podmínky opakuje
* S podmínkou na začátku: kód se provede, zkontroluje se podmínka, pokud platí opakuje se
```c#
do{
    //kod
} while(podminka);
```
* S podmínkou na konci: zkontroluje se podmínka, pokud platí, kód se provede, opakuje se
```c#
while(podminka){
    //kod
}
```
* S počtem opakování: nejdřív se vytvoří proměnná s počáteční hodnotou, poté se uvede podmínka, poté se uvede operace. `for(int i = 0; opakuje se dokud je i menší jak 9;k i se přečte 1)`
```c#
for (int i = 0;i < 9;i++){
    //kod
}
``` 
**Větvení**: kód jde různými cestami na základě nějakých podmínek
* **if**: pokud podmínka platí, kod se provede, pokud ne, neprovede se. 
* **else if**: pokud předchozí if neplatí zkontroluje se podmínka u else if. Může být víc else if za sebou
* **else**: pokud žádná z předchozích if nebo else if neplatí provede se tento kód
```c#
if (podminka){
    //kod
}
else if (jinaPodminka){
    //kod
}
else{
    //kod
}
```
* **switch**: stanovíme nějakou proměnou a stanovíme jednotlivé případy (case), které ukončíme break, pokud žádný z případů nebude platit, stane se default případ
```c#
switch(promena)
{
    case 1: //pokud je hodnota promena 1
    //kod
    break;

    default: //pokud nic z predchozich neplati
    break;
}
``` 

**Podmínka** je logická operace (porovnávání atd.) a její výstup je *true* nebo *false*. **Logický operátor** nám umožňuje provádět logické operace, základní jsou *and* (zapisuje se `&&`) a *or* (`&&`). *Negace* (zapisuje se `!`) obrací hodnotu

Pravdivostní tabulka:

| a | b | !a | and | or | xor |
|:-:|:-:|:--:|:---:|:--:|:---:|
| 0 | 0 |  1 |  0  |  0 |  0  |
| 0 | 1 |  1 |  0  |  1 |  1  |
| 1 | 0 |  0 |  0  |  1 |  1  |
| 1 | 1 |  0 |  1  |  1 |  0  |


## 14. Grafika a prvky na formuláři
v C# se vykreslování provádí pomocí picture boxu, který má událost Paint. Visual studio nám automaticky vytvoří proceduru, která se zavolá pokaždé, když se stane tato událost. 
* Při vykreslování 2d objektů obvykle musíme určit **souřadnice (x,y)**, na kterých se má objekt vykreslit
* U nevyplněných objektů musíme určit **pero** (pens.white) a u vyplněných **štětec** (brushes.white)
* Souřadnice májí 0 v levém horním rohu, x je doprava kladné, y je kladné dolů

Ukázka:
```c#
//černý vyplněný obdélnník se souřadnicemi 150 200 a rozměry 30 40
e.Graphics.FillRectangle(Brushes.Black,150,200,30,40);
//černá nevyplněná elipsa na souřednicích 150 200 a rozměry 10 10
e.Graphics.DrawEllipse(Pens.Black,300,300,10,10);
//modrá čára z bodu 10 10 do bodu 500 500
e.Graphics.DrawLine(Pens.Blue,10,10,500,500);
```
 
## 15. C# a databáze
### Připojení 
Klikne se na **Zdroje dat**, **Přidat nový zdroj dat**, vybrat *Databáse* a další, další. **Nové připojení**, vybere se *Microsoft SQL Server* a jako zprostřetkovatel *Poskytovatel dat.. OLE DB*. Vybere se nazev serveru a databáse a ok. Zaškrknout *Zobrazit připojovací řetezec* a ten zkopírovat a uložit někam. Další, další, zaškrknout *Tabulky* a dokončit
### V C#
#### Připojení
Na začátek se musí dat knihovna SqlClient:
```c#
using System.Data.SqlClient;
```
Potom Vytvořit připojení s vlastním *Připojovacím řetezcem*:
```c#
//text nahradit vlastním connection string
SqlConnection pripojeni = new SqlConnection(@"Data Source=.;Integrated Security=SSPI;Initial Catalog=test");
```
#### Používání
Pokaždé se musí otevřít připojení a po ukončení práce s databási zase zavřít:
```c#
pripojeni.Open();
//čtení, vkládání, upravování nebo mazání 
pripojeni.Close();
```
Pro práci s databásí se musí vytvořit příkaz, přidělit mu připojení, které jsme si vytvořili. Toto příkaz pouze vytvoří, ale ještě **Neprovode**
```c#
SqlCommand prikaz = new SqlCommand();
prikaz.Connection = pripojeni;
prikaz.CommandText = "select * from users";
```
Provést příkaz lze dvěma způsoby. **prikaz.ExecuteNonQuery()** pouze příkaz provede, vhodný na mazání, vkládání, upravování. 
```c#
pripojeni.Open();
//přiklad mazání
SqlCommand prikaz = new SqlCommand();
prikaz.Connection = pripojeni;
prikaz.CommandText = "delete * from users";
prikaz.ExecuteNonQuery();
pripojeni.Close();
```
Nebo pro čtení dat je potřeba **SqlDataReader**. Ten vytvoříme tak, že na příkazu zavoláme metodu *prikaz.ExecuteReader()* ta vrátí nový reader. Potom pokaždé, když zavoláme *reader.Read()*, reader přečte další řádek a můžeme s ním pracovat a taky vrátí *true* nebo *false* jestli má co číst. Jednotlivá data z řádku jsou pak uložena v poli přímo v readeru:
```c#
pripojeni.Open();
//vytvoření příkazu
SqlCommand command = new SqlCommand();
command.Connection = pripojeni;
command.CommandText = "select * from users";
//Vytvoření readeru
SqlDataReader reader = command.ExecuteReader(); 

//dokud reader.Read() vrací true - je co číst - koná
//se kód v cyklu. 
while (reader.Read())
{
    //reader["id"]
    //reader["jmeno"]
    //reader["prijmeni"]
}
pripojeni.Close();
```

#### Zobrazení
Data zobrazujeme do ListView. Nejdříve musíme přidat **colums** a pojmenovat je a potom přepnout **View** na *Details*

Data do ListView přidáme tak, že nejdříve vytvoříme item a pak jej do něj přidáme. Příklad:
```c#
pripojeni.Open();
//vybere všechny data z tabulky users
SqlCommand prikaz = new SqlCommand();
prikaz.Connection = pripojeni;
prikaz.CommandText = "select * from users";
SqlDataReader reader = command.ExecuteReader();

while (reader.Read())
{
//vytvoří se item
ListViewItem item = new ListViewItem();
//první sloupec je jako Text
item.Text = reader["id"].ToString();
//do dalších sloupcůc se pak přidává takto:
item.SubItems.Add(reader["jmeno"].ToString());
item.SubItems.Add(reader["prijmeni"].ToString());     
//nakonec je důležité přidat item do ListView, jinak se nebude nic dít      
listView1.Items.Add(item);
}
pripojeni.Close();
```




