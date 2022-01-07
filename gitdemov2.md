## Git DEMO

Alustetaan työkansio Gitin avulla

1. ```git init ```
    alustetaan git tiedot
    ``` git config --global user.email "you@example.com" ```
    ``` git config --global user.name "Your Name"```
    ```git config --list``` | näyttää asetukset
    ```git config user.name``` | (näyttää käyttäjän)
    ```git config --global init.defaultBranch main``` (muuttaa päähaaran nimeksi main masterin sijaan)
    ```git config --list --global``` | näyttää globaalit asetukset
    ```git config --edit --global``` | (avaa git asetukset oletuseditoriin. tämä valitaan alun perin gittiä asennettaessa)

Luodaan tiedosto a.txt ja sinne sisältöä

2.  ```git add a.txt```

3.  ```git status```

4.  ```git commit -m "Tiedosto a.txt luotu"```

5.  ```git log```

Luodaan tiedosto b.txt ja siihen sisältöä ja tajutaan että se olisi pitänyt lisätä jo edelliseen commititin

6.  ```git add b.txt```
7.  ```git status```
8.   ```git diff HEAD``` näyttää mitä eroa on työkansiolla ja viimeksi commitoidulla tiedolla
9.  ```git commit --amend``` (muutetaan kommentointi sopivaksi ja tallennetaan) TAI ```git commit --amend -m "Lisätty tiedosto A.txt ja B.txt"```
9.  ```git log --oneline ```

Luodaan tiedosto c.txt ja sinne sisältöä

10. ```git add . lisätään c.txt``` = seuraavaan indeksiin ja tajutaan että ei pitänytkään vielä lisätä

11. ```git reset HEAD c.txt``` = poistetaan tulevasta commitista eli perutaan edellinen add . c.txt tiedoston osalta.

12. ```git status```

Lisätään tiedosto d.txt ja siihen sisältöä

13.  ```git add . & git commit -m "lisätty tiedostot c.txt ja d.txt"``` = lisätään ja suoritetaan commit"

14.  ```git log```

Lisätään tietoa d.txt tiedostoon

22.  ```git  checkout -- d.txt``` = palautetaan d.txt aiempaan versioon (edelliseen kommittiin)
	HUOM: git revert *commit hash* = peruu hashissä tehdyt muutokset tiedostoihin
	
23. ```git branch``` = tarkastetaan puu

24. ```git branch uusibranch``` = luodaan uus branch

25. ```git chekcout uusibranch``` = siirrytään uuteen branchiin

Luodaan uusi tiedosto e.txt ja siihen sisältöä

26.  ```git add e.txt``` = lisätään seuraavaan committiin
27.  ```git commit -m "viesti"``` luodaan commit
28.  ```git log``` 
29.  ```git chekcout master``` = siirrytään master branchiin

30.  ```git branch``` = tarkastetaan branch
31.  ```git merge uusibranch``` = yhdistetään haarat

Tarkastetaan että e.txt on ilmestynyt työkansioon

34.  ```git branch -d uusibranch``` = poistetaan sivuhaara

#### Tiedostojen palauttamisesta: 

**Tallennettujen *commitoimattomien* tietojen peruminen**: 

Lisätään työkansioon tiedosto x.txt vaikkapa VScodella ja sisällöksi X

35. ```git add .```

36.  ```git commit -m "Lisätty tiedosto X.txt"```

Lisätään tiedostoon X.txt väärää sisältöä ja tallennetaan tiedosto | HUOM:  Ei committia tässä välissä

37. Lisätään tiedostoon X.txt uutta sisältöä esim. ZZZ ja tallennetaan.

Huomataan että uusi sisältö oli virhe ja halutaan palata tiedoston X.txt osalta aikaisempaan commitoituun sisältöön
38.  ```git status```
39.  ```git checkout -- X.txt```

**Tallennettujen ja *commitoitujen* tietojen peruminen**:

41. Lisätään tiedostoon X.txt uutta sisältöä ZXZX ja tallennetaan muutokset
42.  ```git commit -am "Sisältöä muokattu"``` (em. komento ei toimi tiedostoissa joita ei aiemmin ole jo lisätty git add komenolla)

Huomataan että uusi commitoitu sisältö oli virhe ja se halutaan perua. Tarkastetaan mitä muutoksia commitissa oli

43.  ```git log --oneline```
44.  ```git show *commitin id numero*```
45.  ```git revert *peruttavan commitin id numero*```TAI ```git revert *peruttavan commitin id numero* --no-edit``` (jolloin perumisen aiheuttamaa commit viestiä ei muokata)

**Työhakemistosta poistettun tiedoston palauttaminen**

49.  ```del X.txt```
50.  ```git checkout HEAD X.txt```

HUOM jos poistaminen olisi ehditty jo commitoida
 ```git reset --hard HEAD~1```

#### Työhakemiston synkronoiminen GitHubiin

1. luodaan repositorio GitHubiin ja otetaan repositorion URL osoite leikepöydälle
2.  ```git remote add origin https://github.com/AzureandGit/githarjoitus.git``` = kytketään paikallinen työkansio Github repositorioon
3. Tarkastetaan etärepositorio =  ```git remote -v```
4.  Pusketaan paikallinen työkansio Githubiin =  ``` git push -u origin mastergit``` 
4.1  ```git remote rm origin``` = poistaa remoten
5. Listätään Githubin kautta tiedosto = GitHubissa ollaan yksi commit edellä
6. Haetaan githubin tilanne = ```git fetch```
7. Synkronoidaan githubin tilanne paikalliseen työkansioon = ``` git pull ```