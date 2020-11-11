# MENU
Opciones diferentes.
funcionInicial = do
    funcionMenu
funcionMenu = do        
            putStrLn("*Elige una opcion*")
            putStrLn("*Menu*")
            putStrLn("1.- Serie Fibonacci")
            putStrLn("2.- Serie De Numeros del 1 al 10")
            putStrLn("3.- Factorial")
            putStrLn("4.- Calculadora")
            putStrLn("5.- Salir")
            putStrLn(" ")
            menu <- getLine
            
            
            case menu of 
                "1" -> funcionFibo
                "2" -> funcionwen
                "3" -> funcionFactorial
                "4" -> funcionopc
                "5" -> putStrLn("Salir...")
                _   -> putStrLn("otra opcion")

funcionFibo = do
        
        pedirfibo

pedirfibo :: IO ()
pedirfibo = do
    putStrLn("Que posicion deseas")
    j <- getLine
    putStrLn("El resultado es:"++show(fibonacci (read j)))
    funcionInicial

fibonacci j = do
        if j < 2
            then do 
                j
        else do
            fibonacci (j-1) + fibonacci (j-2)
            
funcionwen = do
    wen 1

wen :: Integer -> IO()
wen a = do
    if a<=10
        then do
            print a
            wen (a+1)
        else do
        putStrLn("")
        funcionInicial

funcionFactorial = do 

    let factorial = product[1..5]
    print(factorial)
    funcionInicial


funcionopc = do 

    putStrLn("-----Calculadora-----")
    putStrLn("*Elige una opcion*")
    putStrLn("1.- Suma")
    putStrLn("2.- Resta")
    putStrLn("3.- Multiplicacion")
    putStrLn("4.- Division")
    putStrLn("5.- Salir")
    putStrLn(" ")
    opc <- getLine

    case opc of 
        "1" -> funcionSuma
        "2" -> funcionResta
        "3" -> funcionMultiplicacion
        "4" -> funcionDivision
        "5" -> putStrLn("Salir...")
        _    -> putStrLn("otra opcion")

funcionSuma = do
    putStrLn("Dame el numero 1: ")
    a <- getLine
    putStrLn("Dame el numero 2: ")
    b <- getLine

    let aInt = read a::Int
    let bInt = read b::Int
    let resultado = aInt + bInt 
                    
    putStrLn("Tu resultado es una suma de: "++ show resultado)
    funcionInicial

funcionResta = do
    putStrLn("Dame el numero 1: ")
    a <- getLine
    putStrLn("Dame el numero 2: ")
    b <- getLine

    let aInt = read a::Int
    let bInt = read b::Int
    let resultado = aInt - bInt 
                    
    putStrLn("Tu resultado es una resta de: "++ show resultado)
    funcionInicial

funcionMultiplicacion = do
    putStrLn("Dame el numero 1: ")
    a <- getLine
    putStrLn("Dame el numero 2: ")
    b <- getLine

    let aInt = read a::Int
    let bInt = read b::Int
    let resultado = aInt * bInt 
                    
    putStrLn("Tu resultado es una multiplicacion de: "++ show resultado)
    funcionInicial

funcionDivision :: IO ()
funcionDivision = do
    putStrLn("Dame el numero 1: ")
    a <- getLine
    putStrLn("Dame el numero 2: ")
    b <- getLine

    let aInt = read a::Int
    let bInt = read b::Int
    let resultado =div aInt  bInt 
                    
    putStrLn("Tu resultado es una division de: "++ show resultado)

    funcionInicial
