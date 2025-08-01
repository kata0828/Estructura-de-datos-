# Estructura-de-datos-
taller#2
# Taller 02 - Ejercicio 1 - El índice de masa corporal
module Taller02
  VERSION = "0.1.0"


  class Persona
    # Atributos
    @peso : Float64
    @altura : Float64
    @año_nacimiento : Int32
    @genero : String
    # Constructor, inicializador
    def initialize (@peso,  @altura,  @año_nacimiento, @genero)
    end


    # getters
    getter peso
    getter altura  
    def año_nacimiento : Int32
      return @año_nacimiento
    end
   
    # Otros métodos
    def es_hombre?(@genero : String) Bool
      if @genero == "HOMBRE"
        return true
      end
    end
    def es_mujer?(@genero : String) Bool
      if @genero == "MUJER"
        return true
      end
    end
    def edad
      2025 - año_nacimiento
    end
    def es_menor_de_edad?
     if edad < 18
      return true
     end
    end
    def nacio_en_el_siglo_pasado? : Bool
       if @año_nacimiento >= 1900 && @año_nacimiento <= 1999
      return true 
      else
      return false
      end 
    end 
    def imc : Float32
      peso / altura ** 2
    end
    def clasificacion_imc (imc : Float64 ) : String
      if imc < 18.5
        return "Bajo peso"
      elsif imc >= 18.5 && imc < 24.9
        return "Peso normal"
      elsif imc >= 25 && imc < 29.9
        return "Sobrepeso"
      else
        return "Obesidad"
      end
    end
    def es_mujer_con_sobrepeso? : Bool
      if @genero == "MUJER" && imc >= 25 && imc < 29.9
        return true
      else
        return false
      end
    end
    def es_hombre_con_obesidad? : Bool
      if @genero == "HOMBRE" && imc >= 30
        return true
      else
        return false
      end 
    end 
    def es_flaco_mayor_de_64_años? : Bool
      if @edad > 64 && imc < 18.5
        return true
      else
        return false
      end

    end
  end  # Fin de la clase
 
end # Fin del módulo

