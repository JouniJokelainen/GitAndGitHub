![Git ja GitHub](/gitjagithub.jpg)


------------------

### Mitä versiohallinnalla tarkoitetaan?
Versionhallinnalla tarkoittaa menetelmää, joka säilöö tietoa ja siihen tehtyjä muutoksia.

Sen käyttöön on pääsääntöisesti kaksi syytä: 
1. Versionhallinta mahdollistaa tiedon varmuuskopioinnin. Varmuuskopiot (*commitit*) sisältävät sekä tiedon nykyisen, että aikaisemman tilan.  
2. Versiohallinta (*GitHub:n* kautta) mahdollistaa tiedon jakamisen muille, sekä osallistumisen muiden projekteihin.


### Mikä [Git](https://git-scm.com) on?

Git on hajautetun versiohallinnan menetelmä jossa ideana on tarjota säilytyspaikka käytettävälle tiedolle ja pitää kirjaa tietoon tehdyistä muutoksista. Ohjelmistotyössä versiohallinnan käyttäminen yhteistyöskentelyyn ja muutosten jäljittämiseen on normi. Alunperin Git:n on kehittänyt suomalainen [Linus Thorvalds](https://fi.wikipedia.org/wiki/Linus_Torvalds).

### Mikä [GitHub](https://github.com/) on?

*GitHub* mahdollistaa myös saman tiedon parissa työskentelyn eri tietokoneilta. Saman tiedon parissa työskennellään kuitenkin usein eri tietokoneilta (mikroluokka, kotikone, jne.).

Toisaalta versiohallinta toimii myös varmuuskopiona työllesi. Näin tieto ei häviä, vaikka tietokoneesi hajoaisi.

*GitHub* (ja myös [GitLab](https://about.gitlab.com/)) ovat palveluita, joissa voidaan pitää Git-muotoisia varastoja (*Repository*). Ne mahdollistavat tiedon jakamisen muille saman tiedon parissa työskenteleville henkilöille.

### Git:n peruskäyttö

Git:ä voidaan käyttää jokoa Git komentoriviltä tai suoraan kehitystyökalun (esim. Visual Studio Code) kautta. On hyvä tietää Git komentorivin peruskomennot vaikka jatkossa Git:ä käyttäisikin kehitystyökalun avulla. Näin Git toiminnallisuudet sisäistää paremmin.

Git järjestelmänä koostuu kolmesta osasta  
1. Työkansio tietoineen (*working directory*)
2. Git indeksi (*staging area*)
3. Paikallinen versionhallinta repositorio .git hakemistossa (*local .git*)

![Git prosessi](https://uidaholib.github.io/get-git/images/workflow.png)

**Git työkentely:**

Git tietojen määrittäminen:
- Git versiohallinnan ottaminen käyttöön työkansiossa: ```git init```   
- Git käyttäjänimen määrittäminen: ```git config user.name```   
- Sähköpostiosoitteen määrittäminen: ``` git config --global user.email "erkki.esimerkki@example.com" ```  
- Git tietojen näyttäminen: ```git config --list --global```    

Git työskentelyn perusprosessi:
- Tiedon tuottaminen ja muokkaaminen Git työkansiossa   
- Tiedon lisääminen Git indeksiin: ```git add b.txt``` tai ```git add .```  
- *Commit:n* luominen indeksissä olevista tiedoista: ```git commit -m "Commit viesti"```   
- *Git commit:n* listaaminen: ```git log``` tai ```git log --oneline``` 
- *Git* tilan tarkastminen: ```git status```   

**Github työskentely:**

Työhakemiston synkronoiminen *GitHub:n*:
- Paikallisen työkansion kytkeminen GitHub repositorioon: ```git remote add origin https://github.com/GitHubTunnus/GitRepositorio.git```   
- Etärepositorio kytköksen tarkistaminen: ```git remote -v```   
- ``` git push -u origin master```   

![Gitin peruskäyttö](https://gitlab.jyu.fi/tie/ohj2/esimerkit/k2020/raw/master/luennot/luento02/git.png)


Linus Thorvalds
>"*Kun Microsoft alkaa tehdä ohjelmia Linuxille, se tarkoittaa että minä olen voittanut.*"
