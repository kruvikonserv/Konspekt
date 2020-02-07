# **Konspekt KTA-19E (Elvis Takkis)**
1. Ülevaade kursuses kasutatud käsurea programmide ja näidete kohta.
   - ping -c 3 host_name 
      > saadab vastuvõtvale signaali ja võtab selle vastu (c -3 tähendab et on saadetud signaali)
   - printf
      > prindib päringu (sisendi kasutamiseks)
   - netcat (nc) 
      > on arvutivõrgu utilil võrguühenduste lugemiseks ja võrguühenduste kirjutamiseks
   - nc -l port_nr 
      > "kuulab" viidatud porti
   - nc localhost port_nr 
      > võtab vastu viidatud pordi
   - ^D 
      > katkestab pordi ühenduse
   - ^C 
      > peatab tatluse
   -     > example.txt 
      > salvestab tulemuse faili example.txt
   - host host_name
      > host saab varjunime ja IP-aadressi
   - dig host_name 
      > host saab varjunime, IP-aadressi, milline server ja millal vastatakse
   - ip addr show 
      > näitab mis liidesed su arvutis on (ethernet: eth0, wifi: wlan0, loopback: lo) 
   - ip route show default 
      > leiab vaikimisi gateway
   - sudo tcpdump -n host host_name 
      > võimaldab kasutajal liiklus jälgida (tuleb , läheb , pikkus) võrgu vahel, millele arvuti on ühendatud, väljumiseks ctr+C
   - traceroute host_name 
      > loetleb teie Linuxi ja mõne muu masina vahel hoste (saates pakette suurenevate TTL-idega, kuni esimene jõuab sihtkohta)
2. Ülevaade põhilistest võrguseadmetest ja nende ülesannetest:
   - ruuter (router)
      > ... on elektrooniline seade, mis ühendab omavahel kaht või enamat arvutivõrku, ning võimaldab nendevahelise andmeside.Andmeside kahe arvutivõrgu vahel toimib pakettidena. Iga pakett sisaldab informatsiooni selle kohta, millisest võrgust see tuleb ja millisesse võrku see minema peab. Nende aadresside järgi saab ruuter otsustada, kas paketi saatja ja vastuvõtja on ühes võrgus või on vastuvõtja saatjast erinevas võrgus. 
   - kohtvõrgukommutaator(switch)
      > ...  on arvutivõrgu seade, mille abil luuakse ühendused koht- ehk LAN-võrgus. Kommutaatorid töötavad peamiselt Ethernetis ehk juhtmetega võrkudes. Kommutaatori eellaseks oli kohtvõrgu jaotur, mis saatis kõik paketid valimatult kõikidele arvutitele. See süsteem töötas, sest arvuti võrgukaart võtab vaikimisi vastu ainult pakette, millel on tema MAC-aadress.
   - tulemüür (firewall)
      > ... on tarkvara või seade, mis turvakaalutlustel piirab ja reguleerib võrguliiklust arvutivõrgus või võrkude vahel vastavalt määratud reeglitele. Tavaliselt kasutatakse tulemüüri interneti ja kohaliku kohtvõrgu vahel. Tulemüüri esmane otstarve on väljastpoolt juurdepääsu takistamine ressurssidele, millele pole sellist juurdepääsu ette nähtud. On ka tulemüüre mis piiravad väljuvat liiklust.
   - WiFi tugijaam (WiFi access point)
      > ... on arvutivõrkude loomisel traadita pääsupunkt (WAP) või lihtsalt pöörduspunkt (AP)ja võrguseade mis võimaldab teistel Wi-Fi-seadmetel juhtmega võrguga ühenduse luua. AP ühendub tavaliselt ruuteriga (juhtmega võrgu kaudu) eraldiseisva seadmena, kuid see võib olla ka ruuteri enda lahutamatu komponent. AP füüsiline asukoht paikneb seal, kus on saadaval WiFi-juurdepääs WLAN-ile.
