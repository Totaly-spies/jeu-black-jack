import tkinter as tk
import random as rd

#cette fonction permettra de créer un jeu de carte mélangé 
def jeu_de_carte():
    symbole= ['coeur','trefle','pique','carreau']
    valeur= ['2','3','4','5','6','7','8','9','10','valet','reine','roi','as']
    deck= []
    for symbole in symbole:
        for valeur in valeur:
            deck.append((valeur, symbole))
    rd.shuffle(deck)
    return deck

#cette fonction servira de compteur de point
def cmt_point(main):
    total = 0
    nbr_as = 0
    for carte in main:
        if carte[0]=='valet' or carte[0]=='reine'or carte[0]=='roi':
            total=total+10
        elif carte[0] == 'As':
            total=total+11
            nbr_as=total+1
        else:
            total=total+int(carte[0])
    while total > 21 and nbr_as > 0:
        total=total-10
        nbr_as=nbr_as-1
    return total

#cette fonction permettra de visualiser la main du joueur
def afficher_main(main):
    for carte in main:
        print(carte[0],"de",carte[1])

def jeu():
    deck=jeu_de_carte()
    
    #fonction qui permettra au joueur de piocher une carte
    def tirer_carte:
        main_joueur.append(deck.pop())
        print("main du joueur:")
        afficher_main(main_joueur)

    #pourquoi pas fonction def cartes ici whyyy?

    main_joueur=[deck.pop()]
    print("main du joueur:")
    afficher_main(main_joueur)

    #sa sert a quoi celui d'en haut et d'en bas whyyy?

    main_croupier=[deck.pop()]
    print("main du croupier:")
    afficher_main(main_croupier)
    
    main_joueur.append(deck.pop())
    print("main du joueur:")
    afficher_main(main_joueur)
    
    main_croupier.append(deck.pop())

    ###############################
    
    if cmt_point(main_joueur)==21:
        print("BLACKJACK !!!")
    elif 
    ################################
    
    total_croupier=cmt_point(main_croupier)
    print("main du croupier:")
    afficher_main(main_croupier)
    while total_croupier<17:
        main_croupier.append(deck.pop())
        total_croupier=cmt_point(main_croupier)
        print("le croupier tire une carte")
        print("main du croupier:")
        afficher_main(main_croupier)
    
    if total_croupier>21 or total_joueur>total_croupier:
        print("Tu as gagné")
    elif total_croupier>total_joueur or total_joueur>21:
        print("le croupier a gagné")
    else:
        print("égalité")


#Partie graphique

racine = tk.Tk()
racine.title("Black Jack")
bouton_tirer_carte=tk.Button(racine,texte="Carte!", #nom de la fonction qui va permettre de tirer)

canvas_largeur=1500
canvas_hauteur=1000
canvas= tk.Canvas(racine,background="green",canvas_largeur,canvas_hauteur)
#racine.mainloop()
