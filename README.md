# Votaciones
En el Ciudadanos , usamos la clave como dirección y booleano como valor. Entonces, inicialmente, el valor booleano para un ciudadano será falso y una vez que hayan emitido su voto, cambiará a verdadero. Con esto, podemos asegurarnos de que cada ciudadano pueda emitir su voto solo una vez.

    function addCandidato(string memory _nombre) private{
        candidatocount++;
        candidatos[candidatocount] = Candidato(candidatocount, _nombre, 0);
    }
 
Mantenemos el alcance de la función, ya que privateno todos deberían poder agregar candidatos.


 
    function vote(uint _candidatoid) public{
        require(!ciudadanos[msg.sender]);
        
        ciudadanos[msg.sender] = true;
        candidatos[_candidatoid].voteCount ++;
    }
Si este es su primer voto, cambiamos el valor booleano del ciudadano a Verdadero e incrementamos el recuento de votos del candidato en particular que la ciudad eligió para votar con la ayuda del candidatoid
