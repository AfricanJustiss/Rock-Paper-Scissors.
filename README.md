# Rock-Paper-Scissors.
A simple Rock paper scissors game against the computer.


     Private Sub btnGo_Click(ByVal sender As Object, ByVal e As System.EventArgs) Handles btnGo.Click
        
        Const intRock As Integer = 1
        
        Const intpaper As Integer = 2
        
        Const intscissors As Integer = 3
        
        Static intComputerScore As Integer
        
        Static intPlayerScore As Integer
          
        Static intDraw As Integer
           
        Dim intcomputerthrow As Integer

        'Generate computer throw
        Randomize()
        intcomputerthrow = Int(3 * Rnd() + 1)
        'If Me.RadRock.Checked And computerThrow = ROCK Then
        ' Me.lblWinner.Text = "Computer throws Rock. It's a Draw!" 'Rock Rock
        ' ElseIf Me.RadRock.Checked And computerThrow = PAPER Then
        'Me.lblWinner.Text = "Computer throws Paper. Computer Wins!" 'Rock Paper
        'ElseIf Me.RadRock.Checked And computerThrow = radScissors Then
        '  Me.lblWinner.Text = "Computer throws scissors. You win!" 'Rock Scissors
        'End If

        '  If Me.RadPaper.Checked And computerThrow = ROCK Then
        'Me.lblWinner.Text = "Computer throws Rock. It's A Draw!" 'Rock Rock
        'ElseIf Me.RadRock.Checked And computerThrow = Paper Then
        'Me.lblWinner.Text = "Computer throws paper. Computer Wins!" 'Rock Paper
        'ElseIf Me.RadRock.Checked And computerthrow = SCISSORS Then
        'Me.lblWinner.Text = "Computer throws Scissors. You Win!" 'Rock Scissors
        ' End If

        ' If Me.radScissors.Checked And computerThrow = ROCK Then
        ' Me.lblWinner.Text = "Computer throws Rock. Computer Wins!" 'Scissors Rock
        ' ElseIf Me.radScissors.Checked And computerThrow = Paper Then
        'Me.lblWinner.Text = "Computer Throws Paper. You Win!" 'Scissors Paper
        'ElseIf Me.radScissors.Checked And computerThrow = SCISSORS Then
        ' Me.lblWinner.Text = "Computer throw Scissors. It's a Draw!" 'Scissors Scissors
        ' End If


        Select Case intcomputerthrow
            Case intRock
                If Me.RadRock.Checked Then
                    Me.lblComputerWinner.Text = "Computer throws Rock. It's A Draw!"
                    intDraw = intDraw + 1
                ElseIf Me.RadPaper.Checked Then
                    Me.lblComputerWinner.Text = "Computer throws rock. You Win!"
                    intPlayerScore = intPlayerScore + 1
                ElseIf Me.radScissors.Checked Then
                    Me.lblComputerWinner.Text = "Computer throws Rock. Computer Wins!"
                    intComputerScore = intComputerScore + 1
                End If
            Case intpaper

                If Me.RadRock.Checked Then
                    Me.lblComputerWinner.Text = "Computer Throws Paper. Computer Wins!"
                    intComputerScore = intComputerScore + 1
                ElseIf Me.RadPaper.Checked Then
                    Me.lblComputerWinner.Text = "Computer Throws Paper. Its A Draw!"
                    intDraw = intDraw + 1
                ElseIf Me.radScissors.Checked Then
                    Me.lblComputerWinner.Text = "Computer Throws Paper. You Win!"
                    intPlayerScore = intPlayerScore + 1
                End If
            Case intscissors

                If Me.radScissors.Checked Then
                    Me.lblComputerWinner.Text = "Computer Throws Scissors. Its A Draw!"
                    intDraw = intDraw + 1
                ElseIf Me.RadPaper.Checked Then
                    Me.lblComputerWinner.Text = "Computer Throws Scissors. Computer Wins!"
                    intComputerScore = intComputerScore + 1
                ElseIf Me.RadRock.Checked Then
                    Me.lblComputerWinner.Text = "Computer Throws Scissors. You Win!"
                    intPlayerScore = intPlayerScore + 1
                End If
        End Select
        Me.lblComputerScore.Text = intComputerScore
        Me.lblPlayerScore.Text = intPlayerScore
        Me.lblDrawScore.Text = intDraw
