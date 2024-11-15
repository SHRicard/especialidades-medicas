# especialidades-medicas

Repositorio con datos estructurados sobre **especialidades médicas** y sus prestaciones asociadas. Incluye información detallada sobre diversas especialidades, los servicios o prestaciones que ofrecen, y los centros médicos donde se realizan. Ideal para integrar en aplicaciones de gestión de servicios médicos, plataformas de atención en salud o sistemas de consulta de especialidades.

## Características

- **Estructura de datos clara y accesible**: Información organizada sobre especialidades médicas, prestaciones y centros.
- **Datos actualizables**: Puedes agregar, modificar o eliminar especialidades según las necesidades de tu aplicación.
- **Facilita la integración**: Ideal para proyectos en aplicaciones de salud, clínicas, hospitales y gestión médica.

## Ejemplo de uso

Si deseas interactuar con esta información en una aplicación, puedes importar el archivo de datos en formato **JSON** o **TypeScript** y usarlo en tu proyecto. A continuación se muestra un ejemplo de cómo utilizar estos datos en un componente de React.

### Instalación

1. Clona este repositorio o descarga el archivo `especialidades.ts` que contiene los datos.
2. Asegúrate de tener un entorno de **React** configurado en tu proyecto.
3. Importa el archivo de datos en tu componente.

### Componente React

```tsx
import React, { useState } from 'react';

// Suponiendo que tienes los datos en un archivo 'especialidades.ts'
import { especialidad } from './especialidades';

const EspecialidadesComponent = () => {
  const [especialidadesFiltradas, setEspecialidadesFiltradas] = useState<any[]>(especialidad);

  // Función para filtrar especialidades por nombre
  const filtrarPorEspecialidad = (nombre: string) => {
    const resultados = especialidad.filter((especialidad) =>
      especialidad.nombre.toLowerCase().includes(nombre.toLowerCase())
    );
    setEspecialidadesFiltradas(resultados);
  };

  return (
    <div>
      <h1>Especialidades Médicas</h1>
      <input
        type="text"
        placeholder="Buscar especialidad"
        onChange={(e) => filtrarPorEspecialidad(e.target.value)}
      />
      <ul>
        {especialidadesFiltradas.map((especialidad, index) => (
          <li key={index}>
            <h2>{especialidad.nombre}</h2>
            <ul>
              {especialidad.prestaciones.map((prestacion, idx) => (
                <li key={idx}>
                  <h3>{prestacion.nombre}</h3>
                  <ul>
                    {prestacion.centros.map((centro, index) => (
                      <li key={index}>{centro.codigo}</li>
                    ))}
                  </ul>
                </li>
              ))}
            </ul>
          </li>
        ))}
      </ul>
    </div>
  );
};

export default EspecialidadesComponent;
```
## ¡Se Agradece Mucho Una Estrellita! 🌟

Si este proyecto te ha sido útil o te ha gustado, no dudes en darle una estrella ⭐️ en GitHub. ¡Tu apoyo nos motiva a seguir mejorando! 😊

[¡Dale una estrella aquí!](https://github.com/SHRicard/especialidades-medicas)

¡Gracias por contribuir al open-source! 🎉
