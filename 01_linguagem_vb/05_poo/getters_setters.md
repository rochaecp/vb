## Métodos acessadores (getters)

~~~vb
Public Class Pet
    Private _nome As String

    ' Getter para acessar o nome do pet
    Public Function GetNome() As String
        Return _nome
    End Function
End Class
~~~


## Métodos modificadores (setters)

~~~vb
public class Pessoa {
    private String nome;

    // Setter para modificar o nome da pessoa
    public void setNome(String nome) {
        if(nome != null && !nome.isEmpty()) {
            this.nome = nome;
        } else {
            throw new IllegalArgumentException("Nome não pode ser nulo ou vazio.");
        }
    }
}
~~~