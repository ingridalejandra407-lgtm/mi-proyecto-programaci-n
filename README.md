# mi-proyecto-programaci-n
        """Retorna una descripcion legible con los datos de la sala reservada."""
        return (
            f"ReservaSala {self.nombre} | "
            f"Capacidad: {self.capacidad} personas | "
            f"Horas: {self.horas}"
        )

    def calcular_costo(self):
        """Calcula el costo total multiplicando el precio base por las horas."""
        return self.precio_base * self.horas

    def extender_horas(self, horas_extra):
        """Aumenta las horas de reserva validando que el valor sea positivo."""
        if horas_extra <= 0:
            raise DatosInvalidosError("Las horas adicionales deben ser mayores a cero")
        self.horas += horas_extra
        return self.horas

    def verificar_aforo(self, cantidad_asistentes):
        """Comprueba si el numero de asistentes cabe dentro de la capacidad."""
        return 0 < cantidad_asistentes <= self.capacidad