---
title: "Pro Git Book"
date: 2022-04-14
description: "Aprendiendo Git como se debe"
---

# 🕹 Curso de GIT

<details open>
<summary> 💊 índice <summary>
  1. Inicio- Sobre el control de Versiones
  2. Fundamentos de Git
  3. Ramificaciones en Git
  4. Git en el servidor
  5. Git en entornos distribuidos
  6. GitHub
  7. Herramientas de Git
  8. Personalización de Git
  9. Git y oitros Sistemas
  10. Los entresijos internos de Git
</details>
  
<details>
  <summary> 1. Inicio - Sobre el control de Versiones </summary>
  
  # Acerca del control de Versiones (VCS)
  
  ## ¿Qué es un control de versiones?
  
  Es un sistema que registra todo cambio en un archivo o conjunto de archivos a lo largo del tiempo siendo capaz de recuperarlos más adelante.
  
  el Version control system te permite regresar a versiones anteriores de tus archivos, comparar cambios, ver quien modifico el archivo, quien introdujo un problema y cuando, etc.
  
  También nos ayuda a recuperar archivos por si estos se pierden o se dañan.
  
  ### Sistema de control de verisones locales
  
  Un VCS surge para eliminar los errores que surgian al guardar copias y copias de un proyecto o de cualquier tipo de archivo. Como primer solución surgen los VCS locales que consistian en una base de datos para registrar todo cambio.
  
  ### Sistemas de Control de Versiones Centralizados
  
  Ahora los desarrolladores necesitaban colaborar con otras personas que estuvieran en otra locación o posición geográfica así es como surgen los CSCVS, los cuales tienen un servidor único que contiene todo los archivos ***versionados*** y varios clientes que descarganm los archivos desde ese lugar central. Este ha diso el estándar para el control de versiones por muchos años. Una de sus ventajas es que hasta cierto punto todo desarrollador sabe en que trabajan los demás, Los administradores tiene control detallado sobre qué puede hacer cada usuario, y es mucho más fácil administrar un CVCS que tener que lidiar con bases de datos locales en cada cliente. 
  
  Su más seria desventaja es que si el servidor centralizado falla puede causar muchos problemas con el trabajo de los colaboradores de un proyecto. Y si se llega a estropear y no se realizaro copias de seguiridad adecuadas se perdera toda la información.
  
  ### Sistemas de Control de Versiones Distribuidos
  
  Los DVCS ofrecen soluciones para los problemas mencionados ya que los clientes no solo descargan la última copia instantánea de los archivos, sino que se replica completamente el ***repositorio***.
  
  De esta manera si un servidor deja de funcionar, cualquiera de los repositorios disponibles en los clientes puede ser copiado al servidor con el fin de restaurarlo. Cada CLon es realmente una copia completa de todos los datos.
  
  Ademas, estos sistemas se encargan de manejar numerosos repositorios remotos con los cuales pueden trabajar, de tal manera que puedes colaborar simultáneamente con diferentes grupos de personas en distintas maneras dentro del mismo proyecto, permitiendo establcer ***varios flujos de trabajo*** que no son posibles en sistemas centralizados (como los jerarquicos).
  
</details>
