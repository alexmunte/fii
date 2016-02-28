Exercitii pentru laboratorul 2
==============================

1. > Să se scrie comanda care să parcurgă recursiv directorul dat ca argument și 
   > să afișeze permisiunile tuturor fișierelor și subdirectoarelor întâlnite. 

   Solutie: 
      * `find . -exec stat --format="%n --> %a" {} \;`
      * `find . -intf "%f %M\n"`

2. > Să se scrie comanda ce afișează pentru toate fișierele găsite în directorul dat 
   > ca argument în linia de comandă, parcurs recursiv, fișiere ale căror nume încep 
   > sau se termină cu litera 'a', următoarele proprietăți: numele fișierului, data 
   > ultimei modificări și dimensiunea fișierului în Kbytes. 

   Solutie:
      * `find . \( -name "*a" -or -name "a*" \) -printf "% p %a %k"`

3. > Să se scrie comanda care să sorteze descrescător liniile de text din fișierul 
   > /etc/passwd, iar rezultatul sortării să fie salvat în fișierul output.txt. 

   Solutie:
      * `sort -r /etc/passwd > output.txt`

4. > Să se scrie comanda care să sorteze crescător după UID liniile de text din 
   > fișierul /etc/passwd. 

   Solutie:
      * `sort /etc/passwd --numeric-sort --key=3 -t:

5. > Să se scrie comanda ce afișează toate fișierele și directoarele, precum și drepturile 
   > de acces asociate acestora, aflate în directorul dat ca argument în linia de comandă, 
   > parcurs recursiv, pentru care grupul proprietarului are drepturi de citire și de execuție.

   Solutie:
      * `find . \( -perm /g+r -and -perm /g+x \) -printf "%p %M \n"`

6. > Să se scrie comanda ce afișează toate fișierele de tip normal (i.e., fișiere obișnuite) 
   > pe care le dețineți în cont și care au fost modificate în ultima săptămână, împreună 
   > cu drepturile de acces și data ultimei modificări.
   
   Solutie:
      * `find . -type f -mtime 7 -printf "%p -- %M -- %t\n"`

7. > Să se scrie comanda ce afișează toate fișierele găsite începând din directorul dat ca argument 
   > în linia de comandă, parcurs recursiv, pentru care proprietarul fișierului are drept de execuție 
   > asupra sa, precum și data ultimei accesări a fișierului și dimensiunea sa în Kbytes.

   Solutie:
      * `find . -perm /o+x -printf "%p %a %k\n"`


