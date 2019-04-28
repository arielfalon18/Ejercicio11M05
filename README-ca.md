🌍
*[Čeština](README-cs.md) ∙ [Deutsch](README-de.md) ∙ [Ελληνικά](README-el.md) ∙ [English](README.md) ∙ [Español](README-es.md) ∙ [Français](README-fr.md) ∙ [Indonesia](README-id.md) ∙ [Italiano](README-it.md) ∙ [日本語](README-ja.md) ∙ [한국어](README-ko.md) ∙ [Português](README-pt.md) ∙ [Română](README-ro.md) ∙ [Русский](README-ru.md) ∙ [Slovenščina](README-sl.md) ∙ [Українська](README-uk.md) ∙ [简体中文](README-zh.md) ∙ [繁體中文](README-zh-Hant.md)*


# The Art of Command Line

[![Ask a Question](https://img.shields.io/badge/%3f-Ask%20a%20Question-ff69b4.svg)](https://airtable.com/shrzMhx00YiIVAWJg)

[![Join the chat at https://gitter.im/jlevy/the-art-of-command-line](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/jlevy/the-art-of-command-line?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge)


- [Meta](#meta)
- [Basics](#basics)
- [Everyday use](#everyday-use)
- [Processing files and data](#processing-files-and-data)
- [System debugging](#system-debugging)
- [One-liners](#one-liners)
- [Obscure but useful](#obscure-but-useful)
- [macOS only](#macos-only)
- [Windows only](#windows-only)
- [More resources](#more-resources)
- [Disclaimer](#disclaimer)


![curl -s 'https://raw.githubusercontent.com/jlevy/the-art-of-command-line/master/README.md' | egrep -o '`\w+`' | tr -d '`' | cowsay -W50](cowsay.png)

La fluïdesa de la línia de comandes és una habilitat sovint descuidada o considerada arcana, però millora la vostra flexibilitat i productivitat com a enginyer de maneres òbvies i subtils. Es tracta d’una selecció de notes i consells sobre l’ús de la línia de comandaments que hem trobat útils quan es treballa amb Linux. Alguns consells són elementals, i alguns són bastant específics, sofisticats o obscurs. Aquesta pàgina no és llarga, però si podeu utilitzar i recordar tots els elements aquí, ja sabeu molt.

Aquest treball és el resultat de [molts autors i traductors] (AUTHORS.md).
Algunos de esta
[originalment] (http://www.quora.com/What-are-some-lesser-known-but-useful-Unix-commands)
[va aparèixer] (http://www.quora.com/What-are-the-most-useful-Swiss-army-knife-one-liners-on-Unix)
a [Quora] (http://www.quora.com/What-are-some-time-saving-tips-that-every-Linux-user-should-know),
pero des de llavors es traslladarà un GitHub, on les persones més talentoses que l’autor original s’hagi realitzat amb nombroses millores.
[** Si us plau, envieu una pregunta **] (https://airtable.com/shrzMhx00YiIVAWJg) Si té alguna pregunta relacionada amb la línia de comandament. [** Si us plau, contribuïu amb **] (/ CONTRIBUTING.md) Si ves un error o alguna cosa que pugui ser millor!
## Meta

Abast:

- Aquesta guia és tan important com per experimentar. Els objectius son * amplitud * (tot el que és important), * especificitat * (exemples concrets del cas més comú) i * caràcter * (evitar les coses essencials o les recerques que poden buscar fàcilment en una altra part). Cada consell és essencial en alguna situació o afany de molt temps en comparació amb altres alternatives.
- S’escriu per a Linux, amb excepció de "[macOS only] (# només macos)" i "[només Windows] (# Windows-only)" secciones Muchos dels altres elements s’aplicen. o macOS (o incluso en Cygwin).
- El enfoque está en Bash interactiu, encara que molts consells apliquen a uns altres shells a les secuencias de comandos generales de Bash.
- Incluye los comandos Unix "estàndard" com els que requeririen la instal·lació de paquets especials - Sempre i quan sean prou importants com per a merèixer la inclusió.

Notas:

- Per mantenir això en una pàgina, el contingut inclou implícitament la referència. Heu de tenir prou intel·ligent com per obtenir més detalls en una altra part més que una vegada més la idea de l'ordre de Google. Utilitzeu `apt ',` yum`, `dnf`,` pacman`, `pip` o` brew` (segons sea apropiat) per instalar nous programes.
- Utilitzeu [Explainshell] (http://explainshell.com/) per obtenir un desglose útil del que hacen els comandos, opcions, tuberías, etc.

## Conceptes bàsics

- Aprende Bash básico. En realitat, escriviu `man bash` i almenys roza todo el asunto; És bastant fàcil de seguir i no és tan llarg. Les cartes alternatives poden ser agradables, però Bash és potent i sempre està disponible (aprenent * solo * zsh, fish, etc., encara que és tentador per a la seva pròpia computadora portàtil;

- Aprendeu bé com a mínim un editor basat en text. L’editor `nano` és un dels més simples per a l’edició bàsica (obrir, editar, guardar, buscar). Sin embargo, per a l’usuari avançat en un terminal de text, no s’ha de sustentar en Vim (`vi`), l’editor difícil d’avançar però venerable, ràpid i complet. Muchas personas també usen el clàssic Emacs, particularment per a les edicions més grans. (Per supòsit, és poc probable que qualsevol desenvolupador de programari modern que treballi en un projecte únic i únic amb un editor basat únicament en un text i també estiguis familiaritzat amb els IDE i les eines gràfiques modernes).

- Encontrar documentació:
  - Separeu com fer la documentació oficial amb "home" (per a home, "man man" enumera els números de les seccions, per exemple, 1 es comandos "regulares", 5 es archivos / convenciones i 8 son para administración). Troba les pàgines personals amb "propòsits".
  - Separeu que alguns comandaments no hi hagi fils executables, que siguin integrats en Bash, i que pugueu obtenir ajuda amb ells amb ajuda i ajuda -d. Poseu-vos un comando inexactible, un shell incorporat o un alias utilitzant "type command".
  - `curl cheat.sh / command` dará una breve" hoja de trucs "amb exemples comuns per a un comando de shell.
- Aproximació sobre la redirecció de la sortida i l'entrada amb `>` y `<` y las tuberías using `|`. Sabre `>` sobrescribe el fitxer de sortida i `>>` adjunta. Aprendre sobre stdout y stderr.

- Obtén informació sobre l 'expansió global d' arxius amb `*` (i quizás `?` Y `[` ... `]`) i la diferència entre les comelles dobles `` y` `` (consulteu més informació sobre la expansió de variables a continuació.)

- Familiaritzeu-vos amb la gestió de treball de Bash: `&`, ** ctrl-z **, ** ctrl-c **, `jobs`,` fg`, `bg`,` kill`, etc.

- Sabre `ssh`, i els fonaments de la
{
      # Your code here
}
```

- Un "document aquí" permet [redirecció de múltiples línies d’entrada] (https://www.tldp.org/LDP/abs/html/here-docs.html) com si es tractés d’un fitxer:
`` `
cat << EOF
entrada
en múltiples línies
EOF
`` `

- A Bash, redirigeix ​​tant la sortida estàndard com l’error estàndard a través de: `some-command> logfile 2> & 1` o` some-command &> logfile`. Sovint, per assegurar que una ordre no deixa un controlador de fitxer obert a l'entrada estàndard, lligant-lo al terminal en què es troba, també és bo afegir `/ / dev / null`.

- Utilitzeu `man ascii` per a una bona taula ASCII, amb valors hexadecimal i decimal. Per a informació de codificació general, són útils `man unicode`,` man utf-8` i `man latin1`.

- Utilitzeu "pantalla" o [`tmux`] (https://tmux.github.io/) per multiplicar la pantalla, especialment útil per a sessions ssh remotes i per separar-les i tornar-les a afegir a una sessió. `byobu` pot millorar la pantalla o tmux proporcionant més informació i una gestió més senzilla. Una alternativa més mínima per a la persistència de la sessió només és [`dtach`] (https://github.com/bogner/dtach).

- A ssh, és útil saber com portar túnel amb "-L" o "-D" (i de vegades `-R`), p. Ex. per accedir a llocs web des d'un servidor remot.

- Pot ser útil fer algunes optimitzacions a la vostra configuració ssh; per exemple, aquest fitxer `/ / .ssh / config` conté paràmetres per evitar connexions caigudes en determinats entorns de xarxa, utilitza compressió (que és útil per a connexions de baixa amplada de banda) i canals multiplex al mateix servidor amb un fitxer de control local :
`` `
      TCPKeepAlive = sí
      ServerAliveInterval = 15
      ServerAliveCountMax = 6
      Compressió = sí
      ControlMaster auto
      ControlPath / tmp /% r @% h:% p
      ControlPersist sí
`` `

- Algunes altres opcions rellevants per a ssh són sensibles a la seguretat i haurien d'estar habilitades amb cura, p. Ex. per subxarxa o amfitrió o per xarxes de confiança: `StrictHostKeyChecking = no`,` ForwardAgent = yes?

- Tingueu en compte [`mosh`] (https://mosh.mit.edu/) una alternativa a ssh que utilitza UDP, evitant connexions caigudes i afegint comoditat a la carretera (cal configurar el servidor).

- Per obtenir els permisos en un fitxer de forma octal, que és útil per a la configuració del sistema però no disponible a `ls` i fàcil de bungle, utilitzeu alguna cosa com
`` `sh
      stat -c '% A% a% n' / etc / zona horària
`` `

- Per a la selecció interactiva de valors de la sortida d’una altra comanda, utilitzeu [`percol`] (https://github.com/mooz/percol) o [` fzf`] (https://github.com/junegunn/fzf ).

- Per a la interacció amb fitxers basats en la sortida d’una altra comanda (com `git`), utilitzeu` fpp` ([PathPicker] (https://github.com/facebook/PathPicker)).

- Per a un servidor web senzill per a tots els fitxers del directori actual (i subdirectors), disponibles per a qualsevol persona de la vostra xarxa, utilitzeu:
`python-m SimpleHTTPServer 7777` (per al port 7777 i Python 2) i` python -m http.server 7777` (per al port 7777 i Python 3).

- Per executar una ordre com a un altre usuari, utilitzeu "sudo". Per defecte, s'executa com a root; utilitzeu `-u` per especificar un altre usuari. Utilitzeu `-i` per iniciar sessió com a aquest usuari (se us demanarà _la vostra_ contrasenya).

- Per canviar el shell a un altre usuari, utilitzeu `su username 'o` su - username'. Aquest últim amb "-" obté un entorn com si un altre usuari només iniciés la sessió. Omissant el nom d’usuari per defecte a root. Se us demanarà la contrasenya de l’usuari que esteu canviant a.

- Saber sobre el [128K limit] (https://wiki.debian.org/CommonErrorMessages/ArgumentListTooLong) a les línies d'ordres. Aquest error "Llista d'arguments massa llarg" és comú quan un comodí coincideix amb un gran nombre de fitxers. (Quan això succeeix, poden ajudar alternatives com `find` i` xargs`).

- Per obtenir una calculadora bàsica (i, per descomptat, accedir a Python en general), utilitzeu l'intèrpret de "python". Per exemple,
`` `
>>> 2 + 3
5
`` `


## Processament de fitxers i dades

- Per localitzar un fitxer per nom al directori actual, `trobar. -iname '* something *' '(o similar). Per trobar un fitxer en qualsevol lloc pel nom, utilitzeu "localitzar alguna cosa" (però tingueu en compte que "updatedb" pot no haver indexat fitxers creats recentment)

- Per a la cerca general a través de fitxers d'origen o de dades, hi ha diverses opcions més avançades o més ràpides que `grep -r`, incloent-hi (en brut des del més antic al més recent) [` ack`] (https://github.com/beyondgrep / ack2), [`ag`] (https://github.com/ggreer/the_silver_searcher) (" el cercador de plata ") i [` rg "] (https://github.com/BurntSushi/ripgrep) ( ripgrep).

- Per convertir HTML a text: `lynx -dump -stdin`

- Per a Markdown, HTML i tot tipus de conversions de documents, proveu [`pandoc`] (http://pandoc.org/). Per exemple, per convertir un document Markdown en format Word: `pandoc README.md --des del marcatge --to docx -o temp.docx

- Si heu de gestionar XML, `xmlstarlet` és vell però bo.

- Per a JSON, utilitzeu [`jq`] (http://stedolan.github.io/jq/). Per a un ús interactiu, vegeu també [`jid`] (https://github.com/simeji/jid) i [` jiq`] (https://github.com/fiatjaf/jiq).

- Per a YAML, utilitzeu [`shyaml`] (https://github.com/0k/shyaml).

- Per a fitxers Excel o CSV, [csvkit] (https://github.com/onyxfish/csvkit) proporciona "in2csv", "csvcut", "csvjoin", "csvgrep", etc.

- Per a Amazon S3, [`s3cmd`] (https://github.com/s3tools/s3cmd) és c

- Tingueu en compte que MacOS es basa en BSD Unix, i molts comandaments (per exemple, "ps", "ls", "tail", "awk", "sed") tenen moltes variacions subtils de Linux, que estan en gran part influïdes per System V-. eines Unix i GNU d’estil. Sovint es pot dir la diferència notant una pàgina de manual amb el títol "Manual de comandaments generals de BSD". En alguns casos, també es poden instal·lar versions GNU (com ara "gawk" i "gsed" per a GNU awk i sed). Si escriviu scripts de Bash multiplataforma, eviteu aquestes ordres (per exemple, penseu en Python o `perl`) o proveu acuradament.
 


- To get macOS release information, use `sw_vers`.

## Windows only

Aquests elements només són rellevants * a Windows.

### Ways to obtain Unix tools under Windows

- Accediu a la potència del intèrpret d'ordres Unix a Microsoft Windows instal·lant [Cygwin] (https://cygwin.com/). La majoria de les coses que es descriuen en aquest document s’aplicaran a la caixa.

- A Windows 10, podeu utilitzar [Subsistema de Windows per a Linux (WSL)] (https://msdn.microsoft.com/commandline/wsl/about), que proporciona un entorn familiar de Bash amb les utilitats de la línia de comandaments Unix.

- Si voleu utilitzar principalment les eines de desenvolupament de GNU (com ara GCC) a Windows, considereu [MinGW] (http://www.mingw.org/) i el seu [MSYS] (http://www.mingw.org/wiki / msys), que proporciona utilitats com bash, gawk, make i grep. MSYS no té totes les funcions en comparació amb Cygwin. MinGW és especialment útil per a la creació de ports Windows originals d’eines Unix.

- Una altra opció per aconseguir que Unix aparegui sota Windows sigui [Efectiu] (https://github.com/dthree/cash). Tingueu en compte que només hi ha poques ordres i opcions de línia d’ordres Unix disponibles en aquest entorn.

### Useful Windows command-line tools

- Podeu realitzar i escriure la majoria de les tasques d’administració del sistema de Windows des de la línia d’ordres mitjançant l’aprenentatge i l’ús`wmic`.

- Les eines natives de xarxa de Windows de la línia de comandes que podeu trobar útils inclouen `ping`, `ipconfig`, `tracert`, and `netstat`.

- You can perform [many useful Windows tasks](http://www.thewindowsclub.com/rundll32-shortcut-commands-windows) by invoking the `Rundll32` command.

### Cygwin tips and tricks

- Instal·leu programes Unix addicionals amb el gestor de paquets de Cygwin.

- Use `mintty` as your command-line window.

- Accediu al porta-retalls de Windows `/dev/clipboard`.

- Run `cygstart`per obrir un fitxer arbitrari a través de la seva aplicació registrada.

- Access the Windows registry with `regtool`.

- Note that a `C:\`El camí d'accés de la unitat de Windows es converteix en `/ cygdrive / c` sota Cygwin i el de Cygwin`/` appears under `C:\cygwin`a Windows. Converteix entre Cygwin i els camins de fitxers d’estil de Windows amb`cygpath`. Això és molt útil en scripts que criden als programes de Windows.

## More resources

- [awesome-shell](https://github.com/alebcay/awesome-shell): A curated list of shell tools and resources.
- [awesome-osx-command-line](https://github.com/herrbischoff/awesome-osx-command-line): A more in-depth guide for the macOS command line.
- [Strict mode](http://redsymbol.net/articles/unofficial-bash-strict-mode/) for writing better shell scripts.
- [shellcheck](https://github.com/koalaman/shellcheck):Una eina d'anàlisi estàtica d'un script de shell. Essencialment, pèls per bash / sh / zsh.
- [Filenames and Pathnames in Shell](http://www.dwheeler.com/essays/filenames-in-shell.html): Les minúcies tristament complexes sobre com gestionar els noms de fitxer correctament en scripts de shell
- [Data Science at the Command Line](http://datascienceatthecommandline.com/#tools): More ordres i eines útils per fer ciències de dades, a partir del llibre del mateix nom

## Disclaimer

Amb l'excepció de tasques molt petites, el codi s'escriu perquè els altres la puguin llegir. Amb el poder ve la responsabilitat. El fet que * pugueu fer alguna cosa a Bash no significa necessàriament que hagueu de fer alguna cosa a Bash. ;)


## License

[![Creative Commons License](https://i.creativecommons.org/l/by-sa/4.0/88x31.png)](http://creativecommons.org/licenses/by-sa/4.0/)

This work is licensed under a [Creative Commons Attribution-ShareAlike 4.0 International License](http://creativecommons.org/licenses/by-sa/4.0/).
