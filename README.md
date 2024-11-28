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
    [else (+ 1 (tamanho-time (rest (treinador-time treinador))))]))  


3:(define (tem-vaga? treinador)
  (<= (tamanho-time treinador) 5))   


4:(define (recebe-inicial treinador pokemoncapturado)
  (cond
    [(empty? (treinador-time treinador)) ; Se o time do treinador estiver vazio
(make-treinador (treinador-nome treinador) ; Cria um novo treinador com o Pokémon capturado
(treinador-idade treinador)
(cons pokemoncapturado (treinador-time treinador)))] 
    [else
treinador])) 

5:(define (insere-pokemon treinador pokemoncapturado)
  (cond
    [(empty? (treinador-time treinador)) 
treinador] 
    [(>= (length (treinador-time treinador)) 6) ; Se o time já tiver 6 Pokémon
treinador] 
    [else
(make-treinador
(treinador-nome treinador)
(treinador-idade treinador)
(cons pokemoncapturado (treinador-time treinador)))])) 

(define p1 (make-pokemon "Pikachu" "Electric" "vazio"))
(define p2 (make-pokemon "Bulbasaur" "Grass" "Poison"))
(define pc1 (make-pokemoncapturado p1 "Raio" 5 35 30))
(define pc2 (make-pokemoncapturado p2 "Flor" 5 45 40))
(define t1 (make-treinador "Ash" 10 (cons pc1 empty))) 

(insere-pokemon t1 pc2)  

