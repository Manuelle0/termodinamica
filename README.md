import math

print("=== SISTEMA DE FÍSICA -2º BIMESTRE ===")
print("Escolha o tema:")
print("1. 1ª Lei do Termodinâmica")
print("2. Ciclos Termodinâmicos")
print("3. Calores Específicos dos Gases Perfeitos")
print("4. Máquinas térmicas e 2ª Lei da termodinâmica")
print("5. Ciclos de Carnot")
print("6. Refrigeradores")
print("7. Ondas")
print("0. Sair")

while True:
    tema = input("\nDigite o número do tema: ")
    if tema  =='0':
        print("Encerrando programa...")
        break
    #1ª Lei da termodinâmica
    elif tema == '1':
        print("\n=== 1ª LEI DA TERMODINÂMICA ===")
        print("ΔU = Q - W")
        print("1. Calcular variação de energia interna")
        print("2. Calcular calor trocado")
        print("3. Calcular trabalho realizado")

        opçao = input("Escolha o cálculo: ")

        if opçao == '1':
            Q = float(input("Calor Trocado (J): "))
            W = float(input("Trabalho realizado (J): "))
            delta_U = Q - W 
            print(f"\nVariação de energia interna(ΔU) = {delta_U} J")
            if delta_U > 0:
                print("A energia interna do sistema aumentou.")
            elif delta_U < 0:
                print("A energia interna do sistema diminuiu.")
        else:
                print("A energia interna do sistema permaneceu constante.")

    elif opçao == '2':
            delta_U = float(input("Variação de energia interna (J): "))
            W = float(input("Trabalho realizados (J):"))
            Q = delta_U + W 
            print(f"\nCalor trocado (Q) = {Q} J")
            if Q > 0:
                print("O sisitema absorveu o calor.")
            elif Q < 0:
                print("O sistema liberou calor.")     
    elif opçao == '3':
        Q = float(input("Calor trocado (J): "))
        delta_U = float(input("Variação de energia interna (J): "))
        W = Q - delta_U
        print(f"\nTrabalho realizado (W) = {W} J")
        if W > 0:
            print("O sistema realizou trabalho sobre o ambiente.")
        elif W < 0:
            print("O ambiente realizou trabalho sobre o sistema.")

              
            #Ciclos Termodinamicos
elif tema == '2':
        print("\n=== CICLOS TERMODINÂMICOS ===")
        print("1. Trabalho no ciclo (Área do ciclo)")
        print("2. Rendimento ciclo")

        opçao = input("Escolha o cálculo: ")
        if opçao  == '1':
            print("\nDigite os valores do ciclo no diagrama P x V")
            P_max = float(input("Pressão máxima (Pa): "))
            P_min = float(input("Pressão mínima (Pa): "))
            V_max = float(input("Volume máximo (m³): "))
            V_min = float(input("Volume mínimo (m³): "))
            W = (P_max - P_min * V_max - V_min)
            print(f"\nTrabalho no ciclo = {W} J")

elif opçao == '2':
        Q_abs = float(input("Calor absorvido (J): "))
        Q_libera = float(input("Calor liberado (J): "))
        rendimento = (Q_abs - Q_libera) / Q_abs
        print(f"\nRendimento do ciclo = {rendimento:.2%}")

# Calores Específicos dos Gases Perfeitos
elif tema == '3':
        print("\n=== CALORES ESPECÍFICOS DOS GASES PERFEITOS ===")
        print("1. Calor específico a volume constante (Cv)")
        print("2. Calor específico a pressão constante (Cp)")
        print("3. Relação entre Cp e Cv (γ = Cp/Cv)") 

        opcao = input("Escolha o cálculo: ")
        R = 8.314 #Constante dos gases
        
        if opcao = '1':
            graus_liberdade = int(input("Graus de liberdade do gás (1-3): "))
            Cv = (graus_liberdade / 2)* R
            print(f"\nCv = {Cv} J/(mol·K)")

        elif opcao == '2':
            graus_liberdade = int(input("Graus de liberdade do gás (1-3): "))
            Cp = ((graus_liberdade / 2) + 1)* R
            print(f"\nCp = {Cp} J/(mol·K)")

        elif opcao == '3':
            graus_liberdade = int(input("Graus de liberdade do gás (1-3): "))
            gamma = ((graus_liberdade / 2) + 1) / (graus_liberdade /2)
            print(f"\nγ = Cp/Cv = {gamma:.4f}")

# Máquinas Térmicas e 2ª Lei
elif tema == '4':
        print("\n=== MÁQUINAS TÉRMICAS E 2ª LEI ===")
        print("1. Rendimento da máquina térmica")
        print("2. Calor rejeitado para a fonte fria")

        opcao == input("Escolha o cálculo: ")

    if opcao == '1':
        Q_quente = float(input("Calor absorvido da fonte quente (J): "))
        Q_fria = float(input("Calor absorvido da fonte fria (J): "))
        rendimento = (Q_quente - Q_fria) / Q_quente
        print(f"\nRendimento = {rendimento:.2%}")
        
    elif opcao == '2':
        Q_quente = float(input("Calor absorvido da fonte quente (J): "))
        rendimento = float(input("Rendimento da máquina (Decimal): "))
        Q_fria = Q_quente * (1 - rendimento)
        print(f"\nCalor rejeitado = {Q_fria} J")

# Calor de Carnot
    elif tema == '5':
        print("\n=== CICLO DE CARNOT ===")
        T_quente = float(input("temperatura da fonte quente (K): "))
        T_fria = float(input("temperatura da fonte fria (K): "))
        rendimento = 1 - (T_fria / T_quente)
        print(f"\nRendimento de Carnot = {rendimento:.2%}")

# Refrigeradores
elif tema == '6':
    print("\n=== REFRIGERADORES ===")
    print("1. Coeficiente de desempenho (COP)")
    print("2. Calor removido da fonte fria")

    opcao = input("Escolha o cálculo")

    if opcao == '1':
        T_fria = float(input("Temperatura da fonte fria (K): "))
        T_quente = float(input("Temperatura da fonte quente (K): "))
        COP = T_fria / (T_quente - T_fria)
        print(f"\n COP = {COP:.2f}")

    elif opcao == '2': 
        W = float(input("Trabalho realizado (J): "))
        COP = flaot(input("Coeficiente de desempenho (COP): "))
        Q_fria = COP * W
        print(f"\nCalor removido = {Q_fria} J")
# ondas 
elif tema=='7':
    print("\n=== ONDAS ===")
    print("1. equaçao fundamental da ondulatoria")
    print("2. energia transpotada por uma onda ")
    
    opçao=input("escolha o calculo")


    if opcao=='1':
        print("\nequaçao: v=λ ·f")
        print("1. calcular velocidade de propagaçao")
        print("2. calcular comprimento de ondas")
        print("3. calcular frequencia ")
        

        sub_opcao=input("escolha:")

        if sub_opcao=='1':
            lambd=float(input("comprimento de ondas (m):"))
            f=float(input("frequencia (Hz):"))
            V=lambd *f
            print(f"\n velocidade de propagaçao = {V} m/s:")


        elif sub_opcao=='2':
            v=float(input("velocidade de porpagaçao(m/s): "))
            f=float(input("frequencia (Hz):"))
            lambd= V / f
            print(f"\nComprimento de onda = {lambd} m")
        elif sub_opcao=='3':
            V=float(input("velocidade de propagaçao (m/s):"))
            lambd=float(input("comprimento de onda (m):"))
            f=V / lambd
            print(f"\nfrequencia={f} hz")
