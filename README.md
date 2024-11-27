1: (define pikachu (make-pokemon "Pikachu" "Electric" 'vazio))
    (define bulbasaur (make-pokemon "Bulbasaur" "Grass" "Poison"))
    (define charmander (make-pokemon "Charmander" "Fire" 'vazio))
    (define squirtle (make-pokemon "Squirtle" "Water" 'vazio))

(define pikachu-capturado (make-pokemoncapturado pikachu "Raichu" 5 100 80))
   (define bulbasaur-capturado (make-pokemoncapturado bulbasaur "Bulby" 7 120 100))
   (define charmander-capturado (make-pokemoncapturado charmander "Flame" 6 90 70))
   (define squirtle-capturado (make-pokemoncapturado squirtle "Squirt" 8 110 90))

(define ash (make-treinador "Ash Ketchum" 10 (cons pikachu-capturado (cons charmander-capturado empty))))

(define misty (make-treinador "Misty" 12 (cons squirtle-capturado (cons bulbasaur-capturado empty))))

(define brock (make-treinador "Brock" 15 (cons pikachu-capturado (cons squirtle-capturado empty))))

(define may (make-treinador "May" 13 (cons bulbasaur-capturado (cons charmander-capturado empty))))


2:(define (tamanho-time treinador)
  (cond
    [(empty? (treinador-time treinador)) 0]  ; Se o time estiver vazio, o tamanho é 0
    [else (+ 1 (tamanho-time (rest (treinador-time treinador))))]))  ; Caso contrário, conta 1 e chama recursivamente para o resto do time



3:(define (tem-vaga? treinador)
  (<= (tamanho-time treinador) 5))  ; Se o número de Pokémon no time for 5 ou menos, há vaga (porque o time pode ter no máximo 6 Pokémon)