3. Võrguprotokollid ja nende kasutus (lühidalt):
   - SSH
      > ...on krüptograafiline võrguprotokoll turvaliseks võrguteenuste opereerimiseks turvamata võrgu kaudu.
   - telnet
      > ... on TCP/IP-il põhinev võrguprotokoll, mis pakub kahesuunalist interaktiivset suhtlusteenust.
   - IMAP, POP3, SMTP
      > ... on kõige sagedamini kasutatavad e-posti protokollid.
   - SNMP
      > ... on lihtne võrguhalduse protokoll on internetistandardi protokoll IP-võrkudes hallatavatelt seadmetelt andmete kogumiseks ja korraldamiseks ning nende andmete muutmist seadmete käitumise mõjutamiseks.
   - HTTP, HTTPS
      > ... hüperteksti edastusprotokoll on protokoll teabe edastamiseks arvutivõrkudes ja (HTTPS) turvaline protokoll autenditud ja krüpteeritud informatsiooni edastamiseks arvutivõrkudes.
   - DNS
      > ... ehk domeeninimede süsteem on internetiteenus, mis teisendab domeeninimed internetis või intranetis kasutatavateks IP-aadressideks ja vajadusel ka vastupidi.
   - NTP
      > ... (võrguaja protokoll) on andmesideprotokoll täpse aja edastamiseks ajaserverites.
   - IP
      > ... ehk internetiaadress on arvutivõrgus asuva seadme identifikaator ehk seadmele määratud alaline või ajutine tunnusnumber, mille abil võrku ühendatud seadmed üksteist leiavad.
   - IPv6
      > ... ehk "uue põlvkonna" Internetiprotokoll on andmesideprotokoll, mis on loodud praegusel ajal üldkasutatava Internetiprotokolli IPv4 asendamiseks.
   - TCP
      > ... ehk edastusohje protokoll on levinuim transpordikihi võrguprotokoll, mida kasutatakse TCP/IP võrkudes.
   - UDP
      > ... ehk kasutajadatagrammi protokoll on transpordikihi andmesideprotokoll, mis on defineeritud IPga sõnumite saatmiseks.
   - ICMP
      > ... ehk interneti kontrollsõnumiprotokoll on andmesideprotokoll, mille abil võrguseadmed vahetavad oleku- ja veainformatsiooni.
4. Diagnostika vahendid:
   - Wireshark
      > ... ei muuda ega tee ise võrgus muud kui vaid 'kuulab' seda ja lubab kasutajal kuuldut näha, analüüsida ja salvestada.
   - tcpdump 
     > ... on tavaline pakettanalüsaator, mis töötab käsureal. See võimaldab kasutajal kuvada TCP/IP ja muud paketid mis edastatakse või  võetakse vastu üle võrgu, kuhu on ühendatud arvuti.
   - ping
      > ...  on arvutivõrgu võrguühenduse diagnostikaprogramm, mille abil IP-võrgus hinnatakse hosti ligipääsetavust programmi käivitanud arvutist, samuti pakettide edastamiseks kuluvat aega.
   - traceroute / tracert
      > ... on arvuti võrgu diagnostika käsud marsuut ja transiidi viivituse mõõtmine.
   - nslookup / dig
      > ... Nslookup on programm mida kasutatakse päringute esitamiseks DNS serverile, et saada infot võrgu kohta. Dig on nslookup-iga sarnane käsureaprogramm nimepäringute tegemiseks. Võrreldes nslookup'iga on tegu palju võimsama vahendiga. Päringutes saab kasutada erinevaid parameetreid, mis teeb kasutamise paindlikuks ja päringute vastused detailsemaks.
   - Ressource monitor (Windows)
      > ... on süsteemi tööriist, mis laseb sul jälgida infot arvuti riistvara ja tarkvara ressursse reaalajas.
   - netstat
      > ... on käsurida mis prindib võrguühendused, marsruutimistabelid, liidesestatistika, maskeraadühendused ja multisaate liikmesuse.
