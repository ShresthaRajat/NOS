#!/bin/sh
#1
if [[ $# != 2 ]]; then
  echo -e "Error! [0] Username or id missing"
  echo -e "please execute again with both username and ID"
  exit
fi
if ! [[ "$2" =~ ^[+-]?[0-9]+$ ]]; then
  echo -e "Error! [1] enter ID as a number"
  exit
fi
username=$1
id=$2
echo -e "------------------------------------------------------------"
echo -e "\t\t\t Welcome \n"
#2
echo -e "Enter secret key!"
password=noway
key=a
count=0
until [[ "$key" = "$password" ]]; do
  if [[ count -lt 3 ]]; then
    if [[ count -gt 0 ]]; then
      echo -e "Error! [2] incorrect password attempt $count"
    fi
    echo -e "Password: \c"
    read key
    count=`expr $count + 1`
    else
      echo -e "Error! [3] login attempts exceeded"
      echo -e "\nprogram terminated\n\t***"
      exit
  fi
done
#3  
echo -e "\v************************************************************"
echo -e "\t\t  login sucessfull \n"
echo -e "\tID: $id\t\t\t\t\tUsername: $username"
echo -e "\t\tAccess Date: \c"
date +%D
echo -e "\t\tAccess Time: \c"
date +%T
echo -e "************************************************************"
echo -e "\t"
country(){
  #4
  echo -e "\n\t SELECT A COUNTRY"
  echo -e "____________________________________________________________"
  echo -e "| Country                    | code                        |"
  echo -e "------------------------------------------------------------"
  echo -e "| Japan                      | JPN                         |"
  echo -e "| Argentina                  | ARG                         |"
  echo -e "| Germany                    | GER                         |"
  echo -e "| France                     | FRA                         |"
  echo -e "| Brazil                     | BRZ                         |"
  echo -e "^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^"
  #5
  echo -e "\nWhich is the best football team?:-\c"
  read wc
  if [[ "$wc" = "FRA" ]]; then
    echo -e "************************************************************"
    echo -e "\t\tFrance is the best team"
    echo -e "The France national football team represents France in international football "
    echo -e "and is controlled by the French Football Federation, also known as FFF, "
    echo -e "or in French: Fédération française de football. The team's colours are"
    echo -e "blue, white and red, and the coq gaulois its symbol. France are"
    echo -e "colloquially known as Les Bleus."
    echo -e "************************************************************"
  elif [[ "$wc" = "JPN" || "$wc" = "ARG" || "$wc" = "GER" || "$wc" = "BRZ" ]]; then
      echo -e "Error! [4] Wrong Country!"
      echo -e "$wc is not the world champion"
      country
  else
    echo -e "Error! [5] Invalid Input!"
    country
  fi  
}
val(){
  # to check if the players are valid
  if [[ $1 != "KAG" && $1 != "MES" && $1 != "REU" && $1 != "LOR" && $1 != "COU" ]]; then
    echo -e "Error! [6] Player doesnt exist Try again"
    player_selection
  fi
} 
numval(){
  # to check if there are exactly 3 inputs
  if [[ $# != 3 ]]; then
  echo -e "Error! [7] Invalid number of inputs, Enter only 3 players"
    player_selection
  fi
  if [[ $1 = $2 || $2 = $3 || $1 = $3  ]]; then
    echo -e "Error! [8] Duplicate inputs!"
    player_selection
  fi
}
player_selection(){
  #6
  a=a
  b=b
  c=c
  echo -e "The Five Star players at the world cup are:"
  echo -e "____________________________________________________________"
  echo -e "| Players                    | code                        |"
  echo -e "------------------------------------------------------------"
  echo -e "| Kagawa                     | KAG                         |"
  echo -e "| Messi                      | MES                         |"
  echo -e "| Reus                       | REU                         |"
  echo -e "| Loris                      | LOR                         |"
  echo -e "| Coutinho                   | COU                         |"
  echo -e "^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^^"
  #7
  echo -e "Choose three players represented by codes separated by spaces"
  #8
  read a b c
  numval $a $b $c
  val "$a"
  val "$b"
  val "$c"
  echo -e " "
}
fun(){
  PS3="Enter a number as per list for choosing a player you want:"
  select player in $a $b $c
    #10
    do
      if [ -z $player ]
        then
          echo -e "Error! [9] Invalid Input!"
      elif [ -r $player ]
        then
        #11
          echo " "
          cat $player
          break
      else
        echo -e "Error! [10] Cant find file!"
      fi
    done
}
execute(){
country
player_selection
fun
echo -e "Do you want to start over?(y):-\c"
read y
case $y in
 "YES"|"yes"|"Yes"|"Y"|"y")
   execute
   ;;
 *)
  echo "Program Terminated"
  exit
  ;;
esac
}
execute;