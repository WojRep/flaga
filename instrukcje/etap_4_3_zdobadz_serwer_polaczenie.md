# Szturm na AWS

## Etap 4.3 - Zdobądź serwer: połączenie z serwerem przez VSCode

Masz już VSCode, masz serwer, znasz jego login, adres ip, wiesz gdzie jest folder .ssh.

[Zobacz jak połączyć się z serwerem przez VSCode](http://bityl.pl/nYH1X)


#### Cel:
Wejdź na Twój serwer przez VSCode.

#### Plan:

#### 1. Otwórz VSCode i zainstaluj rozszeżenie Remote-SSH.

![o01.png](foty_do_instrukcji/o01.png)

Extensions (5 ikonka po lewej od góry)

![002.png](foty_do_instrukcji/002.png)

3. W search wpisz: SSH i kliknij w najwyższą pozycję: Remote-SSH i kliknij Install.

![003.png](foty_do_instrukcji/003.png)

4. Kliknij w Remote Explorer (6 ikonka po lewej od góry)

5. Jeżeli przechodzisz to pokolei, to powinien pojawić Ci się w SSH TARGETS conajmniej 1 punkt do połączenia, zdefiniowany w pliku config (lub Config). Możesz go edytować.
6. Najedź na niego myszką. Po prawej stronie pokaże Ci się przycisk którym połączysz się w nowym oknie z serwerem :)
7. W listwie na górze w nowym oknie spyta się Ciebie o haslo.
- Jeżeli to Cię nie połączy 3 razy i wybierz "more actions" 
- Wybierz Open SSH Configuration File i sprawdź czy tutaj wszystko się zgadza albo spytaj się opomoc.
8. Jesteś na serwerze. Hurra :) To jeszcze raz wyjdź wyłączając to okno.

#### 2. Połącz się z serwerem aby sprowokować otworzenie pliku config w folderze .ssh


#### 3. Otwórz z .ssh plik config i wklej tam w zalezności od tego czy masz server w Home czy w AWS:

Tu będzie też kilka słów więcej o pliku config i folderze .ssh.


#### config dla Home:
```
Host xd_root
  HostName 1.1.1.1
  User root
	
Host xd
  HostName 1.1.1.1
  User xd
  IdentityFile "~/.ssh/tu_wstaw_nazwe_klucza"
```

#### config dla AWS:

```
Host xd_ubuntu
  HostName 1.1.1.1
  User ubuntu
  IdentityFile "~/.ssh/tu_wstaw_nazwe_klucza.pem"

Host xd
  HostName 1.1.1.1
  User moja_nazwa_uzytkownika
  IdentityFile "~/.ssh/tu_wstaw_nazwe_klucza"
```

Od teraz zawsze połączysz się z serwerem w 3 kliknięciach:
- Włączając VSC
- Klikając w Remote Explorer (5 klocek po lewej)/var/www/flaga/app.py
- Kliknij w znaczek po prawej stronie Twojego serwera na liśćie połączeń
- Wpisz hasło i jesteś na swoim serwerze z poziomu VSCt

I jesteś. 

Połącz się i rozłącz kilka razy.


#### VSC: Clone

1. Kliknij w 3 klocek od góry z lewej **(Source Controll)**
2. Kliknij w duży niebieski przycisk na dole **(Clone Repository)**
3. Wklej link do repozytorium które chcesz sklonować
```
git clone https://github.com/ZPXD/zajecia_programowania_xd
```
4. Spyta się Ciebie w jakim folderze - podaj katalog domowy
5. Spyta się Cibie czy otworzyć ten folder - powiedz, że tak

![git_clone1.png](foto/git_clone1.png)
![git_clone_2.png](foto/git_clone_2.png)

##### Mobilność

1. Otwórz Pierwszy plik.
2. Otwórz Drugi plik obok, w innym folderze.
3. Stwórz Trzeci plik i zapisz.
4. Otwórz Pierwsz i Drugi plik aby były jedncześnie widoczne.
5. Flodery - otwórz katalog jako folder - aby mieć listę plików z lewej.


#### 3. Upewnij się, że jesteś jako root na serwerze. ("administratorem").

Zobacz czy jesteś na serwerze jako **root**. Poniższa komenda pokaże Ci root, ubuntu albo inną nazwę.
```
echo $USER
``` 
Jeżeli nie jesteś root, to bądź :) Jeżeli jesteś na np. ubuntu, ustaw **root**.
```
sudo passwd
su
echo $USER
```

#### 4. Update paczek.

Uaktualnij paczki :) 

```
apt update
```




#### 7. Krok dodatkowy: Spróbuj się połączyć z serwerem terminala/powershell ; )

Na windowsie 10 możesz szybko włączyć powershell, nie ważne w jakim folderze jesteś:
- **linux/mac terminal:** (linux, mac) klikając jednocześnie **ctrl+shift+t**
- **windows powershell:** (windows) otwórz folder w którym chcesz otworzyć terminal i kliknij w adres i napisz tam powershell - otworzy się. Od teraz, nie ważne czy jesteś na powershellu czy w terminalu, będę na tego typu okno mówił terminal, a powershell używał jedynie gdy będę opisywał coś co dotyczy konkretnie powershella.

Jeżeli terminal/powershell otworzy się, wpisz:
```
ssh xd_root
```
Działa? Super! :))) Możesz zacżąć bawić się swoim terminalem/powershellem.
Nie działa? Spoko, pomówimy o tym w przyszłości. Narazie to nie takie ważne, idź dalej :)

[Dodatkowe sposoby i instrukcje łączenia się z serwerem: powershell/terminal/PuTTy dla Win7/8/10/11/LinuxUbuntu/MACOS](http://bityl.pl/6X3gF)


**Serwer zdobyty!**

Teraz połącz się aby zacząć na nim tworzyć. Będziesz pisać tu programy, udostępniać je w sieci i robić wiele innych rzeczy. 





#### Wsparcie:

[Pomoc na discordzie dla problemów związanych z Etapem 4](https://discord.gg/8YQAaBHh3u)


**Przejdź dalej:** [Etap 5 - Domena - Instrukcje](http://bityl.pl/Q86MW)
