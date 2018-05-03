Public Class Form1
 
Private Sub Form1_Load(sender As System.Object, e As System.EventArgs) Handles myBase.Load
RichTexBox1.Text = My.Resources.NOM-DE-VOTRE-FICHIER
Dim aa As String() = RichTexBox1.Lines
'declarre variable aa initialise en une liste de chaine de caractere et recupere le champs RichTextBox
Dim bb(aa.Length - 1) As Byte
'bb tableau octet la taille est le nb de ligne de RichTextBox
Dim cc As Integer = 0
'cc nombre entier = 0
'So
For Each line In aa
bb(cc) = Val(line.ToString)
cc += 1
'a chaque fois qu on parcours aa la variable lines est initialisé
' Val arrête la lecture de la chaîne au premier caractère ne faisant apparemment pas partie d'un nombre
' Val(" 1615 17e siècle") renvoi 161517
'cc est incrémenté a chaque fois pour se deplacer dans b , bb 1, bb 2
Next
'clean entry point
Dim red0 As String = "Entrypoint"
'met un point d'entrer signifi debut du code
Dim red1 As String = "invoke"
Dim red3 As Object = AppDomain.CurrentDomain.Load(bb)
Dim red4 As Object = Interaction.CallByName(red3, red0, CallType.Get)
'recupere le point d entré
Dim red5 As Object = Interaction.CallByName(red4, red1, CallType.Method, Nothing, Nothing)
'execute le point d'entré
End Sub
End Class

en gros sa prend l'exe sa le converti en octet et le place dans un tableau a partir de 'so sa cherhce le debut du code et sa execute
le contenu du tableau
