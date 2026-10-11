def main():
    print("=========================================================")
    print("  SISTEMA DE REGISTRO DE ENCOMIENDAS - COURIER CONTINENTAL")
    print("=========================================================\n")

    # Lote de paquetes registrados en el turno
    # Datos: (codigo_paquete, peso_kg, zona_destino, hora_ingreso)
    # Zona 1: Norte (S/ 15.00 base + S/ 2.00 por kg)
    # Zona 2: Sur   (S/ 12.00 base + S/ 1.50 por kg)
    # Zona 3: Centro(S/ 10.00 base + S/ 1.20 por kg)
    paquetes_registrados = [
        ("PKG-101", 3.5, 1, "08:30"),
        ("PKG-102", 5.0, 2, "09:15"),
        ("PKG-103", 2.8, 3, "10:00"),
        ("PKG-104", 7.2, 1, "11:20"),
        ("PKG-105", 4.1, 2, "12:05")
    ]

    # 1. CONTADORES Y ACUMULADORES DE DATOS
    total_paquetes = 0
    peso_total_acumulado = 0.0
    monto_total_recaudado = 0.0

    # Listas para almacenar el historial de encomiendas
    lista_codigos = []
    lista_pesos = []
    lista_zonas = []
    lista_horas = []
    lista_tarifas = []

    # 2. BUCLE REPETITIVO PARA PROCESAR CADA ENCOMIENDA
    for paquete in paquetes_registrados:
        total_paquetes += 1  # Contador de paquetes
        
        # Desempaquetado de datos
        codigo_paquete, peso_paquete, zona_destino, hora_ingreso = paquete

        print(f"--- REGISTRANDO PAQUETE N° {total_paquetes} ---")
        print(f"Código identificador: {codigo_paquete}")
        print(f"Peso del paquete    : {peso_paquete} kg")
        print(f"Hora de ingreso     : {hora_ingreso}")

        # 3. ESTRUCTURA SELECTIVA PARA CÁLCULO DE TARIFAS
        if zona_destino == 1:
            nombre_zona = "Zona Norte"
            tarifa = 15.00 + (peso_paquete * 2.00)
        elif zona_destino == 2:
            nombre_zona = "Zona Sur"
            tarifa = 12.00 + (peso_paquete * 1.50)
        elif zona_destino == 3:
            nombre_zona = "Zona Centro"
            tarifa = 10.00 + (peso_paquete * 1.20)
        else:
            nombre_zona = "Zona Centro (Por defecto)"
            tarifa = 10.00 + (peso_paquete * 1.20)

        print(f"Zona de destino     : {nombre_zona}")
        print(f"Tarifa calculada    : S/ {tarifa:.2f}")

        # ACUMULACIÓN DE DATOS DEL TURNO
        peso_total_acumulado += peso_paquete
        monto_total_recaudado += tarifa

        # Almacenamiento en listas
        lista_codigos.append(codigo_paquete)
        lista_pesos.append(peso_paquete)
        lista_zonas.append(nombre_zona)
        lista_horas.append(hora_ingreso)
        lista_tarifas.append(tarifa)

        print("-" * 55)

    # 4. SALIDA Y REPORTE CONSOLIDADO DEL TURNO
    print("\n=========================================================")
    print("   REPORTE CONSOLIDADO DEL TURNO - COURIER CONTINENTAL")
    print("=========================================================")
    print(f"Total de paquetes procesados : {total_paquetes}")
    print(f"Peso total en almacén        : {peso_total_acumulado:.2f} kg")
    print(f"Monto total de facturación   : S/ {monto_total_recaudado:.2f}")

    if total_paquetes > 0:
        promedio_peso = peso_total_acumulado / total_paquetes
        promedio_costo = monto_total_recaudado / total_paquetes
        print(f"Promedio de peso por paquete : {promedio_peso:.2f} kg")
        print(f"Costo promedio de envío      : S/ {promedio_costo:.2f}")

        print("\n--- DETALLE DE ENCOMIENDAS REGISTRADAS EN ALMACÉN ---")
        for i in range(len(lista_codigos)):
            print(f"{i+1}. Código: {lista_codigos[i]} | Peso: {lista_pesos[i]} kg | Zona: {lista_zonas[i]} | Hora: {lista_horas[i]} | Tarifa: S/ {lista_tarifas[i]:.2f}")

    print("\n=========================================================")
    print("        ¡REGISTRO DE TURNO FINALIZADO CON ÉXITO!")
    print("=========================================================")

# Ejecución del programa
main()
