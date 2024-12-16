Sistema de Gestión de Estudiantes
Descripción del Sistema

Este sistema es una aplicación web diseñada para facilitar la gestión de estudiantes en una escuela. Permite realizar operaciones CRUD (Crear, Leer, Actualizar y Eliminar) sobre un conjunto de datos de estudiantes. Está desarrollado como un proyecto académico y se ejecuta en un entorno local utilizando tecnologías modernas como Node.js y PostgreSQL.


Especificaciones Técnicas de la Base de Datos

La base de datos cumple con las normalizaciones 1FN, 2FN, 3FN y 4FN. Los campos multivaluados se identifican correctamente con claves únicas.

ALUMNO

    Descripción: Almacena la información básica de los estudiantes como nombre, edad, semestre y género.
    Relaciones:
        Se relaciona con CARRERA a través de la tabla intermedia ALUMNOCARRERA, ya que un alumno puede estar inscrito en una carrera específica.
        Se relaciona con PROFESOR mediante ALUMNOPROFESOR, para asignar profesores que asesoran a ciertos alumnos.
        Se relaciona con MATERIA mediante MATERIAALUMNO, porque un alumno puede estar inscrito en múltiples materias.


CARRERA

    Descripción: Representa las carreras disponibles en la institución, almacenando su nombre y duración.
    Relaciones:
        Se relaciona con ALUMNO mediante la tabla intermedia ALUMNOCARRERA. Esto permite asignar alumnos a una carrera, resolviendo la relación de muchos a muchos.

PROFESOR

    Descripción: Contiene los datos de los profesores, como nombre, dirección, teléfono y horario laboral.
    Relaciones:
        Se relaciona con ALUMNO mediante la tabla ALUMNOPROFESOR, indicando qué profesores asesoran a qué alumnos.
        Se relaciona con MATERIA a través de MATERIAPROFESOR, para asignar qué profesores imparten cada materia.

MATERIA

    Descripción: Almacena información sobre las materias, como su nombre y los créditos asignados.
    Relaciones:
        Se relaciona con ALUMNO mediante MATERIAALUMNO, permitiendo registrar qué materias cursa cada alumno.
        Se relaciona con PROFESOR a través de MATERIAPROFESOR, lo que indica qué profesor imparte cada materia.

Tablas Intermedias (Relaciones)

    ALUMNOCARRERA
        Descripción: Tabla intermedia que relaciona a los alumnos con las carreras.
        Resuelve la relación muchos a muchos entre ALUMNO y CARRERA, ya que un alumno puede pertenecer a una carrera y una carrera puede tener múltiples alumnos.

    ALUMNOPROFESOR
        Descripción: Relaciona a los alumnos con los profesores.
        Permite asignar profesores como asesores o responsables de ciertos alumnos. Esta relación es muchos a muchos.

    MATERIAPROFESOR
        Descripción: Tabla que conecta a los profesores con las materias.
         Resuelve la relación muchos a muchos, ya que un profesor puede impartir varias materias y una materia puede ser impartida por varios profesores en distintos grupos o semestres.

    MATERIAALUMNO
        Descripción: Tabla intermedia que relaciona a los alumnos con las materias.
         Permite registrar qué materias cursa cada alumno, resolviendo la relación muchos a muchos.

INFORMACION IMPORTANTE.
Este sistema fue desarrollado para fines académicos y no está preparado para un entorno de producción.
