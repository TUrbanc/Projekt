@startuml

actor "Uporabnik" as user

package Racunalnik {
left to right direction
usecase "predvajanje zvoka"as play
usecase "izbira frekvence"as izbira
usecase "filtriranje zvocnih frekvenc" as filter
usecase "pretvorba frekvenc zvoka v napetostne nivoje" as pretvorba
}

package Receiver {
left to right direction
usecase "spreminjanje jakosti svetlobe"as sprememba
}

usecase "BT prenos napetostnih nivojev" as prenos

user ...> play
user ...> izbira
play -> izbira
izbira ...> filter
filter -> pretvorba
pretvorba ...> prenos
prenos ...> sprememba

@enduml