# calcular el total de horas y clasificar la jornada
# paula yesenia saenz
# problema 5

def evaluar_jornada_laboral(matriz_recursos):
    RESULTADOS = []
    UMBRAL_HORAS = 40
    
    for recurso in matriz_recursos:
        nombre = recurso[0]
        total_horas = sum(recurso[1:])
        
        
        if total_horas > UMBRAL_HORAS:
            clasificacion = "Sobretiempo"
        else:
            clasificacion = "Horario Estándar"
            
        RESULTADOS.append([nombre, total_horas, clasificacion])
    
    return RESULTADOS

if __name__ == "__main__":
    print("SISTEMA DE CONTROL DE HORAS LABORALES")
    
    
    control_horas = [
        ["Ana Pérez", 8, 9, 8, 8, 9],
        ["Carlos Gómez", 8, 8, 7, 8, 8],
        ["María López", 9, 9, 10, 8, 9],   
        ["Jorge Ruiz", 8, 8, 8, 8, 8]  
    ]
    
    
    reporte_final = evaluar_jornada_laboral(control_horas)
    
    
    print("\nREPORTE SEMANAL DE JORNADAS:")
    print(f"{'Nombre del Recurso':<20}  {'Total Horas':<12}  {'Clasificación'}")
    print("-" * 55)
    
    for registro in reporte_final:
        print(f"{registro[0]:<20}  {registro[1]:<12}  {registro[2]}")
